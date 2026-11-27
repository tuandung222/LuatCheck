# Kế hoạch tái cấu trúc tài liệu trước D3/D4

Ngày 28/11/2026. Đây là **kế hoạch, chưa thực hiện thay đổi nào**. Căn cứ: đọc cây thư mục, so sánh các thư mục trùng, đối chiếu vài câu quan trọng giữa tài liệu và README. Phần kiến trúc sẽ được bổ sung khi agent vẽ lại sơ đồ bằng mã nguồn báo kết quả (mục 2, ghi rõ là chưa có).

Mục tiêu: người chấm D4 (B2 tái lập, 12% final) và chính nhóm chỉ cần một đường đi rõ ràng: README, một lệnh chạy, một lệnh tái lập, tài liệu khớp với mã; tài liệu cũ của D2 nằm ở nơi nhìn là biết đã lỗi thời.

## 1. Những vấn đề đã xác nhận

| # | Vấn đề | Bằng chứng | Hậu quả |
|---|---|---|---|
| P1 | Thư mục review bị tách đôi giữa `docs/reviews/` và `docs/historical/reviews/` | Bốn tệp ghi chú (3 README/RETRY_POLICY và `SEMANTIC_JUDGING.md`) nằm ở `historical`, còn bằng chứng nằm ở `docs/reviews/`. Hai phía không có tệp trùng. Hệ quả nghiêm trọng hơn dự đoán: `manifest.json` của gói `pilot2-blind-export-check-v3` liệt kê `SEMANTIC_JUDGING.md` (sha256 khớp bản ở `historical`) nên gói bằng chứng bị thiếu tệp; các script xác minh trong `docs/reviews/*` dùng `parents[3]` và đường dẫn cố định nên không thể chuyển sang `historical` | Gói bằng chứng không toàn vẹn; sửa ban đầu "hợp nhất vào historical" sẽ làm hỏng script |
| P2 | `REPRODUCE_D2.md` mâu thuẫn với README về kiểm định người chấm | Guide ghi "no labels exist yet" (F9) và "Human audit: not yet done; 2 x 30 items"; README và D2 báo cáo công bố κ 0,93 và 0,80 trên 60 mẫu | Số liệu trong báo cáo không truy ngược được từ guide tái lập |
| P3 | `RUNBOOK_D2.md` viết cho "agent chạy benchmark tối nay" (23/10) và trỏ vào đường dẫn đã chuyển | Tham chiếu `docs/plans/D2_COMPLETION_PLAN.md` và `docs/reviews/metrics_review_2026-10-23.md`, nhưng hai tệp đó nay nằm dưới `docs/historical/` | Liên kết gãy; tài liệu như một ghi chú bàn giao nội bộ chứ không phải hướng dẫn |
| P4 | `REPRODUCE_D2.md` ghi "Mac latency runs in progress when this was written" | Dòng 42 | Trạng thái run không còn đúng |
| P5 | Tên tài liệu gắn với mốc D2 | `REPRODUCE_D2.md`, `RUNBOOK_D2.md`, `make report_d2`, `make slides_d2`, `run_d2_benchmarks.sh`, `config/d2_*.yaml`, `deliverables/d2/` | D3 cần thêm kết quả mới (model mới, dataset lớn hơn, embedding thật, GraphRAG) mà không có chỗ để đặt |
| P6 | `architecture.md` mô tả "một domain: Bộ luật Lao động 2019" | Câu mở đầu của `docs/reference/architecture.md`; README nói hai corpus (HCMUT và luật lao động) | Sơ đồ kiến trúc và mô tả không khớp hệ thống hiện tại |
| P7 | Cấu hình mặc định và cấu hình demo khác nhau, chưa có chỗ ghi rõ | `config/config.yaml:41` đặt `dense_model_type: "tfidf"` (nhận xét "không phải neural embeddings"); README demo dùng `make demo-web-gemma2` | Dễ nhầm hệ thống mặc định chạy embedding thật; góp ý D2 yêu cầu embedding thật là bắt buộc |
| P8 | Dữ liệu chạy chiếm gần hết repo | `evaluation/runs` 693 MB, 9.103 trong 9.852 tệp được theo dõi bởi git (khoảng 92%) | Clone chậm; khó thấy tệp quan trọng; cần xác định phần nào là raw results cho D4 |
| P9 | Thư mục `deliverables/d3/report/` chứa bản nháp D3 cũ đã bị loại | README của nó đánh dấu HISTORICAL; `make report_d3` vẫn có | Dễ bị build và nộp nhầm |
| P10 | `redteam/` còn kết quả của pipeline đã bỏ | `redteam/README.md`: HISTORICAL; `make redteam` bị vô hiệu | Yêu cầu D3 cần ≥10 ca chạy native; thư mục hiện gây hiểu lầm |
| P11 | `docs/materials/` 29 MB gồm PDF nguồn pháp lý và tài liệu môn học lẫn nhau | `docs/materials/{benchmark-sources,hcmut-sources,labour-sources,d2,d3}` | Cần ghi rõ giấy phép/nguồn cho từng loại, nhất là khi thêm dataset công khai |

