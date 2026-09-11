# K4 — Ngày 1: Bài Tập & Phản Ánh
## Khám Phá LLM API | Phiếu Thực Hành

**Thời lượng:** 4 tiếng
**Cách làm:** Trả lời từng câu ngay sau khi hoàn thành block tương ứng —
đừng để dồn hết về cuối buổi. Thay dòng `*Câu trả lời của bạn*` bằng câu
trả lời thật (chấm tự động sẽ đếm số câu đã trả lời).

---

## Block 1 — API Cơ Bản (trả lời sau Checkpoint 1)

### Câu 1.1 — Độ nhạy của temperature
Gọi `call_openai` với temperature 0.0, 0.5, 1.0 và 1.5 dùng prompt
**"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**
**temp 0.0**: *('Một sự thật thú vị về Việt Nam là đất nước này có một hệ thống hang động lớn nhất thế giới, đó là hang Sơn Đoòng. Hang Sơn Đoòng nằm trong Vườn quốc gia Phong Nha-Kẻ Bàng, tỉnh Quảng Bình. Hang động này được phát hiện vào năm 1991 bởi một người dân địa phương tên là Hồ Khanh, nhưng mãi đến năm 2009, một đoàn thám hiểm người Anh mới chính thức khảo sát và công bố về kích thước khổnglồ của nó. Hang Sơn Đoòng có chiều dài hơn 5 km, cao 200 m và rộng 150 m, đủ lớn để chứa cả một tòa nhà chọc trời 40 tầng. Bên trong hang có cả một hệ sinh thái riêng với rừng cây, sông ngầm và các loài động thực vật độc đáo.', 3.361321100004716)*
**temp 0.5**:*(('Một sự thật thú vị về Việt Nam là đất nước này là một trong những quốc gia hàng đầu thế giới về sản xuất và xuất khẩu cà phê. Việt Nam đứng thứ hai thế giới về sản lượng cà phê xuất khẩu, chỉ sau Brazil. Đặc biệt, Việt Nam nổi tiếng với cà phê robusta, loại cà phê có hương vị đậm đà và thường được sử dụng trong các sản phẩm cà phê hòa tan. Cà phê cũng là một phần quan trọng trong văn hóa ẩm thực của Việt Nam, với nhiều cách pha chế độc đáo như cà phê sữa đá và cà phê trứng.', 2.8010450000001583))*
**temp 1.0**:*('Một sự thật thú vị về Việt Nam là quốc gia này là nhà sản xuất hạt tiêu đen lớn nhất thế giới. Việt Nam chiếm khoảng 35-40% sản lượng hạt tiêu toàn cầu, với các vùng trồng chính tập trung ở các tỉnh như Đắk Lắk, Đắk Nông, và Bà Rịa - Vũng Tàu. Hạt tiêu Việt Nam nổi tiếng với chất lượng tốt và hương vị đặc trưng, là một mặt hàng xuất khẩu quan trọng, góp phần không nhỏ vào nền kinh tế nông nghiệp của đất nước.', 3.721108700003242)*
**tem 1.5**:*('Một sự thật thú vị về Việt Nam là nước này là một trong những quốc gia sản xuất và xuất khẩu cà phê lớn nhất thế giới, chỉ đứng sau Brazil. Hạt cà phê Robusta là loại cà phê chính được sản xuất ở Việt Nam, chiếm khoảng 97% sản lượng cà phê của đất nước. Ngành công nghiệp cà phê đóng góp đáng kể vào nền kinh tế Việt Nam và đã trở thành một phần không thể thiếu trong văn hóa địa phương, với cà phê sữa đá và cà phê trứng là những món thức uống đặc trưng mà du khách không thể bỏ qua khi ghé thăm.', 3.0602129999897443)*



