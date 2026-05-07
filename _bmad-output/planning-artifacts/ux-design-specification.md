---
stepsCompleted:
  - 1
  - 2
  - 3
  - 4
  - 5
  - 6
  - 7
  - 8
inputDocuments:
  - path: "_bmad-output/planning-artifacts/prd.md"
    type: "brd"
    title: "BRD - Tài liệu yêu cầu kinh doanh Mua thẻ cào trên viettelmoney.vn"
  - path: "_bmad-output/planning-artifacts/prd-validation-report.md"
    type: "validation-report"◊
    title: "PRD Validation Report"
  - path: "https://www.figma.com/design/MvKWlDKG55tlppKWNTbTwr/-Web--D%E1%BB%8Bch-v%E1%BB%A5----Website-vtmoney.vn?node-id=5318-41390"
    type: "figma-design"
    title: "Website Nạp điện thoại/ Mua thẻ [04/2026]"
---

# UX Design Specification Mua thẻ cào

**Author:** hapu
**Date:** 2026-05-06

---

<!-- UX design content will be appended sequentially through collaborative workflow steps -->

## Executive Summary

### Project Vision

Dịch vụ Mua thẻ cào trên `viettelmoney.vn` cần mang lại trải nghiệm mua thẻ nhanh, rõ giá, rõ ưu đãi và nhận mã chắc chắn ngay sau thanh toán mà không yêu cầu khách hàng đăng nhập hoặc tải app. UX cần kế thừa design system, pattern dịch vụ viễn thông và luồng thanh toán dùng chung của Viettel Money Web, đồng thời tối ưu cho mobile web, webview và traffic từ SEO/quảng cáo/chat.

Trọng tâm UX không chỉ là một màn hình mua thẻ. Đây là dịch vụ guest checkout cho hàng hóa số nhạy cảm, nơi khách hàng cần tin tưởng rằng: đã trả tiền thì sẽ nhận được mã, có thể lưu/copy/gửi lại mã, và có cách xử lý rõ nếu thanh toán hoặc cấp mã gặp sự cố.

### Target Users

- Khách hàng mua nhanh 1 thẻ cào cho bản thân hoặc người thân, ưu tiên tốc độ và sự chắc chắn.
- Khách hàng mua nhiều thẻ trong một giao dịch, cần kiểm soát danh sách thẻ, số lượng, chiết khấu và tổng tiền.
- Khách hàng đến từ SEO, ads, webview, Zalo/Messenger/chat, email/campaign hoặc menu dịch vụ trên website, thường không muốn tải app hoặc đăng nhập.
- Khách hàng cần nhận lại mã sau khi đóng trang, mất webview hoặc không nhận được SMS/email.
- CSKH/Vận hành cần tra cứu trạng thái giao dịch, trạng thái cấp mã và trạng thái gửi SMS/email để hỗ trợ khách.
- Kinh doanh/PO cần theo dõi doanh số, tỷ lệ chuyển đổi, funnel, nguồn traffic và hiệu quả theo nhà mạng/mệnh giá.

### Stakeholder Map

- **Người mua lẻ:** cần mua nhanh, rõ giá, nhận mã chắc chắn.
- **Người mua nhiều thẻ:** cần danh sách thẻ rõ, tổng tiền chính xác, thao tác copy/lưu/gửi lại dễ dùng.
- **Kinh doanh/PO:** cần conversion tốt, tracking đủ, dữ liệu theo nhà mạng/mệnh giá/nguồn traffic.
- **Marketing/Ads/SEO:** cần landing dễ chuyển đổi, tải nhanh, đủ trust signal và đo attribution đúng.
- **Payment/CTT:** cần trạng thái thanh toán rõ, xử lý pending/timeout ổn định.
- **CSKH/Vận hành:** cần mã giao dịch, trạng thái thanh toán/cấp mã/SMS/email, lỗi và dữ liệu tra cứu.
- **Risk/Fraud/Compliance:** cần giới hạn giao dịch, chống lạm dụng chiết khấu, bảo vệ mã thẻ và dữ liệu liên hệ.
- **Đối soát/Tài chính:** cần dữ liệu đơn hàng, chiết khấu, trạng thái thanh toán, cấp mã và hoàn/hủy nếu có.

### Key Design Challenges

- Giữ luồng mua đủ ngắn cho khách không đăng nhập nhưng vẫn tạo cảm giác tin cậy cho giao dịch thanh toán.
- Thiết kế mua nhiều thẻ trên mobile sao cho danh sách thẻ, số lượng, chiết khấu và tổng tiền vẫn dễ hiểu.
- Ưu tiên hiển thị mã thẻ/seri trên màn thành công mà vẫn bảo vệ dữ liệu nhạy cảm.
- Xử lý trạng thái lỗi, timeout, thanh toán thành công nhưng chưa có mã, cấp mã một phần hoặc gửi SMS/email lỗi bằng thông điệp rõ ràng.
- Đảm bảo trải nghiệm ổn định trong mobile web và webview từ các kênh quảng cáo/chat.
- Cân bằng SEO content với luồng mua nhanh: nội dung đủ tin cậy và index được nhưng không đẩy module mua xuống quá sâu.

### Design Opportunities

- Dùng lợi thế “không cần đăng nhập/tải app” để tạo luồng mua nhanh hơn app hoặc bên thứ ba.
- Hiển thị chiết khấu và tổng tiền minh bạch để tăng niềm tin trước thanh toán.
- Biến màn thành công thành điểm nhận hàng: mã thẻ dễ thấy, dễ copy, SMS/email rõ trạng thái, mã giao dịch sẵn để hỗ trợ.
- Tách pattern mua 1 thẻ và mua nhiều thẻ để tối ưu từng nhu cầu thay vì ép vào một trải nghiệm chung.
- Dùng trust signals đúng lúc: thương hiệu Viettel Money, cổng thanh toán quen thuộc, mã giao dịch, cam kết kênh nhận mã và hỗ trợ khi lỗi.

