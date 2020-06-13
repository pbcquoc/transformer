# Tìm hiểu mô hình Transformer 
## Transformer - Ngươi Không Phải Là Anh Hùng, Ngươi Là Quái Vật Nhiều Đầu.


Trong [blog](https://pbcquoc.github.io/transformer/) này, mình sẽ trình bày chi tiết cách mô hình Transformer hoạt động, cũng như là cách cài đặt mô hình chi tiết cho những bạn mới có kiến thức cơ bản về deep learning như CNN hoặc LSTM cũng có thể hiểu được.<br/><br/>Sự nổi tiếng của mô hình Transformer thì không cần phải bàn cãi, vì nó chính là nền tảng của rất nhiều mô hình khác mà nổi tiếng nhất là BERT (Bidirectional Encoder Representations from Transformers) một mô hình dùng để học biểu diễn của các từ tốt nhất hiện tại và đã tạo ra một bước ngoặc lớn cho động đồng NLP trong năm 2019. Và chính Google cũng đã áp dụng BERT trong cỗ máy tìm kiếm của họ. Để hiểu BERT, các bạn cần phải nắm rõ về mô hình Transformer.

<p align="center">
<img src="https://pbcquoc.github.io/images/transformer/bert.jpg" >
</p>

Ý tưởng chủ đạo của Transformer vẫn là áp dụng cơ thể Attention, những ở mức phức tạp hơn và thật sự là thú vị hơn so với cách được đề xuất trước đó trong một [bài báo](https://arxiv.org/abs/1508.04025) của tác giả Lương Minh Thắng, một người Việt rất nổi tiếng trong cộng đồng deep learning. 

# Tổng Quan Mô Hình
Để cho dễ cảm nhận được cách mà mô hình hoạt động, mình sẽ trình bày trước toàn bộ kiến trúc mô hình ở mức high-level và sau đó sẽ đi chi tiết từng phần nhỏ cũng như công thức toán của nó. 

Giống như những mô hình dịch máy khác, kiến trúc tổng quan của mô hình transformer bao gồm 2 phần lớn là encoder và decoder. Encoder dùng để học vector biểu của câu với mong muốn rằng vector này mang thông tin hoàn hảo của câu đó. Decoder thực hiện chức năng chuyển vector biểu diễn kia thành ngôn ngữ đích.

Trong ví dụ ở dưới, encoder của mô hình transformer nhận một câu tiếng việt, và encode thành một vector biểu diễn ngữ nghĩa của câu <i>little sun</i>, sau đó mô hình decoder nhận vector biểu diễn này, và dịch nó thành câu tiếng việt <i>mặt trời bé nhỏ</i>

<p align="center">
<img src="https://pbcquoc.github.io/images/transformer/overview.jpg" >
</p>

Một trong những ưu điểm của transformer là mô hình này có khả năng xử lý song song cho các từ. Như các bạn thấy, Encoders của mô hình transfomer là một dạng feedforward neural nets, bao gồm nhiều encoder layer khác, mỗi encoder layer này xử lý đồng thời các từ. Trong khi đó, với mô hình LSTM, thì các từ phải được xử lý tuần tự. Ngoài ra, mô hình Transformer còn xử lý câu đầu vào theo 2 hướng mà không cần phải stack thêm một môt hình LSTM nữa như trong kiến trúc Bidirectional LSTM. 

<p align="center">
<img src="https://pbcquoc.github.io/images/transformer/overview2.jpg" >
</p>

Một cái nhìn vừa tổng quát và chi tiết sẽ giúp ích cho các bạn. Mình sẽ đi vào chi tiết một số phần cực kì quan trọng như sinusoidal position encoding, multi head attention của encoder, còn của decoder thì các bạn thấy được kiến trúc rất giống với của encoder, do đó mình sẽ chỉ đi nhanh qua mà thôi. 

<p align="center">
<img src="https://pbcquoc.github.io/images/transformer/overview3.jpg" >
</p>

[Read More](https://pbcquoc.github.io/transformer/)
# Dataset
Mình cung cấp sẵn cho các bạn một dữ liêu [en-vi](https://drive.google.com/file/d/1Fuo_ALIFKlUvOPbK5rUA5OfAS2wKn_95/view) tương đối lớn gồm 600k câu được thu thập và xử lý trên TED.

Hy vọng với bộ dữ liệu này, các bạn sẽ không phải khó khăn khi tìm kiếm dữ liệu để học hỏi. 

# Implementation
Các bạn hãy xem file [notebook](https://github.com/pbcquoc/transformer/blob/master/transformer.ipynb) trên nhé.

## Problem
Nếu có bất kì vấn đề gì, các bạn có thể liên hệ với mình @ pbcquoc@gmail.com


