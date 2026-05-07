---
stepsCompleted:
  - step-01-init
  - step-02-discovery
  - step-02b-vision
  - step-02c-executive-summary
  - step-03-success
  - step-04-journeys
  - step-05-domain
  - step-06-innovation-skipped
  - step-07-project-type
  - step-08-scoping
  - step-09-functional
  - step-10-nonfunctional
  - step-11-polish
  - step-12-complete
  - step-e-01-discovery
  - step-e-02-review
  - step-e-03-edit
date: "2026-05-05"
inputDocuments:
  - path: "/Users/kdroid/Desktop/TTS-94962354-050526-1047-35.pdf"
    type: "service-description"
    title: "Mô tả_Mua thẻ cào"
  - path: "/Users/kdroid/Downloads/TK-74650736-220426-0854-267.pdf"
    type: "reference-brd"
    title: "BRD_Dự án website bán hàng - ưu tiên sản phẩm Data"
  - path: "/Users/kdroid/Downloads/Telegram Desktop/2. FTTH_ Internet truyền hình-v4-20260422_110707.pdf"
    type: "reference-business-flow"
    title: "FTTH/Internet truyền hình"
  - path: "https://www.figma.com/design/MvKWlDKG55tlppKWNTbTwr/-Web--D%E1%BB%8Bch-v%E1%BB%A5----Website-vtmoney.vn?node-id=5318-41390"
    type: "figma-design"
    title: "Website Nạp điện thoại/ Mua thẻ [04/2026]"
    fileKey: "MvKWlDKG55tlppKWNTbTwr"
    nodeId: "5318:41390"
documentCounts:
  productBriefs: 0
  research: 0
  brainstorming: 0
  projectDocs: 0
  userProvided: 4
classification:
  loaiDuAn: "Ứng dụng web giao dịch"
  linhVuc: "Thanh toán số kết hợp thương mại dịch vụ viễn thông trả trước"
  doPhucTap: "Cao"
  boiCanhDuAn: "Mở rộng kênh web trên nền tảng Viettel Money hiện hữu"
  nghiepVuChinh: "Mua mã thẻ cào trả trước qua website Viettel Money"
  nhanPhu:
    - "Mở rộng kênh từ app sang web"
    - "Dịch vụ hàng hóa số cần giao mã tức thời"
    - "Luồng thanh toán có trạng thái giao dịch"
    - "Trải nghiệm web responsive cho SEO, quảng cáo và webview"
    - "Có tra cứu lịch sử và hỗ trợ sau giao dịch"
  scopeGuard: "BRD cần bao phủ toàn bộ luồng mua, thanh toán, giao mã thẻ, trạng thái giao dịch, xử lý lỗi, đối soát, hỗ trợ khách hàng, kiểm soát rủi ro và điểm giống/khác so với luồng app hiện hữu."
vision:
  statement: "Viettel Money Web giúp khách hàng mua một hoặc nhiều thẻ cào trong vài bước, không cần đăng nhập hay tải app, với chiết khấu rõ ràng, lựa chọn mệnh giá linh hoạt, thanh toán thuận tiện và nhận mã thẻ/seri ngay sau thanh toán qua màn hình, SMS và email tùy chọn; đồng thời đảm bảo kiểm soát rủi ro, bảo mật mã thẻ và hỗ trợ tra cứu/xử lý sau giao dịch."
  differentiators:
    - "Không cần đăng nhập hoặc tải app."
    - "Có chiết khấu trực tiếp, hiển thị rõ trước khi thanh toán."
    - "Hỗ trợ mua nhiều thẻ, nhiều mệnh giá trong một giao dịch."
    - "Nhận mã thẻ/seri ngay trên màn hình thành công, qua SMS và email nếu khách hàng nhập email."
  businessGoal: "Tăng doanh số bán thẻ cào qua kênh website Viettel Money."
releaseMode: "phased"
workflowType: "prd"
workflow: "edit"
lastEdited: "2026-05-06"
editHistory:
  - date: "2026-05-06"
    changes: "Cập nhật PRD theo validation report: bổ sung NFR đo được, compliance/risk matrix, out-of-scope MVP, web performance/accessibility target, FR25 và frontmatter."
  - date: "2026-05-06"
    changes: "Điều chỉnh BRD dễ đọc hơn cho stakeholder và bổ sung yêu cầu kế thừa từ input mẫu Data, FTTH và mô tả dịch vụ Mua thẻ cào."
---

# BRD - Tài liệu yêu cầu nghiệp vụ Mua thẻ cào trên viettelmoney.vn

**Người lập:** hapu
**Ngày:** 2026-05-05

## Tóm tắt điều hành

Dự án triển khai dịch vụ Mua thẻ cào trên website `viettelmoney.vn`, cho phép khách hàng mua một hoặc nhiều mã thẻ cào trong vài bước mà không cần đăng nhập hoặc tải app Viettel Money. Dịch vụ hướng tới kênh mua nhanh trên web, phục vụ khách hàng có nhu cầu mua thẻ tức thời từ trình duyệt, traffic SEO/quảng cáo, webview hoặc các điểm chạm số khác.

Mục tiêu kinh doanh chính là tăng doanh số bán thẻ cào qua kênh website Viettel Money bằng cách giảm rào cản truy cập, tối ưu tỷ lệ hoàn tất giao dịch và mở rộng tệp khách hàng ngoài app. Khách hàng có thể chọn nhà mạng, mệnh giá, số lượng thẻ, xem chiết khấu trực tiếp trước thanh toán và nhận mã thẻ/seri ngay sau khi giao dịch thành công.

Sau thanh toán, hệ thống hiển thị mã thẻ/seri trên màn hình giao dịch thành công, gửi mã qua SMS và gửi thêm qua email nếu khách hàng nhập email. Luồng nghiệp vụ cần đảm bảo xử lý đầy đủ các trạng thái thanh toán, cấp phát mã, gửi thông báo, tra cứu lịch sử, hỗ trợ sau giao dịch, bảo mật mã thẻ và đối soát vận hành.

### Điểm khác biệt

Điểm khác biệt của dịch vụ là mô hình mua thẻ cào nhanh trên web, không yêu cầu đăng nhập hoặc cài app nhưng vẫn giữ được các lợi thế của hệ sinh thái Viettel Money: thanh toán số, chiết khấu rõ ràng, giao mã tức thời và hỗ trợ tra cứu sau giao dịch.

Dịch vụ không chỉ là một trang giới thiệu hoặc form mua hàng đơn giản. Đây là luồng giao dịch có hàng hóa số nhạy cảm, trong đó mã thẻ/seri cần được cấp phát chính xác, hiển thị an toàn và gửi đến đúng kênh nhận sau thanh toán. Khả năng mua nhiều thẻ, nhiều mệnh giá trong một giao dịch giúp tăng giá trị đơn hàng và phục vụ tốt hơn các nhu cầu mua hộ, mua nhiều hoặc mua theo ngân sách cụ thể.

Insight cốt lõi là khách hàng mua thẻ cào thường cần tốc độ, giá rõ ràng, ưu đãi trực tiếp và nhận mã chắc chắn ngay sau thanh toán. Nếu website giảm được bước đăng nhập/tải app, hiển thị chiết khấu minh bạch và xử lý tốt phần cấp phát mã, kênh web có thể chuyển đổi traffic bên ngoài thành doanh số hiệu quả.

### Phân loại dự án

Dự án thuộc nhóm **ứng dụng web giao dịch**, triển khai trong lĩnh vực **thanh toán số kết hợp thương mại dịch vụ viễn thông trả trước**. Đây là dự án **mở rộng kênh web trên nền tảng Viettel Money hiện hữu**, không phải sản phẩm độc lập.

Độ phức tạp được xác định là **cao** do có các yếu tố: giao dịch thanh toán, cấp phát hàng hóa số, bảo mật mã thẻ/seri, mua nhiều thẻ trong một đơn, trạng thái giao dịch bất đồng bộ, gửi SMS/email, lịch sử giao dịch, xử lý lỗi/time-out, chống lạm dụng chiết khấu và đối soát giữa các hệ thống liên quan.

BRD cần bao phủ toàn bộ luồng mua, thanh toán, giao mã thẻ, trạng thái giao dịch, xử lý lỗi, đối soát, hỗ trợ khách hàng, kiểm soát rủi ro và điểm giống/khác so với luồng app Viettel Money hiện hữu.

## Tiêu chí thành công

### Thành công phía khách hàng

Khách hàng có thể hoàn tất mua thẻ cào trên `viettelmoney.vn` trong luồng web ngắn, không cần đăng nhập hoặc tải app. Trải nghiệm được coi là thành công khi khách chọn được nhà mạng, mệnh giá, số lượng thẻ, nhìn thấy chiết khấu/tổng tiền trước thanh toán và nhận mã thẻ/seri ngay sau khi thanh toán thành công.

Tiêu chí thành công phía khách hàng:

- Khách hàng nhận được mã thẻ/seri trên màn hình giao dịch thành công trong vòng dưới 2 giây sau khi thanh toán thành công.
- Khách hàng nhận thêm mã qua SMS; email được gửi nếu khách hàng nhập email.
- Khách hàng có thể mua nhiều thẻ trong cùng một giao dịch.
- Khách hàng nhìn thấy rõ chiết khấu, tổng tiền thanh toán và thông tin từng thẻ trước khi xác nhận.
- Khách hàng có thể tra cứu hoặc được hỗ trợ xử lý khi giao dịch lỗi, timeout, đã thanh toán nhưng chưa nhận mã.

### Thành công kinh doanh