### Entry Scenarios

1. **Mua gấp 1 thẻ:** khách vào từ mobile web/SEO/chat, cần chọn nhanh nhà mạng, mệnh giá, thanh toán và nhận mã ngay.
2. **Mua nhiều thẻ:** khách mua nhiều mã cho người thân, nhân viên, đại lý nhỏ hoặc theo ngân sách; cần giỏ tóm tắt, số lượng rõ và danh sách mã sau thanh toán dễ quản lý.
3. **Vào từ ads/webview:** khách có mức tin tưởng thấp hơn, dễ rớt phiên, cần trang nhẹ, không popup phức tạp, trust signal rõ và trạng thái thanh toán dễ hiểu.
4. **Cần hỗ trợ sau giao dịch:** khách đã thanh toán nhưng chưa nhận mã/SMS/email; cần mã giao dịch và hướng dẫn tra cứu/liên hệ CSKH.

### Critical UX Decisions

| Nhóm quyết định | Hướng UX cần chốt trong spec |
|---|---|
| Guest checkout | Guest là luồng chính; không ép tải app/đăng nhập trước khi mua. Số điện thoại nhận SMS là thông tin bắt buộc để có kênh cứu giao dịch; email là tùy chọn. |
| Multi-card model | Hỗ trợ mua nhiều thẻ trong một giao dịch. UI cần làm rõ mệnh giá, số lượng, chiết khấu và thành tiền theo từng dòng/nhóm. |
| Price model | Phân biệt rõ mệnh giá thẻ, chiết khấu và số tiền phải thanh toán. Nếu giá/chiết khấu thay đổi trước thanh toán, khách cần xác nhận lại. |
| Fulfillment model | Màn thành công là nơi nhận hàng. Cần hiển thị nhà mạng, mệnh giá, serial, mã thẻ, mã giao dịch, trạng thái gửi SMS/email, copy controls và hướng dẫn hỗ trợ. |
| Sensitive code handling | Mã thẻ/seri là dữ liệu nhạy cảm. UX cần quy định hiển thị, copy, che/hiện nếu cần, cảnh báo không chia sẻ mã và cách xem lại/nhận lại theo chính sách. |
| State model | Cần bao phủ created order, redirecting to payment, payment pending, payment failed/cancelled, payment success/card issuing pending, card issued success, card issuing failed/partial. |
| Channel model | Mobile web và webview là ưu tiên; không phụ thuộc popup/new tab, cần xử lý back/refresh/payment return rõ ràng. |

### Success Screen Requirements

Màn thành công phải trả lời ngay 4 câu hỏi của khách:

- Giao dịch đã thành công chưa?
- Khách nhận được bao nhiêu mã thẻ?
- Mã nào dùng để nạp và serial tương ứng là gì?
- Nếu có lỗi, cần xem lại hoặc cần hỗ trợ thì làm gì?

Nội dung tối thiểu trên màn thành công:

- Trạng thái thanh toán/cấp mã.
- Mã giao dịch.
- Tổng tiền đã thanh toán và chiết khấu đã nhận.
- Danh sách thẻ theo nhà mạng/mệnh giá, gồm serial và mã thẻ.
- Copy từng mã và copy tất cả nếu mua nhiều thẻ.
- Trạng thái gửi SMS/email.
- Hướng dẫn nạp thẻ hoặc “Nạp ngay” cho thẻ Viettel nếu được hỗ trợ.
- Kênh hỗ trợ/tra cứu khi có vấn đề.

### UX Measurement Focus

- Conversion theo từng bước: vào trang, chọn nhà mạng/mệnh giá, thay đổi số lượng, nhập thông tin nhận mã, xác nhận, bắt đầu thanh toán, thanh toán thành công, cấp mã thành công.
- Drop-off theo entry channel: SEO, ads/webview, chat/link chia sẻ, email/campaign, điểm chạm nội bộ.
- Tỷ lệ thanh toán pending/timeout và tỷ lệ khách cần CSKH hỗ trợ.
- Tỷ lệ copy mã, gửi SMS/email thành công, và khách mua thêm sau giao dịch thành công.

## Core User Experience

### Defining Experience

Trải nghiệm lõi của dịch vụ là: khách hàng chọn thẻ, thấy rõ chiết khấu/tổng tiền, thanh toán và nhận mã thẻ ngay trên web mà không cần đăng nhập hoặc tải app.

Hành động quan trọng nhất cần làm đúng là hoàn tất giao dịch mua thẻ trong luồng ngắn và đáng tin. Nếu chỉ tối ưu một tương tác, đó là chuyển từ “tôi muốn mua thẻ” sang “tôi đã nhận được mã thẻ và có thể dùng ngay” với ít bước nhất, ít nghi ngờ nhất.

Core loop:

1. Vào trang dịch vụ từ SEO/ads/chat/webview/menu.
2. Chọn nhà mạng.
3. Chọn mệnh giá và số lượng.
4. Xem chiết khấu, tổng tiền và kênh nhận mã.
5. Xác nhận giao dịch.
6. Thanh toán qua CTT/cổng thanh toán.
7. Nhận mã thẻ/seri trên màn hình thành công, SMS và email nếu có.
8. Copy/lưu mã, mua thêm hoặc liên hệ hỗ trợ nếu có vấn đề.

