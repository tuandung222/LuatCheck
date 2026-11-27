# D3 / D4 Final: yêu cầu quan trọng và đối chiếu với trạng thái repo

Nhóm G8, hướng **Application**, đề tài LuatCheck. Thành viên (theo bìa D2): Lê Trí Quyền (nhóm trưởng, người gửi email nộp bài), Nguyễn Hoàng Phong, Võ Phạm Tuấn Dũng. Tổng hợp ngày 27-28/11/2026.

## 0. Nguồn và cách kiểm tra

Năm tệp của giảng viên (bản cập nhật 24/11/2026). Tài liệu này đã trích nội dung của chúng; **các tệp gốc không nằm trong repo** (repo công khai, và email có địa chỉ của sinh viên khác), giữ ở máy của nhóm:

| Tệp | Nội dung | Đã đối chiếu |
|---|---|---|
| `01-Yeu-cau-Final.pdf` (5 trang) | Mục tiêu, hạn nộp, lịch; định dạng và cách nộp; nội dung báo cáo; bằng chứng tối thiểu; yêu cầu theo hướng; D4; trình bày/demo; checklist; nguyên tắc chấm | Đọc toàn bộ 5 trang |
| `02-Rubric-Final.pdf` (5 trang) | Công thức điểm, 11 tiêu chí và mô tả mức điểm, quy tắc nhất quán, đối chiếu C1-C5, ghi nhận nhận xét | Đọc toàn bộ 5 trang |
| `03-Bieu-mau-Final.pdf` (2 trang) | 8 biểu mẫu | Đọc toàn bộ 2 trang |
| `CO5151-Final-Rubric.xlsx` | Ba sheet: `Tong hop`, `Chi tiet`, `Tieu chi` | Đọc cả ba sheet, công thức cả 8 nhóm, ô kiểm tra dữ liệu; mô tả mức điểm trong `Tieu chi` khớp với rubric PDF |
| `CO5151-D3-announcement-email.pdf` | Email của giảng viên ngày 24/11/2026 (12:59). | Đọc toàn bộ |

Phần mục 14 (trạng thái repo) dựa trên việc đọc mã, tài liệu và tìm kiếm trong repo, **chưa chạy lại hệ thống hay bộ đánh giá**. Số liệu lấy từ README được ghi rõ là theo README. Các mục ghi **cần xác nhận** là chỗ chưa đủ thông tin để kết luận.