Mục tiêu kinh doanh chính của MVP là tăng doanh số bán thẻ cào qua kênh website Viettel Money. Thành công được đo bằng doanh số, số lượng giao dịch, tỷ lệ chuyển đổi và khả năng giảm rớt đơn trong luồng mua/thanh toán.

Chỉ tiêu MVP:

- Doanh số mục tiêu: 200 triệu đồng/tháng.
- Số giao dịch mục tiêu: khoảng 1.000 giao dịch/ngày.
- Visit-to-purchase CR: 20-30% trong giai đoạn MVP, tính bằng số đơn hàng thành công / số lượt truy cập trang dịch vụ.
- Checkout completion rate: >= 95%, tính bằng số thanh toán thành công / số giao dịch đã bắt đầu thanh toán.
- Cart/checkout abandonment rate được theo dõi theo từng bước: chọn thẻ, nhập thông tin nhận mã, xác nhận giao dịch, chọn phương thức thanh toán, thanh toán.

### Thành công vận hành

Dịch vụ cần đảm bảo luồng thanh toán và cấp phát mã thẻ hoạt động ổn định, có trạng thái rõ ràng, hỗ trợ vận hành/đối soát và bảo mật dữ liệu mã thẻ.

Tiêu chí vận hành:

- Thời gian cấp và hiển thị mã thẻ sau thanh toán thành công: dưới 2 giây.
- Fulfillment success rate: >= 99%, tính bằng số giao dịch nhận mã thành công / số giao dịch thanh toán thành công.
- Tỷ lệ gửi SMS thành công mục tiêu: >= 98% trong các giao dịch đã cấp mã thành công, đo theo trạng thái trả về từ kênh SMS.
- Tỷ lệ gửi email thành công mục tiêu: >= 95% với nhóm giao dịch có email hợp lệ, đo theo trạng thái trả về từ kênh email.
- Trang dịch vụ đáp ứng chuẩn performance Viettel Money Web; nếu chưa có chuẩn nội bộ cụ thể, mục tiêu MVP là LCP <= 2,5 giây ở P75 trên mobile và webview phổ biến.
- Hệ thống ghi nhận riêng trạng thái thanh toán, trạng thái cấp mã thẻ và trạng thái gửi SMS/email.
- Có cơ chế xử lý các trường hợp: thanh toán thất bại, thanh toán timeout, thanh toán thành công nhưng cấp mã thất bại, cấp mã thành công nhưng gửi SMS/email thất bại.
- Mã thẻ/seri được bảo vệ trong hiển thị, lưu trữ, log, analytics và lịch sử giao dịch.
- Có dữ liệu phục vụ CSKH/đối soát: mã giao dịch, thời gian giao dịch, nhà mạng, mệnh giá, số lượng, trạng thái thanh toán, trạng thái cấp mã, trạng thái gửi SMS/email.

### Chỉ số đo lường

Các chỉ số cần đo sau khi triển khai MVP:

- Doanh số theo ngày/tháng.
- Số giao dịch thành công theo ngày.
- Số lượng thẻ bán ra theo nhà mạng, mệnh giá và số lượng thẻ/giao dịch.
- Visit-to-purchase CR.
- Checkout completion rate.
- Fulfillment success rate.
- Thời gian trung bình từ thanh toán thành công đến hiển thị mã.
- Tỷ lệ gửi SMS thành công.
- Tỷ lệ gửi email thành công với giao dịch có email.
- LCP/P75 của trang dịch vụ trên mobile web và webview.
- Tỷ lệ tương tác chọn nhà mạng/mệnh giá/số lượng phản hồi dưới 300ms ở P95.
- Tỷ lệ giao dịch cần CSKH hỗ trợ.
- Tỷ lệ lỗi “đã thanh toán nhưng chưa nhận mã”.
- Tỷ lệ rớt đơn theo từng bước trong funnel.

## Phạm vi sản phẩm

### MVP

MVP cần chứng minh được luồng mua thẻ cào nhanh trên web, không đăng nhập, có chiết khấu và nhận mã tức thời sau thanh toán.

Phạm vi MVP:

- Trang dịch vụ Mua thẻ cào trên `viettelmoney.vn`.
- Không yêu cầu khách hàng đăng nhập hoặc tải app.
- Chọn nhà mạng, mệnh giá và số lượng thẻ.
- Hỗ trợ mua nhiều thẻ trong một giao dịch.
- Hiển thị chiết khấu và tổng tiền trước thanh toán.
- Nhập số điện thoại nhận SMS.
- Nhập email tùy chọn để nhận thêm mã thẻ qua email.
- Xác nhận thông tin giao dịch trước thanh toán.
- Tích hợp cổng/thành phần thanh toán trên web.
- Hiển thị kết quả giao dịch thành công/thất bại/timeout.
- Hiển thị mã thẻ/seri ngay trên màn hình thành công.
- Gửi mã thẻ/seri qua SMS.
- Gửi mã thẻ/seri qua email nếu khách hàng nhập email.
- Ghi nhận lịch sử/trạng thái giao dịch để hỗ trợ tra cứu, CSKH và đối soát.
- Theo dõi funnel và các chỉ số thành công đã nêu.

Các giới hạn cho khách không đăng nhập như số lượng thẻ/lần, giá trị đơn tối đa, tần suất mua/ngày cần được chốt trong giai đoạn thiết kế chi tiết hoặc theo chính sách Risk/Fraud.

### Ngoài phạm vi MVP

Các hạng mục sau không thuộc phạm vi MVP, trừ khi được phê duyệt bổ sung trong kế hoạch delivery:

- Bắt buộc khách hàng đăng nhập, tải app hoặc chuyển toàn bộ luồng mua sang app.
- Tài khoản khách hàng đầy đủ trên web để xem lịch sử mua dài hạn sau đăng nhập.
- Hoàn tiền tự động nâng cao cho mọi trường hợp lỗi; MVP chỉ cần ghi nhận trạng thái đủ để xử lý theo chính sách vận hành hiện hành.
- Loyalty, tích điểm, phân hạng khách hàng hoặc cá nhân hóa ưu đãi theo hồ sơ khách hàng.
- Quản trị kho mã thẻ nâng cao ngoài các năng lực cần thiết để cấp phát đúng, không trùng và có trạng thái giao dịch.
- Remarketing hoặc sử dụng số điện thoại/email cho mục đích ngoài giao dịch nếu chưa được chính sách nội bộ phê duyệt.
- Tối ưu SEO nội dung dài hạn như cụm landing page, blog hoặc hệ thống nội dung mở rộng.

### Tính năng tăng trưởng sau MVP

Các tính năng tăng trưởng sau MVP:

- Cấu hình campaign chiết khấu linh hoạt theo nhà mạng, mệnh giá, kênh traffic hoặc thời gian.
- Tối ưu funnel theo dữ liệu rớt đơn thực tế.
- Gợi ý mệnh giá phổ biến hoặc combo nhiều thẻ.
- Nâng cấp lịch sử giao dịch/tra cứu giao dịch cho khách không đăng nhập bằng số điện thoại, mã giao dịch hoặc OTP.
- Mở rộng phương thức thanh toán nếu MVP chưa hỗ trợ đầy đủ.
- Tối ưu SEO/landing content theo chiến dịch Kinh doanh/PO.
- Cơ chế remarketing với nhóm khách nhập email/số điện thoại, nếu được pháp chế/risk phê duyệt.

### Tầm nhìn tương lai

Phiên bản tương lai có thể phát triển thành kênh web bán dịch vụ viễn thông trả trước đầy đủ trên Viettel Money, bao gồm thẻ cào, nạp điện thoại, data, gói dịch vụ viễn thông và các sản phẩm số liên quan. Kênh web cần duy trì ưu thế mua nhanh, không rào cản, có ưu đãi rõ ràng, nhận hàng số tức thời và có năng lực vận hành/đối soát đủ tin cậy để mở rộng quy mô doanh số.

## Hành trình người dùng

### Hành trình 1: Khách hàng mua 1 thẻ thành công

Anh Minh cần mua nhanh một thẻ cào để nạp cho người thân. Anh không muốn tải app hoặc đăng nhập vì đang dùng trình duyệt trên điện thoại. Anh truy cập trang Mua thẻ cào trên `viettelmoney.vn`, thấy ngay các lựa chọn nhà mạng, mệnh giá, chiết khấu và nút mua.

Anh chọn nhà mạng, chọn một mệnh giá, để số lượng là 1, nhập số điện thoại nhận SMS và có thể bỏ qua email nếu không cần. Trước khi thanh toán, hệ thống hiển thị rõ thông tin giao dịch: nhà mạng, mệnh giá, số lượng, chiết khấu, tổng tiền cần thanh toán và số điện thoại nhận mã.

Anh xác nhận giao dịch, chọn phương thức thanh toán và hoàn tất thanh toán. Trong vòng dưới 2 giây sau khi thanh toán thành công, màn hình kết quả hiển thị mã thẻ/seri. Đồng thời hệ thống gửi mã qua SMS đến số điện thoại đã nhập. Anh có thể sao chép mã hoặc lưu lại thông tin giao dịch.

Giá trị sản phẩm xuất hiện ở khoảnh khắc anh nhận mã ngay mà không phải tải app, đăng nhập hoặc chờ xử lý thủ công.

### Hành trình 2: Khách hàng mua nhiều thẻ thành công

Chị Hương cần mua nhiều thẻ cào để gửi cho nhân viên, đại lý nhỏ hoặc người thân. Nếu mua từng thẻ riêng lẻ, chị phải lặp lại thanh toán nhiều lần và khó kiểm soát tổng tiền. Chị truy cập trang Mua thẻ cào trên `viettelmoney.vn` để mua nhiều thẻ trong một giao dịch.