**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Câu trả lời của bỞ độ nhạy thấp (0.0), mô hình chọn cách an toàn và dễ đoán nhất. Khi độ nhạy tăng lên, mô hình trở nên "nhạy bén" hơn với các xác suất từ vựng khác, tạo ra những câu trả lời đa dạng và linh hoạt hơn.n*

### Câu 1.2 — Chọn temperature cho sản phẩm
**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *('Khi cấu hình temperature cho một chatbot hỗ trợ khách hàng, việc chọn mức độ temperature phù hợp rất quan trọng để đảm bảo câutrả lời nhất quán, hữu ích và không gây nhầm lẫn. Temperature trong ngữ cảnh của mô hình ngôn ngữ ảnh hưởng đến mức độ sáng tạo và ngẫu nhiên của các phản hồi. Dưới đây là một số gợi ý:\n\n1. **Low Temperature (khoảng 0.2 - 0.3):**\n   - Đối với chatbot hỗ trợ khách hàng, nhiệt độ thấp thường được ưu tiên. Mức độ temperature thấp giúp đảm bảo rằng các phản hồi của chatbot sẽ nhất quán, rõ ràng và tập trung vào việc cung cấp thông tin chính xác và có cấu trúc. Điều này rất quan trọng để giải quyết các yêu cầu hoặc vấn đề của khách hàng một cách hiệu quả.\n\n2. **Medium Temperature (khoảng 0.4 - 0.6):**\n   - Có thể được sử dụng nếu muốn chatbot thêm một chút sáng tạo nhưng vẫn đảm bảo độ tin cậy. Mức nhiệt độ này có thể giúp chatbot cung cấp phản hồi thân thiện hơn mà không quá mạo hiểm hoặc đưa ra thông tin sai lệch', 4.710246200003894)*

### Câu 1.3 — Đánh đổi chi phí
Kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người gọi API 3 lần,
mỗi lần trung bình ~350 token đầu ra.

**Ước tính GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này? Nêu một
trường hợp GPT-4o xứng đáng với chi phí và một trường hợp nên dùng mini:**
> *('Để ước tính chi phí của việc sử dụng GPT-4o và GPT-4o-mini cho khối lượng công việc đã mô tả, chúng ta cần cân nhắc một số yếutố liên quan đến giá cả và hiệu suất. Mặc dù không có thông tin cụ thể về giá của các mô hình này (vì chi phí có thể thay đổi theo thời gian và từng dịch vụ), ta có thể dự đoán dựa trên mức giá trung bình hoặc xu hướng giá thường thấy trong lĩnh vực này.\n\nGiả sử:\n- GPT-4o có giá cao hơn GPT-4o-mini đáng kể vì nó là phiên bản đầy đủ, có khả năng mạnh mẽ hơn.\n- Số token xử lý trongngày: 10.000 người dùng x 3 lần gọi x 350 token = 10.500.000 token/ngày.\n\n### Ước tính chi phí:\n\n1. **GPT-4o:**\n   - Thườngsẽ có chi phí cao hơn do công suất lớn hơn, khả năng hiểu ngữ cảnh và sinh văn bản chất lượng cao hơn.\n   - Ví dụ giả định: nếuGPT-4o có giá $0.10 trên 1,000 token, tổng chi phí', 4.291291999979876)*

---

## Block 2 — System Prompt & Token (trả lời sau Checkpoint 2)

### Câu 2.1 — Sức mạnh của persona
Gọi `chat_with_system_prompt` hai lần với cùng câu hỏi
**"Giải thích blockchain là gì?"** nhưng hai system prompt khác nhau:
- "Bạn là giáo viên tiểu học, giải thích thật đơn giản cho trẻ 8 tuổi."
- "Bạn là chuyên gia tài chính, trả lời chuyên sâu bằng thuật ngữ kỹ thuật."