### Platform Strategy

Dịch vụ được thiết kế ưu tiên cho mobile web và webview, vì phần lớn traffic có thể đến từ quảng cáo, tìm kiếm, Zalo/Messenger/chat hoặc các điểm chạm mobile. Desktop và tablet vẫn cần hỗ trợ đầy đủ nhưng không phải trải nghiệm ưu tiên số một.

Chiến lược nền tảng:

- Mobile-first cho layout, form, CTA và success screen.
- Webview-safe: không phụ thuộc popup/tab mới, hạn chế redirect nhiều tầng, giữ trạng thái đơn hàng khi quay lại từ thanh toán.
- SEO-ready: trang đủ thông tin về dịch vụ, nhà mạng, mệnh giá, chiết khấu và cách nhận mã nhưng không làm chậm luồng mua.
- Design-system-first: kế thừa Viettel Money Web, pattern Data/FTTH/Nạp điện thoại và CTT/cổng thanh toán.
- Guest-first: không yêu cầu đăng nhập/tải app; đăng nhập nếu có chỉ là hỗ trợ thêm, không phải điều kiện hoàn tất mua.

### Effortless Interactions

Các tương tác cần gần như không cần suy nghĩ:

- Chọn nhà mạng bằng logo/tên dễ nhận biết.
- Chọn mệnh giá bằng tile rõ giá trị và ưu đãi.
- Tăng/giảm số lượng bằng stepper, đặc biệt cho mua nhiều thẻ.
- Nhìn ngay được `Tạm tính - Chiết khấu = Tổng thanh toán`.
- Hiểu ngay sẽ nhận mã qua màn hình thành công, SMS và email nếu nhập.
- Xác nhận giao dịch mà không phải đọc quá nhiều nội dung phụ.
- Copy từng mã hoặc copy tất cả sau khi thanh toán thành công.
- Tìm mã giao dịch và kênh hỗ trợ khi gặp lỗi.

Những việc nên tự động hóa hoặc giảm thao tác:

- Tự chọn nhà mạng/mệnh giá mặc định theo cấu hình nếu phù hợp.
- Tự tính lại chiết khấu và tổng tiền khi đổi số lượng/mệnh giá.
- Tự nhóm danh sách mã theo nhà mạng/mệnh giá trên màn thành công.
- Tự hiển thị trạng thái đang xử lý nếu thanh toán/cấp mã chậm.
- Tự ghi nhận trạng thái SMS/email để khách không phải đoán.

### Critical Success Moments

Các khoảnh khắc quyết định trải nghiệm thành công:

1. **First viewport:** khách thấy ngay đây là trang chính thống Viettel Money để mua thẻ, có ưu đãi và có thể mua ngay.
2. **Price clarity:** khách hiểu rõ mệnh giá thẻ, chiết khấu và số tiền phải trả trước khi thanh toán.
3. **Pre-payment confidence:** trước khi sang CTT, khách kiểm tra lại nhà mạng, mệnh giá, số lượng, số điện thoại, email nếu có và tổng tiền.
4. **Payment return:** khi quay lại từ thanh toán, khách thấy trạng thái rõ ràng, không bị bỏ ở màn hình mơ hồ.
5. **Code fulfillment:** sau thanh toán thành công, mã thẻ/seri hiển thị trong dưới 2 giây hoặc có trạng thái đang xử lý rõ.
6. **Multi-card success:** nếu mua nhiều thẻ, khách nhận đủ danh sách mã, không nhầm mệnh giá/số lượng, copy được thuận tiện.
7. **Recovery:** nếu mất webview, SMS/email lỗi hoặc chưa thấy mã, khách có mã giao dịch và hướng dẫn hỗ trợ.

### Experience Principles

- **Mua nhanh nhưng không mơ hồ:** giảm bước thừa, nhưng mọi thông tin tiền/mã/trạng thái phải rõ.
- **Chiết khấu luôn nhìn thấy:** ưu đãi là điểm khác biệt, cần xuất hiện ở chọn mệnh giá, summary và xác nhận.
- **Mua nhiều thẻ phải có trật tự:** danh sách, số lượng, tổng tiền và mã nhận được phải được nhóm rõ trên mobile.
- **Màn thành công là nơi nhận hàng:** ưu tiên mã thẻ/seri, copy, trạng thái gửi SMS/email và mã giao dịch.
- **Không đăng nhập nhưng vẫn cứu được giao dịch:** số điện thoại, email nếu có, mã giao dịch và CSKH flow phải bù cho việc không có tài khoản.
- **Webview là môi trường thật:** thiết kế phải chịu được back, refresh, payment return, mạng yếu và browser hạn chế.

## Desired Emotional Response

### Primary Emotional Goals

Mục tiêu cảm xúc chính là tạo cảm giác **tin tưởng và kiểm soát được giao dịch**. Khách hàng cần cảm thấy đây là trang chính thống, giá/chiết khấu rõ ràng, thanh toán an toàn và mã thẻ sẽ được giao đúng sau khi trả tiền.

Sau khi hoàn tất giao dịch, cảm xúc mong muốn là **nhẹ nhõm và chắc chắn**: khách nhìn thấy mã thẻ/seri, biết mã đã được gửi qua SMS/email nếu có, và có mã giao dịch để được hỗ trợ nếu cần.

### Emotional Journey Mapping