Chị chọn nhà mạng, chọn mệnh giá, tăng số lượng thẻ hoặc thêm nhiều mệnh giá theo nhu cầu. Hệ thống hiển thị danh sách thẻ trong đơn, số lượng từng mệnh giá, chiết khấu áp dụng và tổng tiền sau chiết khấu. Nếu chị nhập email, hệ thống ghi nhận email để gửi lại danh sách mã sau thanh toán.

Chị xác nhận đơn hàng và thanh toán một lần. Sau khi thanh toán thành công, hệ thống cấp phát đủ danh sách mã thẻ/seri tương ứng với số lượng đã mua và hiển thị ngay trên màn hình thành công. SMS được gửi theo cơ chế đã cấu hình; email nếu có sẽ chứa danh sách mã hoặc thông tin nhận mã theo chính sách bảo mật.

Điểm thành công của journey này là khách hàng mua được nhiều thẻ trong một lần thanh toán, nhìn rõ tổng tiền/chiết khấu và nhận đủ danh sách mã ngay sau giao dịch.

### Hành trình 3: Khách hàng gặp lỗi sau thanh toán

Anh Nam thanh toán mua thẻ cào trên web nhưng sau khi quay lại từ cổng thanh toán, màn hình bị timeout hoặc chưa hiển thị mã. Anh lo rằng tiền đã bị trừ nhưng chưa nhận được thẻ.

Hệ thống cần hiển thị trạng thái rõ ràng thay vì chỉ báo lỗi chung. Nếu thanh toán chưa xác nhận thành công, hệ thống thông báo giao dịch đang xử lý hoặc thất bại. Nếu thanh toán đã thành công nhưng cấp mã đang chờ xử lý, hệ thống thông báo trạng thái chờ cấp mã và hướng dẫn khách kiểm tra SMS/email hoặc liên hệ CSKH với mã giao dịch.

Nếu SMS/email chậm, khách vẫn có thể dựa vào màn hình kết quả hoặc mã giao dịch để yêu cầu hỗ trợ. Nếu mã đã cấp thành công nhưng kênh gửi thất bại, CSKH/Vận hành có thể tra cứu trạng thái và hỗ trợ theo quy trình.

Journey này đảm bảo khách không bị bỏ rơi trong các tình huống nhạy cảm như đã thanh toán nhưng chưa nhận mã, timeout, gửi SMS/email lỗi hoặc cần xem lại thông tin giao dịch.

### Hành trình 4: CSKH/Vận hành tra cứu giao dịch

Một khách hàng liên hệ CSKH vì đã thanh toán nhưng chưa nhận được mã thẻ qua SMS. Nhân viên CSKH cần nhanh chóng xác định giao dịch có tồn tại không, thanh toán đã thành công chưa, mã thẻ đã được cấp chưa và SMS/email đã gửi thành công hay thất bại.

Nhân viên tra cứu theo một hoặc nhiều thông tin: mã giao dịch, số điện thoại nhận SMS, email, thời gian giao dịch, nhà mạng, mệnh giá hoặc số tiền. Hệ thống hiển thị trạng thái thanh toán, trạng thái cấp mã, trạng thái gửi SMS/email, số lượng thẻ trong đơn, mã lỗi nếu có và lịch sử xử lý.

Nếu thanh toán thành công và mã đã cấp, CSKH hướng dẫn khách kiểm tra lại kênh nhận hoặc thực hiện quy trình hỗ trợ phù hợp theo chính sách bảo mật. Nếu thanh toán thành công nhưng cấp mã thất bại, CSKH chuyển xử lý vận hành/đối soát. Nếu thanh toán thất bại hoặc timeout, CSKH giải thích trạng thái và hướng dẫn khách theo quy trình hoàn/hủy nếu có.

Journey này cho thấy hệ thống cần dữ liệu trạng thái đủ chi tiết để giảm thời gian xử lý khiếu nại và tránh trả lời chung chung cho khách.

### Hành trình 5: Kinh doanh/PO theo dõi doanh số và hiệu quả dịch vụ

Hằng ngày hoặc theo từng chiến dịch, đội Kinh doanh/PO cần theo dõi hiệu quả dịch vụ Mua thẻ cào trên website Viettel Money. Mục tiêu chính là kiểm tra doanh số, số lượng giao dịch, số lượng thẻ bán ra, mệnh giá bán chạy, nhà mạng bán chạy, tỷ lệ chuyển đổi, tỷ lệ rớt đơn trong funnel và hiệu quả theo từng nguồn traffic/quảng cáo.

Kinh doanh/PO truy xuất báo cáo theo ngày, chiến dịch, nhà mạng, mệnh giá, số lượng thẻ/giao dịch, mức chiết khấu, nguồn traffic và trạng thái giao dịch. Hệ thống cần hiển thị các chỉ số chính như doanh số, số giao dịch thành công, số lượng thẻ bán ra, Visit-to-purchase CR, Checkout completion rate, tỷ lệ thanh toán thành công, tỷ lệ cấp mã thành công và tỷ lệ lỗi cần CSKH hỗ trợ.

Khi phát hiện doanh số thấp, tỷ lệ rớt đơn cao hoặc một nhà mạng/mệnh giá/nguồn traffic có hiệu quả kém, Kinh doanh/PO cần dữ liệu đủ chi tiết để điều chỉnh ads, chiết khấu, nội dung hiển thị, mệnh giá ưu tiên hoặc đề xuất tối ưu luồng mua.

Journey này tạo yêu cầu về dashboard/báo cáo kinh doanh, tracking funnel, tracking theo nguồn traffic/quảng cáo, phân tích doanh số theo nhà mạng/mệnh giá/chiến dịch và dữ liệu đủ chi tiết để PO ra quyết định tối ưu sản phẩm.

### Hành trình 6: Kinh doanh/PO cấu hình dịch vụ và chiến dịch

Đội Kinh doanh/PO cần vận hành dịch vụ theo mục tiêu kinh doanh và từng chiến dịch. Họ cần cấu hình nhà mạng được bán, mệnh giá hiển thị, mức chiết khấu, nội dung hiển thị, nguồn traffic/chiến dịch và có thể theo dõi hiệu quả bán hàng.

Người vận hành cấu hình danh sách nhà mạng, mệnh giá, trạng thái bật/tắt dịch vụ, mức chiết khấu theo chính sách và nội dung liên quan trên trang dịch vụ. Trong chiến dịch, họ cần theo dõi doanh số, số giao dịch, tỷ lệ chuyển đổi, mệnh giá bán chạy và tỷ lệ rớt đơn để đề xuất tối ưu.

Nếu có thay đổi chính sách chiết khấu hoặc tạm dừng nhà mạng/mệnh giá, người vận hành cần cập nhật cấu hình mà không ảnh hưởng đến các giao dịch đã phát sinh. Các thay đổi quan trọng cần có ghi nhận lịch sử cấu hình để phục vụ kiểm soát nội bộ.

Journey này cho thấy dịch vụ cần khả năng cấu hình linh hoạt, theo dõi hiệu quả và kiểm soát thay đổi.

### Tổng hợp yêu cầu từ hành trình

Các journey trên cho thấy hệ thống cần các nhóm năng lực chính:

- Luồng mua thẻ không đăng nhập trên web.
- Chọn nhà mạng, mệnh giá, số lượng và hỗ trợ mua nhiều thẻ trong một giao dịch.
- Hiển thị chiết khấu, tổng tiền và thông tin xác nhận trước thanh toán.
- Nhập số điện thoại nhận SMS và email tùy chọn.
- Tích hợp thanh toán web và xử lý trạng thái thành công/thất bại/timeout.
- Cấp phát mã thẻ/seri trong vòng dưới 2 giây sau thanh toán thành công.
- Hiển thị mã thẻ/seri trên màn hình thành công.
- Gửi mã qua SMS và email nếu có.
- Theo dõi trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email riêng biệt.
- Cơ chế xử lý lỗi sau thanh toán, đặc biệt trường hợp đã thanh toán nhưng chưa nhận mã.
- Công cụ/dữ liệu tra cứu cho CSKH và vận hành.
- Báo cáo/dashboards cho Kinh doanh và PO theo dõi doanh số, giao dịch, số lượng thẻ bán ra, hiệu quả chiết khấu, funnel chuyển đổi, nguồn traffic/quảng cáo và lỗi ảnh hưởng đến doanh thu.
- Cấu hình nhà mạng, mệnh giá, chiết khấu, bật/tắt dịch vụ, chiến dịch, nguồn traffic và nội dung hiển thị.
- Ghi nhận log/trạng thái đủ chi tiết để hỗ trợ khiếu nại, vận hành và kiểm soát nội bộ.

## Yêu cầu nghiệp vụ đặc thù

### Tuân thủ và quy định

Dịch vụ Mua thẻ cào trên `viettelmoney.vn` là luồng giao dịch thanh toán số có phát sinh hàng hóa số là mã thẻ/seri. BRD cần yêu cầu hệ thống tuân thủ các quy định, chính sách nội bộ và quy trình vận hành hiện hành của Viettel Money đối với giao dịch thanh toán, bảo mật dữ liệu khách hàng, bảo vệ dữ liệu mã thẻ và xử lý khiếu nại sau giao dịch.

Các yêu cầu chính:

- Không cấp mã thẻ nếu giao dịch thanh toán chưa được xác nhận thành công.
- Giao dịch phải có mã giao dịch duy nhất để phục vụ tra cứu, CSKH, vận hành và đối soát.
- Các thay đổi cấu hình quan trọng như nhà mạng, mệnh giá, chiết khấu, bật/tắt dịch vụ cần được ghi nhận để phục vụ kiểm soát nội bộ.
- Các thông tin liên hệ khách hàng như số điện thoại và email chỉ được sử dụng cho mục đích gửi mã, hỗ trợ giao dịch và các mục đích khác nếu được chính sách nội bộ cho phép.
- Quy trình xử lý lỗi, hoàn/hủy hoặc hỗ trợ sau thanh toán cần tuân thủ chính sách vận hành hiện hành của Viettel Money.

