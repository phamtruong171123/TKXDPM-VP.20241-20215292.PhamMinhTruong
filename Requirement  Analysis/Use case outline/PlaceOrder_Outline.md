# Place Order Use Case Outline

## Basic Flow

1. **Khách hàng chọn sản phẩm**:
   - Khách hàng duyệt danh sách sản phẩm và chọn sản phẩm muốn mua.
   - Khách hàng thêm sản phẩm vào giỏ hàng với số lượng mong muốn.

2. **Xem lại giỏ hàng**:
   - Khách hàng truy cập vào giỏ hàng để kiểm tra số lượng và tổng giá các sản phẩm.
   - Phần mềm hiển thị danh sách sản phẩm, số lượng, và tổng giá (chưa bao gồm VAT).

3. **Kiểm tra tồn kho**:
   - Phần mềm kiểm tra số lượng tồn kho cho từng sản phẩm trong giỏ hàng.
   - Nếu có sản phẩm nào không đủ số lượng, phần mềm yêu cầu khách hàng cập nhật lại giỏ hàng.

4. **Nhập thông tin giao hàng**:
   - Khách hàng cung cấp thông tin giao hàng: tên người nhận, email, số điện thoại, tỉnh/thành phố, và địa chỉ giao hàng.
   - Phần mềm kiểm tra thông tin và yêu cầu cập nhật nếu có thông tin thiếu hoặc không hợp lệ.

5. **Tính toán phí giao hàng**:
   - Phần mềm tính toán phí giao hàng dựa trên trọng lượng sản phẩm và vị trí giao hàng.
   - Phí giao hàng được hiển thị cho khách hàng trước khi thanh toán.

6. **Chọn phương thức thanh toán**:
   - Khách hàng chọn phương thức thanh toán qua VNPay bằng thẻ tín dụng.
   - Phần mềm kết nối với VNPay để xử lý thanh toán.

7. **Lưu thông tin hóa đơn và thanh toán**:
   - Phần mềm lưu trữ thông tin hóa đơn tạm thời, bao gồm danh sách sản phẩm, số lượng, giá sản phẩm, tổng giá chưa bao gồm VAT, tổng giá bao gồm VAT, phí giao hàng, và tổng số tiền thanh toán.
   - Khách hàng cung cấp thông tin thanh toán theo yêu cầu của VNPay.

8. **Hoàn tất và gửi thông tin đơn hàng**:
   - Sau khi thanh toán thành công, phần mềm gửi thông tin đơn hàng và hóa đơn qua email cho khách hàng.
   - Đơn hàng được đánh dấu là đang chờ xử lý và ghi nhận thông tin giao dịch thanh toán.

## Alternative Flows

- **Số lượng tồn kho không đủ**:
  - Nếu số lượng tồn kho không đủ cho sản phẩm trong giỏ hàng, phần mềm yêu cầu khách hàng cập nhật lại giỏ hàng.
  - Khách hàng phải điều chỉnh số lượng sản phẩm hoặc xóa sản phẩm khỏi giỏ hàng trước khi tiếp tục.

- **Thông tin giao hàng không hợp lệ**:
  - Nếu thông tin giao hàng không đầy đủ hoặc không hợp lệ, phần mềm yêu cầu khách hàng nhập lại thông tin chính xác.
  - Phần mềm sẽ thông báo lỗi và yêu cầu sửa chữa thông tin.

- **Thanh toán thất bại**:
  - Nếu quá trình thanh toán qua VNPay thất bại, phần mềm thông báo lỗi và yêu cầu khách hàng thử lại.
  - Khách hàng có thể kiểm tra thông tin thẻ tín dụng và thử thanh toán lại.

- **Khách hàng hủy đơn hàng**:
  - Trong quá trình đặt hàng, nếu khách hàng thay đổi ý định và muốn hủy đơn hàng, họ có thể thực hiện việc hủy đơn hàng trước khi đơn hàng được phê duyệt.
  - Khách hàng sẽ nhận được thông báo xác nhận việc hủy đơn hàng và số tiền sẽ được hoàn trả đầy đủ.

- **Rush Order Delivery**:
  - Nếu khách hàng chọn dịch vụ giao hàng gấp và địa chỉ giao hàng không nằm trong khu vực hỗ trợ, phần mềm sẽ yêu cầu khách hàng cập nhật lại địa chỉ hoặc phương thức giao hàng.
  - Nếu chỉ một số sản phẩm đủ điều kiện giao hàng gấp, các sản phẩm này sẽ được giao riêng và phí giao hàng sẽ được tính riêng biệt.