- **Khi vào trang:** khách cần thấy tin cậy, rõ đây là dịch vụ của Viettel Money, không phải trang trung gian không rõ nguồn gốc.
- **Khi chọn nhà mạng/mệnh giá/số lượng:** khách cần thấy thao tác đơn giản, không sợ chọn nhầm, đặc biệt khi mua nhiều thẻ.
- **Khi nhìn chiết khấu/tổng tiền:** khách cần thấy minh bạch, hiểu rõ giá trị thẻ và số tiền thực trả.
- **Trước thanh toán:** khách cần cảm thấy đã kiểm tra đủ thông tin và có thể yên tâm bấm thanh toán.
- **Khi quay lại từ thanh toán:** khách cần thấy trạng thái rõ ràng, không bị rơi vào cảm giác “tiền đã trừ nhưng không biết chuyện gì xảy ra”.
- **Khi nhận mã:** khách cần cảm thấy hoàn tất, có thể dùng mã ngay, copy dễ, không cần tìm kiếm thêm.
- **Khi có lỗi:** khách cần được trấn an bằng trạng thái, mã giao dịch và hướng dẫn tiếp theo, không bị bỏ rơi.

### Micro-Emotions

Các micro-emotions quan trọng:

- **Trust vs. Skepticism:** phải giảm nghi ngờ bằng branding Viettel Money, thông tin giá rõ, trạng thái giao dịch rõ.
- **Confidence vs. Confusion:** mỗi bước cần nói rõ khách đang chọn gì, sẽ trả bao nhiêu, sẽ nhận gì.
- **Control vs. Anxiety:** khách phải kiểm soát được số lượng, tổng tiền, kênh nhận mã và cách xử lý khi lỗi.
- **Relief vs. Panic:** sau thanh toán, màn kết quả cần xuất hiện nhanh hoặc có trạng thái đang xử lý đáng tin.
- **Satisfaction vs. Friction:** copy mã, mua thêm, gửi lại SMS/email và liên hệ hỗ trợ phải dễ làm.

### Design Implications

- **Tin tưởng** → dùng Viettel Money branding rõ, domain/URL chính thống, cổng thanh toán quen thuộc, mã giao dịch và hỗ trợ rõ ràng.
- **Kiểm soát** → hiển thị summary cố định/dễ mở: nhà mạng, mệnh giá, số lượng, chiết khấu, tổng tiền, số điện thoại/email.
- **Minh bạch** → tách rõ `Mệnh giá`, `Chiết khấu`, `Tổng thanh toán`; dùng ví dụ/format tiền dễ hiểu.
- **Nhẹ nhõm** → màn thành công ưu tiên mã thẻ/seri, copy controls, trạng thái SMS/email và hướng dẫn nạp.
- **Không hoảng khi lỗi** → các trạng thái pending/timeout/fail phải có message cụ thể, CTA phù hợp và mã giao dịch.
- **Tự tin khi mua nhiều** → danh sách thẻ nhóm rõ theo nhà mạng/mệnh giá, đánh số mã nếu cần, copy từng mã/copy tất cả.

### Emotional Design Principles

- **Rõ hơn là đẹp hơn:** giao dịch tiền thật cần rõ thông tin trước khi cần trang trí.
- **Không để khách phải đoán:** mọi trạng thái thanh toán/cấp mã/SMS/email phải có nhãn dễ hiểu.
- **Ưu đãi phải tạo tin tưởng, không gây nghi ngờ:** chiết khấu cần minh bạch và nhất quán từ chọn thẻ đến xác nhận.
- **Màn thành công phải làm khách thở phào:** mã hiện rõ, thao tác copy dễ, có bằng chứng giao dịch.
- **Lỗi cũng phải có đường ra:** timeout, pending, gửi SMS/email lỗi đều cần hướng dẫn và kênh hỗ trợ.

## UX Pattern Analysis & Inspiration

### Inspiring Products Analysis

**Viettel Money app/web**

Nguồn tham chiếu chính vì dịch vụ cần kế thừa design system, luồng thanh toán, màn xác nhận giao dịch, màn kết quả giao dịch, ngôn ngữ tin cậy và trạng thái vận hành hiện hữu.

Pattern cần học:

- Màn xác nhận giao dịch có cấu trúc quen thuộc: thông tin dịch vụ, thông tin khách nhập, số tiền, CTA thanh toán.
- Màn kết quả giao dịch theo receipt pattern: trạng thái, mã giao dịch, thông tin thanh toán, hướng dẫn tiếp theo.
- Cách dùng màu sắc, typography, icon, CTA và ngôn ngữ xác nhận cần đồng nhất với Viettel Money để tạo niềm tin.
- Luồng thanh toán/CTT cần được kế thừa tối đa để giảm rủi ro học lại và tăng cảm giác chính thống.

**MoMo/ZaloPay**

Nguồn tham chiếu cho trải nghiệm giao dịch nhanh trên mobile: chọn mệnh giá, nhà mạng, ưu đãi, trạng thái thanh toán và CTA rõ. Khi tham khảo cần phân biệt rõ giữa nạp điện thoại trực tiếp và mua mã thẻ cào để tránh khách hiểu nhầm số điện thoại nhập vào là thuê bao được nạp.

Pattern cần học:

- Tile mệnh giá dễ quét trên mobile.
- Ưu đãi/chiết khấu hiển thị gần quyết định mua.
- CTA chính nổi bật, số bước ít.
- Trạng thái giao dịch sau thanh toán rõ, có hướng dẫn tiếp theo.

**My Viettel/Viettel Telecom**

Nguồn tham chiếu cho cách trình bày sản phẩm viễn thông, nhà mạng, mệnh giá, mã thẻ/serial và hướng dẫn nạp. Đây là nguồn quan trọng để đảm bảo khách hiểu đúng bản chất “mua mã thẻ cào”, không nhầm với nạp trực tiếp.