### Ma trận tuân thủ, dữ liệu và kiểm soát

| Nhóm kiểm soát | Yêu cầu nghiệp vụ | Chủ trì xác nhận | Tiêu chí nghiệm thu MVP |
|---|---|---|---|
| Biên thanh toán/CTT | Giao dịch chỉ được cấp mã sau khi CTT/cổng thanh toán xác nhận thanh toán thành công. | PO, Đội phát triển, Vận hành thanh toán | 100% giao dịch cấp mã có trạng thái thanh toán thành công; không có giao dịch cấp mã khi thanh toán thất bại/timeout/chưa xác nhận. |
| Audit trail giao dịch | Lưu mã giao dịch, trạng thái thanh toán, trạng thái cấp mã, trạng thái gửi SMS/email, thời gian và mã lỗi nếu có. | PO, CSKH/Vận hành | 100% giao dịch có mã giao dịch duy nhất và chuỗi trạng thái đủ để tra cứu/đối soát. |
| Quyền truy cập CSKH/Vận hành | Dữ liệu tra cứu, mã thẻ/seri và lịch sử xử lý chỉ hiển thị theo quyền được cấp. | PO, CSKH/Vận hành, An toàn thông tin | Mọi lượt tra cứu dữ liệu nhạy cảm có người dùng, thời gian, lý do/nguồn thao tác và được ghi log kiểm soát. |
| Bảo vệ mã thẻ/seri | Không đưa mã thẻ/seri vào log, GA, Adjust, analytics hoặc công cụ ghi nhận hành vi. | Đội phát triển, An toàn thông tin | Kiểm thử tracking/log không phát hiện mã thẻ/seri ở event, URL, request tracking hoặc log ứng dụng. |
| Lưu trữ và masking | Mã thẻ/seri, số điện thoại và email được lưu, hiển thị, che/mask và tra cứu theo chính sách nội bộ. | PO, An toàn thông tin, Pháp chế/Vận hành | CSKH chỉ xem dữ liệu phù hợp vai trò; màn hình tra cứu áp dụng masking hoặc cơ chế hiển thị theo quyền. |
| Guest checkout Risk/Fraud | Có khả năng áp dụng giới hạn số lượng thẻ, giá trị đơn, tần suất mua và rule theo nguồn traffic khi chính sách Risk/Fraud được chốt. | Risk/Fraud, PO, Kinh doanh | MVP ghi nhận đủ dữ liệu để bật giới hạn; giới hạn cụ thể được cấu hình/chốt trước go-live. |
| Khiếu nại và xử lý sau giao dịch | Có dữ liệu phục vụ xử lý trường hợp đã thanh toán nhưng chưa nhận mã, cấp mã một phần, gửi SMS/email lỗi. | CSKH/Vận hành, PO | CSKH tra cứu được giao dịch theo mã giao dịch/số điện thoại/email và thấy trạng thái thanh toán/cấp mã/gửi thông báo. |

### Quy tắc trạng thái và cấp mã

Dịch vụ cần quản lý rõ ba nhóm trạng thái: thanh toán, cấp mã thẻ và gửi SMS/email. Việc tách trạng thái giúp CSKH, Vận hành và PO biết chính xác giao dịch đang vướng ở bước nào, thay vì chỉ nhìn thấy một trạng thái lỗi chung.

Các trạng thái tối thiểu cần được ghi nhận:

- Giao dịch được tạo.
- Chờ thanh toán.
- Thanh toán thành công.
- Thanh toán thất bại.
- Thanh toán timeout.
- Đang cấp mã thẻ.
- Cấp mã thẻ thành công.
- Cấp mã thẻ thất bại.
- Gửi SMS thành công/thất bại.
- Gửi email thành công/thất bại nếu khách hàng nhập email.

Quy tắc nghiệp vụ cần đảm bảo:

- Mã thẻ/seri phải được cấp phát đủ số lượng theo đơn hàng đã thanh toán.
- Không được cấp trùng mã thẻ.
- Với giao dịch mua nhiều thẻ, hệ thống cần xử lý rõ trường hợp cấp mã một phần hoặc lỗi cấp mã.
- Thời gian cấp và hiển thị mã thẻ sau thanh toán thành công phải dưới 2 giây theo mục tiêu MVP.
- Mã thẻ/seri không được lộ trong log, analytics, tracking hoặc các công cụ ghi nhận hành vi người dùng.
- Cần có cơ chế bảo vệ mã thẻ khi hiển thị trên màn hình thành công, khi gửi SMS/email và khi tra cứu lại.
- Vì khách hàng không đăng nhập, hệ thống cần lưu đủ thông tin giao dịch để hỗ trợ tra cứu sau giao dịch: mã giao dịch, số điện thoại nhận SMS, email nếu có, thời gian, nhà mạng, mệnh giá, số lượng, trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email.
- Các giới hạn giao dịch cho khách không đăng nhập như số lượng thẻ/lần, giá trị đơn tối đa, tần suất mua/ngày chưa được chốt và cần được xác định trong thiết kế chi tiết theo chính sách Risk/Fraud.

### Yêu cầu kế thừa từ input mẫu

BRD cần kế thừa các điểm đã có trong mô tả dịch vụ Mua thẻ cào hiện hữu và tài liệu mẫu Data/FTTH để đội sản phẩm, UX và phát triển dễ đối chiếu:

- Trang Mua thẻ cào cần có cấu trúc gần với các dịch vụ viễn thông hiện hữu trên Viettel Money Web: chọn dịch vụ, chọn nhà mạng, chọn mệnh giá/số lượng, xác nhận giao dịch, thanh toán và xem kết quả.
- Danh sách nhà mạng hiển thị logo và tên nhà mạng; nếu chính sách kinh doanh cho phép, Viettel có thể là nhà mạng được chọn mặc định.
- Danh sách mệnh giá trả về theo từng nhà mạng; nếu cần giá trị mặc định để giảm thao tác, mệnh giá 50.000 đồng có thể là lựa chọn mặc định theo input sản phẩm hiện hữu.
- Mệnh giá cần hiển thị kèm chiết khấu/ưu đãi tương ứng để khách nhìn thấy lợi ích trước khi thanh toán.
- Màn xác nhận giao dịch cần dùng cấu trúc chung của các dịch vụ core payment, chỉ thay phần thông tin dịch vụ: dịch vụ Mua thẻ cào, nhà mạng, số điện thoại nhận mã, mệnh giá, số lượng, chiết khấu và tổng tiền.
- Màn kết quả giao dịch cần dùng cấu trúc chung của các dịch vụ core payment, bổ sung block hiển thị thẻ cào gồm logo/tên nhà mạng, mệnh giá, số seri, mã thẻ và mã giao dịch.
- Với thẻ Viettel, nếu hệ thống hiện hữu hỗ trợ, có thể hiển thị hành động “Nạp ngay” hoặc hướng dẫn nạp thẻ phù hợp; tính năng này không được làm chậm việc hiển thị mã thẻ sau thanh toán.
- Nếu có khu vực “Thẻ cào đã mua” hoặc tra cứu giao dịch sau mua, danh sách cần hiển thị tối thiểu nhà mạng, mệnh giá, trạng thái giao dịch và thời gian giao dịch; quyền xem lại mã thẻ/seri cần tuân thủ chính sách bảo mật.
- Các form nhập liệu cần có hint text, kiểm tra định dạng và lỗi inline tương tự các màn hình mẫu FTTH; lỗi cần nói rõ khách phải sửa gì.
- Các thành phần điều hướng như menu dịch vụ, tab dịch vụ, dropdown nhà mạng hoặc khu vực hướng dẫn cần kế thừa pattern hiện hữu của Viettel Money Web nếu phù hợp.

### Yêu cầu phối hợp hệ thống

Dịch vụ cần tích hợp với các hệ thống/thành phần hiện hữu của Viettel Money Web và các hệ thống liên quan đến thanh toán, cấp phát mã, gửi thông báo, CSKH và báo cáo.

Các nhóm tích hợp cần xem xét:

- Tích hợp cổng/thành phần thanh toán web.
- Tích hợp hệ thống cung cấp danh sách nhà mạng, mệnh giá, chiết khấu và trạng thái bật/tắt dịch vụ.
- Tích hợp hệ thống cấp phát mã thẻ/seri.
- Tích hợp SMS để gửi mã thẻ sau giao dịch.
- Tích hợp email nếu khách hàng nhập email.
- Tích hợp dữ liệu tra cứu cho CSKH/Vận hành.
- Tích hợp báo cáo/dashboard cho Kinh doanh/PO theo dõi doanh số, số giao dịch, số lượng thẻ bán ra, nguồn traffic/quảng cáo, funnel chuyển đổi và lỗi ảnh hưởng doanh thu.

### Kiểm soát rủi ro

Các rủi ro domain cần được kiểm soát trong thiết kế nghiệp vụ và vận hành:

- **Lạm dụng chiết khấu:** cần theo dõi tần suất mua, số lượng thẻ, giá trị đơn và nguồn traffic để phát hiện hành vi bất thường.
- **Mua số lượng lớn không đăng nhập:** cần xác định giới hạn giao dịch phù hợp trong thiết kế chi tiết.
- **Thanh toán thành công nhưng cấp mã lỗi:** cần có trạng thái riêng, cách xử lý lại/xử lý vận hành và hướng dẫn CSKH.
- **Cấp mã thành công nhưng gửi SMS/email lỗi:** màn hình thành công vẫn là kênh hiển thị chính; trạng thái gửi thông báo cần được ghi nhận để hỗ trợ tra cứu.
- **Timeout khi phản hồi thanh toán hoặc cấp mã chậm:** cần có cơ chế kiểm tra lại trạng thái, không tự động cấp mã khi chưa xác nhận thanh toán thành công.
- **Khách nhập sai số điện thoại/email:** cần hiển thị xác nhận thông tin trước thanh toán và có quy trình hỗ trợ phù hợp sau giao dịch.
- **Lộ mã thẻ/seri:** cần kiểm soát hiển thị, lưu trữ, log, analytics và quyền truy cập khi tra cứu lại.

## Yêu cầu đặc thù cho ứng dụng web

### Tổng quan loại dự án

Dịch vụ Mua thẻ cào trên `viettelmoney.vn` là ứng dụng web giao dịch nằm trong hệ sinh thái Viettel Money Web. Dịch vụ cần ưu tiên trải nghiệm mobile web và webview vì khách hàng có thể đến từ quảng cáo, tìm kiếm, mạng xã hội, tin nhắn hoặc các điểm chạm số khác. Desktop và tablet vẫn cần được hỗ trợ để đảm bảo trải nghiệm đầy đủ trên các thiết bị phổ biến.

Dịch vụ không được thiết kế như một website độc lập. Các màn hình, luồng thanh toán và thành phần giao diện cần kế thừa nền tảng, design system và cổng thanh toán dùng chung của Viettel Money.

### Nguyên tắc kế thừa nền tảng

Dịch vụ cần bám nền tảng Viettel Money Web hiện hữu. BRD không quyết định cách xây dựng chi tiết, nhưng sản phẩm cuối cần đáp ứng các nguyên tắc sau:

- Trang dịch vụ Mua thẻ cào truy cập được qua trình duyệt web.
- Luồng mua hỗ trợ khách không đăng nhập.
- Luồng thanh toán sử dụng cổng thanh toán/thành phần thanh toán dùng chung của Viettel Money.
- Các màn xác nhận giao dịch, kết quả giao dịch và trạng thái thanh toán cần tái sử dụng pattern hiện hữu nếu phù hợp.
- Khi thanh toán hoặc cấp mã chậm, khách cần thấy trạng thái đang xử lý và có cách kiểm tra lại giao dịch.
- Refresh, back, retry hoặc timeout trong quá trình thanh toán/cấp mã không được làm khách mất thông tin đơn hàng đã tạo.

### Hỗ trợ trình duyệt và thiết bị

Dịch vụ cần hỗ trợ các môi trường truy cập chính:

- Mobile web là ưu tiên cao nhất.
- Desktop và tablet là bắt buộc.
- Trình duyệt phổ biến: Chrome, Safari, Edge.
- Webview trong các nền tảng quảng cáo/tin nhắn phổ biến như Facebook, TikTok, Zalo, Messenger cần được kiểm thử vì đây có thể là nguồn traffic chính từ ads.

Yêu cầu trải nghiệm trên webview:

- Không phụ thuộc vào popup/tab mới nếu có thể tránh.
- Các đường dẫn chiến dịch cần dùng `https://` và hạn chế redirect nhiều tầng để tránh bị chặn hoặc lệch tracking.
- Form nhập liệu cần tối ưu cho bàn phím mobile.
- Trạng thái thanh toán cần rõ ràng khi người dùng quay lại từ cổng thanh toán.
- Luồng mua không được mất dữ liệu đơn hàng khi chuyển sang bước thanh toán hoặc quay lại từ thanh toán.

### Kênh truy cập và hành trình từ input mẫu

Dịch vụ cần sẵn sàng cho các nguồn truy cập đã được nêu trong tài liệu mẫu website bán hàng:

- **SEO:** khách tìm kiếm từ khóa liên quan đến mua thẻ cào/nạp thẻ và vào trang dịch vụ trên Viettel Money Web.
- **Facebook/TikTok Ads:** khách click quảng cáo và mở trang trong webview của nền tảng quảng cáo.
- **Zalo/Messenger/nhóm chat:** khách click link được chia sẻ hoặc link từ thông báo/tin nhắn.
- **Email/campaign:** khách click link từ email hoặc chiến dịch bán hàng, nếu kênh này được sử dụng.
- **Điểm chạm nội bộ Viettel Money:** khách đi từ menu/danh mục dịch vụ viễn thông trên website.

Yêu cầu chung cho các kênh này là link phải dẫn khách vào đúng trang dịch vụ, bảo toàn thông tin campaign cần thiết cho đo lường và không làm khách phải tải app/đăng nhập trước khi mua.

### Sẵn sàng cho SEO và traffic

Trang dịch vụ cần phục vụ được traffic từ tìm kiếm và quảng cáo. SEO là yêu cầu hỗ trợ chuyển đổi, không phải mục tiêu tách biệt khỏi nghiệp vụ bán hàng.

Yêu cầu:

- Trang dịch vụ có URL rõ ràng, có thể chia sẻ và dùng trong chiến dịch quảng cáo.
- Nội dung trang cần đủ thông tin để khách hiểu dịch vụ, chiết khấu, nhà mạng/mệnh giá hỗ trợ và cách nhận mã.
- Trang cần có tiêu đề, mô tả và nội dung cơ bản phù hợp cho tìm kiếm.
- Tracking cần ghi nhận nguồn traffic/chiến dịch qua GA và Adjust để Kinh doanh/PO theo dõi hiệu quả.
- Các tham số campaign/source/medium cần được bảo toàn trong luồng mua và thanh toán ở mức phù hợp để phục vụ đo lường chuyển đổi.

### Responsive design và chuẩn UI/UX

Dịch vụ cần sử dụng design system Viettel Money và tái sử dụng các component/pattern hiện hữu cho nhóm dịch vụ viễn thông, xác nhận giao dịch, cổng thanh toán và kết quả giao dịch.

Yêu cầu UI/UX:

- Màn chọn thẻ cần hiển thị rõ nhà mạng, mệnh giá, số lượng, chiết khấu và tổng tiền.
- Luồng mua nhiều thẻ cần có khu vực tổng hợp đơn hàng rõ ràng, tránh làm rối màn hình mobile.
- Email là thông tin tùy chọn, không được trở thành rào cản mua hàng.
- Màn xác nhận giao dịch dùng pattern chung với các dịch vụ web hiện hữu nếu phù hợp.
- Cổng thanh toán sử dụng CTT/cổng thanh toán dùng chung.
- Màn thành công phải ưu tiên hiển thị mã thẻ/seri, không chôn thông tin mã dưới các thông tin giao dịch phụ.
- Cần hỗ trợ thao tác sao chép mã thẻ/seri, đặc biệt với giao dịch mua nhiều thẻ.
- Trạng thái lỗi, timeout hoặc đang xử lý phải có thông điệp rõ ràng và hướng dẫn hành động tiếp theo.

### Yêu cầu tốc độ và ổn định trải nghiệm

Dịch vụ cần tuân thủ chuẩn performance của Viettel Money Web cho web bán hàng, ưu tiên mobile web và webview. Mục tiêu performance là giảm rớt đơn, đảm bảo luồng thanh toán ổn định và hiển thị mã nhanh sau khi thanh toán thành công.

Yêu cầu performance:

- Trang dịch vụ cần đáp ứng chuẩn performance Viettel Money Web; nếu chưa có chuẩn nội bộ chi tiết, LCP mục tiêu là <= 2,5 giây ở P75 trên mobile web và webview phổ biến.
- Các tài nguyên hình ảnh/banner cần tối ưu để không làm vượt ngưỡng performance đã nêu; dung lượng và định dạng tài nguyên được kiểm tra trước go-live.
- Luồng chọn thẻ, cập nhật số lượng, tính chiết khấu và tổng tiền cần phản hồi dưới 300ms ở P95 trong điều kiện tải MVP.
- Sau khi thanh toán thành công, thời gian cấp và hiển thị mã thẻ/seri trên màn hình kết quả phải dưới 2 giây.
- Khi phản hồi thanh toán hoặc cấp mã chậm, hệ thống cần có cơ chế kiểm tra lại trạng thái và hiển thị trạng thái đang xử lý phù hợp.
- Không để lỗi tải trang, timeout hoặc refresh làm mất trạng thái đơn hàng trong quá trình thanh toán.

### Accessibility và khả dụng form

Dịch vụ cần đáp ứng chuẩn UI/UX và accessibility của Viettel Money Web; nếu chưa có chuẩn nội bộ cụ thể, dùng WCAG 2.1 AA làm baseline cho các màn giao dịch chính.

- Các trường nhập liệu có label rõ ràng.
- Lỗi nhập số điện thoại/email hiển thị dễ hiểu.
- CTA chính rõ ràng trên mobile.
- Màu sắc và trạng thái chọn/không chọn cần đủ tương phản.
- Người dùng có thể kiểm tra lại thông tin trước khi thanh toán.
- Nội dung quan trọng như tổng tiền, chiết khấu và mã thẻ không bị che khuất trên các kích thước màn hình phổ biến.

### Lưu ý phối hợp triển khai

Các điểm cần lưu ý khi triển khai:

- Tận dụng pattern hiện hữu từ các dịch vụ Data, FTTH, Nạp điện thoại và các luồng thanh toán web đã có.
- Đối chiếu cấu trúc màn hình với input mẫu: màn dịch vụ, màn xác nhận giao dịch, màn kết quả giao dịch, danh sách/tra cứu giao dịch và các trạng thái lỗi.
- Cần kiểm thử đầy đủ trên mobile browser, desktop browser và webview.
- Cần tracking funnel từng bước qua GA và Adjust: vào trang, chọn nhà mạng/mệnh giá, thay đổi số lượng, nhập thông tin nhận mã, xác nhận, bắt đầu thanh toán, thanh toán thành công, cấp mã thành công, giao dịch thất bại/timeout.
- Cần thống nhất mapping event giữa GA, Adjust và hệ thống báo cáo nội bộ để tránh lệch số liệu giữa traffic, đơn hàng và doanh thu.
- Với traffic từ webview/quảng cáo, cần kiểm tra các trường hợp prefetch/click ảo hoặc mất attribution để hạn chế sai lệch số liệu.
- Cần phân biệt rõ lỗi giao diện, lỗi thanh toán, lỗi cấp mã và lỗi gửi SMS/email.
- Cần thống nhất với đội vận hành/CSKH về dữ liệu hiển thị khi tra cứu giao dịch.

## Phạm vi dự án và phát triển theo giai đoạn

### Chiến lược MVP

**Cách tiếp cận MVP:** Revenue MVP

MVP của dịch vụ Mua thẻ cào trên `viettelmoney.vn` cần đủ năng lực để tạo doanh số thực tế, đo tỷ lệ chuyển đổi và chứng minh rằng kênh web không đăng nhập có thể bán thẻ cào hiệu quả. MVP không phải bản thử nghiệm giao diện; đây là phiên bản giao dịch thật, có thanh toán, cấp mã, gửi SMS/email, tracking và dữ liệu vận hành.

**Mô hình phát hành:** Phased delivery

Dự án triển khai theo hướng có MVP trước, sau đó mở rộng các tính năng tăng trưởng và tối ưu nâng cao dựa trên dữ liệu thực tế.

**Nguồn lực cần phối hợp:** PO/Kinh doanh, UX/UI, đội phát triển web, đội tích hợp/thanh toán CTT, hệ thống cấp mã thẻ, SMS/Email, QA, CSKH/Vận hành và báo cáo/tracking GA/Adjust.

### Phạm vi MVP (Giai đoạn 1)

**Hành trình người dùng được hỗ trợ:**

- Khách hàng mua 1 thẻ thành công.
- Khách hàng mua nhiều thẻ thành công.
- Khách hàng gặp lỗi sau thanh toán.
- CSKH/Vận hành tra cứu giao dịch.
- Kinh doanh/PO theo dõi doanh số và hiệu quả dịch vụ.
- Kinh doanh/PO cấu hình dịch vụ và chiến dịch.

**Năng lực bắt buộc:**

- Trang dịch vụ Mua thẻ cào trên `viettelmoney.vn`.
- Hỗ trợ khách hàng mua không cần đăng nhập và không cần tải app.
- Hỗ trợ đa nhà mạng ngay trong MVP, bao gồm các nhà mạng theo danh sách kinh doanh/cấu hình được phê duyệt.
- Hiển thị danh sách mệnh giá theo từng nhà mạng.
- Cho phép khách hàng chọn nhà mạng, mệnh giá và số lượng thẻ.
- Cho phép mua nhiều thẻ trong một giao dịch.
- Hiển thị chiết khấu, tổng tiền và thông tin đơn hàng trước thanh toán.
- Nhập số điện thoại nhận SMS.
- Nhập email tùy chọn để nhận thêm mã thẻ.
- Màn xác nhận giao dịch trước thanh toán.
- Thanh toán qua CTT/cổng thanh toán dùng chung.
- Màn kết quả giao dịch thành công/thất bại/timeout.
- Block hiển thị thẻ cào trên màn kết quả gồm logo/tên nhà mạng, mệnh giá, số seri, mã thẻ và mã giao dịch.
- Hành động sao chép mã thẻ/seri; với thẻ Viettel có thể bổ sung hành động “Nạp ngay” hoặc hướng dẫn nạp nếu hệ thống hiện hữu hỗ trợ.
- Cấp và hiển thị mã thẻ/seri trên màn hình thành công trong dưới 2 giây sau khi thanh toán thành công.
- Gửi mã thẻ/seri qua SMS.
- Gửi mã thẻ/seri qua email nếu khách hàng nhập email.
- Ghi nhận riêng trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email.
- Cơ chế xử lý lỗi đã thanh toán nhưng chưa nhận mã, thanh toán timeout, cấp mã lỗi, gửi SMS/email lỗi.
- Công cụ/dữ liệu tra cứu cho CSKH/Vận hành.
- Báo cáo/dashboard cho Kinh doanh/PO theo dõi doanh số, số giao dịch, số lượng thẻ bán ra, nhà mạng/mệnh giá bán chạy, nguồn traffic/quảng cáo, funnel chuyển đổi và lỗi ảnh hưởng doanh thu.
- Cấu hình nhà mạng, mệnh giá, chiết khấu, bật/tắt dịch vụ, chiến dịch, nguồn traffic và nội dung hiển thị.
- Tracking funnel qua GA và Adjust.
- Kiểm thử trên mobile web, desktop/tablet và webview phổ biến.
- Sử dụng design system Viettel Money và CTT/cổng thanh toán dùng chung.

### Tính năng sau MVP

**Giai đoạn 2 (Growth):**

- Tối ưu funnel dựa trên dữ liệu rớt đơn thực tế.
- Cấu hình campaign chiết khấu linh hoạt hơn theo nhà mạng, mệnh giá, thời gian, nguồn traffic hoặc chiến dịch.
- Gợi ý mệnh giá phổ biến hoặc combo nhiều thẻ.
- Nâng cấp dashboard cho Kinh doanh/PO theo chiến dịch và nguồn traffic.
- Nâng cấp tra cứu giao dịch cho khách không đăng nhập bằng số điện thoại, mã giao dịch hoặc OTP nếu cần.
- Tối ưu SEO/content theo các nhóm từ khóa và chiến dịch bán hàng.
- Bổ sung cơ chế kiểm soát giới hạn giao dịch guest theo chính sách Risk/Fraud sau khi có dữ liệu thực tế.

**Giai đoạn 3 (Expansion):**

- Mở rộng sang các sản phẩm viễn thông trả trước hoặc hàng hóa số liên quan nếu phù hợp: nạp điện thoại, data, gói viễn thông, thẻ game hoặc dịch vụ số khác.
- Cá nhân hóa ưu đãi hoặc gợi ý mua dựa trên hành vi, nếu được chính sách dữ liệu cho phép.
- Remarketing với nhóm khách nhập email/số điện thoại, nếu được pháp chế/risk phê duyệt.
- Tự động hóa cảnh báo vận hành khi có bất thường về thanh toán, cấp mã, gửi SMS/email hoặc tỷ lệ lỗi theo nhà mạng/mệnh giá.

### Chiến lược kiểm soát rủi ro

**Rủi ro vận hành hệ thống:**

- Rủi ro thanh toán thành công nhưng cấp mã lỗi: cần tách trạng thái thanh toán/cấp mã, có cơ chế kiểm tra lại và quy trình CSKH/Vận hành.
- Rủi ro mua nhiều thẻ nhưng cấp mã một phần: cần quy định xử lý atomic hoặc trạng thái chi tiết theo từng mã thẻ.
- Rủi ro thanh toán/cấp mã chậm: cần thông điệp đang xử lý và cách kiểm tra lại trạng thái.
- Rủi ro lệch nguồn traffic/tracking trên webview: cần kiểm thử GA/Adjust và mapping event rõ.

**Rủi ro thị trường/doanh số:**

- CR thực tế thấp hơn mục tiêu 20-30%: cần đo funnel từng bước để tối ưu UX, nội dung, chiết khấu và nguồn traffic.
- Doanh số thấp hơn mục tiêu 200 triệu/tháng: cần theo dõi theo nhà mạng, mệnh giá, nguồn traffic, mức chiết khấu và tỷ lệ thanh toán thành công để xác định điểm nghẽn.
- Khách không tin tưởng luồng web không đăng nhập: cần hiển thị rõ thương hiệu Viettel Money, chính sách nhận mã, trạng thái giao dịch và kênh hỗ trợ.

**Rủi ro nguồn lực:**

- Nếu nguồn lực hạn chế, không được cắt các năng lực cốt lõi: thanh toán, cấp mã, mua nhiều thẻ, SMS/email, CSKH tra cứu, tracking GA/Adjust.
- Có thể giảm độ phức tạp của dashboard/cấu hình trong MVP nếu vẫn đảm bảo Kinh doanh/PO có dữ liệu tối thiểu để theo dõi doanh số và lỗi.
- Các tính năng gợi ý combo, remarketing, cá nhân hóa và tối ưu nâng cao có thể để sau MVP.

## Yêu cầu chức năng

### Truy cập dịch vụ và chọn sản phẩm

- FR1: Khách hàng có thể truy cập trang dịch vụ Mua thẻ cào trên `viettelmoney.vn` bằng trình duyệt web mà không cần đăng nhập.
- FR2: Khách hàng có thể xem danh sách nhà mạng được hỗ trợ theo cấu hình kinh doanh.
- FR3: Khách hàng có thể chọn một nhà mạng để mua thẻ cào.
- FR4: Khách hàng có thể xem danh sách mệnh giá khả dụng tương ứng với nhà mạng đã chọn.
- FR5: Khách hàng có thể chọn một hoặc nhiều mệnh giá thẻ cào theo nhu cầu.
- FR6: Khách hàng có thể xem thông tin chiết khấu áp dụng cho nhà mạng, mệnh giá hoặc chiến dịch nếu có.
- FR7: Hệ thống có thể hiển thị trạng thái khả dụng của nhà mạng, mệnh giá hoặc dịch vụ khi bị tạm dừng/bảo trì.