**Hai phản hồi khác nhau như thế nào (độ dài, từ vựng, ví dụ)? System prompt
ảnh hưởng đến hành vi model ra sao?** (3–4 câu)
> *Cau tra loi 1: Blockchain giống như một cuốn sổ tay kỹ thuật số, nơi chúng ta ghi lại mọi thứ rất rõ ràng và không thể xóa đi. Hãy tưởng tượng có mộtnhóm bạn cùng chơi một trò chơi, và mỗi lần một người ghi điểm thì tất cả các bạn đều ghi lại số điểm đó trong sổ tay của riêng mình. Điều đặc biệt ở đây là mọi cuốn sổ tay đều giống hệt nhau, và không ai có thể thay đổi điểm số ở trong sổ của mình mà không có sự đồng ý của tất cả mọi người.

Mỗi trang trong sổ tay (hay mỗi "khối" trong blockchain) có thông tin về điểm số trước đó. Nếu một trang mới được viết, nó sẽ kết nối chặt chẽ với trang trước. Điều này làm cho thông tin đã ghi lại rất an toàn và khó có thể bị thay đổi mà không ai hay biết.

Vì vậy, blockchain giúp chúng ta lưu giữ thông tin một cách công bằng và an toàn!

Cau tra loi 2: Blockchain là một cấu trúc dữ liệu phân tán và bất biến, hoạt động như một sổ cái kỹ thuật số, ghi lại các giao dịch trên nhiều máy tính trong một mạng lưới ngang hàng (peer-to-peer). Nó được thiết kế để đảm bảo tính minh bạch, bảo mật và không thể thay đổi của dữ liệu.*

### Câu 2.2 — tiktoken vs đếm từ
Chọn một đoạn văn tiếng Việt ~100 từ. So sánh số token theo `count_tokens`
(tiktoken) với ước lượng `số từ / 0.75` mà Part 1 đã dùng.

**Hai con số chênh nhau bao nhiêu phần trăm? Vì sao tiếng Việt thường tốn
nhiều token hơn tiếng Anh cùng độ dài?**
> *Mức chênh lệch giữa thực tế và ước lượng lên tới 66,6% ((235 - 141) / 141). Công thức / 0.75 chỉ chính xác với tiếng Anh; khi áp dụng cho tiếng Việt, số token thực tế thường cao gấp 1,5 đến 2 lần.*

---

## Block 3 — Streaming & Độ Bền (trả lời sau Checkpoint 3)

### Câu 3.1 — Trải nghiệm người dùng với streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì
non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Lựa chọn giữa streaming và non-streaming phụ thuộc chủ yếu vào việc hệ thống phục vụ người dùng trực tiếp hay xử lý dữ liệu ngầm. Streaming đặc biệt quan trọng đối với các giao diện chat thời gian thực hoặc các tác vụ tạo nội dung dài, giúp giảm thiểu độ trễ cảm nhận để người dùng có thể đọc ngay những từ đầu tiên và kịp thời ấn nút dừng nếu AI bắt đầu đi lạc đề. Ngược lại, non-streaming lại là phương pháp tối ưu cho các quy trình tự động ở phía backend, nơi hệ thống bắt buộc phải nhận được khối dữ liệu hoàn chỉnh (thường ở định dạng JSON), đợi trọn vẹn các tham số để thực thi lời gọi hàm (Function Calling), hoặc cần chạy toàn bộ văn bản đầu ra qua các bộ lọc kiểm duyệt an toàn trước khi chuyển sang bước xử lý tiếp theo.*

### Câu 3.2 — Vì sao backoff theo cấp số nhân?
**So với delay cố định (ví dụ luôn chờ 1 giây), exponential backoff có lợi
thế gì khi API bị quá tải? Điều gì xảy ra nếu hàng nghìn client cùng retry
với delay cố định giống nhau?**
> *So với độ trễ cố định, exponential backoff (thời gian chờ tăng theo cấp số nhân) giúp máy chủ đang quá tải có đủ khoảng nghỉ để phục hồi, giải phóng bộ nhớ và xử lý hàng đợi thay vì liên tục bị "dội bom" bằng các yêu cầu mới. Nếu hàng nghìn client cùng sử dụng một mức delay cố định, hệ thống sẽ phải đối mặt với hiệu ứng bầy đàn (Thundering Herd) — toàn bộ các request bị lỗi sẽ đồng loạt gửi yêu cầu lại vào cùng một tích tắc ở giây tiếp theo, tạo thành một cuộc tấn công DDoS tự phát lặp đi lặp lại khiến server liên tục sụp đổ mà không bao giờ có cơ hội ngóc đầu lên được.*