**Hai nguồn lịch khác nhau.** Trang hướng dẫn chung của môn (https://lexuanbach.github.io/5151/project.html) vẫn ghi lịch cũ hai vòng bảo vệ (D3 v1 hạn 29/11, final 11/12). Email 24/11 và `01-Yeu-cau-Final.pdf` nêu rõ lịch mới **thay thế** lịch hai vòng và các hạn final cũ, nên dùng lịch ở mục 1. Trang chung vẫn là nơi định nghĩa R1-R9, RT1-RT4, AT1-AT4 (bản cập nhật 24/11 không nhắc lại nội dung các mã này).

Định nghĩa R1-R9 (theo trang chung): R1 kiến trúc agent (sơ đồ + luồng điều khiển); R2 tools/MCP có phân quyền; R3 bộ nhớ (ngắn hạn + dài hạn/episodic, chính sách ghi/truy hồi); **R4 ≥3 trục nâng cao ngoài tools/memory** (ví dụ planning/search, reflection/verification, multi-agent, RAG, RL fine-tuning, computer use, guardrails; chiều sâu quan trọng hơn số lượng); R5 đánh giá định lượng; R6 security (threat model, ≥10 ca direct + indirect injection, least privilege, audit log); R7 demo có video dự phòng; R8 mã nguồn tái lập; R9 báo cáo 6-8 trang kèm AI-use và contribution statement.

## 1. Mốc thời gian

| Mốc | Thời điểm (giờ VN, UTC+7) |
|---|---|
| Hạn nộp chung cho cả 8 nhóm (báo cáo, slide, code, kết quả, video dự phòng, khai báo) | **23:59 Chủ nhật 06/12/2026 (tuần 49)**; không đổi theo ngày báo cáo |
| Peer evaluation cá nhân, gửi riêng tới giảng viên, **không CC nhóm** | Trước 23:59 06/12/2026 |
| **Báo cáo của G8** | **Thứ Bảy 12/12/2026 (tuần 50), online**: trình bày + demo 21:00-21:20, hỏi đáp 21:20-21:30 |
| Vào Meet kiểm tra âm thanh và chia sẻ màn hình (G5-G8) | 19:20 ngày 12/12. Link: https://meet.google.com/vsn-xeui-bcu |
| Nộp trễ | Trừ 10% mỗi ngày, tối đa 3 ngày; sau đó bài nộp nhận 0. Gia hạn do giảng viên xác định theo thông báo, không tự trừ toàn bộ final hoặc trừ hai lần |

Các nhóm khác (để biết lịch): G1-G4 trực tiếp tại B4-305 thứ Tư 09/12 từ 18:00 (có mặt trước 17:50); G5 19:30, G6 20:00, G7 20:30 và G8 21:00 ngày 12/12.

Mỗi nhóm báo cáo **một lần** 30 phút (20 trình bày + demo, 10 hỏi đáp). Lịch này thay thế lịch hai vòng bảo vệ và các hạn final trong thông báo trước.

## 2. Gói nộp và cách nộp

Nhóm trưởng gửi **một email** tới `lexuanbach@hcmut.edu.vn`, **CC tất cả thành viên**, tiêu đề `[CO5151][G8] Final report + presentation`.

| Tệp / thông tin | Ghi chú |
|---|---|
| `G8-Final-report.pdf` | 6-8 trang nội dung, hai cột (ACM/IEEE hoặc tương đương), tiếng Việt hoặc Anh dùng nhất quán. Tài liệu tham khảo và phụ lục không tính vào 6-8 trang. **Không cần bìa riêng hoặc mục lục.** Dữ liệu và lập luận chính phải nằm trong thân bài; phụ lục chỉ để chi tiết tái lập và bằng chứng bổ sung |
| `G8-Final-slides.pdf` | |
| `G8-Response-to-D2.pdf` | Bảng phản hồi góp ý Proposal/D2 (có thể nằm trong phụ lục báo cáo) |
| `G8-Contributions.pdf` | Bảng đóng góp + AI-use statement (có thể nằm trong phụ lục báo cáo) |
| Link repo | **Tag `final`** và **commit hash đầy đủ**, ghi cả trong báo cáo lẫn email |
| Link dữ liệu, raw results/logs, video dự phòng | Kiểm tra giảng viên có quyền truy cập |

**Khóa phiên bản.** Bản được chấm là bản tại hạn nộp. Nếu cần sửa lỗi sau hạn: giữ nguyên tag đã nộp và thông báo rõ commit mới, lý do, thay đổi và ảnh hưởng tới kết quả để giảng viên xem xét. **Không tự thay bài nộp bằng bản mới trước buổi báo cáo.**

## 3. Cơ cấu điểm

Final = 50% điểm đồ án = 25% điểm môn. Trong final: báo cáo 60%, mã nguồn/tái lập 20%, trình bày/demo/hỏi đáp/đóng góp 20%. Mỗi nhóm một điểm bảo vệ (cùng rubric cho trực tiếp và online).

**Công thức** (mỗi tiêu chí chấm 0-10; điểm quy đổi = điểm/10 × trọng số w; giữ số chưa làm tròn):

- R = (15·A1 + 10·A2 + 20·A3 + 10·A4 + 5·A5) / 60
- C = (8·B1 + 12·B2) / 20
- P = 0.20·P1 + 0.30·P2 + 0.30·P3 + 0.20·P4
- **F = 0.60·R + 0.20·C + 0.20·P** (ví dụ R=8, C=9, P=8 thì F=8.20)
- PRJ = 0.20·D1 + 0.30·D2 + 0.50·F
- Hệ số cá nhân k ∈ [0.8, 1.1], chỉ áp dụng khi có bằng chứng: PRJ_i = min(10, k_i × PRJ). Không nhân k thêm vào từng tiêu chí hay riêng F. Với k=1, final đóng góp 25% điểm môn.

Mức điểm: 9-10 xuất sắc; 7 đến dưới 9 tốt; 5 đến dưới 7 đạt; 0 đến dưới 5 chưa đạt (có thể chấm thập phân). Điểm 0 dành cho phần không có bằng chứng/sản phẩm; không tự động cho 0 toàn final khi thiếu một tiêu chí. Rubric ghi trọng số chi tiết "cần được phát hành trước khi áp dụng".

| Tiêu chí | % final | Điều kiện đạt 9-10 | Dấu hiệu bị kéo xuống |
|---|---:|---|---|
| A1 Bài toán, kiến trúc, lập luận thiết kế (mục 1-3) | 15 | Bài toán và đóng góp rõ; kiến trúc có cơ sở, các trục phối hợp hợp lý; so sánh phương án và giải thích trade-off | 5-7: ghép cơ học, lý do dùng agent mờ. Dưới 5: thiếu thành phần trọng yếu hoặc sơ đồ sai với hệ thống |
| A2 Triển khai và bằng chứng hệ thống (mục 4) | 10 | Mô tả chính xác code đang chạy; trace nối quyết định, tools, memory, kết quả; chỉ rõ phần tự làm và giới hạn | 5-7: mô tả theo framework/ảnh chụp. Dưới 5: không khớp code/demo, dùng kế hoạch thay kết quả |
| A3 Đánh giá định lượng (mục 5) | **20** | Đạt 20 tasks, 2 cấu hình, 3 runs; số liệu truy vết được, so sánh công bằng, có độ biến thiên, cost/latency, phân tích lỗi sâu; đáp ứng hướng đã duyệt | 5-7: thiếu một hay nhiều mức tối thiểu, ablation yếu, ít runs. Dưới 5: chỉ demo vài ví dụ; số liệu bịa không là bằng chứng |
| A4 Security, safety, responsible use (mục 6, 8) | 10 | Threat model sát hệ thống; đủ ca tấn công có kết quả/log; kiểm soát quyền được kiểm thử; giải thích lỗi và residual risk; xử lý dữ liệu có trách nhiệm | 5-7: thử nghiệm hạn chế, quyền/logs chủ yếu mới mô tả. Dưới 5: chỉ lặp nguy cơ chung |
| A5 Chất lượng báo cáo, trung thực kết luận | 5 | 6-8 trang mạch lạc, hình/bảng đọc được; claim khớp số liệu, nguồn đúng, giới hạn và khai báo đầy đủ | 5-7: thiếu khai báo/giới hạn/nguồn hoặc có mâu thuẫn chưa xử lý |
| B1 Chất lượng mã nguồn | 8 | Code đúng phiên bản, đầy đủ, tổ chức rõ; end-to-end chạy; lỗi và retry được xử lý; tách rõ dependencies và phần tự xây | 5-7: chỉ happy path, còn bước thủ công. Dưới 5: thiếu code chính, không truy cập được, sai phiên bản |
| B2 Tái lập và truy vết | **12** | Chạy lại từ checkout sạch theo hướng dẫn; scripts tái tạo bảng từ raw results; điều kiện API/hardware, thời gian, chi phí rõ; tag/hash khớp | 5-7: chỉ tái lập một phần. Dưới 5: chỉ có screenshot/video |
| P1 Cấu trúc trình bày, thời gian | 4 | Đúng trọng tâm, chuỗi bài toán-thiết kế-bằng chứng; slide dễ đọc, đúng giờ; nêu rõ thay đổi từ D2 | 5-7: phần nền dài, vượt giờ |
| P2 Demo và giải thích hành vi | 6 | Chứng minh hành vi thực; giải thích trace, quyết định, lỗi/phòng vệ; chỉ rõ phiên bản và giới hạn demo | 5-7: demo hẹp, khó phân biệt chạy thật và chuẩn bị sẵn. Dưới 5: video không phản ánh bản code báo cáo |
| P3 Hỏi đáp, làm chủ công việc | 6 | Trả lời chính xác, có bằng chứng, hiểu trade-off; các thành viên nắm phần mình làm | 5-7: mức hiểu không đồng đều. Dưới 5: mâu thuẫn với sản phẩm |
| P4 Xử lý góp ý, bằng chứng đóng góp | 4 | Góp ý được xử lý hoặc phản hồi có căn cứ; chỉ rõ thay đổi và bằng chứng; đóng góp từng người nhất quán | 5-7: ít bằng chứng, khai chung chung. Dưới 5: bỏ qua góp ý trọng yếu |

**Quy tắc áp dụng nhất quán (rubric mục 3, 5):**
- Báo cáo và code chấm trên bản đã nộp; P ghi nhận tại buổi bảo vệ của nhóm, không lấy trung bình hai buổi.
- A2 chấm độ chính xác và bằng chứng trong báo cáo; B1 kiểm tra code thực; P2 kiểm tra demo và khả năng giải thích. Một hệ thống có thể cung cấp bằng chứng cho nhiều tiêu chí nhưng không phạt thêm cho cùng một lỗi.
- Video dự phòng là phương án đã yêu cầu khi lỗi mạng/API: chấm theo bằng chứng và khả năng giải thích; không tự động cho 0, cũng không coi là đã xác minh live.
- Cần thể hiện thay đổi từ D2 và bằng chứng sửa. Điểm thực nghiệm tăng không phải điều kiện để điểm cao; sửa một kết luận quá mạnh hoặc xác định rõ nguyên nhân thất bại cũng là tiến bộ.
- Hai hướng Research/Application cùng trọng số. Các thay đổi phạm vi đã được giảng viên duyệt được xem xét theo phạm vi đó; mọi ngoại lệ phải có ghi nhận, không tự bỏ yêu cầu tối thiểu.
- Sai phạm học thuật xử lý theo quy định môn học. Không dùng số liệu, nguồn hoặc đóng góp bịa.
- Mỗi nhóm nhận danh sách điểm mạnh, hạn chế và nhận xét cuối; mỗi nhận xét chỉ rõ tiêu chí, trang/commit/log và lý do. Đối chiếu bảng phản hồi D2 (đã làm/chưa làm, bằng chứng).
- Hệ số cá nhân dùng contribution statement, đánh giá nội bộ, sản phẩm thực tế và hỏi đáp; không dùng số commit làm thước đo duy nhất.
- Đối chiếu rubric chung: C1 (architecture) ứng với A1 (+A2/B1); C2 (implementation, demo) với A2, B1, P2; C3 (evaluation, security) với A3, A4 (+P3); C4 (report, reproducibility) với A5, B2; C5 (presentation, defense, contribution) với P1, P3, P4 và hệ số cá nhân. Chỉ để đối chiếu, không phải phép chấm thứ hai.

**Excel `CO5151-Final-Rubric.xlsx`:** là mẫu bảng chấm của giảng viên cho cả 8 nhóm, chưa có điểm. Điểm nhập 0-10 bước 0.1; ô trống không phải điểm 0; mỗi nhóm cần đủ 11 điểm hợp lệ; Final = 60% báo cáo + 20% code + 20% bảo vệ, không làm tròn điểm trung gian; chưa xử lý nộp trễ và hệ số cá nhân. Công thức khớp với rubric PDF. Nhóm chỉ dùng để tự đối chiếu.

## 4. Cấu trúc báo cáo D3 (theo mục 3 của yêu cầu)

Abstract rồi 9 mục đánh số 1-9, sau đó References và phụ lục.

- **Abstract:** bài toán, cách tiếp cận, kết quả chính **có số liệu**, giới hạn quan trọng. Nêu rõ tên đề tài, nhóm, thành viên, hướng Application.
- **1. Introduction:** người dùng/bài toán, lý do dùng agent, phạm vi, đóng góp thực tế. Application nêu nhu cầu và kịch bản sử dụng. Phân biệt phần tự xây dựng với framework, model, mã, dữ liệu có sẵn.
- **2. Background và related work/systems:** so sánh với hệ thống/phương pháp gần nhất, chỉ ra khác biệt và khoảng trống; trích dẫn đúng nguồn đã kiểm tra. Không dùng tên framework hoặc số lượng agent làm bằng chứng về tính mới.
- **3. System design:** sơ đồ kiến trúc và luồng điều khiển thực tế (R1); tool/MCP hoặc function calling tương đương và phân quyền (R2); quản lý context cùng bộ nhớ dài hạn/episodic, chính sách ghi và truy hồi (R3); đánh dấu **≥3 trục nâng cao** ngoài tools/memory (R4), giải thích vai trò, tương tác, lựa chọn thiết kế và phương án thay thế đã cân nhắc.
- **4. Implementation:** stack, model/version, framework, phần tự cài đặt, xử lý lỗi, giới hạn kỹ thuật; **một trace thật** nối đầu vào, quyết định của agent, tool calls, memory và đầu ra; thay đổi quan trọng so với D2 và lý do; phần chưa cài đặt phải ghi rõ.
- **5. Evaluation:** câu hỏi đánh giá; task set và cách lấy mẫu; tiêu chí thành công; baseline/configuration; **ngân sách**; số lần chạy; bảng kết quả; cost/latency; ablation; phân tích lỗi. Cấu hình và log đủ để kiểm tra số liệu (chi tiết ở mục 5 bên dưới).
- **6. Security và safety:** threat model; kết quả kiểm thử injection; kiểm soát quyền; hành động cần phê duyệt; audit log; biện pháp xử lý; rủi ro còn lại. Gắn với đúng hệ thống đang triển khai, không chỉ liệt kê nguy cơ chung của LLM.
- **7. Limitations, threats to validity, extensibility:** phân biệt giới hạn thiết kế với giới hạn của phép đo; điều chưa kiểm chứng; khả năng khái quát; hướng mở rộng/triển khai. Không suy rộng từ demo hay task set nhỏ.
- **8. Ethics và responsible use:** nguồn/quyền sử dụng dữ liệu, riêng tư, các bên có thể bị ảnh hưởng, phạm vi sử dụng phù hợp, trách nhiệm khi agent thực hiện hành động.
- **9. Conclusion:** trả lời câu hỏi/giả thuyết ban đầu bằng kết quả đã đo; giá trị đạt được; vấn đề còn mở. Kết quả âm hoặc không cải thiện vẫn có giá trị nếu thiết kế đánh giá và lập luận chặt chẽ.
- **References và phụ lục:** lệnh tái lập, dependencies, phần cứng, seeds/run IDs, ngân sách thực tế, đường dẫn raw results, bảng đóng góp, AI-use statement (công cụ/model, công đoạn dùng, cách nhóm kiểm tra đầu ra). Bảng phản hồi Proposal/D2 có thể nộp riêng.

## 5. Bằng chứng đánh giá tối thiểu

| Nội dung | Yêu cầu và cách báo cáo |
|---|---|
| Task set | ≥20 task instances; nêu nguồn, cách chọn, độ khó, tiêu chí đúng/sai, dữ liệu kiểm thử. **Không chỉ đổi tên trong cùng một ví dụ demo** |
| Cấu hình | ≥2 cấu hình để ablation. Giữ điều kiện so sánh tương đương; chỉ rõ thành phần thay đổi và giả thuyết được kiểm tra |
| Lặp lại | ≥3 runs/seeds mỗi cấu hình trên task set đánh giá; báo cáo trung bình và độ biến thiên. Nếu API không hỗ trợ seed: ghi run IDs, thời gian, tham số và giới hạn tái lập |
| Chỉ số | Success có quy tắc chấm rõ; cost và latency cùng đơn vị, cùng mẫu số. Nêu cách tính chi phí, model, ngày chạy, và các lần lỗi/retry được tính thế nào |
| Phân tích lỗi | Phân loại nguyên nhân, số lượng/tỷ lệ, ví dụ có trace. **Không bỏ các lần chạy thất bại khỏi bảng mà không giải thích** |
| Security | ≥10 attack cases tổng cộng, gồm direct và indirect prompt injection; nêu payload/điểm vào, mục tiêu, kết quả, phòng vệ, residual risk. Bộ tấn công báo cáo riêng |

Thiết kế tối thiểu 20 tasks × 2 cấu hình × 3 runs = 120 lượt task-run cho thí nghiệm chính. **Nếu một trường hợp không áp dụng hoặc tài nguyên không đủ: ghi giới hạn và trao đổi với giảng viên; không tự tuyên bố đã đạt yêu cầu.**

Nếu dùng LLM-as-judge: mô tả model, prompt, tiêu chí và cách kiểm tra độ tin cậy trên một mẫu có người đọc/chấm; nêu rủi ro contamination của benchmark công khai. Dùng raw results để tính bảng; giữ liên kết giữa task ID, cấu hình, run ID, log và dòng kết quả.

## 6. Yêu cầu riêng theo hướng đã duyệt: Application (AT1-AT4)

- Nhóm người dùng cụ thể.
- Ít nhất **ba kịch bản**, gồm một người dùng bất cẩn hoặc có ý đồ xấu.
- Ít nhất **một walkthrough với người dùng tiềm năng thật**.
- Xử lý tool failure, timeout, malformed output; retry an toàn cho hành động không idempotent.
- Đo cost/latency theo **tải thực tế**, nêu giới hạn vận hành; phân biệt giới hạn đã đo với ước lượng.
- Mọi tool ghi không thể hoàn tác cần kiểm tra quyền, xác nhận hoặc sandbox; trình bày **audit trail của một hành động được bảo vệ**.
- Application được đánh giá qua giá trị sử dụng và độ vững của hệ thống. **Không cộng điểm chỉ vì model đắt, nhiều agent, giao diện đẹp hoặc số trang dài.**

(Hướng Research có RT1-RT4: giả thuyết bác bỏ được, baseline ngoài, ablation, mean/SD, contamination, đóng gói harness. Không áp dụng cho G8; ghi ở đây để biết.)

## 7. D4: mã nguồn và tái lập

- README mô tả cài đặt, cấu hình, lệnh chạy; dependencies được pin; `.env.example` chỉ chứa tên biến và giá trị mẫu; dữ liệu hoặc hướng dẫn lấy dữ liệu; scripts chạy đánh giá và tổng hợp bảng; seeds/configs; log/trace đại diện; raw results; báo cáo chi phí thực tế. **Không đưa API key, token hoặc dữ liệu cá nhân chưa xử lý** vào gói nộp.
- **Một lệnh chạy hệ thống và một lệnh tái lập đánh giá/bảng kết quả**, sau các bước cài đặt và cấp credential đã mô tả. Nêu yêu cầu phần cứng, API/network, thời gian, chi phí dự kiến, bước thủ công không thể tự động hóa.
- Với dịch vụ bên ngoài: phân biệt chạy lại live với đọc lại kết quả đã lưu; kết quả lưu không thay thế bằng chứng hệ thống hoạt động.
- Tag `final`; ghi commit hash đầy đủ. Code, cấu hình, log, kết quả phải khớp báo cáo. Giảng viên phải truy cập được repo và dữ liệu; không bắt buộc công khai nếu có lý do về dữ liệu/quyền sử dụng.

## 8. Trình bày, demo và hỏi đáp

**20 phút trình bày + demo** (gợi ý, có thể điều chỉnh nhưng phải kết thúc phần này ở phút 20): 2 bài toán/đóng góp; 4 kiến trúc, tools, memory và các trục nâng cao; 6 live demo; 5 đánh giá, baseline/ablation, cost/latency, security; 3 thay đổi từ D2, hạn chế, kết luận.

**10 phút hỏi đáp:** làm rõ lựa chọn thiết kế, kiểm tra code/trace, số liệu, bảo mật, giới hạn, đóng góp từng người. Mọi thành viên có mặt và sẵn sàng trả lời về phần mình; giảng viên có thể chỉ định người trả lời; không dành toàn bộ hỏi đáp cho một người.

**Live demo:** ít nhất một task hoàn thành từ đầu đến cuối trên hệ thống thực; mở được trace để giải thích tool calls, memory, quyết định, kiểm soát quyền; chuẩn bị một tình huống lỗi hoặc tấn công có kiểm soát. Demo dùng **bản đã nộp**, hoặc bản sửa **đã được giảng viên chấp thuận** và ghi rõ khác biệt.

**Chuẩn bị:** slide PDF, video demo dự phòng đúng commit, log/trace mẫu. Nếu lỗi mạng/API: thông báo chuyển sang video và giải thích bằng chứng, không giới thiệu video là chạy trực tiếp. Slide và biểu đồ đọc được, **có nguồn cho hình/bảng trích dẫn**, số liệu thống nhất với báo cáo.

**Buổi online:** tên hiển thị `G8 - Họ tên`; kiểm tra micro và quyền chia sẻ màn hình trước giờ bắt đầu; mở sẵn repo, terminal, dữ liệu mẫu, video; chỉ chia sẻ cửa sổ cần thiết, tránh lộ API key và dữ liệu riêng tư; thống nhất **một người chia sẻ màn hình chính và một người dự phòng**.

Các nhóm khác chuẩn bị câu hỏi phản biện dựa trên báo cáo của nhóm; phản biện của sinh viên chỉ là đầu vào góp ý, điểm do giảng viên chấm, không áp dụng tỷ lệ 30%-30%-40% của seminar. Nhóm G8 cũng phải chuẩn bị phiếu phản biện cho nhóm được giao (biểu mẫu 7); email chưa nêu nhóm nào, cần hỏi giảng viên.

## 9. Checklist trước khi nộp (mục 8 của yêu cầu, đủ 11 mục)

- [ ] Báo cáo D3 đủ nội dung, bảng kết quả và giới hạn; 6-8 trang nội dung, tài liệu tham khảo và phụ lục tách rõ.
- [ ] Kiến trúc phản ánh đúng code; tools/MCP, memory và ≥3 trục nâng cao có bằng chứng hoạt động.
- [ ] Đánh giá ≥20 tasks, 2 configurations, 3 runs/seeds; success, cost, latency, độ biến thiên; có error analysis.
- [ ] Application: kịch bản/người dùng, robustness, operational envelope, guarded actions.
- [ ] Threat model gắn với hệ thống; ≥10 ca tấn công bao phủ direct/indirect injection; có log và kết quả.
- [ ] Repo có tag final/commit hash, quyền truy cập, README, pinned dependencies, cấu hình mẫu, scripts, raw results đầy đủ.
- [ ] Đã chạy thử từ môi trường sạch hoặc checkout mới; nêu điều kiện cần và phần chưa thể tái lập.
- [ ] Slide final và video dự phòng đúng phiên bản; demo đã chạy thử trong điều kiện báo cáo.
- [ ] Bảng phản hồi góp ý Proposal/D2 có vị trí sửa và bằng chứng.
- [ ] Contribution statement và AI-use statement đầy đủ; từng thành viên gửi peer evaluation riêng trực tiếp tới giảng viên trước 23:59 06/12/2026, không CC nhóm.
- [ ] Email nộp cuối gửi đúng hạn 23:59 Chủ nhật 06/12/2026; các link mở được bằng tài khoản có quyền của giảng viên.

## 10. Biểu mẫu (từ `03-Bieu-mau-Final.pdf`)

1. **Phản hồi góp ý Proposal/D2.** Đầu bảng: nhóm, đề tài, hướng. Cột: ID (R1, R2...), góp ý và nguồn, hành động hoặc lý do không sửa, vị trí sửa + bằng chứng (mục/trang, commit, kết quả/log), trạng thái (xong / một phần / chưa). Mỗi góp ý một dòng; không chỉ ghi "đã sửa". Góp ý chưa giải quyết: nêu lý do, ảnh hưởng tới kết luận, phần còn hạn chế. Nộp cùng báo cáo trước 23:59 06/12/2026.
2. **Bảng thực nghiệm và nguồn kết quả.** Cột: cấu hình, tasks/runs, success (mean, SD), cost/task, latency/task, raw results/config. Hàng mẫu: baseline, hệ thống đầy đủ, ablation (baseline và ablation có thể trùng nếu giải thích được vai trò). Ghi đơn vị, mẫu số, điều kiện so sánh, cách tính. **Không điền số giả.** Raw results cần task ID, config ID, run ID, verdict, chi phí, thời gian, lỗi, trace path.
3. **Kiểm thử bảo mật.** Cột: case ID/loại (A01 direct, A02 indirect...), điểm vào và mục tiêu, phòng vệ, kết quả quan sát, log/rủi ro còn lại. Làm rõ "thành công" là của tấn công hay của phòng vệ. Dùng môi trường kiểm thử và dữ liệu mẫu, **không thử trên tài khoản/dữ liệu của bên thứ ba**.
4. **Đối chiếu yêu cầu và bằng chứng.** Mỗi yêu cầu R1-R9 một dòng, cộng AT1-AT4; cột: vị trí trong báo cáo, code/config/log, trạng thái hoặc giới hạn.
5. **Contribution statement và AI-use statement.** Cột: thành viên/MSHV, phần phụ trách, sản phẩm thực tế, bằng chứng (commit/PR/task/log/section), tỷ lệ đóng góp (tổng 100%). Mô tả đóng góp thật gồm thiết kế, thử nghiệm, phân tích, viết; số commit không phản ánh toàn bộ. **Tất cả thành viên xác nhận bảng chung.** AI-use: công cụ/model và phiên bản nếu biết; công đoạn dùng; phần đầu ra được sử dụng; cách kiểm tra code, số liệu, trích dẫn; nếu không dùng thì ghi rõ. Nhóm chịu trách nhiệm về nội dung nộp.
6. **Đánh giá nội bộ cá nhân (gửi riêng giảng viên).** Người đánh giá, nhóm, ngày. Mỗi thành viên (gồm bản thân): tỷ lệ đóng góp (tổng do một người phân bổ = 100%), tin cậy 1-5, kỹ thuật 1-5, hợp tác 1-5, một bằng chứng cụ thể. Mức 1 rất hạn chế, 3 đáp ứng vai trò, 5 nổi bật có bằng chứng. Gửi trực tiếp `lexuanbach@hcmut.edu.vn`, không CC thành viên khác. Không tự động chuyển thành hệ số điểm.
7. **Phiếu phản biện.** Nhóm phản biện, nhóm được phản biện, ngày. Gồm: tóm tắt hệ thống ba câu; đóng góp kỹ thuật mạnh nhất và bằng chứng; hai điểm cần cải thiện về đánh giá kèm đề xuất; hai điểm về bảo mật kèm đề xuất (nếu chưa thấy thì ghi phạm vi đã kiểm tra, không bịa); kiểm tra tái lập (chạy được/một phần/chưa, môi trường, lệnh, lỗi); hai câu hỏi cho phần hỏi đáp; góp ý D2 nào đã xử lý, bằng chứng, việc còn mở.
8. **Thông tin bàn giao D4.** Repo URL; tag final; commit hash; lệnh cài đặt; lệnh chạy demo; lệnh đánh giá; lệnh tạo bảng kết quả; dữ liệu và quyền truy cập; model/version và ngày chạy; hardware; thời gian/chi phí; video dự phòng; raw results/logs; giới hạn tái lập.

## 11. Đối chiếu độ phủ nguồn

| Nguồn | Phần | Nằm ở mục |
|---|---|---|
| Yêu cầu | 1 Mục tiêu, hạn, lịch | 1, 3 |
| Yêu cầu | 2 Định dạng, cách nộp, tag và khóa phiên bản | 2 |
| Yêu cầu | 3 Nội dung báo cáo | 4 |
| Yêu cầu | 4 Bằng chứng tối thiểu | 5 |
| Yêu cầu | 5 Hướng Research/Application | 6 |
| Yêu cầu | 6 D4 | 7 |
| Yêu cầu | 7 Trình bày, demo, hỏi đáp | 8 |
| Yêu cầu | 8 Checklist | 9 |
| Yêu cầu | 9 Nguyên tắc chấm, nộp trễ | 1, 3 |
| Rubric | 1 Cơ cấu, công thức, k | 3 |
| Rubric | 2 Mức điểm; tiêu chí A1-A5, B1-B2, P1-P4 | 3 |
| Rubric | 3 Quy tắc nhất quán; 4 Đối chiếu C1-C5; 5 Nhận xét bắt buộc | 3 |
| Biểu mẫu | 8 biểu mẫu | 10 |
| Excel | 3 sheet | 3 (ghi chú Excel) |
| Email | Thông báo ngày 24/11 | 1, 2 (lịch, cách nộp, cấu trúc điểm) |

## 12. Góp ý D2 của giảng viên và hướng xử lý (bản nháp cho biểu mẫu 1)

Nhận xét do nhóm chuyển lại ngày 28/11/2026. Hai dòng cuối của danh sách đang để trống, chưa biết có nhận xét nào khác hay không.

| ID | Góp ý | Hướng xử lý dự kiến | Bằng chứng cần có | Trạng thái |
|---|---|---|---|---|
| R1 | D2 chạy benchmark với dataset quá nhỏ | Thêm benchmark công khai uy tín quy mô lớn hơn, bên cạnh 2 benchmark tự xây (2×50 câu). Cơ sở khảo sát: `docs/historical/reviews/public_vn_legal_benchmarks_2026-10-23.md` | Task set mới, nguồn, giấy phép, cách chọn mẫu, raw results | Chưa |
| R2 | D2 chỉ benchmark với 2 model Bonsai quá nhỏ | Thêm nhiều controller model qua API và/hoặc local lớn hơn; so sánh chi phí | Bảng model × cấu hình, cost/task, latency/task, run IDs | Chưa |
| R3 | D2 chưa có tính mới, thiết kế quá kinh điển | Chọn một đóng góp có thể kiểm chứng (ví dụ GraphRAG pháp lý có kiểm chứng trích dẫn, hoặc phân tích chi phí chạy trên desktop) và ablation tách tác động | Mục 1-3 báo cáo, ablation | Chưa |
| R4 | D2 có thể thử GraphRAG cho domain luật | Thử đồ thị tham chiếu/sửa đổi giữa điều khoản và so với cấu hình hiện tại | Cài đặt, ablation, error analysis | Chưa |
| R5, R6 | (để trống trong nhận xét) | Hỏi lại nhóm/giảng viên | | |

Quyết định nhóm đã nêu thêm: retrieval phải chạy với **mô hình embedding deep learning thật**, bắt buộc và không tắt mặc định như D2 (hiện `config/config.yaml:41` đặt `dense_model_type: "tfidf"`). Chi phí chạy trên desktop phải được làm rõ.

## 13. Việc cần xác nhận với giảng viên hoặc nhóm

- Nhóm được giao phản biện (biểu mẫu 7) là nhóm nào.
- Hai nhận xét trống (R5, R6) của giảng viên về D2.
- Walkthrough với người dùng thật đã làm chưa; benchmark khó hơn đã làm chưa (mục 14).
- Nếu có hạng mục không đủ tài nguyên: trao đổi với giảng viên trước, theo yêu cầu mục 5.

## 14. Đối chiếu với trạng thái repo (nhận định ban đầu)

Commit hiện tại: `139d751` trên `main`. Báo cáo D2 đã nộp ghi revision `21a70e4cb5f8f07a20183b4636aed2fb3afb49c5`. Các tag đang có: `v1`, `v1.0`, `v1.0-final` (chưa có tag `final` theo yêu cầu D4).

| Yêu cầu | Trạng thái repo | Việc cần làm |
|---|---|---|
| ≥20 tasks, ≥2 cấu hình, ≥3 seeds | Theo README: 2 benchmark × 50 câu, 3 cấu hình (no verifier, verifier, verifier + reranker), seeds 42/123/2026, 1.090 trial/controller. Có `evaluation/benchmarks/` với `hcmut_v1`, `labour_vi_v1` | Chọn cấu hình vào bảng chính theo biểu mẫu 2. **Không thấy benchmark mới "khó hơn, chưa từng thấy"** mà D2 hứa cho tuần 45-46 (chỉ có `hcmut_v1`, `labour_vi_v1`, `bll2019_v1`); cần xác nhận với nhóm |
| Ablation retrieval end-to-end | D2 kế hoạch tuần 46 có "dense-retrieval ablation". Repo có probe retrieval tầng đầu (README, 917 câu) | Xác nhận chạy end-to-end chưa; probe tầng đầu không thay thế ablation hệ thống |
| Cost/latency | Theo README: latency tuần tự (4B median 33.0 s, p95 86 s; 2B 13.3 s) và chi phí judge 2,17 USD | **Thiếu đo theo tải thực tế (concurrency)**; AT yêu cầu operational envelope, ghi rõ đã đo hay ước lượng |
| LLM-as-judge | Theo README: deepseek-v4-flash, kiểm định 60 mẫu người chấm (κ 0,93 và 0,80) | Nêu rủi ro contamination trong báo cáo |
| Error analysis | Có ghi chú dạng historical (`docs/historical/reviews/v3_failure_analysis_2026-10-24.md`) | Viết lại từ raw results mới, có trace path |
| Security ≥10 ca, direct + indirect | `redteam/test_cases.json` có 10 ca (4 direct, 4 indirect, 2 poisoned shard). `redteam/README.md` ghi kết quả cũ thuộc pipeline đã bỏ (nay nằm trong `redteam/legacy/`); `Makefile` dòng 89-90 vô hiệu hóa `make redteam` | **Chạy lại trên pipeline native, lưu log và kết quả**; rủi ro lớn nhất cho A4. Các ca "poisoned shard" cần xếp vào indirect |
| Hành động được bảo vệ + audit trail | Đã xác nhận trong mã: `send_summary` xếp `IRREVERSIBLE_WRITE` (`src/tools/permissions.py`); API có `/api/v1/summary-proposals/{id}/confirm` trả `queued_locally` hoặc `duplicate_suppressed` (`src/api/app.py:692-701`); có `src/security/audit_logger.py`. Hành động chỉ ghi vào hàng đợi cục bộ, chưa gửi thật | Chưa kiểm tra riêng việc gắn SHA-256 của payload ở đường web API (README nói có). Chuẩn bị một audit trail thật để demo; kiểm tra retry an toàn khi tool lỗi |
| ≥3 kịch bản, có người dùng bất cẩn/ác ý | D2 có demo guardrail injection, refuse, clarify | Chọn đúng 3 kịch bản và ghi vào báo cáo |
| Walkthrough với người dùng thật | `docs/reviews/native-benchmark-2026-10-22/team-status-2026-10-22.json` ghi "not yet conducted", chưa có ngày hẹn lại. D2 giao việc này cho Quyền và Phong ở tuần 45 (2-8/11) | **Chưa thấy bằng chứng đã làm.** Cần xác nhận với nhóm; nếu chưa thì sắp xếp ngay vì thiếu yêu cầu AT |
| ≥3 trục nâng cao (R4) | D1 khai 3 trục (`deliverables/d1/report/chap1.tex:88-90`): planning/search, reflection/verification, guardrails. D2 báo cáo không dùng từ "axis" | Gắn bằng chứng chạy được cho từng trục. **D1 mô tả L1 chấm bằng độ tương đồng embedding, còn L1 hiện tại là heuristic từ vựng tất định** (README, `lexical_grounding_v2.py`); ghi trong mục thay đổi so với D2/D1 |
| Tag `final`, commit hash, quyền truy cập | Chưa có tag `final`. Bìa D2 và slide D2 vẫn trỏ tới `github.com/tuandung222/LuatCheck-D2`; repo đã đổi tên thành `LuatCheck` | Tạo tag sau khi đóng băng; dùng URL mới trong báo cáo và email; kiểm tra giảng viên truy cập repo và dữ liệu (index trên Hugging Face) |
| Một lệnh chạy và một lệnh tái lập | Có `docs/guides/REPRODUCE_D2.md`, `make report-check`, `make demo-web-gemma2` (README) | Gói lại thành lệnh cho D3; chạy thử từ checkout sạch |
| Báo cáo 6-8 trang hai cột | D2 là 12 trang PDF (bìa + nội dung ≤10 trang + tài liệu tham khảo), LaTeX `article` một cột. bản nháp D3 cũ đã chuyển sang `deliverables/d3/retired-draft/` (đã loại bỏ, không build) | Viết mới theo mẫu hai cột, không bìa, không mục lục, dùng số liệu native |
| Bảng phản hồi góp ý D2 | Repo không có nhận xét của giảng viên về Proposal/D2 | **Cần bạn cung cấp nhận xét D2 và Proposal của giảng viên** |
| Contribution, AI-use, peer evaluation | Có bảng đóng góp và AI-use từ D2 (`sections/sec8_contributions.tex`) | Cập nhật cho D3, tổng 100%, mọi thành viên xác nhận; mỗi người tự gửi peer evaluation riêng |
| Slide + video dự phòng | Có slide D2 và video dự phòng D2 | Làm slide final có nguồn cho hình/bảng; quay lại video đúng commit final |

## 15. Việc nên làm theo thứ tự (tính từ 28/11 còn 8 ngày tới hạn nộp)

1. Chốt phạm vi: xác nhận 3 trục nâng cao, 3 kịch bản Application, cấu hình chính và cấu hình ablation.
2. Chạy lại red-team native (≥10 ca), lưu log. Đo tải thực tế cho cost/latency. Sắp xếp walkthrough nếu chưa làm.
3. Đóng băng code, chạy toàn bộ đánh giá lần cuối, sinh bảng từ raw results, tag `final`.
4. Chạy thử từ checkout sạch, ghi điều kiện và phần chưa tái lập.
5. Viết báo cáo 6-8 trang, bảng phản hồi D2, contribution/AI-use.
6. Làm slide và quay video dự phòng đúng commit; tập demo bản online có người chia sẻ dự phòng; chuẩn bị tình huống lỗi/tấn công có kiểm soát.
7. Gửi email đúng hạn (đúng tiêu đề, đủ 4 tệp PDF và link); mỗi thành viên gửi peer evaluation riêng.