### Tạo đơn mua thẻ

- FR8: Khách hàng có thể chọn số lượng thẻ cần mua cho từng mệnh giá.
- FR9: Khách hàng có thể mua một thẻ trong một giao dịch.
- FR10: Khách hàng có thể mua nhiều thẻ trong một giao dịch.
- FR11: Khách hàng có thể xem danh sách thẻ trong đơn hàng trước khi thanh toán.
- FR12: Hệ thống có thể tính tổng tiền đơn hàng dựa trên nhà mạng, mệnh giá, số lượng và chiết khấu.
- FR13: Khách hàng có thể nhập số điện thoại để nhận mã thẻ qua SMS.
- FR14: Khách hàng có thể nhập email tùy chọn để nhận thêm mã thẻ qua email.
- FR15: Hệ thống có thể kiểm tra định dạng số điện thoại và email trước khi khách hàng xác nhận giao dịch.
- FR16: Khách hàng có thể xem lại thông tin đơn hàng, số điện thoại, email nếu có, chiết khấu và tổng tiền trước khi thanh toán.

### Xác nhận và thanh toán

- FR17: Khách hàng có thể xác nhận giao dịch mua thẻ cào trước khi chuyển sang thanh toán.
- FR18: Hệ thống có thể tạo mã giao dịch duy nhất cho mỗi đơn mua thẻ.
- FR19: Khách hàng có thể thanh toán đơn mua thẻ qua CTT/cổng thanh toán dùng chung của Viettel Money.
- FR20: Hệ thống có thể nhận và lưu trạng thái thanh toán của giao dịch.
- FR21: Hệ thống có thể phân biệt các trạng thái thanh toán: chờ thanh toán, thanh toán thành công, thanh toán thất bại và thanh toán timeout.
- FR22: Hệ thống không cấp mã thẻ khi giao dịch chưa được xác nhận thanh toán thành công.

### Cấp phát và hiển thị mã thẻ

- FR23: Hệ thống có thể cấp phát mã thẻ/seri sau khi giao dịch được xác nhận thanh toán thành công.
- FR24: Hệ thống có thể cấp phát đủ số lượng mã thẻ/seri tương ứng với đơn hàng đã thanh toán.
- FR25: Hệ thống có thể xử lý giao dịch mua nhiều thẻ và lưu trạng thái cấp mã theo từng mã thẻ trong mọi giao dịch mua nhiều thẻ.
- FR26: Hệ thống có thể ngăn việc cấp trùng mã thẻ/seri.
- FR27: Khách hàng có thể xem mã thẻ/seri trên màn hình giao dịch thành công.
- FR28: Khách hàng có thể xem danh sách mã thẻ/seri khi mua nhiều thẻ trong một giao dịch.
- FR29: Khách hàng có thể sao chép mã thẻ/seri từ màn hình giao dịch thành công.
- FR30: Hệ thống có thể hiển thị thông tin giao dịch thành công gồm nhà mạng, mệnh giá, số lượng, tổng tiền, chiết khấu và mã giao dịch.

### Gửi thông báo SMS/email

- FR31: Hệ thống có thể gửi mã thẻ/seri qua SMS đến số điện thoại khách hàng đã nhập.
- FR32: Hệ thống có thể gửi mã thẻ/seri qua email nếu khách hàng đã nhập email.
- FR33: Hệ thống có thể ghi nhận trạng thái gửi SMS cho từng giao dịch.
- FR34: Hệ thống có thể ghi nhận trạng thái gửi email cho từng giao dịch có email.
- FR35: Hệ thống có thể xử lý trường hợp cấp mã thành công nhưng gửi SMS hoặc email thất bại.

### Xử lý trạng thái và lỗi giao dịch

- FR36: Hệ thống có thể hiển thị kết quả giao dịch thành công, thất bại, timeout hoặc đang xử lý.
- FR37: Hệ thống có thể truy vấn lại trạng thái giao dịch khi phản hồi thanh toán hoặc cấp mã chậm.
- FR38: Hệ thống có thể ghi nhận riêng trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email.
- FR39: Hệ thống có thể xử lý trường hợp thanh toán thành công nhưng cấp mã thẻ thất bại.
- FR40: Hệ thống có thể xử lý trường hợp thanh toán thành công nhưng chỉ cấp được một phần mã thẻ trong giao dịch mua nhiều thẻ.
- FR41: Hệ thống có thể cung cấp mã giao dịch và hướng dẫn tiếp theo cho khách hàng khi giao dịch lỗi, timeout hoặc đang xử lý.
- FR42: Hệ thống có thể bảo vệ mã thẻ/seri khỏi việc hiển thị trong log, analytics hoặc tracking.

### Tra cứu, CSKH và vận hành

- FR43: CSKH/Vận hành có thể tra cứu giao dịch theo mã giao dịch.
- FR44: CSKH/Vận hành có thể tra cứu giao dịch theo số điện thoại nhận SMS.
- FR45: CSKH/Vận hành có thể tra cứu giao dịch theo email nếu khách hàng đã nhập email.
- FR46: CSKH/Vận hành có thể tra cứu giao dịch theo thời gian, nhà mạng, mệnh giá hoặc số tiền.
- FR47: CSKH/Vận hành có thể xem trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email của giao dịch.
- FR48: CSKH/Vận hành có thể xem số lượng thẻ trong giao dịch và trạng thái của từng mã thẻ nếu giao dịch mua nhiều thẻ.
- FR49: CSKH/Vận hành có thể xem mã lỗi hoặc lý do thất bại nếu giao dịch thanh toán, cấp mã hoặc gửi thông báo lỗi.
- FR50: Hệ thống có thể lưu lịch sử xử lý/trạng thái phục vụ tra cứu, khiếu nại và kiểm soát nội bộ.

### Báo cáo, cấu hình và tracking

- FR51: Kinh doanh/PO có thể xem báo cáo doanh số theo ngày, tháng hoặc chiến dịch.
- FR52: Kinh doanh/PO có thể xem số giao dịch thành công và số lượng thẻ bán ra.
- FR53: Kinh doanh/PO có thể xem doanh số và số lượng thẻ theo nhà mạng, mệnh giá và nguồn traffic/quảng cáo.
- FR54: Kinh doanh/PO có thể xem Visit-to-purchase CR và Checkout completion rate.
- FR55: Kinh doanh/PO có thể xem tỷ lệ cấp mã thành công, tỷ lệ gửi SMS/email thành công và tỷ lệ lỗi ảnh hưởng doanh thu.
- FR56: Kinh doanh/PO có thể cấu hình danh sách nhà mạng được bán.
- FR57: Kinh doanh/PO có thể cấu hình danh sách mệnh giá theo từng nhà mạng.
- FR58: Kinh doanh/PO có thể cấu hình chiết khấu theo chính sách kinh doanh hoặc chiến dịch.
- FR59: Kinh doanh/PO có thể bật/tắt dịch vụ, nhà mạng hoặc mệnh giá theo nhu cầu vận hành.
- FR60: Hệ thống có thể ghi nhận lịch sử thay đổi cấu hình quan trọng.
- FR61: Hệ thống có thể gửi sự kiện tracking funnel qua GA và Adjust.
- FR62: Hệ thống có thể ghi nhận các bước funnel chính: vào trang, chọn nhà mạng/mệnh giá, thay đổi số lượng, nhập thông tin nhận mã, xác nhận, bắt đầu thanh toán, thanh toán thành công, cấp mã thành công, giao dịch thất bại/timeout.

### Kế thừa giao diện và kênh vào

- FR63: Hệ thống có thể ghi nhận nguồn truy cập/campaign từ SEO, ads, webview, chat/link chia sẻ, email/campaign và điểm chạm nội bộ nếu các kênh này được sử dụng.
- FR64: Hệ thống có thể hiển thị logo/tên nhà mạng và lựa chọn mặc định theo cấu hình kinh doanh.
- FR65: Hệ thống có thể hiển thị mệnh giá mặc định theo cấu hình kinh doanh, ví dụ 50.000 đồng nếu được phê duyệt.
- FR66: Màn kết quả giao dịch có thể hiển thị block thẻ cào gồm logo/tên nhà mạng, mệnh giá, số seri và mã thẻ.
- FR67: Với thẻ Viettel, hệ thống có thể hiển thị hành động “Nạp ngay” hoặc hướng dẫn nạp thẻ nếu năng lực này được hỗ trợ trong nền tảng hiện hữu.

## Yêu cầu phi chức năng

### Performance

- NFR1: Trang dịch vụ Mua thẻ cào cần đạt LCP <= 2,5 giây ở P75 trên mobile web và webview phổ biến, đo bằng công cụ performance/RUM của Viettel Money hoặc công cụ tương đương trước go-live.
- NFR2: Luồng chọn nhà mạng, mệnh giá, số lượng, tính chiết khấu và tổng tiền cần phản hồi dưới 300ms ở P95 trong điều kiện tải MVP, đo bằng instrumentation frontend hoặc kiểm thử hiệu năng.
- NFR3: Sau khi thanh toán thành công, hệ thống phải cấp và hiển thị mã thẻ/seri trên màn hình kết quả trong vòng dưới 2 giây ở P95, đo từ thời điểm nhận xác nhận thanh toán thành công đến thời điểm màn hình hiển thị mã.
- NFR4: Khi phản hồi thanh toán hoặc cấp mã chậm quá 2 giây, màn hình phải hiển thị trạng thái đang xử lý và truy vấn lại trạng thái theo cơ chế được đội phát triển xác nhận.
- NFR5: Refresh, back, retry hoặc timeout không được làm mất trạng thái đơn hàng đã tạo; kiểm thử E2E phải bao phủ các tình huống này trên mobile web, desktop và webview.
- NFR6: Hình ảnh, banner và tài nguyên tĩnh phải được tối ưu theo chuẩn performance Viettel Money Web; nếu chưa có chuẩn nội bộ, tổng tài nguyên phục vụ first view trên mobile không vượt ngưỡng do đội phát triển xác nhận trước go-live.

