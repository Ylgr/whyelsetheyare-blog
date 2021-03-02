---
title: "Blockchain ký sự - Phần 3: Chữ ký số và các giao dịch"
date: 2021-03-01T05:40:49.328Z
toc: true
featured_image: /images/finance-money-transaction-technology_31965-1134.jpg
tags:
  - blockchain
  - crytocurrency
---
# 1. Transaction là gì?

Transaction (giao dịch) là danh từ đề cập đến sự kiện điều kiện để biến đổi số dư của một tài khoản. Trong Blockchain cũng không ngoại lệ, nó là bản ghi chép dữ liệu chuyển tiền, nhận tiền hay việc kích hoạt làm thay đổi trạng thái của smart contract nào đó (việc này thông thường sẽ tốn phí gas với các mạng như ethereum hay bandwidth với các mạng như EOS).

Transaction trên Blockchain được chia làm 3 loại khác nhau để giải quyết bài toán tránh trùng lặp giao dịch: UTXO, nonce và các loại khác.

# 2. Giải thích hoạt động của transaction

## 2.1. UTXO

Coin điển hình BTC, LTC, BCH, QTUM.

Là kiểu định nghĩa giao dịch đầu tiên của transaction. Một UTXO bao gồm các thông số: input, output, timestamp, hash,....

Khi mỗi giao dịch được thực hiện, sẽ cần require một hoạch nhiều UTXO làm input và sẽ có không hoặc nhiều UTXO khác làm ouput. Ví dụ, khi bạn thực hiện một giao dịch 0.1 BTC, tại thời điểm đó hệ thống đã thống kê bạn có 3 UTXO khác còn lại là 0.06 BTC, 0.03 BTC và 0.05 BTC. Tại thời điểm này giả sử thuật toán ví đã xử lý và chọn 0.06 BTC và 0.03 BTC làm UTXO input, khi đó output sẽ là 0.1 BTC được chuyển đi là 0.02 BTC nhận lại.

Đơn vị sử dụng cho phí giao dịch của những coin này là satoshis/byte. Đồng nghĩa với việc transaction càng ít input và output sẽ càng tiếp kiến chi phí.

Thực tế này đòi hỏi các nhà làm ví cần tìm ra thuật toán tối ưu chọn UTXO cho ví của mình để tối thiểu hóa số tiền phí của user. Vì nhiều trường hơp, cùng gửi 1 số tiền mà user phải chịu 2 khoản phí khác nhau trong khi trả cùng lượng byte fee.

Bằng cách sử dụng UTXO, user có thể revert lại transaction vừa thực hiện (mà chưa được verify) bằng cách sử dụng đúng input của transaction trước và thay thế output đầu ra (yêu cầu tăng byte fee trả cho mạng lưới). Khi đó transaction có fee lớn hơn sẽ được thực hiện trước làm transaction trước đó vi phạm rule và phải revert.

## 2.2. Nonce

Thay vì lưu số dư vào các UTXO, những loại crypto phổ biến khác như ETH, EOS, TROX, ... đã chọn cách xử lý số dư của user trực tiếp trên tài khoản. Khi đó họ cần xử dụng một con số "nonce" để đánh dấu và định danh transaction. Mỗi transaction sẽ có một "nonce" khác nhau và nonce sau yêu cầu cao hơn nonce trước. Bằng cách này transaction sẽ không phải chịu khoản byte fee như kiến trúc UTXO.

Khi sử dụng nonce, ta hoàn toàn có thể revert transaction (pending) bằng cách thực hiện một transaction tương tự cùng số nonce với transaction cũ nhưng thêm fee bỏ ra cho transacction, cách hoạt động tương tự với UTXO.

## 2.3. Khác

Vì khác nên cũng đa dạng lắm loại không như 2 loại trên. Điển hình như những token được xử lý trên mạng Omni.

Omni về bản chất không phải là một blockchain tự vận hành. Sự vận hành của Blockchain này về bản chất là ánh xạ từ Bitcoin sang. Omni bất giờ chỉ đóng vai trò sở hữu những đồng coin trên mạng lưới đó. Lấy ví dụ khi user muốn thực hiện gửi USDT của mình đi, họ phải thực hiện một transaction mà trong đó output của UTXO sẽ là khoản dust 512 satoshis BTC, địa chỉ nhận BTC và mã coin id của USDT là 31 vào output của UTXO.

Nói cách khác Omni sẽ không trực tiếp xử lý giao dịch mà nhờ BTC xác nhận giao dịch và ghi chép lại biến đổi vào số dư người dùng.



# 3. Chữ ký số