## 2. Kiến trúc (chờ agent)

Agent đang vẽ lại sơ đồ bằng skill `archify` từ mã `src/`. Khi có báo cáo, thêm vào đây danh sách các chỗ `architecture.md`, README và `docs/images/architecture.png` lệch với mã, và quyết định thay thế sơ đồ cũ bằng sơ đồ mới.

## 3. Cấu trúc đích đề xuất

Nguyên tắc: không xóa, chỉ di chuyển và đánh dấu; mọi đường dẫn mà Makefile, `RESULTS_PROVENANCE.md` và báo cáo D2 đã nộp đang dùng phải còn truy cập được hoặc có chuyển hướng.

```
README.md                         # giữ; cập nhật theo D3 (một lệnh chạy, một lệnh tái lập)
docs/
  README.md                       # chỉ mục; ghi rõ tài liệu nào là hiện hành
  reference/                      # đặc tả hệ thống hiện hành (cập nhật cho khớp mã)
    architecture.md               # viết lại theo mã, kèm sơ đồ mới
  guides/
    REPRODUCE.md                  # thay REPRODUCE_D2.md: D3 làm bản chính, D2 giữ làm phụ lục
    RUNBOOK.md                    # tổng quát hóa; chuyển ghi chú bàn giao nội bộ sang historical
  design/                         # giữ; thêm graphrag.md và embedding.md khi làm
  materials/                      # giữ; thêm SOURCES.md ghi nguồn + giấy phép từng dataset
  historical/                     # mọi thứ đã lỗi thời, mỗi tệp có biểu ngữ "HISTORICAL"
    reviews/                      # hợp nhất docs/reviews cũ vào đây
deliverables/
  README.md
  d1/  d2/                        # giữ nguyên, chỉ đọc (đã nộp)
  d3/
    D3_REQUIREMENTS.md            # yêu cầu của giảng viên + trạng thái
    report/                       # báo cáo mới 6-8 trang hai cột (xóa bản nháp cũ khỏi build)
    slides/  demo/  forms/        # slide, video, 8 biểu mẫu
```

## 4. Các bước thực hiện (theo thứ tự ưu tiên)

1. **Ghép lại các thư mục review bị tách đôi (P1).** ĐÃ LÀM 28/11: chuyển 4 tệp về cạnh bằng chứng (`git mv`, chưa commit); manifest của gói pilot2-v3 khớp lại cả 3 hash. Bằng chứng ở lại `docs/reviews/` vì script và test dùng đường dẫn cố định.
2. **Sửa mâu thuẫn số liệu (P2, P4).** ĐÃ LÀM 28/11 trong `REPRODUCE_D2.md`: nhãn kiểm định đã đủ 30/30 mỗi benchmark (commit `138128e`), agreement 96,7% (κ 0,93) và 90,0% (κ 0,80) khớp `agreement.json`; ghi chú trạng thái các run Mac theo `REGISTRY.md`. Phát hiện thêm: chỉ có một người chấm (không có human-vs-human) và `AUDIT_NOTES.md` của hai run gọi controller là "Qwen3-4B" thay vì Bonsai 4B (chưa sửa vì là bằng chứng của run).
3. **Sửa liên kết gãy và biểu ngữ trạng thái (P3, P4, P9, P10).** ĐÃ LÀM MỘT PHẦN 28/11: sửa 16 dòng đường dẫn trong `docs/guides`, `docs/design`, `docs/reference` (không còn đường dẫn tệp nào trong các thư mục này trỏ tới tệp không tồn tại); thêm biểu ngữ trạng thái vào `REPRODUCE_D2.md`, `RUNBOOK_D2.md`, `BENCHMARKS_AND_METRICS.md`; thêm `docs/reviews/README.md`. P9 và P10 đã làm xong (xem dưới). Còn khoảng 12 chú thích trong `config/`, `evaluation/`, `src/`, `tests/` vẫn trỏ `docs/reviews/<ghi chú>.md` cũ; không sửa vì commit `0c0d3d6` ghi rằng sửa chú thích trong tệp harness có thể làm các run bị coi là cũ. Cần quyết định riêng.
4. **Viết lại `architecture.md` và thay sơ đồ (P6)** từ bản vẽ của agent và đối chiếu với mã; cập nhật hình trong README.
5. **Tách "mặc định" và "demo" (P7).** Thêm một bảng trong `architecture.md` và README: cấu hình nào bật mặc định, cấu hình nào dùng cho demo và đánh giá. Khi bật embedding thật làm mặc định, đổi `config.yaml` và ghi vào bảng.
6. **Đổi tên theo hướng không gắn mốc (P5).** Thêm `REPRODUCE.md`, `RUNBOOK.md`, và target `make reproduce`; giữ bí danh `*_d2` cho báo cáo D2 đã nộp để các liên kết cũ vẫn chạy. Không đổi tên `config/d2_*.yaml` nếu `RESULTS_PROVENANCE` đang tham chiếu; chỉ thêm cấu hình D3 mới.
7. **Quyết định về dữ liệu chạy (P8).** Không xóa raw results (D4 cần). Cân nhắc Git LFS hoặc đặt các run lớn lên Hugging Face và để trong repo chỉ `manifest.json` cùng các bảng tổng hợp, nhưng chỉ khi kiểm tra `make report-check` vẫn chạy được. Việc này ảnh hưởng tái lập nên cần nhóm quyết định.
8. **Thêm `docs/materials/SOURCES.md` (P11)** liệt kê từng nguồn dữ liệu, giấy phép và rủi ro contamination, để dùng trực tiếp cho mục Ethics và responsible use của báo cáo.
9. **Đóng băng và tag `final`** sau khi tài liệu khớp mã; chạy thử từ checkout mới.