Pattern cần học:

- Cách trình bày mệnh giá và loại thẻ.
- Cách hiển thị/hướng dẫn sử dụng mã thẻ.
- Cách phân biệt số seri và mã thẻ.
- Ngôn ngữ gần với hành vi nạp thẻ viễn thông của người dùng Việt Nam.

**VNPay/ngân hàng số Việt Nam**

Nguồn tham chiếu cho xác nhận giao dịch tài chính, trạng thái pending/failure, xử lý thanh toán bị gián đoạn và niềm tin trước khi trả tiền.

Pattern cần học:

- Màn xác nhận trước thanh toán có đủ thông tin tiền và người nhận/dịch vụ.
- Trạng thái pending/failed không làm khách hoang mang.
- Mã giao dịch, thời gian giao dịch và hướng dẫn hỗ trợ hiển thị rõ.

**Payoo/cổng top-up hoặc gift-card code flows**

Nguồn tham chiếu cho việc giao mã số sau thanh toán, đặc biệt khi có nhiều mã trong một giao dịch.

Pattern cần học:

- Hiển thị nhiều mã theo danh sách dễ đọc.
- Copy từng mã và copy tất cả.
- Gửi lại qua email/SMS hoặc lưu thông tin nếu được phép.
- Xử lý mã/serial như dữ liệu nhạy cảm.

**Shopee/Lazada Checkout**

Chỉ dùng chọn lọc cho order summary, nhiều item, ưu đãi và tổng tiền. Không dùng làm mô hình checkout chính vì thẻ cào cần tốc độ, sự chắc chắn và ít bước hơn shopping flow.

Pattern có thể học:

- Tách giá trị hàng, ưu đãi/giảm giá và tổng thanh toán.
- Summary nhiều item trước khi trả tiền.
- Cách nhóm item để người dùng kiểm tra nhanh.

Pattern cần tránh:

- Giỏ hàng quá nặng.
- Voucher stacking/cross-sell/upsell làm chậm quyết định mua.
- Nhiều block nội dung làm purchase module bị đẩy xuống dưới.

**Grab/Gojek Receipt Flow**

Chỉ dùng cho receipt, trạng thái giao dịch và hỗ trợ sau giao dịch, không dùng cho purchase flow.

Pattern cần học:

- Receipt là bằng chứng giao dịch, không chỉ là trang cảm ơn.
- Có mã giao dịch, trạng thái, kênh hỗ trợ và hành động sau giao dịch.
- Pending/failed state có ngôn ngữ rõ, tránh khiến khách tự đoán.

### Transferable UX Patterns

**Navigation Patterns**

- First viewport ưu tiên purchase module, không bắt khách đọc nhiều nội dung trước khi mua.
- Luồng chính theo bước tuyến tính: chọn thẻ → nhập thông tin nhận mã → xác nhận → thanh toán → nhận mã.
- Với webview, hạn chế popup/tab mới và giữ CTA rõ trên mobile.
- SEO content đặt sau hoặc xung quanh purchase module, không làm chậm nhiệm vụ mua nhanh.

**Interaction Patterns**

- Chọn nhà mạng trước mệnh giá; nếu có lựa chọn mặc định, cần thể hiện rõ khách vẫn đổi được.
- Denomination tile cho mệnh giá, kèm chiết khấu, giá thanh toán và trạng thái khả dụng/tạm hết.
- Quantity stepper cho số lượng thẻ.
- Multi-card summary: ví dụ `5 thẻ x 100.000đ`, tổng mệnh giá, tổng thanh toán, tổng tiết kiệm.
- Order summary luôn nhìn thấy hoặc dễ mở.
- Confirmation screen trước payment để giảm lỗi chọn nhầm.
- Receipt/success screen có copy từng mã, copy tất cả, serial, trạng thái gửi SMS/email và mã giao dịch.
- Pending/timeout recovery có trạng thái, SLA/hướng dẫn xử lý và kênh hỗ trợ.

**Visual Patterns**

- Branding Viettel Money rõ ở đầu trang và các màn giao dịch.
- Giá trị tiền, chiết khấu và tổng thanh toán dùng phân cấp thị giác rõ.
- Success state dùng màu/trạng thái quen thuộc nhưng ưu tiên mã thẻ/seri hơn nội dung phụ.
- Error/pending state dùng message ngắn, CTA cụ thể và mã giao dịch.
- Danh sách nhiều mã cần chia card/nhóm rõ, không gom thành đoạn dài khó copy.

### Anti-Patterns to Avoid

- Landing page quá dài làm purchase module bị đẩy xuống dưới.
- Hiển thị chiết khấu mơ hồ, không rõ giảm trên mệnh giá nào hoặc điều kiện gì.
- Copy quá sát pattern nạp điện thoại khiến khách hiểu nhầm số điện thoại là thuê bao được nạp trực tiếp.
- Bắt đăng nhập/tải app trong luồng guest checkout.
- Mua nhiều thẻ nhưng không có summary rõ trước thanh toán.
- Cho phép mua nhiều thẻ nhưng receipt gom mã khó đọc hoặc không phân biệt serial/mã thẻ.
- Success screen chỉ báo “thành công” nhưng mã thẻ/seri khó tìm hoặc buộc khách tự tìm trong SMS/email.
- Hiển thị mã thẻ chỉ trong toast/modal tạm thời.
- Không xử lý trường hợp hết hàng theo mệnh giá trước khi thanh toán.
- Không cảnh báo rằng mã thẻ đã mua thường không hoàn/đổi nếu đã phát hành, nếu chính sách này áp dụng.
- Timeout/pending không có hướng dẫn, khiến khách thanh toán lại hoặc liên hệ CSKH trong hoang mang.
- Webview flow phụ thuộc popup, tab mới hoặc redirect nhiều tầng.
- Đẩy người dùng sang app quá sớm làm đứt conversion trên web.

