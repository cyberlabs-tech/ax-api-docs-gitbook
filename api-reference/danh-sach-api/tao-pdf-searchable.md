---
description: Api cho phép chuyển đổi file imgae hoặc pdf thành PDF Searchable.
---

# Tạo PDF Searchable

## Cài đặt API

{% swagger method="post" path="/ocr/pdfSearchable" baseUrl="https://axt.cyberapis.com" summary="Tạo PDF Searchable" %}
{% swagger-description %}
Nhận dạng văn bản chữ tiếng Việt
{% endswagger-description %}

{% swagger-parameter in="query" name="chartype" type="String" required="true" %}
text: Chữ in

handwri: Chữ viết tay \
mix: Cả chữ in và chữ viết tay(mặc định).
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" required="false" %}
Mã file, xác định tính duy nhất của file đầu vào(có thể để trống).
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-Sender" type="String" required="true" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Thành công" %}
```javascript
chuỗi Base64 của PDF 
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark>` `<mark style="color:yellow;">``</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>.
{% endhint %}

#### Thông tin trả về

Kết quả trả về là một chuỗi `Base64` là PDF Searchable đầu ra.
