---
title: "Blockchain ký sự phần 2: Bản chất"
date: 2021-02-15T04:19:20.205Z
toc: true
featured_image: https://builtin.com/sites/default/files/styles/medium/public/2019-01/blockchain-companies.jpg
tags:
  - blockchain
---
# 1. Đặc điểm cấu tạo

Blockchain về bản chất là một công nghệ ghép nối từ 3 dạng công nghệ đã có từ trước đó bao gồm: Mật mã học (cryptography), mạng ngang hàng (P2P network) và giao thức lý thuyết trò chơi (game theory protocol).

## 1.1. Cryptography

Cryptography trong một Blockchain network có vai trò khá rộng lớn từ việc làm định danh đến chuẩn giao tiếp cho đến dữ liệu. Nói nôm na đó là cách mà cách các nodes trong mạng nhận dạng nhau, cách lưu dữ liệu vào trong block, cách lưu block vào chain, cách mở / khóa block, ... cho đến cách mà một người sở hữu một loại tài sản nào đó trong mạng lưới.

Bài viết này sẽ chỉ dừng ở cấp độ giới thiệu khái quát, ta sẽ có một chủ đề chuyên sâu về Cryptography sau này.

## 1.2. P2P network

Thông thường, với các hệ thống cơ bản sẽ được bố trí phân phối theo hình thức giao tiếp Client-Server. Với nhiều hệ thống Blockchain, điều này không phải là ngoại lệ nhưng về tổng quan thì không phải. Với phần đa các giao thức Blockchain phổ biến, các node sẽ làm việc với nhau bằng mạng ngang hàng (p2p network). Những Blockchain thế hệ 3.0 hay có sáng tạo bằng việc kết hợp p2p network và client-server thành giao thức hỗn hợp nhưng tổng quan lại thì nhắc đến Blockchain thì sẽ mặc định trước hết là giao thức p2p network.

## 1.3. Game theory protocol

Lý thuyết trò chơi là một trong những chủ đề hot trong giới toán học và kinh tế học, với công nghệ nó cũng là phần không thể thiếu. Trong game theory protocol của Blockchain, những người tham gia đóng vai trò duy trình mạng lưới sẽ bằng cách này hay cách khác nhận được lợi ích từ nó. VD như trong một mạng Proof of Work, các node sẽ đóng vai trò làm miners để xác thực giao dịch và tìm ra đoạn hash khóa block, Node nào tìm ra đoạn hash khóa block sẽ nhận được một lượng coin của mạng lưới làm phần thưởng.

Game theory là một chủ đề rất thú vị, chúng ta sẽ bàn luận nhiều hơn về nó.

# 2. Hình thức hoạt động

Trong giới Blockchain, chúng ta đã có rất nhiều loại Blockchain với những cách hoạt động gần giống nhau. Nên để diễn tả chung về quy trình làm việc, mình sẽ lấy VD về ông tổ của Blockchain: Bitcoin.

![](https://www.weusecoins.com/images/bitcoin-transaction-life-cycle-high-resolution.png)

Trình tự ở đây sẽ là:

\- Sender tạo transaction request gửi BTC cho Receiver và ký request đó bằng private key để có được raw transaction (là chuỗi ký tự hex dữ liệu).

\- Sender đẩy transaction lên 1 node của mạng Blockchain, node đó sẽ đẩy thông tin transaction lên Bitcoin network.

\- Transaction được xác thực để đảm bảo thông tin gửi đi là xác minh (địa chỉ gửi hợp lệ, địa chỉ nhận hợp lệ, số dư gửi đi hợp lệ, nonce hợp hệ, ...).

\- Khi đã đủ số lượng node verify, transaction sẽ được đẩy vào Block.

\- Block chờ đủ blocktime sẽ được miner tìm ra đoạn hash khóa block (miner nhận được phần thưởng BTC từ việc tính toán ra hash).

\- Block có khóa sẽ gắn vào chain và dữ liệu từ đó sẽ bất biến và tồn tại vĩnh viễn cùng với chain. 

\- Receiver nhận được BTC.

# 3. Tính bảo mật, độ an toàn



# 4. Phân loại