### Bảo mật

- NFR7: Mã thẻ/seri được phân loại là dữ liệu nhạy cảm và phải được bảo vệ trong hiển thị, lưu trữ, gửi SMS/email, tra cứu CSKH và đối soát theo chính sách nội bộ.
- NFR8: Mã thẻ/seri không được xuất hiện trong URL, log ứng dụng, log web server, GA, Adjust, analytics, tracking event hoặc công cụ ghi nhận hành vi; tiêu chí nghiệm thu là kiểm tra mẫu log/event không phát hiện mã thẻ/seri.
- NFR9: Quyền truy cập dữ liệu giao dịch, mã thẻ/seri và màn tra cứu CSKH/Vận hành phải được phân quyền theo vai trò; mọi lượt truy cập dữ liệu nhạy cảm phải có log gồm người truy cập, thời gian và hành động.
- NFR10: Số điện thoại và email khách hàng chỉ được dùng cho gửi mã, hỗ trợ giao dịch và mục đích khác đã được chính sách nội bộ phê duyệt; event tracking không được chứa thông tin này ở dạng thô nếu không được cho phép.
- NFR11: 100% giao dịch cấp mã phải có xác nhận thanh toán thành công trước đó; kiểm thử đối soát không được phát hiện giao dịch cấp mã khi thanh toán thất bại, timeout hoặc chưa xác nhận.
- NFR12: 100% thay đổi cấu hình quan trọng như nhà mạng, mệnh giá, chiết khấu, bật/tắt dịch vụ phải được ghi nhận lịch sử gồm người thay đổi, thời gian, giá trị trước/sau và lý do nếu có.
- NFR13: Guest checkout phải hỗ trợ áp dụng giới hạn số lượng thẻ, giá trị đơn và tần suất mua theo chính sách Risk/Fraud; giới hạn cụ thể phải được chốt trước go-live hoặc ghi nhận là cấu hình mặc định được phê duyệt.

### Độ tin cậy

- NFR14: Hệ thống phải phân biệt và lưu riêng trạng thái thanh toán, trạng thái cấp mã thẻ và trạng thái gửi SMS/email cho 100% giao dịch.
- NFR15: Hệ thống phải xử lý được các tình huống thanh toán thất bại, thanh toán timeout, thanh toán thành công nhưng cấp mã lỗi, cấp mã thành công nhưng gửi SMS/email lỗi; mỗi tình huống có trạng thái hiển thị và mã lỗi/diễn giải phục vụ CSKH.
- NFR16: Với giao dịch mua nhiều thẻ, hệ thống phải ghi nhận trạng thái từng mã thẻ để xác định mã đã cấp thành công, lỗi hoặc cần xử lý trong 100% giao dịch mua nhiều thẻ.
- NFR17: Màn hình kết quả giao dịch phải cung cấp mã giao dịch trong 100% trạng thái thành công, thất bại, timeout hoặc đang xử lý để khách hàng liên hệ CSKH.
- NFR18: Fulfillment success rate mục tiêu MVP là >= 99%, tính bằng số giao dịch nhận mã thành công / số giao dịch thanh toán thành công, đo theo báo cáo vận hành hằng ngày.
- NFR19: Tỷ lệ gửi SMS thành công mục tiêu là >= 98% với giao dịch đã cấp mã thành công; tỷ lệ gửi email thành công mục tiêu là >= 95% với giao dịch có email hợp lệ.
- NFR20: CSKH/Vận hành phải tra cứu được giao dịch theo mã giao dịch hoặc số điện thoại nhận SMS trong 100% trường hợp khách liên hệ có thông tin tối thiểu hợp lệ.

### Khả năng mở rộng

- NFR21: Hệ thống phải đáp ứng mục tiêu MVP 1.000 giao dịch/ngày và có khả năng xử lý tối thiểu 3 lần mức trung bình ngày MVP trong các ngày chiến dịch, đo bằng kiểm thử tải hoặc số liệu vận hành được đội phát triển phê duyệt.
- NFR22: Luồng mua, cấp mã, gửi SMS/email và tracking phải duy trì checkout completion rate >= 95% và fulfillment success rate >= 99% trong điều kiện tải MVP.
- NFR23: Báo cáo và tracking phải xử lý dữ liệu theo ngày, chiến dịch, nhà mạng, mệnh giá, nguồn traffic và trạng thái giao dịch với độ trễ dữ liệu phù hợp chuẩn báo cáo Viettel Money; nếu chưa có chuẩn, dữ liệu phục vụ báo cáo ngày cần sẵn sàng trong ngày T+1.
- NFR24: Hệ thống phải hỗ trợ thêm/bớt nhà mạng, mệnh giá và chiến dịch chiết khấu bằng cấu hình mà không thay đổi luồng mua cốt lõi.
- NFR25: Các thành phần cấp mã, gửi SMS/email và tracking phải có khả năng mở rộng theo tăng trưởng số lượng giao dịch mà không làm giảm các KPI fulfillment, SMS/email delivery và checkout đã nêu.

### Accessibility và khả dụng

- NFR26: Dịch vụ phải tuân thủ chuẩn UI/UX và accessibility của Viettel Money Web; nếu chưa có chuẩn nội bộ cụ thể, các màn giao dịch chính dùng WCAG 2.1 AA làm baseline kiểm tra.
- NFR27: Form số điện thoại và email phải có label, hướng dẫn và thông báo lỗi rõ ràng; kiểm thử UX phải xác nhận khách hiểu lỗi nhập liệu và cách sửa.
- NFR28: CTA chính trong từng bước phải hiển thị rõ trên mobile web và webview, không bị che bởi bàn phím, sticky area hoặc nội dung khác ở các kích thước màn hình phổ biến.
- NFR29: Trạng thái chọn/không chọn nhà mạng, mệnh giá và số lượng phải có tương phản/biểu hiện đủ rõ theo chuẩn UI/UX; kiểm thử giao diện phải bao phủ trạng thái normal, selected, disabled và error.
- NFR30: Tổng tiền, chiết khấu, mã thẻ/seri và mã giao dịch không được bị che khuất hoặc tràn layout trên mobile, desktop, tablet và webview phổ biến.
- NFR31: Khách hàng phải có bước xác nhận lại nhà mạng, mệnh giá, số lượng, chiết khấu, tổng tiền, số điện thoại và email nếu có trước khi thanh toán.
- NFR32: Email là thông tin tùy chọn; khách hàng bỏ trống email vẫn phải tiếp tục thanh toán được nếu số điện thoại hợp lệ.

### Tích hợp

- NFR33: CTT/cổng thanh toán dùng chung phải trả về hoặc cho phép truy vấn trạng thái chờ thanh toán, thanh toán thành công, thanh toán thất bại và timeout để hệ thống xử lý đúng trạng thái giao dịch.
- NFR34: Hệ thống cấp mã thẻ phải hỗ trợ cấp đủ số lượng mã theo đơn hàng, không cấp trùng mã và trả về trạng thái lỗi đủ để vận hành xử lý.
- NFR35: SMS/email phải trả về trạng thái gửi thành công/thất bại để hệ thống ghi nhận cho 100% giao dịch có phát sinh gửi thông báo.
- NFR36: Các tích hợp thanh toán, cấp mã, SMS/email phải hỗ trợ cơ chế truy vấn lại trạng thái khi phản hồi chậm hoặc không nhận được phản hồi trong thời gian chờ được đội phát triển xác nhận.
- NFR37: Dữ liệu giao dịch phải đủ trường để kết nối với báo cáo, CSKH/Vận hành và tracking GA/Adjust, gồm mã giao dịch, thời gian, nhà mạng, mệnh giá, số lượng, chiết khấu, trạng thái thanh toán, trạng thái cấp mã và trạng thái gửi SMS/email.

### Tracking và theo dõi vận hành

- NFR38: Hệ thống phải gửi tracking funnel qua GA và Adjust cho các bước chính: vào trang, chọn nhà mạng/mệnh giá, thay đổi số lượng, nhập thông tin nhận mã, xác nhận, bắt đầu thanh toán, thanh toán thành công, cấp mã thành công, giao dịch thất bại/timeout.
- NFR39: 100% event tracking không được chứa mã thẻ/seri, số điện thoại/email dạng thô hoặc dữ liệu nhạy cảm chưa được phê duyệt.
- NFR40: Mapping event giữa GA, Adjust và báo cáo nội bộ phải được thống nhất trước go-live; chênh lệch số đơn thành công giữa tracking và báo cáo giao dịch cần có ngưỡng kiểm soát hoặc quy trình đối soát.
- NFR41: Với traffic từ webview/quảng cáo, quy trình QA phải kiểm tra prefetch, click ảo, mất attribution và bảo toàn campaign/source/medium qua luồng mua-thanh toán.
- NFR42: Hệ thống phải log đủ mã giao dịch, trạng thái và mã lỗi để phục vụ vận hành; log không được chứa mã thẻ/seri ở dạng lộ.
- NFR43: Hệ thống cần dashboard hoặc báo cáo vận hành theo dõi tối thiểu các KPI: doanh số, số giao dịch thành công, fulfillment success rate, thời gian hiển thị mã P95, SMS/email delivery rate, lỗi thanh toán, lỗi cấp mã và lỗi gửi thông báo.