---

## Block 4 — Mini-Project (trả lời sau Checkpoint 4)

### Câu 4.1 — Thiết kế persona
**Bạn chọn persona gì cho trợ lý của mình? Viết lại system prompt đó và giải
thích 1–2 lựa chọn từ ngữ quan trọng trong prompt (ví dụ: vì sao yêu cầu
"trả lời ngắn gọn", vì sao chỉ định ngôn ngữ...):**
> *Tôi chọn persona là một cộng sự công nghệ thực tế với system prompt cốt lõi: "Bạn là một AI hỗ trợ trực diện, hãy trả lời ngay ở câu đầu tiên, loại bỏ hoàn toàn các cụm từ mào đầu rập khuôn và ưu tiên định dạng thông tin bằng gạch đầu dòng hoặc bảng biểu để tối ưu khả năng đọc lướt." Trong đó, yêu cầu "loại bỏ mào đầu" nhằm triệt tiêu các câu giao tiếp dư thừa của AI (như "Dưới đây là câu trả lời..."), giúp bạn nhận được giải pháp ngay lập tức để tiết kiệm thời gian. Bên cạnh đó, cụm từ "tối ưu khả năng đọc lướt" bắt buộc mô hình phải cấu trúc dữ liệu một cách khoa học và trực quan, ngăn chặn việc tạo ra những khối văn bản dày đặc (wall-of-text) gây mệt mỏi cho mắt khi bạn cần tra cứu nhanh thông tin.*

### Câu 4.2 — Hạn chế & cải thiện
**Trợ lý của bạn hiện có hạn chế lớn nhất là gì (ví dụ: history chỉ 3 lượt,
không có bộ nhớ dài hạn, không kiểm duyệt nội dung...)? Đề xuất một cải
thiện cụ thể và mô tả ngắn cách triển khai:**
> *Hạn chế lớn nhất của trợ lý hiện tại là thiếu bộ nhớ dài hạn xuyên suốt các phiên làm việc, khiến AI không thể tự động ghi nhớ sở thích cá nhân hay ngữ cảnh chuyên sâu từ những cuộc trò chuyện trong quá khứ. Để khắc phục, tôi đề xuất tích hợp một cơ sở dữ liệu vector (như Pinecone hoặc Qdrant) kết hợp với kỹ thuật RAG (Retrieval-Augmented Generation). Cụ thể, sau mỗi phiên hội thoại, hệ thống sẽ tự động tóm tắt và chuyển đổi các thông tin quan trọng của người dùng thành dữ liệu nhúng (embeddings) để lưu trữ; khi bắt đầu một chuỗi câu hỏi mới, AI sẽ tiến hành tìm kiếm ngữ nghĩa trong cơ sở dữ liệu này để trích xuất các "ký ức" liên quan nhất và âm thầm chèn vào system prompt, giúp duy trì tính cá nhân hóa và sự liền mạch mà không làm quá tải giới hạn token của cửa sổ ngữ cảnh.*

---

## Danh Sách Kiểm Tra Nộp Bài

- [ ] `python grade.py` — xem điểm tự động, mục tiêu ≥ 75/100
- [ ] Cả 4 checkpoint pytest đều pass
- [ ] Tất cả 9 câu trong file này đã được trả lời
- [ ] Đã copy bài làm vào folder `solution/`, push lên fork và dán link trên trang bài Lab ở VLearn trước 23:59 ngày 11/09/2026