## 5. Việc không nên làm

- Không sửa nội dung `deliverables/d1/` và `deliverables/d2/`: đó là bản đã nộp.
- Không di chuyển tệp mà `Makefile`, `RESULTS_PROVENANCE.md` hoặc `conftest.py` đang trỏ tới mà chưa chạy `make report-check` và bộ test.
- Không xóa `evaluation/runs/*` để giảm dung lượng.

## 6. Chưa kiểm tra

- Chưa so từng tệp trong các cặp review trùng, chỉ đếm số mục khác nhau.
- Chưa kiểm tra toàn bộ liên kết trong `docs/` (mới thấy các liên kết gãy ở P3).
- Chưa kiểm tra `design/*.md` có còn khớp với mã hay không.
- Chưa chạy bộ test hay `make report-check`.

## 7. Kết quả P9 và P10 (28/11/2026)

- **P9:** `deliverables/d3/report/` đổi thành `deliverables/d3/retired-draft/` (`git mv`, chưa commit) để chừa chỗ cho báo cáo D3 thật. `make report` chỉ còn build D2; `make report_d3` in thông báo đã loại bỏ và thoát lỗi; dòng bản nháp D3 trong `deliverables/README.md` đã thay bằng mô tả thư mục mới; `make clean` không còn quét `d3/report`.
- **P10:** các tệp cũ của pipeline đã bỏ (`redteam_results.json`, `adversarial_matrix_results.json`, `run_redteam.py`, `test_adversarial_matrix.py`) chuyển vào `redteam/legacy/`; hai script cũ chỉ sửa đường dẫn trong chuỗi (đường dẫn ghi kết quả và dẫn chiếu `D2_EXPERIMENT_PLAN.md`). `redteam/test_cases.json` giữ nguyên. `redteam/README.md` viết lại: nêu rõ chưa có kết quả native và ghi 4 quan sát về 10 ca hiện có (đều đặt `expected_behavior: refuse`; chỉ `DIRECT_01` là injection đúng nghĩa; ca gián tiếp đi qua `pasted_doc` chứ không qua index; không ca nào nhắm HCMUT; chỉ một ca nhắm cổng phê duyệt `send_summary`). `make redteam` vẫn chỉ in con trỏ.
- **Kiểm tra:** `evaluation/check_report_provenance.py --no-write` trả `OK: 9 result tables checked` trước và sau khi sửa Makefile (các run chính đã được ghim ở commit `cdb6b24` nên không bị coi là cũ). Hai script cũ biên dịch được (`py_compile`). **Chưa chạy** bộ pytest và `make report_d2` (máy chưa có môi trường và LaTeX).
- `docs/reviews/d2-gap-review-2026-10-21/source-manifest.json` vẫn ghi hash của các đường dẫn `redteam/*` cũ; đó là ảnh chụp tại thời điểm review nên để nguyên.