### Design Inspiration Strategy

**Primary inspiration**

- Kế thừa Viettel Money app/web cho design system, payment pattern, receipt, trạng thái giao dịch và trust language.
- Kế thừa MoMo/ZaloPay cho chọn mệnh giá, ưu đãi, CTA mobile-first và trạng thái giao dịch nhanh.
- Kế thừa My Viettel/Viettel Telecom cho ngôn ngữ viễn thông, mệnh giá, mã thẻ/serial và hướng dẫn nạp.

**Secondary inspiration**

- Tham khảo VNPay/ngân hàng số cho xác nhận giao dịch tài chính, pending/failure state và niềm tin trước thanh toán.
- Tham khảo Payoo/top-up code/gift-card flows cho hiển thị nhiều mã, copy mã, gửi lại SMS/email và xử lý mã số nhạy cảm.

**Tertiary inspiration**

- Dùng Shopee/Lazada chỉ cho order summary, nhiều item, chiết khấu và tổng thanh toán.
- Dùng Grab/Gojek chỉ cho receipt, trạng thái giao dịch và hỗ trợ sau giao dịch.

**What to adopt**

- Purchase module ở first viewport.
- Tile mệnh giá kèm chiết khấu.
- Summary rõ trước thanh toán.
- Receipt/success screen như nơi nhận hàng.
- Pending/error state có mã giao dịch và hướng dẫn.

**What to adapt**

- Checkout summary của e-commerce cần rút gọn để phù hợp mua nhanh.
- Receipt của dịch vụ vận chuyển cần chuyển thành fulfillment screen cho mã thẻ/seri.
- Pattern top-up cần điều chỉnh để không gây nhầm giữa “mua mã thẻ” và “nạp trực tiếp”.

**What to avoid**

- Shopping-cart UX nặng.
- Nội dung landing dài làm giảm tốc độ mua.
- Flow app-login/deeplink làm điều kiện hoàn tất mua.
- Receipt thiếu mã thẻ hoặc thiếu khả năng copy/lưu/gửi lại.

## Design System Foundation

### 1.1 Design System Choice

Dịch vụ Mua thẻ cào sử dụng **Viettel Money Design System hiện hữu** làm nền tảng thiết kế. Đây là lựa chọn bắt buộc vì dịch vụ nằm trong `viettelmoney.vn`, cần kế thừa nhận diện thương hiệu, pattern thanh toán, component giao dịch và chuẩn UI/UX đã dùng cho các dịch vụ viễn thông/web payment hiện hữu.

Không tạo design system mới cho MVP. Không dùng Material Design, Ant Design, MUI hoặc hệ thống UI bên ngoài làm nền chính nếu điều đó làm lệch trải nghiệm Viettel Money.

### Rationale for Selection

- **Niềm tin:** khách mua không đăng nhập cần nhận ra đây là dịch vụ chính thống của Viettel Money ngay trong first viewport.
- **Tính nhất quán:** luồng xác nhận, thanh toán và kết quả giao dịch cần quen thuộc với các dịch vụ Data, FTTH, Nạp điện thoại và core payment.
- **Tốc độ triển khai:** dùng lại component/pattern hiện hữu giúp giảm thời gian thiết kế, phát triển và QA.
- **Giảm rủi ro giao dịch:** các pattern đã quen thuộc cho thanh toán, receipt, trạng thái lỗi và hỗ trợ sau giao dịch nên được tái sử dụng.
- **Phù hợp vận hành:** CSKH/Vận hành/Kinh doanh/PO dễ đối chiếu với các dịch vụ hiện hữu trên Viettel Money Web.

### Implementation Approach

Các nhóm component/pattern cần kế thừa:

- Header/branding Viettel Money Web.
- Menu/danh mục dịch vụ viễn thông nếu áp dụng.
- Tab hoặc entry service theo pattern Data/FTTH nếu phù hợp.
- Tile chọn nhà mạng và mệnh giá.
- Form nhập số điện thoại/email với validation inline.
- Bottom sticky CTA trên mobile.
- Order summary/confirmation screen.
- CTT/cổng thanh toán dùng chung.
- Transaction result/receipt pattern.
- Error, pending, timeout và support message pattern.
- Tracking event naming/mapping theo GA/Adjust nếu đã có chuẩn.

Các component cần thiết kế/bổ sung riêng cho Mua thẻ cào:

- Quantity stepper cho số lượng thẻ theo mệnh giá.
- Multi-card summary cho một hoặc nhiều mệnh giá.
- Discount display theo từng mệnh giá và tổng đơn.
- Card-code block trên success screen gồm nhà mạng, mệnh giá, serial, mã thẻ.
- Copy từng mã/copy tất cả.
- Trạng thái gửi SMS/email.
- Hướng dẫn nạp hoặc “Nạp ngay” cho thẻ Viettel nếu được hỗ trợ.
- Recovery/support block khi thanh toán thành công nhưng cấp mã/SMS/email có vấn đề.

### Customization Strategy

Customization chỉ tập trung vào các điểm đặc thù của hàng hóa số là mã thẻ cào:

- **Mua nhiều thẻ:** đảm bảo danh sách thẻ, số lượng, tổng tiền và mã nhận được không rối trên mobile.
- **Mã thẻ nhạy cảm:** thiết kế hiển thị/copy/che mã theo chính sách bảo mật.
- **Chiết khấu:** ưu đãi phải rõ từ chọn mệnh giá đến xác nhận giao dịch.
- **Success screen:** nâng cấp receipt thành màn nhận hàng, ưu tiên mã thẻ/seri.
- **Webview:** component phải hoạt động tốt trong Facebook/TikTok/Zalo/Messenger webview, không phụ thuộc popup/tab mới.
- **SEO/landing:** phần nội dung hỗ trợ SEO không được phá vỡ nhịp mua nhanh.

## 2. Core User Experience

### 2.1 Defining Experience

Defining experience của dịch vụ là: **chọn thẻ nhanh, thấy rõ ưu đãi, thanh toán một lần và nhận mã thẻ dùng được ngay**.

Nếu người dùng kể lại cho người khác, câu mô tả mong muốn là: “Vào web Viettel Money, chọn mệnh giá, thấy giảm giá, thanh toán xong là mã hiện ngay, không cần tải app.”

Tương tác phải được làm tốt nhất là khoảnh khắc chuyển từ **ý định mua** sang **nhận mã chắc chắn**. Toàn bộ UX phải phục vụ khoảnh khắc đó: chọn ít bước, giá rõ, thanh toán đáng tin, mã thẻ hiện nổi bật, copy dễ và có đường hỗ trợ nếu lỗi.

### 2.2 User Mental Model

Người dùng bước vào dịch vụ với mental model quen thuộc từ việc mua/nạp thẻ:

- Chọn nhà mạng.
- Chọn mệnh giá.
- Trả tiền.
- Nhận mã để nạp.

Họ kỳ vọng giao dịch giống mua một hàng hóa số: thanh toán xong phải nhận được mã ngay. Vì không đăng nhập, họ cũng có lo lắng tự nhiên: nếu đóng trang, mất mạng, webview lỗi hoặc SMS không tới thì lấy lại mã bằng cách nào?

Các điểm dễ gây nhầm:

- Số điện thoại nhập vào là số nhận SMS, không nhất thiết là thuê bao được nạp trực tiếp.
- Mệnh giá thẻ khác với số tiền thanh toán sau chiết khấu.
- Mua nhiều thẻ có thể gây nhầm số lượng, mệnh giá và danh sách mã nhận được.
- Thanh toán pending/timeout có thể khiến khách tưởng bị trừ tiền nhưng không nhận thẻ.
- Email là tùy chọn, nhưng có giá trị như kênh nhận lại mã.

### 2.3 Success Criteria

Core experience thành công khi:

- Khách hiểu trong first viewport rằng đây là trang chính thống Viettel Money để mua thẻ cào.
- Khách chọn được nhà mạng/mệnh giá/số lượng mà không cần hướng dẫn.
- Khách nhìn thấy rõ `Mệnh giá`, `Chiết khấu`, `Tổng thanh toán`.
- Khách biết sẽ nhận mã trên màn hình thành công và qua SMS; email nếu nhập.
- Khách xác nhận giao dịch mà không sợ chọn nhầm.
- Sau thanh toán, mã thẻ/seri hiển thị nhanh, dễ đọc, dễ copy.
- Với mua nhiều thẻ, danh sách mã được nhóm rõ và có copy từng mã/copy tất cả.
- Nếu lỗi/pending/timeout, khách thấy trạng thái, mã giao dịch và hướng dẫn tiếp theo.

### 2.4 Novel UX Patterns

Dịch vụ không cần tạo interaction hoàn toàn mới. Nên dùng các pattern quen thuộc:

- Tile chọn nhà mạng/mệnh giá.
- Stepper số lượng.
- Order summary.
- Confirmation screen.
- Payment redirect/return.
- Receipt/success screen.
- Error/pending state.

Điểm mới nằm ở cách kết hợp các pattern cho guest checkout và hàng hóa số nhạy cảm:

- Receipt không chỉ là biên nhận mà là nơi nhận mã thẻ.
- Multi-card summary cần rõ như checkout nhưng nhẹ hơn e-commerce.
- Mã thẻ/seri cần vừa nổi bật vừa có nguyên tắc bảo mật.
- Guest flow cần cơ chế recovery bằng số điện thoại/email/mã giao dịch thay cho lịch sử tài khoản.

### 2.5 Experience Mechanics

**1. Initiation**

Khách bắt đầu từ SEO, ads/webview, chat link, email/campaign hoặc menu dịch vụ. First viewport cần cho thấy ngay:

- Viettel Money branding.
- Dịch vụ Mua thẻ cào.
- Nhà mạng/mệnh giá.
- Ưu đãi/chiết khấu nếu có.
- CTA bắt đầu mua.

**2. Interaction**

Khách thực hiện:

- Chọn nhà mạng.
- Chọn một hoặc nhiều mệnh giá.
- Tăng/giảm số lượng bằng stepper.
- Nhập số điện thoại nhận SMS.
- Nhập email nếu muốn nhận thêm mã.
- Kiểm tra summary.
- Xác nhận và thanh toán.

Hệ thống phản hồi ngay khi khách thay đổi lựa chọn:

- Cập nhật chiết khấu.
- Cập nhật tổng thanh toán.
- Cập nhật số lượng mã sẽ nhận.
- Hiển thị lỗi inline nếu số điện thoại/email sai định dạng.
- Hiển thị trạng thái tạm hết nếu mệnh giá/nhà mạng không khả dụng.

**3. Feedback**

UX cần phản hồi rõ ở từng bước:

- Selected state cho nhà mạng/mệnh giá.
- Summary hiển thị tổng số thẻ và tổng tiền.
- Confirmation screen trước CTT.
- Loading/processing state khi chuyển thanh toán hoặc chờ cấp mã.
- Success/fail/pending state sau khi quay lại từ thanh toán.

**4. Completion**

Giao dịch hoàn tất khi khách thấy:

- Trạng thái thành công.
- Mã giao dịch.
- Danh sách mã thẻ/seri.
- Tổng tiền và chiết khấu.
- Trạng thái gửi SMS/email.
- Copy controls.
- Hướng dẫn nạp hoặc “Nạp ngay” nếu có.
- Mua thêm hoặc liên hệ hỗ trợ.

**5. Recovery**

Nếu giao dịch không hoàn tất bình thường:

- Pending: hiển thị đang xử lý, mã giao dịch, hướng dẫn chờ/tra cứu.
- Payment failed/cancelled: hiển thị thất bại, CTA thử lại hoặc quay về chọn thẻ.
- Payment success but card issuing pending: nói rõ đã thanh toán thành công, mã đang được xử lý, không khuyến khích thanh toán lại ngay.
- SMS/email failed: mã vẫn hiển thị trên màn hình nếu đã cấp thành công, đồng thời có hướng dẫn hỗ trợ/gửi lại nếu được phép.

## Visual Design Foundation

### Color System

Dịch vụ sử dụng color system hiện hữu của Viettel Money. Màu sắc cần ưu tiên nhận diện thương hiệu, độ tin cậy trong giao dịch và khả năng đọc rõ trên mobile/webview.

Nguyên tắc sử dụng màu:

- **Primary color:** dùng theo Viettel Money brand cho CTA chính, selected state và điểm nhấn giao dịch.
- **Neutral colors:** dùng cho nền, text, border, divider và card để giữ giao diện rõ, không gây nhiễu khi khách kiểm tra tiền/mã.
- **Success color:** dùng cho trạng thái thanh toán/cấp mã thành công.
- **Warning color:** dùng cho pending, đang xử lý, thay đổi giá/chiết khấu hoặc mệnh giá tạm hết.
- **Error color:** dùng cho thanh toán thất bại, lỗi nhập liệu, cấp mã thất bại hoặc gửi SMS/email lỗi.
- **Discount/highlight color:** dùng tiết chế để nhấn chiết khấu, số tiền tiết kiệm và ưu đãi, không được cạnh tranh với CTA thanh toán.

Mã thẻ/seri là nội dung nhạy cảm nên không dùng màu trang trí quá mạnh. Block mã thẻ cần nổi bật bằng hierarchy, spacing và label rõ hơn là hiệu ứng màu.

### Typography System

Typography kế thừa Viettel Money Design System. Tone chữ cần rõ ràng, tin cậy, ngắn gọn và thân thiện, phù hợp giao dịch tài chính trên mobile.

Nguyên tắc typography:

- Heading dùng để định hướng bước: Mua thẻ cào, Xác nhận giao dịch, Thanh toán đang xử lý, Giao dịch thành công.
- Body text ngắn, trực tiếp, tránh mô tả dài trong luồng mua.
- Số tiền, mệnh giá, chiết khấu và mã thẻ/seri cần có hierarchy riêng, dễ quét.
- Error/pending message dùng câu ngắn, nói rõ trạng thái và hành động tiếp theo.
- Font size tối thiểu trên mobile cần đủ đọc, không buộc khách zoom trong webview.
- Mã thẻ/seri nên dùng kiểu hiển thị dễ phân biệt ký tự, hỗ trợ copy và giảm đọc nhầm.

### Spacing & Layout Foundation

Layout ưu tiên mobile-first, thao tác nhanh, thông tin giao dịch rõ và ít nhiễu.

Nguyên tắc spacing/layout:

- First viewport cần hiển thị được dịch vụ, nhà mạng/mệnh giá hoặc entry mua, ưu đãi chính và CTA.
- Các nhóm thông tin chính tách bằng card/section rõ: chọn thẻ, thông tin nhận mã, summary, xác nhận, kết quả.
- Khoảng cách giữa các tile mệnh giá đủ để thao tác bằng tay trên mobile.
- Bottom sticky CTA được dùng khi phù hợp, nhưng không che tổng tiền, mã thẻ hoặc lỗi form.
- Multi-card summary cần nhóm theo nhà mạng/mệnh giá, tránh danh sách dài không cấu trúc.
- Success screen ưu tiên block mã thẻ/seri ở vùng dễ thấy, thông tin phụ đặt sau.
- SEO content/FAQ đặt sau purchase module hoặc dưới luồng chính để không làm chậm mua nhanh.

### Accessibility Considerations

Dịch vụ cần tuân thủ chuẩn UI/UX/accessibility của Viettel Money; nếu chưa có chuẩn nội bộ cụ thể, dùng WCAG 2.1 AA làm baseline cho các màn giao dịch chính.

Yêu cầu accessibility:

- Text và CTA đạt tương phản đủ trên mobile/webview.
- Form số điện thoại/email có label, hint và lỗi inline rõ.
- Không chỉ dùng màu để biểu thị selected/error/success; cần có label/icon/trạng thái đi kèm.
- Button copy mã cần có nhãn rõ, trạng thái sau copy và vùng bấm đủ lớn.
- Nội dung quan trọng như tổng tiền, chiết khấu, mã giao dịch, mã thẻ/seri không được bị che bởi sticky CTA hoặc keyboard.
- Pending/error state cần có text dễ hiểu, không chỉ icon.
