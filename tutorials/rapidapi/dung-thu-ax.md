# Dùng thử AX

## Truy cập trang của AX

Bạn có thể truy cập bằng một trong các cách sau:

* Tìm kiếm trên [trang chợ APIs](https://rapidapi.com/hub) với từ khóa `vietnam ocr` và click vào kết quả đầu tiên.

![Search "vietnam ocr"](<../../.gitbook/assets/image (16).png>)

* hoặc truy cập đường dẫn [trực tiếp](https://rapidapi.com/cybereyetech/api/cyber-eye-ocr-handwritting-recognition/).

## Tạo thử request

![Test endpoint](<../../.gitbook/assets/image (1).png>)

Sau khi truy cập, bạn sẽ thấy giao diện cho phép dùng thử các API.

* Bên trái màn hình là danh sách các endpoints mà AX cung cấp.

![Danh sách endpoint mà AX cung cấp trên RapidAPI](<../../.gitbook/assets/image (10).png>)

* Khung giữa là nơi điền các tham số để tạo request.
* Bên phải là khung hiển thị kết quả trả về.

{% hint style="info" %}
Bạn có thể chọn bất kỳ endpoint nào để trải nghiệm thử công nghệ của chúng tôi.
{% endhint %}

## Tạo request

Để tạo request, trên giao diện của RapidAPI, bạn cần điền 3 tham số trong body của request gồm:

* `fileId`: một unique id cho file của bạn.
* `fileExtension`: định dạng file của bạn, có thể là `pdf | jpg | png ...`
* `fileBase64`: mã `base64` của file.&#x20;

Các file cần nhận dạng thường là file ảnh hoặc pdf. Để chuẩn hóa đầu vào, các tính năng nhận dạng AX cung cấp có chung định dạng là `base64` của file ảnh hoặc pdf. Do đó, trước khi thực hiện request, bạn cần encode file thành dạng base64.

![Điền tham số request](<../../.gitbook/assets/image (5) (1).png>)

Sau khi điền đủ tham số, bạn có thể bấm nút **Test Endpoint** để nhận kết quả trả về từ AX.

{% hint style="info" %}
Nếu bạn không có sẵn file để thử, bạn có thể sử dụng file mà chúng tôi đã tạo sẵn và chỉ cần bấm nút **Test Endpoint**.
{% endhint %}

## Kết quả trả về

{% hint style="info" %}
Tùy từng endpoint, thời gian trả về kết quả có thể tử vài trăm _miliseconds_ tới và vài _seconds_.
{% endhint %}

Kết quả trả về body có dạng json bao gồm các thông tin nhận dạng được kèm độ tin cậy của từng trường thông tin.

![response's body](<../../.gitbook/assets/image (4) (1).png>)
