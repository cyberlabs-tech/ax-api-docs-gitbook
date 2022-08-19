---
description: >-
  API cho phép nhận dạng các files ảnh hoặc pdf sau đó tự động bóc tách các
  thông tin cần thiết trong những files đó.
---

# Trích xuất thông tin

## **Văn bản hành chính**

{% swagger method="post" path="/ocr/vbhc" baseUrl="https://ax.cyberapis.com" summary="Process VBHC" %}
{% swagger-description %}
API trả các thông tin như nội bộ ban hành, số, ký hiệu, địa điểm, ngày ban hành... của văn bản hành chính.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-Sender" required="true" type="String" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" %}
Mã file, xác định tính duy nhất của file đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Ví dụ thành công" %}
```javascript
[
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "noiBanHanh",
        "Value": "BỘ HỌC VÀ CÔNG NGHỆ",
        "Confidence": 0.8309705
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "noiBanHanh_Goc",
        "Value": "BỘKHOA HỌC VÀ CÔNG NGHỆ",
        "Confidence": 0.8309705,
        "ValueInfos": [
            {
                "Text": "BỘKHOA HỌC VÀ CÔNG NGHỆ",
                "Line": 0,
                "X": 26,
                "Y": 41,
                "Width": 707,
                "Height": 68,
                "PageWidth": 754,
                "PageHeight": 155,
                "LineConfidence": 0.8309705
            }
        ]
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "soVaKyHieu_Goc",
        "Value": "Số:5t6/QĐ-BKHCN",
        "Confidence": 0.604783654,
        "ValueInfos": [
            {
                "Text": "Số:5t6/QĐ-BKHCN",
                "Line": 0,
                "X": 5,
                "Y": 23,
                "Width": 558,
                "Height": 78,
                "PageWidth": 582,
                "PageHeight": 120,
                "LineConfidence": 0.604783654
            }
        ]
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "so",
        "Value": "56",
        "Confidence": 0.604783654
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "kyHieu",
        "Value": "QĐ-BKHCN",
        "Confidence": 0.604783654
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "soVaKyHieu",
        "Value": "56/QĐ-BKHCN",
        "Confidence": 0.604783654
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "diaDiemVaNgayBanHanh_Goc",
        "Value": "Hà Nội, ngày 06 tháng 3 năm2020",
        "Confidence": 0.480032563,
        "ValueInfos": [
            {
                "Text": "Hà Nội, ngày 06 tháng 3 năm2020",
                "Line": 0,
                "X": 46,
                "Y": 21,
                "Width": 887,
                "Height": 75,
                "PageWidth": 970,
                "PageHeight": 119,
                "LineConfidence": 0.480032563
            }
        ]
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "diaDiemVaNgayBanHanh",
        "Value": "Hà Nội, ngày 06 tháng 03 năm 2020",
        "Confidence": 0.480032563
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "diaDiemBanHanh",
        "Value": "Hà Nội",
        "Confidence": 0.480032563
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "ngayBanHanh",
        "Value": "06/03/2020",
        "Confidence": 0.480032563
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "loaiVanBan_tieuDeTrichYeu",
        "Value": "QUYẾT ĐINH\r\nBan hành Kế hoạch theo dõi tình hình thi hành pháp luật năm 2020\r\ncủa Bộ Khoa học và Công nghệ”",
        "Confidence": 0.13111271,
        "ValueInfos": [
            {
                "Text": "QUYẾT ĐINH",
                "Line": 0,
                "X": 735,
                "Y": 52,
                "Width": 398,
                "Height": 60,
                "PageWidth": 1876,
                "PageHeight": 326,
                "LineConfidence": 0.9965884
            },
            {
                "Text": "Ban hành Kế hoạch theo dõi tình hình thi hành pháp luật năm 2020",
                "Line": 1,
                "X": 38,
                "Y": 117,
                "Width": 1788,
                "Height": 75,
                "PageWidth": 1876,
                "PageHeight": 326,
                "LineConfidence": 0.263179064
            },
            {
                "Text": "của Bộ Khoa học và Công nghệ”",
                "Line": 2,
                "X": 511,
                "Y": 189,
                "Width": 845,
                "Height": 71,
                "PageWidth": 1876,
                "PageHeight": 326,
                "LineConfidence": 0.499893636
            }
        ]
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "loaiVanBan",
        "Value": "Quyết định",
        "Confidence": 0.13111271
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "tieuDeTrichYeu",
        "Value": "Ban hành Kế hoạch theo dõi tình hình thi hành pháp luật năm 2020\ncủa Bộ Khoa học và Công nghệ”",
        "Confidence": 0.13111271
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "noiNhan",
        "Value": "- Như Điều 3\n- Bộ trưởng (đê b/c)\n- Lưu: VT. PC",
        "Confidence": 0.222352073
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "noiNhan_Goc",
        "Value": "Nơi nhận:\r\n- Như Điều 3:\r\n- Bộ trưởng (đê b/c):\r\n- Lưu: VT. PC",
        "Confidence": 0.222352073,
        "ValueInfos": [
            {
                "Text": "Nơi nhận:",
                "Line": 0,
                "X": 28,
                "Y": 64,
                "Width": 240,
                "Height": 41,
                "PageWidth": 464,
                "PageHeight": 357,
                "LineConfidence": 0.951060534
            },
            {
                "Text": "- Như Điều 3:",
                "Line": 1,
                "X": 15,
                "Y": 114,
                "Width": 290,
                "Height": 44,
                "PageWidth": 464,
                "PageHeight": 357,
                "LineConfidence": 0.603409946
            },
            {
                "Text": "- Bộ trưởng (đê b/c):",
                "Line": 2,
                "X": 13,
                "Y": 167,
                "Width": 415,
                "Height": 45,
                "PageWidth": 464,
                "PageHeight": 357,
                "LineConfidence": 0.817341
            },
            {
                "Text": "- Lưu: VT. PC",
                "Line": 3,
                "X": 16,
                "Y": 221,
                "Width": 292,
                "Height": 42,
                "PageWidth": 464,
                "PageHeight": 357,
                "LineConfidence": 0.4740425
            }
        ]
    },
    {
        "Page": 0,
        "IsVBHCField": true,
        "Type": "nguoiKy",
        "Value": "Bùi Thế Duy",
        "Confidence": 0.364318281
    },
    {
        "Page": 0,
        "IsVBHCField": false,
        "Type": "nguoiKy_Goc",
        "Value": "KT. BỘ TRƯỞNG\r\nTHỨ TRƯỞNG\r\nBùi Thế Duy",
        "Confidence": 0.364318281,
        "ValueInfos": [
            {
                "Text": "KT. BỘ TRƯỞNG",
                "Line": 0,
                "X": 220,
                "Y": 83,
                "Width": 465,
                "Height": 51,
                "PageWidth": 820,
                "PageHeight": 599,
                "LineConfidence": 0.3863762
            },
            {
                "Text": "THỨ TRƯỞNG",
                "Line": 1,
                "X": 226,
                "Y": 141,
                "Width": 424,
                "Height": 58,
                "PageWidth": 820,
                "PageHeight": 599,
                "LineConfidence": 0.995854139
            },
            {
                "Text": "Bùi Thế Duy",
                "Line": 2,
                "X": 276,
                "Y": 455,
                "Width": 342,
                "Height": 75,
                "PageWidth": 820,
                "PageHeight": 599,
                "LineConfidence": 0.946836233
            }
        ]
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark>` `<mark style="color:yellow;">``</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>.
{% endhint %}

#### Ví dụ ảnh đầu vào

{% file src="../../.gitbook/assets/cbimage.png" %}
Mẫu văn bản hành chính.
{% endfile %}

#### Ý nghĩa thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

| Trường thông tin | Kiểu dữ liệu | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Page`           | number       | Thứ tự của trang, bắt đầu bằng giá trị 0                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `IsVBHCField`    | boolean      | Thứ tự của trang, bắt đầu bằng giá trị 0                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `Type`           | number       | Tên trường bóc tách được từ biểu mẫu                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Value`          | string       | Giá trị (nội dung) trường thông tin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `ValueInfos`     | array object | <table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><code>Text</code></td><td>Giá trị text của dòng (hoặc cụm).</td></tr><tr><td><code>Line</code></td><td>tự của dòng, bắt đầu bằng giá trị 0</td></tr><tr><td><code>X</code></td><td>Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Y</code></td><td>ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Width</code></td><td>Chiều rộng của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Height</code></td><td>Chiều cao của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>PageWidth</code></td><td>Chiều rộng của trang.</td></tr><tr><td><code>PageHeight</code></td><td>Chiều cao của trang.</td></tr><tr><td><code>LineConfidence</code></td><td>Độ chính xác của cả dòng <code>Text</code> (trong <code>LineInfo</code>).</td></tr></tbody></table> |

## Chứng minh nhân dân

{% swagger method="post" path="/ocr/cmnd" baseUrl="https://ax.cyberapis.com" summary="Process CMND" %}
{% swagger-description %}
API trả các thông tin như họ tên, giới tính, dân tộc, ngày sinh, hộ khẩu trường trú... của chứng minh nhân dân.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-Sender" required="true" type="String" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" %}
Mã file, xác định tính duy nhất của file đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Ví dụ thành công" %}
```javascript
[
    {
        "AnhChanDung": "System.Drawing.Bitmap",
        "CmndImage": "System.Drawing.Bitmap",
        "DanToc": null,
        "DanTocConfidence": 0,
        "DauVetRiengVaDiHinh": null,
        "DauVetRiengVaDiHinhConfidence": 0,
        "DoBackFace": false,
        "DoFrontFace": true,
        "GioiTinh": null,
        "GioiTinhConfidence": 0,
        "HoKhauThuongTru": "Xã Xuân Minh Huyện Thọ Xuân, Thanh Hóa",
        "HoKhauThuongTruConfidence": 0.99361074,
        "HoTen": "NGUYÊN HOÀI LINH",
        "HoTenConfidence": 0.82419324,
        "HoTenKhac": null,
        "HoTenKhacConfidence": 0,
        "NgayCap": null,
        "NgayCapConfidence": 0,
        "NgayHetHan": null,
        "NgayHetHanConfidence": 0,
        "NgaySinh": "23-05-1995",
        "NgaySinhConfidence": 0.99991417,
        "NguyenQuan": "Xã Xuân Minh Huyện Thọ Xuân, Thanh Hóa",
        "NguyenQuanConfidence": 0.99502015,
        "NoiCap": null,
        "NoiCapConfidence": 0,
        "QuocTich": null,
        "QuocTichConfidence": 0,
        "SoCmnd": "174324001",
        "SoCmndConfidence": 0.9999404,
        "TonGiao": null,
        "TonGiaoConfidence": 0,
        "Type": 0,
        "VanTayPhai": null,
        "VanTayTrai": null
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>.
{% endhint %}

#### Ví dụ ảnh đầu vào

{% file src="../../.gitbook/assets/CMND.png" %}
Mẫu chứng minh nhân dân
{% endfile %}

#### Ý nghĩa thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

| Trường thông tin                | Kiểu dữ liệu | Ghi chú                                                                                                                   |
| ------------------------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------- |
| `Type`                          | number       | Kiểu chứng minh nhân dân (CMND\_CU - chứng minh K dân cũ, CMND\_MOI - chứng minh nhân dân mới, CCCD - căn cước công dân). |
| `SoCmnd`                        | string       | Số chứng minh nhân dân                                                                                                    |
| `SoCmndConfidence`              | number       | Độ chính xác nhận dạng số chứng minh nhân dân.                                                                            |
| `HoTen`                         | string       | Họ và tên                                                                                                                 |
| `HoTenConfidence`               | number       | Độ chính xác nhận dạng họ và tên.                                                                                         |
| `HoTenKhac`                     | string       | Họ và tên khác, nếu có (đối với cmnd kiểu mới).                                                                           |
| `HoTenKhacConfidence`           | number       | Độ chính xác nhận dạng họ và tên khác, nếu có (đối với cmnd kiểu mới).                                                    |
| `NgaySinh`                      | string       | Ngày tháng năm sinh.                                                                                                      |
| `NgaySinhConfidence`            | number       | Độ chính xác nhận dạng ngày tháng năm sinh.                                                                               |
| `GioiTinh`                      | string       | Giới tính.                                                                                                                |
| `GioiTinhConfidence`            | number       | Độ chính xác nhận dạng giới tính.                                                                                         |
| `NguyenQuan`                    | string       | Nguyên quán.                                                                                                              |
| `NguyenQuanConfidence`          | number       | Độ chính xác nhận dạng nguyên quán.                                                                                       |
| `HoKhauThuongTru`               | string       | Hộ khẩu thường trú.                                                                                                       |
| `HoKhauThuongTruConfidence`     | number       | Độ chính xác nhận dạng hộ khẩu thường trú.                                                                                |
| `DanToc`                        | string       | Dân tộc.                                                                                                                  |
| `DanTocConfidence`              | number       | Độ chính xác nhận dạng dân tộc.                                                                                           |
| `QuocTich`                      | string       | Quốc tịch.                                                                                                                |
| `QuocTichConfidence`            | number       | Độ chính xác nhận dạng quốc tịch.                                                                                         |
| `NgayHetHan`                    | string       | Ngày hết hạn.                                                                                                             |
| `NgayHetHanConfidence`          | number       | Độ chính xác nhận dạng ngày hết hạn.                                                                                      |
| `DauVetRiengVaDiHinh`           | string       | Dấu vết riêng và dị hình.                                                                                                 |
| `DauVetRiengVaDiHinhConfidence` | number       | Độ chính xác nhận dạng dấu vết riêng và dị hình.                                                                          |
| `TonGiao`                       | string       | Tôn giáo.                                                                                                                 |
| `TonGiaoConfidence`             | number       | Độ chính xác nhận dạng tôn giáo.                                                                                          |
| `NgayCap`                       | string       | Ngày cấp.                                                                                                                 |
| `NgayCapConfidence`             | number       | Độ chính xác nhận ngày cấp.                                                                                               |
| `NoiCap`                        | string       | Nơi cấp.                                                                                                                  |
| `NoiCapConfidence`              | number       | Độ chính xác nhận nơi cấp.                                                                                                |
| `AnhChanDung`                   | Bitmap       | Ảnh chân dung                                                                                                             |
| `VanTayTrai`                    | Bitmap       | Ảnh vân tay trái                                                                                                          |
| `VanTayPhai`                    | Bitmap       | Ảnh vân tay phải                                                                                                          |

## Hộ chiếu

{% swagger method="post" path="/ocr/passport" baseUrl="https://ax.cyberapis.com" summary="Process Passport" %}
{% swagger-description %}
API trả các thông tin như mã số, số, hộ chiếu, họ tên, quốc tịch, ngày sinh, giới tính... của hộ chiếu.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-Sender" required="true" type="String" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" %}
Mã file, xác định tính duy nhất của file đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Ví dụ thành công" %}
```javascript
[
    {
        "Type": "loai",
        "Value": "",
        "Confidence": 0,
        "ValueInfos": []
    },
    {
        "Type": "maSo",
        "Value": "VNM",
        "Confidence": 0.9217451,
        "ValueInfos": [
            {
                "Text": "VNM",
                "Line": 0,
                "X": 266,
                "Y": 405,
                "Width": 30,
                "Height": 11,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.9217451
            }
        ]
    },
    {
        "Type": "soHoChieu",
        "Value": "B3120756",
        "Confidence": 0.996604264,
        "ValueInfos": [
            {
                "Text": "B3120756",
                "Line": 0,
                "X": 351,
                "Y": 406,
                "Width": 62,
                "Height": 12,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.996604264
            }
        ]
    },
    {
        "Type": "hoTen",
        "Value": "ĐỔ HÙNG CƯỜNG",
        "Confidence": 0.549907446,
        "ValueInfos": [
            {
                "Text": "ĐỔ HÙNG CƯỜNG",
                "Line": 0,
                "X": 178,
                "Y": 434,
                "Width": 117,
                "Height": 16,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.549907446
            }
        ]
    },
    {
        "Type": "quocTich",
        "Value": "VIỆT NAM / VIETNAMESE",
        "Confidence": 0.4421386,
        "ValueInfos": [
            {
                "Text": "VIỆT NAM / VIETNAMESE",
                "Line": 0,
                "X": 311,
                "Y": 451,
                "Width": 142,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.4421386
            }
        ]
    },
    {
        "Type": "ngaySinh",
        "Value": "07/10/1981",
        "Confidence": 0.9680164,
        "ValueInfos": [
            {
                "Text": "07/10/1981",
                "Line": 0,
                "X": 178,
                "Y": 483,
                "Width": 78,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.9680164
            }
        ]
    },
    {
        "Type": "gioiTinh",
        "Value": "NAM / M",
        "Confidence": 0.9968015,
        "ValueInfos": [
            {
                "Text": "NAM / M",
                "Line": 0,
                "X": 178,
                "Y": 515,
                "Width": 60,
                "Height": 14,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.9968015
            }
        ]
    },
    {
        "Type": "ngayCap",
        "Value": "18/05/2009",
        "Confidence": 0.6886836,
        "ValueInfos": [
            {
                "Text": "18/05/2009",
                "Line": 0,
                "X": 180,
                "Y": 547,
                "Width": 78,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.6886836
            }
        ]
    },
    {
        "Type": "noiCap",
        "Value": "Cục Quản lý Xuất nhập cảnh",
        "Confidence": 0.353759319,
        "ValueInfos": [
            {
                "Text": "Cục Quản lý Xuất nhập cảnh",
                "Line": 0,
                "X": 175,
                "Y": 580,
                "Width": 166,
                "Height": 14,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.353759319
            }
        ]
    },
    {
        "Type": "noiSinh",
        "Value": "NAM ĐỊNH",
        "Confidence": 0.9672857,
        "ValueInfos": [
            {
                "Text": "NAM ĐỊNH",
                "Line": 0,
                "X": 320,
                "Y": 484,
                "Width": 76,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.9672857
            }
        ]
    },
    {
        "Type": "soCMND",
        "Value": "172272256",
        "Confidence": 0.9996817,
        "ValueInfos": [
            {
                "Text": "172272256",
                "Line": 0,
                "X": 321,
                "Y": 516,
                "Width": 67,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.9996817
            }
        ]
    },
    {
        "Type": "coGiaTriDen",
        "Value": "18/05/2009 18 /05/2019",
        "Confidence": 0.247945875,
        "ValueInfos": [
            {
                "Text": "18/05/2009",
                "Line": 0,
                "X": 180,
                "Y": 547,
                "Width": 78,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.6886836
            },
            {
                "Text": "18 /05/2019",
                "Line": 1,
                "X": 323,
                "Y": 548,
                "Width": 80,
                "Height": 13,
                "PageWidth": 496,
                "PageHeight": 656,
                "LineConfidence": 0.3600287
            }
        ]
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>.
{% endhint %}

#### Ví dụ ảnh đầu vào

{% file src="../../.gitbook/assets/passport.png" %}
Mẫu hộ chiếu
{% endfile %}

#### Ý nghĩa thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

| Trường thông tin | Kiểu dữ liệu | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Type`           | number       | Tên trường bóc tách được từ biểu mẫu                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Value`          | string       | Giá trị (nội dung) trường thông tin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `X`              | number       | Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `Y`              | number       | ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `Width`          | number       | Chiều rộng của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `Height`         | number       | Chiều cao của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `PageWidth`      | number       | Chiều rộng của trang.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `PageHeight`     | number       | Chiều cao của trang.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Confidence`     | number       | Độ chính xác nhận dạng                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `ValueInfos`     | array object | <table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><code>Text</code></td><td>Giá trị text của dòng (hoặc cụm).</td></tr><tr><td><code>Line</code></td><td>tự của dòng, bắt đầu bằng giá trị 0</td></tr><tr><td><code>X</code></td><td>Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Y</code></td><td>ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Width</code></td><td>Chiều rộng của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Height</code></td><td>Chiều cao của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>PageWidth</code></td><td>Chiều rộng của trang.</td></tr><tr><td><code>PageHeight</code></td><td>Chiều cao của trang.</td></tr><tr><td><code>LineConfidence</code></td><td>Độ chính xác của cả dòng <code>Text</code> (trong <code>LineInfo</code>).</td></tr></tbody></table> |

## Hộ tịch

{% swagger method="post" path="/ocr/hotich" baseUrl="https://ax.cyberapis.com" summary="Process HoTich" %}
{% swagger-description %}
API trả các thông tin như nội bộ ban hành, số, ký hiệu, địa điểm, ngày ban hành... của văn bản hành chính.
{% endswagger-description %}

{% swagger-parameter in="header" name="X-Sender" required="true" type="String" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" %}
Mã file, xác định tính duy nhất của file đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-parameter in="query" name="doctype" type="String" %}
Nhận các giá trị 

`A3`

 hoặc 

`A4`

 (mặc định: 

`A4`

)
{% endswagger-parameter %}

{% swagger-parameter in="query" name="chartype" type="String" %}
text: Chữ in

handwri: Chữ viết tay \
mix: Cả chữ in và chữ viết tay(mặc định).
{% endswagger-parameter %}

{% swagger-parameter in="query" name="formtype" type="String" %}
KS: khai sinh \
KT: Khai tử \
KH: Kết hôn \
HN: Hôn nhân&#x20;

CMC: Nhận cha mẹ con
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Khai sinh A4" %}
```javascript
[
    {
        "Type": "so",
        "Value": "64",
        "Confidence": 0.9999242,
        "ValueInfos": [
            {
                "Text": "64",
                "Line": 0,
                "X": 268,
                "Y": 104,
                "Width": 100,
                "Height": 96,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999242
            }
        ]
    },
    {
        "Type": "nksHoTen",
        "Value": "NGUYỄN THỊ NHÀN",
        "Confidence": 0.9885568,
        "ValueInfos": [
            {
                "Text": "NGUYỄN THỊ NHÀN",
                "Line": 0,
                "X": 391,
                "Y": 433,
                "Width": 693,
                "Height": 137,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9885568
            }
        ]
    },
    {
        "Type": "nksGioiTinh",
        "Value": "Nữ",
        "Confidence": 0.9999987,
        "ValueInfos": [
            {
                "Text": "Nữ",
                "Line": 0,
                "X": 1423,
                "Y": 444,
                "Width": 161,
                "Height": 116,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999987
            }
        ]
    },
    {
        "Type": "nksNgaySinh",
        "Value": "26/6/1948",
        "Confidence": 0.9899297,
        "ValueInfos": [
            {
                "Text": "26/6/1948",
                "Line": 0,
                "X": 641,
                "Y": 548,
                "Width": 439,
                "Height": 96,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9899297
            }
        ]
    },
    {
        "Type": "nksNgaySinhBangChu",
        "Value": "Ngày hai mươi sáu, tháng sáu, năm một ngàn chín trăm bốn mươi tám",
        "Confidence": 0.3127958,
        "ValueInfos": [
            {
                "Text": "Ngày hai",
                "Line": 0,
                "X": 1459,
                "Y": 552,
                "Width": 250,
                "Height": 111,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9972422
            },
            {
                "Text": "mươi sáu, tháng sáu, năm một ngàn chín trăm bốn mươi tám",
                "Line": 1,
                "X": 134,
                "Y": 619,
                "Width": 1751,
                "Height": 137,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.3136608
            }
        ]
    },
    {
        "Type": "nksNoiSinh",
        "Value": "Lòng Gia Lo - Vĩnh Yên",
        "Confidence": 0.5737801,
        "ValueInfos": [
            {
                "Text": "Lòng Gia Lo - Vĩnh Yên",
                "Line": 0,
                "X": 341,
                "Y": 706,
                "Width": 790,
                "Height": 115,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.5737801
            }
        ]
    },
    {
        "Type": "nksDanToc",
        "Value": "Kinh",
        "Confidence": 0.999956846,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 339,
                "Y": 790,
                "Width": 171,
                "Height": 89,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.999956846
            }
        ]
    },
    {
        "Type": "nksQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.9997011,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1130,
                "Y": 790,
                "Width": 354,
                "Height": 110,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9997011
            }
        ]
    },
    {
        "Type": "nksQueQuan",
        "Value": "Khúc Vén",
        "Confidence": 0.384161353,
        "ValueInfos": [
            {
                "Text": "Khúc Vén",
                "Line": 0,
                "X": 456,
                "Y": 864,
                "Width": 352,
                "Height": 108,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.384161353
            }
        ]
    },
    {
        "Type": "chaHoTen",
        "Value": "Nguyễn Văn Phong",
        "Confidence": 0.9979254,
        "ValueInfos": [
            {
                "Text": "Nguyễn Văn Phong",
                "Line": 0,
                "X": 467,
                "Y": 1189,
                "Width": 580,
                "Height": 124,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9979254
            }
        ]
    },
    {
        "Type": "chaDanToc",
        "Value": "Kinh",
        "Confidence": 0.9999614,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 337,
                "Y": 1279,
                "Width": 176,
                "Height": 88,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999614
            }
        ]
    },
    {
        "Type": "choQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.999057353,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1135,
                "Y": 1277,
                "Width": 335,
                "Height": 110,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.999057353
            }
        ]
    },
    {
        "Type": "meHoTen",
        "Value": "Nguyễn Thị Đài",
        "Confidence": 0.8189336,
        "ValueInfos": [
            {
                "Text": "Nguyễn Thị Đài",
                "Line": 0,
                "X": 443,
                "Y": 1349,
                "Width": 544,
                "Height": 118,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.8189336
            }
        ]
    },
    {
        "Type": "meDanToc",
        "Value": "Kinh",
        "Confidence": 0.997030258,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 354,
                "Y": 1438,
                "Width": 181,
                "Height": 94,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.997030258
            }
        ]
    },
    {
        "Type": "meQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.999781251,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1142,
                "Y": 1431,
                "Width": 354,
                "Height": 107,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.999781251
            }
        ]
    },
    {
        "Type": "nycHoTen",
        "Value": "Nguyễn Thị Nhân",
        "Confidence": 0.901808739,
        "ValueInfos": [
            {
                "Text": "Nguyễn Thị Nhân",
                "Line": 0,
                "X": 379,
                "Y": 1653,
                "Width": 590,
                "Height": 134,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.901808739
            }
        ]
    },
    {
        "Type": "nycQuanHe",
        "Value": "Tự Khai",
        "Confidence": 0.977543831,
        "ValueInfos": [
            {
                "Text": "Tự Khai",
                "Line": 0,
                "X": 903,
                "Y": 1752,
                "Width": 306,
                "Height": 105,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.977543831
            }
        ]
    },
    {
        "Type": "ngayDangKy",
        "Value": "28",
        "Confidence": 0.9999901,
        "ValueInfos": [
            {
                "Text": "28",
                "Line": 0,
                "X": 505,
                "Y": 1867,
                "Width": 116,
                "Height": 92,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999901
            }
        ]
    },
    {
        "Type": "thangDangKy",
        "Value": "4",
        "Confidence": 0.9999999,
        "ValueInfos": [
            {
                "Text": "4",
                "Line": 0,
                "X": 880,
                "Y": 1881,
                "Width": 85,
                "Height": 81,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999999
            }
        ]
    },
    {
        "Type": "namDangKy",
        "Value": "2009",
        "Confidence": 0.9999838,
        "ValueInfos": [
            {
                "Text": "2009",
                "Line": 0,
                "X": 1306,
                "Y": 1868,
                "Width": 188,
                "Height": 93,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9999838
            }
        ]
    },
    {
        "Type": "thongTinNguoiKy",
        "Value": "Nguyễn Văn Long LCT UBND xã",
        "Confidence": 0.6920055,
        "ValueInfos": [
            {
                "Text": "Nguyễn Văn Long",
                "Line": 0,
                "X": 965,
                "Y": 1942,
                "Width": 555,
                "Height": 130,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.9949155
            },
            {
                "Text": "LCT UBND xã",
                "Line": 1,
                "X": 124,
                "Y": 2020,
                "Width": 489,
                "Height": 110,
                "PageWidth": 2335,
                "PageHeight": 3407,
                "LineConfidence": 0.695542037
            }
        ]
    },
    {
        "Type": "canBoTuPhapHoTich",
        "Value": "",
        "Confidence": 0.0,
        "ValueInfos": []
    }
]
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Khai tử A4" %}
```javascript
[
    {
        "Type": "so",
        "Value": "16",
        "Confidence": 0.7774303,
        "ValueInfos": [
            {
                "Text": "16",
                "Line": 0,
                "X": 263,
                "Y": 128,
                "Width": 156,
                "Height": 118,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.7774303
            }
        ]
    },
    {
        "Type": "nktHoTen",
        "Value": "ĐINH QUANG NAM",
        "Confidence": 0.987440944,
        "ValueInfos": [
            {
                "Text": "ĐINH QUANG NAM",
                "Line": 0,
                "X": 390,
                "Y": 443,
                "Width": 770,
                "Height": 134,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.987440944
            }
        ]
    },
    {
        "Type": "nktGioiTinh",
        "Value": "Nam",
        "Confidence": 0.9999168,
        "ValueInfos": [
            {
                "Text": "Nam",
                "Line": 0,
                "X": 1433,
                "Y": 447,
                "Width": 237,
                "Height": 122,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9999168
            }
        ]
    },
    {
        "Type": "nktNgaySinh",
        "Value": "1944",
        "Confidence": 0.999997258,
        "ValueInfos": [
            {
                "Text": "1944",
                "Line": 0,
                "X": 908,
                "Y": 552,
                "Width": 263,
                "Height": 116,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.999997258
            }
        ]
    },
    {
        "Type": "nktDanToc",
        "Value": "Kinh",
        "Confidence": 0.935807765,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 518,
                "Y": 640,
                "Width": 229,
                "Height": 120,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.935807765
            }
        ]
    },
    {
        "Type": "nktQuocTich",
        "Value": "Việt nam",
        "Confidence": 0.887269855,
        "ValueInfos": [
            {
                "Text": "Việt nam",
                "Line": 0,
                "X": 1286,
                "Y": 643,
                "Width": 400,
                "Height": 121,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.887269855
            }
        ]
    },
    {
        "Type": "nktNoiCuTru",
        "Value": "Ấp An Bình Xã Trung Hòa - Huyện Trảng Bom - Đồng Nai",
        "Confidence": 0.153563172,
        "ValueInfos": [
            {
                "Text": "Ấp An Bình",
                "Line": 0,
                "X": 1142,
                "Y": 731,
                "Width": 526,
                "Height": 141,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.961487949
            },
            {
                "Text": "Xã Trung Hòa - Huyện Trảng Bom - Đồng Nai",
                "Line": 1,
                "X": 148,
                "Y": 825,
                "Width": 1711,
                "Height": 166,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.159714088
            }
        ]
    },
    {
        "Type": "nktSoGiayToTuyThan",
        "Value": "270430202",
        "Confidence": 0.9406013,
        "ValueInfos": [
            {
                "Text": "270430202",
                "Line": 0,
                "X": 859,
                "Y": 934,
                "Width": 535,
                "Height": 125,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9406013
            }
        ]
    },
    {
        "Type": "nktNgayChet",
        "Value": "0h20' ngày 25/9/2000",
        "Confidence": 0.371222019,
        "ValueInfos": [
            {
                "Text": "0h20' ngày 25/9/2000",
                "Line": 0,
                "X": 837,
                "Y": 1023,
                "Width": 971,
                "Height": 157,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.371222019
            }
        ]
    },
    {
        "Type": "nktNoiChet",
        "Value": "nhà",
        "Confidence": 0.9751488,
        "ValueInfos": [
            {
                "Text": "nhà",
                "Line": 0,
                "X": 736,
                "Y": 1128,
                "Width": 242,
                "Height": 117,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9751488
            }
        ]
    },
    {
        "Type": "nktNguyenNhanChet",
        "Value": "Bệnh",
        "Confidence": 0.991114438,
        "ValueInfos": [
            {
                "Text": "Bệnh",
                "Line": 0,
                "X": 781,
                "Y": 1318,
                "Width": 231,
                "Height": 129,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.991114438
            }
        ]
    },
    {
        "Type": "gbtPhanGhiVeGiayBaoTu",
        "Value": "Ban Ấp An Bình",
        "Confidence": 0.545995355,
        "ValueInfos": [
            {
                "Text": "Ban Ấp An Bình",
                "Line": 0,
                "X": 275,
                "Y": 1673,
                "Width": 765,
                "Height": 146,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.545995355
            }
        ]
    },
    {
        "Type": "nycHoTen",
        "Value": "Đinh Ba Duyên.",
        "Confidence": 0.428936273,
        "ValueInfos": [
            {
                "Text": "Đinh Ba Duyên.",
                "Line": 0,
                "X": 416,
                "Y": 2132,
                "Width": 802,
                "Height": 153,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.428936273
            }
        ]
    },
    {
        "Type": "nycQuanHe",
        "Value": "con",
        "Confidence": 0.9560448,
        "ValueInfos": [
            {
                "Text": "con",
                "Line": 0,
                "X": 1000,
                "Y": 2247,
                "Width": 165,
                "Height": 112,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9560448
            }
        ]
    },
    {
        "Type": "ngayDangKy",
        "Value": "29",
        "Confidence": 0.9999908,
        "ValueInfos": [
            {
                "Text": "29",
                "Line": 0,
                "X": 545,
                "Y": 2377,
                "Width": 151,
                "Height": 105,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9999908
            }
        ]
    },
    {
        "Type": "thangDangKy",
        "Value": "9",
        "Confidence": 0.9999999,
        "ValueInfos": [
            {
                "Text": "9",
                "Line": 0,
                "X": 999,
                "Y": 2375,
                "Width": 98,
                "Height": 106,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9999999
            }
        ]
    },
    {
        "Type": "namDangKy",
        "Value": "2010",
        "Confidence": 0.99996376,
        "ValueInfos": [
            {
                "Text": "2010",
                "Line": 0,
                "X": 1378,
                "Y": 2371,
                "Width": 272,
                "Height": 116,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.99996376
            }
        ]
    },
    {
        "Type": "thongTinNguoiKy",
        "Value": "CT Nguyễn Thành Hồng",
        "Confidence": 0.663094461,
        "ValueInfos": [
            {
                "Text": "CT",
                "Line": 0,
                "X": 1288,
                "Y": 2487,
                "Width": 130,
                "Height": 92,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.851379931
            },
            {
                "Text": "Nguyễn Thành Hồng",
                "Line": 1,
                "X": 171,
                "Y": 2557,
                "Width": 912,
                "Height": 169,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.778846741
            }
        ]
    },
    {
        "Type": "canBoTuPhapHoTich",
        "Value": "Võ Văn Dũng",
        "Confidence": 0.7742672,
        "ValueInfos": [
            {
                "Text": "Võ Văn Dũng",
                "Line": 0,
                "X": 662,
                "Y": 3081,
                "Width": 452,
                "Height": 133,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.7742672
            }
        ]
    }
]
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Kết hôn A4" %}
```javascript
[
    {
        "Type": "so",
        "Value": "16",
        "Confidence": 0.7774303,
        "ValueInfos": [
            {
                "Text": "16",
                "Line": 0,
                "X": 263,
                "Y": 128,
                "Width": 156,
                "Height": 118,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.7774303
            }
        ]
    },
    {
        "Type": "chongHoTen",
        "Value": ""
    },
    {
        "Type": "chongNgaySinh",
        "Value": "1944",
        "Confidence": 0.999997258,
        "ValueInfos": [
            {
                "Text": "1944",
                "Line": 0,
                "X": 908,
                "Y": 552,
                "Width": 263,
                "Height": 116,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.999997258
            }
        ]
    },
    {
        "Type": "chongDanToc",
        "Value": "Kinh",
        "Confidence": 0.935807765,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 518,
                "Y": 640,
                "Width": 229,
                "Height": 120,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.935807765
            }
        ]
    },
    {
        "Type": "chongQuocTich",
        "Value": "Việt nam",
        "Confidence": 0.887269855,
        "ValueInfos": [
            {
                "Text": "Việt nam",
                "Line": 0,
                "X": 1286,
                "Y": 643,
                "Width": 400,
                "Height": 121,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.887269855
            }
        ]
    },
    {
        "Type": "chongNoiCuTru",
        "Value": "Ấp An Bình Xã Trung Hòa - Huyện Trảng Bom - Đồng Nai",
        "Confidence": 0.153563172,
        "ValueInfos": [
            {
                "Text": "Ấp An Bình",
                "Line": 0,
                "X": 1142,
                "Y": 731,
                "Width": 526,
                "Height": 141,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.961487949
            },
            {
                "Text": "Xã Trung Hòa - Huyện Trảng Bom - Đồng Nai",
                "Line": 1,
                "X": 148,
                "Y": 825,
                "Width": 1711,
                "Height": 166,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.159714088
            }
        ]
    },
    {
        "Type": "chongSoGiayToTuyThan",
        "Value": "270430202",
        "Confidence": 0.9406013,
        "ValueInfos": [
            {
                "Text": "270430202",
                "Line": 0,
                "X": 859,
                "Y": 934,
                "Width": 535,
                "Height": 125,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9406013
            }
        ]
    },
    {
        "Type": "voHoTen",
        "Value": ""
    },
    {
        "Type": "voNgaySinh",
        "Value": ""
    },
    {
        "Type": "voDanToc",
        "Value": ""
    },
    {
        "Type": "voQuocTich",
        "Value": ""
    },
    {
        "Type": "voNoiCuTru",
        "Value": ""
    },
    {
        "Type": "voSoGiayToTuyThan",
        "Value": "270430202",
        "Confidence": 0.9406013,
        "ValueInfos": [
            {
                "Text": "270430202",
                "Line": 0,
                "X": 859,
                "Y": 934,
                "Width": 535,
                "Height": 125,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9406013
            }
        ]
    },
    {
        "Type": "ngayDangKy",
        "Value": "29",
        "Confidence": 0.9999908,
        "ValueInfos": [
            {
                "Text": "29",
                "Line": 0,
                "X": 545,
                "Y": 2377,
                "Width": 151,
                "Height": 105,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9999908
            }
        ]
    },
    {
        "Type": "thangDangKy",
        "Value": "9",
        "Confidence": 0.9999999,
        "ValueInfos": [
            {
                "Text": "9",
                "Line": 0,
                "X": 999,
                "Y": 2375,
                "Width": 98,
                "Height": 106,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.9999999
            }
        ]
    },
    {
        "Type": "namDangKy",
        "Value": "2010",
        "Confidence": 0.99996376,
        "ValueInfos": [
            {
                "Text": "2010",
                "Line": 0,
                "X": 1378,
                "Y": 2371,
                "Width": 272,
                "Height": 116,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.99996376
            }
        ]
    },
    {
        "Type": "thongTinNguoiKy",
        "Value": "CT",
        "Confidence": 0.851379931,
        "ValueInfos": [
            {
                "Text": "CT",
                "Line": 0,
                "X": 1288,
                "Y": 2487,
                "Width": 130,
                "Height": 92,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.851379931
            }
        ]
    },
    {
        "Type": "chuKyChong",
        "Value": ""
    },
    {
        "Type": "chuKyVo",
        "Value": ""
    },
    {
        "Type": "canBoTuPhapHoTich",
        "Value": "Cán bộ hộ tịch của Sở Tư pháp Võ Văn Dũng",
        "Confidence": 0.7703518,
        "ValueInfos": [
            {
                "Text": "Cán bộ hộ tịch của Sở Tư pháp",
                "Line": 0,
                "X": 573,
                "Y": 2906,
                "Width": 713,
                "Height": 66,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.994943142
            },
            {
                "Text": "Võ Văn Dũng",
                "Line": 1,
                "X": 662,
                "Y": 3081,
                "Width": 452,
                "Height": 133,
                "PageWidth": 2335,
                "PageHeight": 3386,
                "LineConfidence": 0.7742672
            }
        ]
    }
]
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Hôn nhân A4" %}
```javascript
[
    {
        "Type": "so",
        "Value": "31",
        "Confidence": 0.99978286,
        "ValueInfos": [
            {
                "Text": "31",
                "Line": 0,
                "X": 211,
                "Y": 92,
                "Width": 119,
                "Height": 96,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.99978286
            }
        ]
    },
    {
        "Type": "nxnHoTen",
        "Value": "NGuyễn Thị Hồng Nhung Nữ",
        "Confidence": 0.359118,
        "ValueInfos": [
            {
                "Text": "NGuyễn Thị Hồng Nhung",
                "Line": 0,
                "X": 288,
                "Y": 392,
                "Width": 774,
                "Height": 129,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.3638525
            },
            {
                "Text": "Nữ",
                "Line": 1,
                "X": 1318,
                "Y": 365,
                "Width": 204,
                "Height": 135,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9869879
            }
        ]
    },
    {
        "Type": "nxnGioiTinh",
        "Value": ""
    },
    {
        "Type": "nxnNgaySinh",
        "Value": "04/12/1991",
        "Confidence": 0.9947261,
        "ValueInfos": [
            {
                "Text": "04/12/1991",
                "Line": 0,
                "X": 552,
                "Y": 482,
                "Width": 547,
                "Height": 108,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9947261
            }
        ]
    },
    {
        "Type": "nxnNoiSinh",
        "Value": "Đồng Nai",
        "Confidence": 0.9994262,
        "ValueInfos": [
            {
                "Text": "Đồng Nai",
                "Line": 0,
                "X": 365,
                "Y": 562,
                "Width": 405,
                "Height": 123,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9994262
            }
        ]
    },
    {
        "Type": "nxnDanToc",
        "Value": "Kinh",
        "Confidence": 0.9999633,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 508,
                "Y": 645,
                "Width": 207,
                "Height": 99,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9999633
            }
        ]
    },
    {
        "Type": "nxnQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.704052,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1140,
                "Y": 647,
                "Width": 343,
                "Height": 101,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.704052
            }
        ]
    },
    {
        "Type": "nxnSoGiayToTuyThan",
        "Value": "272029001",
        "Confidence": 0.9968062,
        "ValueInfos": [
            {
                "Text": "272029001",
                "Line": 0,
                "X": 612,
                "Y": 727,
                "Width": 411,
                "Height": 96,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9968062
            }
        ]
    },
    {
        "Type": "nxnNoiCuTru",
        "Value": "ấp Đoàn Kến xã giang Điền huyện Trảng Bom Đình Đồng Nai",
        "Confidence": 0.0324104466,
        "ValueInfos": [
            {
                "Text": "ấp Đoàn Kến xã giang Điền huyện",
                "Line": 0,
                "X": 557,
                "Y": 797,
                "Width": 1060,
                "Height": 136,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.172103822
            },
            {
                "Text": "Trảng Bom Đình Đồng Nai",
                "Line": 1,
                "X": 82,
                "Y": 879,
                "Width": 939,
                "Height": 137,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.188319162
            }
        ]
    },
    {
        "Type": "nxnNoiThuongTruTruocKhiXuatCanh",
        "Value": "",
        "Confidence": 0.0,
        "ValueInfos": []
    },
    {
        "Type": "nxnTinhTrangHonNhan",
        "Value": "Từ 16/10/2009 đến 17/9/2013 Qua kết Hòa Cần Nào với an Tại UBND xã giang Điền là đúng biên độc Thân ./.",
        "Confidence": 0.00035170358,
        "ValueInfos": [
            {
                "Text": "Từ 16/10/2009 đến 17/9/2013",
                "Line": 0,
                "X": 502,
                "Y": 1115,
                "Width": 1025,
                "Height": 123,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9249729
            },
            {
                "Text": "Qua kết Hòa Cần Nào với an Tại UBND xã giang",
                "Line": 1,
                "X": 60,
                "Y": 1200,
                "Width": 1541,
                "Height": 137,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.0241159927
            },
            {
                "Text": "Điền là đúng biên độc Thân ./.",
                "Line": 2,
                "X": 57,
                "Y": 1284,
                "Width": 1107,
                "Height": 142,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.0157667659
            }
        ]
    },
    {
        "Type": "nxnMucDichSuDung",
        "Value": "Đặng Ký Kết Hòa Với Anh Nguyễn Ngọc Hòa Hiền : SN 1990 ấp Tôn Lập 2 xã Công Giáo Trông Rom - ĐN",
        "Confidence": 0.000296664832,
        "ValueInfos": [
            {
                "Text": "Đặng Ký Kết Hòa",
                "Line": 0,
                "X": 1128,
                "Y": 1510,
                "Width": 521,
                "Height": 135,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.4170655
            },
            {
                "Text": "Với Anh Nguyễn Ngọc Hòa Hiền : SN 1990 ấp",
                "Line": 1,
                "X": 79,
                "Y": 1601,
                "Width": 1526,
                "Height": 138,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.1134951
            },
            {
                "Text": "Tôn Lập 2 xã Công Giáo Trông Rom - ĐN",
                "Line": 2,
                "X": 75,
                "Y": 1684,
                "Width": 1311,
                "Height": 146,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.006267361
            }
        ]
    },
    {
        "Type": "nycHoTen",
        "Value": "Nguyễn Thị Hồng Nhung",
        "Confidence": 0.9339117,
        "ValueInfos": [
            {
                "Text": "Nguyễn Thị Hồng Nhung",
                "Line": 0,
                "X": 304,
                "Y": 1888,
                "Width": 803,
                "Height": 143,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.9339117
            }
        ]
    },
    {
        "Type": "nycQuanHe",
        "Value": "Bản Thán",
        "Confidence": 0.8683271,
        "ValueInfos": [
            {
                "Text": "Bản Thán",
                "Line": 0,
                "X": 1324,
                "Y": 1951,
                "Width": 298,
                "Height": 130,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.8683271
            }
        ]
    },
    {
        "Type": "nycSoGiayXacNhan",
        "Value": "Bản Thán",
        "Confidence": 0.8683271,
        "ValueInfos": [
            {
                "Text": "Bản Thán",
                "Line": 0,
                "X": 1324,
                "Y": 1951,
                "Width": 298,
                "Height": 130,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.8683271
            }
        ]
    },
    {
        "Type": "nycNgayGiayXacNhan",
        "Value": "17",
        "Confidence": 0.999924064,
        "ValueInfos": [
            {
                "Text": "17",
                "Line": 0,
                "X": 1127,
                "Y": 2093,
                "Width": 85,
                "Height": 95,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.999924064
            }
        ]
    },
    {
        "Type": "nycThangGiayXacNhan",
        "Value": "9",
        "Confidence": 1.0,
        "ValueInfos": [
            {
                "Text": "9",
                "Line": 0,
                "X": 1317,
                "Y": 2097,
                "Width": 67,
                "Height": 87,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 1.0
            }
        ]
    },
    {
        "Type": "nycNamGiayXacNhan",
        "Value": "2073",
        "Confidence": 0.933752,
        "ValueInfos": [
            {
                "Text": "2073",
                "Line": 0,
                "X": 1482,
                "Y": 2088,
                "Width": 137,
                "Height": 97,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.933752
            }
        ]
    },
    {
        "Type": "thongTinNguoiKy",
        "Value": "PCT: Trịm Hồng Cường )",
        "Confidence": 0.0278961044,
        "ValueInfos": [
            {
                "Text": "PCT:",
                "Line": 0,
                "X": 1270,
                "Y": 2176,
                "Width": 158,
                "Height": 126,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.6147022
            },
            {
                "Text": "Trịm Hồng Cường )",
                "Line": 1,
                "X": 118,
                "Y": 2247,
                "Width": 697,
                "Height": 154,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.0453814939
            }
        ]
    },
    {
        "Type": "canBoTuPhapHoTich",
        "Value": "Hoyện Vương Lê Văn Hùng",
        "Confidence": 0.005403893,
        "ValueInfos": [
            {
                "Text": "Hoyện Vương",
                "Line": 0,
                "X": 572,
                "Y": 2617,
                "Width": 1060,
                "Height": 252,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.006251859
            },
            {
                "Text": "Lê Văn Hùng",
                "Line": 1,
                "X": 883,
                "Y": 2763,
                "Width": 450,
                "Height": 146,
                "PageWidth": 2309,
                "PageHeight": 3389,
                "LineConfidence": 0.864365757
            }
        ]
    }
]
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Nhận cha mẹ con A4" %}
```javascript
[
    {
        "Type": "so",
        "Value": "01",
        "Confidence": 0.999996543,
        "ValueInfos": [
            {
                "Text": "01",
                "Line": 0,
                "X": 285,
                "Y": 125,
                "Width": 112,
                "Height": 82,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999996543
            }
        ]
    },
    {
        "Type": "nnHoTen",
        "Value": "Nguyễn Ngọc Tú",
        "Confidence": 0.5046227,
        "ValueInfos": [
            {
                "Text": "Nguyễn Ngọc Tú",
                "Line": 0,
                "X": 376,
                "Y": 407,
                "Width": 571,
                "Height": 124,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.5046227
            }
        ]
    },
    {
        "Type": "nnNgaySinh",
        "Value": "1982",
        "Confidence": 0.9999455,
        "ValueInfos": [
            {
                "Text": "1982",
                "Line": 0,
                "X": 644,
                "Y": 514,
                "Width": 186,
                "Height": 91,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.9999455
            }
        ]
    },
    {
        "Type": "nnDanToc",
        "Value": "Kinh",
        "Confidence": 0.9920933,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 344,
                "Y": 613,
                "Width": 161,
                "Height": 96,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.9920933
            }
        ]
    },
    {
        "Type": "nnQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.998043239,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1174,
                "Y": 595,
                "Width": 346,
                "Height": 121,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.998043239
            }
        ]
    },
    {
        "Type": "nnQueQuan",
        "Value": "Nam Định",
        "Confidence": 0.999533534,
        "ValueInfos": [
            {
                "Text": "Nam Định",
                "Line": 0,
                "X": 392,
                "Y": 697,
                "Width": 380,
                "Height": 119,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999533534
            }
        ]
    },
    {
        "Type": "nnNoiCuTru",
        "Value": "ấp An Bình, xã Trung Hòa",
        "Confidence": 0.694317,
        "ValueInfos": [
            {
                "Text": "ấp An Bình, xã Trung Hòa",
                "Line": 0,
                "X": 626,
                "Y": 881,
                "Width": 859,
                "Height": 146,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.694317
            }
        ]
    },
    {
        "Type": "nnSoGiayToTuyThan",
        "Value": "271451872",
        "Confidence": 0.7986417,
        "ValueInfos": [
            {
                "Text": "271451872",
                "Line": 0,
                "X": 710,
                "Y": 1084,
                "Width": 427,
                "Height": 112,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.7986417
            }
        ]
    },
    {
        "Type": "ndnHoTen",
        "Value": "Nguyễn Ngọc Tú Anh",
        "Confidence": 0.971431851,
        "ValueInfos": [
            {
                "Text": "Nguyễn Ngọc Tú Anh",
                "Line": 0,
                "X": 392,
                "Y": 1315,
                "Width": 700,
                "Height": 131,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.971431851
            }
        ]
    },
    {
        "Type": "ndnNgaySinh",
        "Value": "27.9.2003",
        "Confidence": 0.99958545,
        "ValueInfos": [
            {
                "Text": "27.9.2003",
                "Line": 0,
                "X": 673,
                "Y": 1419,
                "Width": 444,
                "Height": 106,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.99958545
            }
        ]
    },
    {
        "Type": "ndnNoiSinh",
        "Value": "Bệnh viện Đa khoa Đồng Nai",
        "Confidence": 0.9277523,
        "ValueInfos": [
            {
                "Text": "Bệnh viện Đa khoa Đồng Nai",
                "Line": 0,
                "X": 359,
                "Y": 1506,
                "Width": 987,
                "Height": 129,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.9277523
            }
        ]
    },
    {
        "Type": "ndnDanToc",
        "Value": "Kinh",
        "Confidence": 0.999370456,
        "ValueInfos": [
            {
                "Text": "Kinh",
                "Line": 0,
                "X": 348,
                "Y": 1622,
                "Width": 189,
                "Height": 96,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999370456
            }
        ]
    },
    {
        "Type": "ndnQuocTich",
        "Value": "Việt Nam",
        "Confidence": 0.99773854,
        "ValueInfos": [
            {
                "Text": "Việt Nam",
                "Line": 0,
                "X": 1187,
                "Y": 1605,
                "Width": 355,
                "Height": 118,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.99773854
            }
        ]
    },
    {
        "Type": "ndnQueQuan",
        "Value": "Nam Định",
        "Confidence": 0.993652165,
        "ValueInfos": [
            {
                "Text": "Nam Định",
                "Line": 0,
                "X": 396,
                "Y": 1707,
                "Width": 374,
                "Height": 121,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.993652165
            }
        ]
    },
    {
        "Type": "ndnNoiCuTru",
        "Value": "ấp An Bình xã Trung Hòa",
        "Confidence": 0.420503616,
        "ValueInfos": [
            {
                "Text": "ấp An Bình xã Trung Hòa",
                "Line": 0,
                "X": 648,
                "Y": 1889,
                "Width": 984,
                "Height": 141,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.420503616
            }
        ]
    },
    {
        "Type": "nycHoTen",
        "Value": "Nguyễn Ngọc Tư",
        "Confidence": 0.917373,
        "ValueInfos": [
            {
                "Text": "Nguyễn Ngọc Tư",
                "Line": 0,
                "X": 411,
                "Y": 2228,
                "Width": 679,
                "Height": 135,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.917373
            }
        ]
    },
    {
        "Type": "nycQuanHe",
        "Value": "Tự Khai",
        "Confidence": 0.63122946,
        "ValueInfos": [
            {
                "Text": "Tự Khai",
                "Line": 0,
                "X": 890,
                "Y": 2333,
                "Width": 318,
                "Height": 115,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.63122946
            }
        ]
    },
    {
        "Type": "quyetDinhSo",
        "Value": "16",
        "Confidence": 0.999999046,
        "ValueInfos": [
            {
                "Text": "16",
                "Line": 0,
                "X": 549,
                "Y": 2474,
                "Width": 112,
                "Height": 91,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999999046
            }
        ]
    },
    {
        "Type": "quyetDinhNgay",
        "Value": "21",
        "Confidence": 0.999996066,
        "ValueInfos": [
            {
                "Text": "21",
                "Line": 0,
                "X": 1026,
                "Y": 2473,
                "Width": 111,
                "Height": 89,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999996066
            }
        ]
    },
    {
        "Type": "quyetDinhThang",
        "Value": "5",
        "Confidence": 0.999999762,
        "ValueInfos": [
            {
                "Text": "5",
                "Line": 0,
                "X": 1317,
                "Y": 2473,
                "Width": 84,
                "Height": 85,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.999999762
            }
        ]
    },
    {
        "Type": "quyetDinhNam",
        "Value": "2007",
        "Confidence": 0.9996816,
        "ValueInfos": [
            {
                "Text": "2007",
                "Line": 0,
                "X": 1544,
                "Y": 2461,
                "Width": 158,
                "Height": 95,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.9996816
            }
        ]
    },
    {
        "Type": "thongTinNguoiKy",
        "Value": "Phạm Thị Tô Chủ tịch UBND xã",
        "Confidence": 0.5426619,
        "ValueInfos": [
            {
                "Text": "Phạm Thị Tô",
                "Line": 0,
                "X": 952,
                "Y": 2554,
                "Width": 503,
                "Height": 128,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.9624887
            },
            {
                "Text": "Chủ tịch UBND xã",
                "Line": 1,
                "X": 161,
                "Y": 2650,
                "Width": 754,
                "Height": 130,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.5638112
            }
        ]
    },
    {
        "Type": "canBoTuPhapHoTich",
        "Value": "Va",
        "Confidence": 0.447214067,
        "ValueInfos": [
            {
                "Text": "Va",
                "Line": 0,
                "X": 626,
                "Y": 2948,
                "Width": 520,
                "Height": 217,
                "PageWidth": 2369,
                "PageHeight": 3416,
                "LineConfidence": 0.447214067
            }
        ]
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64.`</mark>
{% endhint %}

#### Ví dụ ảnh đầu vào

{% file src="../../.gitbook/assets/cha me con.png" %}
Mẫu cha mẹ con A4.
{% endfile %}

{% file src="../../.gitbook/assets/Hon Nhan (1).png" %}
Mẫu hôn nhân A4.
{% endfile %}

{% file src="../../.gitbook/assets/ket hon.png" %}
Mẫu kết hôn A4.
{% endfile %}

{% file src="../../.gitbook/assets/khai sinh (1).png" %}
Mẫu khai sinh A4.&#x20;
{% endfile %}

{% file src="../../.gitbook/assets/Khai tu.png" %}
Mẫu khai tử A4.
{% endfile %}

#### Ý nghĩa thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

| Trường thông tin | Kiểu dữ liệu | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Type`           | number       | Tên trường bóc tách được từ biểu mẫu                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Value`          | string       | Giá trị (nội dung) trường thông tin.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `X`              | number       | Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `Y`              | number       | ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `Width`          | number       | Chiều rộng của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `Height`         | number       | Chiều cao của dòng có chữa ký tự Tiếng Việt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `PageWidth`      | number       | Chiều rộng của trang.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `PageHeight`     | number       | Chiều cao của trang.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `Confidence`     | number       | Độ chính xác nhận dạng                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `ValueInfos`     | array object | <table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><code>Text</code></td><td>Giá trị text của dòng (hoặc cụm).</td></tr><tr><td><code>Line</code></td><td>tự của dòng, bắt đầu bằng giá trị 0</td></tr><tr><td><code>X</code></td><td>Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Y</code></td><td>ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Width</code></td><td>Chiều rộng của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Height</code></td><td>Chiều cao của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>PageWidth</code></td><td>Chiều rộng của trang.</td></tr><tr><td><code>PageHeight</code></td><td>Chiều cao của trang.</td></tr><tr><td><code>LineConfidence</code></td><td>Độ chính xác của cả dòng <code>Text</code> (trong <code>LineInfo</code>).</td></tr></tbody></table> |

## Bảo hiểm oto

{% swagger method="post" path="/ocr/auto-insurance" baseUrl="https://ax.cyberapis.com" summary="Process Insurance Car" %}
{% swagger-description %}
API trả về thông tin như chủ xe, địa chỉ, điên thoại, số biển kiểm soát,... của bảo hiểm xe oto. 
{% endswagger-description %}

{% swagger-parameter in="header" name="X-Sender" required="true" type="String" %}
Mã định danh người gọi.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-APIKey" type="String" required="true" %}
Mã định danh của api.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="String" required="true" %}
Định dạng kiểu dữ liệu trả về trong header.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileId" type="String" %}
Mã file, xác định tính duy nhất của file đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileUrl" type="String" %}
Đường dẫn ảnh đầu vào.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBase64" type="String" %}
Định dạng kiểu dữ liệu trả về trong header
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileExtension" type="String" required="false" %}
File đầu vào nhận các giá trị 

`pdf`

 và 

`jpg`

 (mặc định).
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Ví dụ thành công" %}
```json
{
    "chuXe": {
        "Text": "Cao Nguyễn Thị Dung",
        "CharConfidences": [
            0.9791895,
            0.5355251,
            0.9553844,
            0.9953101,
            0.9406395,
            0.8474795,
            0.9712649,
            0.9999157,
            0.9998648,
            0.9999876,
            0.99976784,
            0.9998828,
            0.999895334,
            0.999923468,
            0.9999968,
            0.999797046,
            0.972565055,
            0.96215266,
            0.9993025
        ],
        "WordConfidences": [
            0.500985,
            0.774086356,
            0.9997016,
            0.9349136
        ],
        "WordCharConfidences": {
            "0": [
                0.9791895,
                0.5355251,
                0.9553844
            ],
            "1": [
                0.9406395,
                0.8474795,
                0.9712649,
                0.9999157,
                0.9998648,
                0.9999876
            ],
            "2": [
                0.9998828,
                0.999895334,
                0.999923468
            ],
            "3": [
                0.999797046,
                0.972565055,
                0.96215266,
                0.9993025
            ]
        },
        "LineConfidence": 0.3607,
        "X": 9,
        "Y": 165,
        "Width": 349,
        "Height": 72,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "diaChi": {
        "Text": "1/1101 - 06, T612, Cầu Dữu,Nam Từ Liên, HN",
        "CharConfidences": [
            0.362682462,
            0.6836726,
            0.9222262,
            0.990473,
            0.9501514,
            0.764517069,
            0.489169925,
            0.983732045,
            0.992239952,
            0.8145468,
            0.9984871,
            0.9993699,
            0.89714545,
            0.5210123,
            0.9429361,
            0.953561246,
            0.9990947,
            0.9793011,
            0.972268939,
            0.99720335,
            0.478924781,
            0.999272048,
            0.9999609,
            0.734941363,
            0.845711648,
            0.5592707,
            0.9804072
        ],
        "WordConfidences": [
            0.1645261,
            0.812802,
            0.4583548,
            0.477237731,
            0.340803117
        ],
        "WordCharConfidences": {
            "0": [
                0.362682462,
                0.6836726,
                0.9222262,
                0.990473,
                0.9501514,
                0.764517069
            ],
            "1": [
                0.8145468,
                0.9984871,
                0.9993699
            ],
            "2": [
                0.5210123,
                0.9429361,
                0.953561246,
                0.9990947,
                0.9793011
            ],
            "3": [
                0.99720335,
                0.478924781,
                0.999272048
            ],
            "4": [
                0.734941363,
                0.845711648,
                0.5592707,
                0.9804072
            ]
        },
        "LineConfidence": 0.00214157975,
        "X": 11,
        "Y": 235,
        "Width": 353,
        "Height": 126,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "dienThoai": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "soBienKiemSoat": {
        "Text": "306-530.59",
        "CharConfidences": [
            0.9998319,
            0.96327734,
            0.999191463,
            0.5590771,
            0.7003723,
            0.968336046,
            0.9995851,
            0.999979138,
            0.9928767,
            0.8962277,
            0.998209953
        ],
        "WordConfidences": [
            0.32454747
        ],
        "WordCharConfidences": {
            "0": [
                0.9998319,
                0.96327734,
                0.999191463,
                0.5590771,
                0.7003723,
                0.968336046,
                0.9995851,
                0.999979138,
                0.9928767,
                0.8962277
            ]
        },
        "LineConfidence": 0.324,
        "X": 19,
        "Y": 361,
        "Width": 340,
        "Height": 58,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "soKhung": {
        "Text": "694617395606",
        "CharConfidences": [
            0.967887,
            0.9944989,
            0.8173856,
            0.999845,
            0.9999852,
            0.8664919,
            0.999673,
            0.999936461,
            0.999328256,
            0.997834265,
            0.9999707,
            0.9999906
        ],
        "WordConfidences": [
            0.6794021
        ],
        "WordCharConfidences": {
            "0": [
                0.967887,
                0.9944989,
                0.8173856,
                0.999845,
                0.9999852,
                0.8664919,
                0.999673,
                0.999936461,
                0.999328256,
                0.997834265,
                0.9999707,
                0.9999906
            ]
        },
        "LineConfidence": 0.6794,
        "X": 16,
        "Y": 421,
        "Width": 348,
        "Height": 58,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "soMay": {
        "Text": "09203131960",
        "CharConfidences": [
            0.999982834,
            0.9999491,
            0.9981743,
            0.999984741,
            0.99987483,
            0.9999753,
            0.9973042,
            0.930897,
            0.69912225,
            0.5939457,
            0.8597544
        ],
        "WordConfidences": [
            0.3307567
        ],
        "WordCharConfidences": {
            "0": [
                0.999982834,
                0.9999491,
                0.9981743,
                0.999984741,
                0.99987483,
                0.9999753,
                0.9973042,
                0.930897,
                0.69912225,
                0.5939457,
                0.8597544
            ]
        },
        "LineConfidence": 0.3308,
        "X": 17,
        "Y": 479,
        "Width": 343,
        "Height": 55,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "namSanXuat": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "hangXe": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "loaiXe": {
        "Text": "Muceder- Đen, GI1250",
        "CharConfidences": [
            0.9998299,
            0.8742128,
            0.944917262,
            0.823624,
            0.8582979,
            0.9724826,
            0.7238757,
            0.725108445,
            0.641866,
            0.4280953,
            0.4708027,
            0.6690094,
            0.331256121,
            0.994138837,
            0.9922769,
            0.872732043,
            0.5196758,
            0.249206,
            0.9400601,
            0.9761109
        ],
        "WordConfidences": [
            0.298025131,
            0.0446658432,
            0.102910466
        ],
        "WordCharConfidences": {
            "0": [
                0.9998299,
                0.8742128,
                0.944917262,
                0.823624,
                0.8582979,
                0.9724826,
                0.7238757,
                0.725108445
            ],
            "1": [
                0.4280953,
                0.4708027,
                0.6690094,
                0.331256121
            ],
            "2": [
                0.9922769,
                0.872732043,
                0.5196758,
                0.249206,
                0.9400601,
                0.9761109
            ]
        },
        "LineConfidence": 0.0009,
        "X": 10,
        "Y": 538,
        "Width": 356,
        "Height": 58,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "trongTai": {
        "Text": "Muceder- Đen, GI1250",
        "CharConfidences": [
            0.9998299,
            0.8742128,
            0.944917262,
            0.823624,
            0.8582979,
            0.9724826,
            0.7238757,
            0.725108445,
            0.641866,
            0.4280953,
            0.4708027,
            0.6690094,
            0.331256121,
            0.994138837,
            0.9922769,
            0.872732043,
            0.5196758,
            0.249206,
            0.9400601,
            0.9761109
        ],
        "WordConfidences": [
            0.298025131,
            0.0446658432,
            0.102910466
        ],
        "WordCharConfidences": {
            "0": [
                0.9998299,
                0.8742128,
                0.944917262,
                0.823624,
                0.8582979,
                0.9724826,
                0.7238757,
                0.725108445
            ],
            "1": [
                0.4280953,
                0.4708027,
                0.6690094,
                0.331256121
            ],
            "2": [
                0.9922769,
                0.872732043,
                0.5196758,
                0.249206,
                0.9400601,
                0.9761109
            ]
        },
        "LineConfidence": 0.0009,
        "X": 11,
        "Y": 538,
        "Width": 357,
        "Height": 58,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "soChoNgoi": {
        "Text": "05",
        "CharConfidences": [
            0.8624856,
            0.0,
            0.999995232,
            0.999857664
        ],
        "WordConfidences": [
            0.9998529
        ],
        "WordCharConfidences": {
            "0": [
                0.999995232,
                0.999857664
            ]
        },
        "LineConfidence": 0.8624,
        "X": 12,
        "Y": 602,
        "Width": 364,
        "Height": 54,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "mucDichSuDung": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "gioHieuLuc": {
        "Text": "25h11",
        "CharConfidences": [
            0.701837242,
            0.422786653,
            0.876379,
            0.7367432,
            0.9761243,
            0.0,
            0.959429443,
            0.999974251,
            0.0,
            0.999999642,
            0.9999769,
            0.0,
            0.58360523,
            0.99960047,
            0.9999995
        ],
        "WordConfidences": [
            0.187012613,
            0.959404767,
            0.9999765,
            0.583371758
        ],
        "WordCharConfidences": {
            "0": [
                0.701837242,
                0.422786653,
                0.876379,
                0.7367432,
                0.9761243
            ],
            "1": [
                0.959429443,
                0.999974251
            ],
            "2": [
                0.999999642,
                0.9999769
            ],
            "3": [
                0.58360523,
                0.99960047,
                0.9999995
            ]
        },
        "LineConfidence": 0.1047,
        "X": 413,
        "Y": 78,
        "Width": 360,
        "Height": 45,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "gioKetThuc": {
        "Text": "14h11",
        "CharConfidences": [
            0.999663353,
            0.8655843,
            0.5166193,
            0.999956846,
            0.0,
            0.6033725,
            0.8716613,
            0.0,
            0.999999762,
            0.9999958,
            0.0,
            0.9686848,
            0.868965,
            0.999107063,
            0.999995
        ],
        "WordConfidences": [
            0.447007746,
            0.5259365,
            0.9999956,
            0.840997338
        ],
        "WordCharConfidences": {
            "0": [
                0.999663353,
                0.8655843,
                0.5166193,
                0.999956846
            ],
            "1": [
                0.6033725,
                0.8716613
            ],
            "2": [
                0.999999762,
                0.9999958
            ],
            "3": [
                0.9686848,
                0.868965,
                0.999107063,
                0.999995
            ]
        },
        "LineConfidence": 0.1977,
        "X": 410,
        "Y": 123,
        "Width": 370,
        "Height": 53,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "ngayHieuLuc": {
        "Text": "2359/14/2010",
        "CharConfidences": [
            0.999663353,
            0.8655843,
            0.5166193,
            0.999956846,
            0.0,
            0.6033725,
            0.8716613,
            0.0,
            0.999999762,
            0.9999958,
            0.0,
            0.9686848,
            0.868965,
            1.0,
            1.0,
            0.999107063,
            0.999995
        ],
        "WordConfidences": [
            0.447007746,
            0.5259365,
            0.9999956,
            0.840997338
        ],
        "WordCharConfidences": {
            "0": [
                0.999663353,
                0.8655843,
                0.5166193,
                0.999956846
            ],
            "1": [
                0.6033725,
                0.8716613
            ],
            "2": [
                0.999999762,
                0.9999958
            ],
            "3": [
                0.9686848,
                0.868965,
                0.999107063,
                0.999995
            ]
        },
        "LineConfidence": 0.1977,
        "X": 415,
        "Y": 123,
        "Width": 363,
        "Height": 52,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "ngayKetThuc": {
        "Text": "2359/14/2011",
        "CharConfidences": [
            0.999663353,
            0.8655843,
            0.5166193,
            0.999956846,
            0.0,
            0.6033725,
            0.8716613,
            0.0,
            0.999999762,
            0.9999958,
            0.0,
            0.9686848,
            0.868965,
            1.0,
            1.0,
            0.999107063,
            0.999995
        ],
        "WordConfidences": [
            0.447007746,
            0.5259365,
            0.9999956,
            0.840997338
        ],
        "WordCharConfidences": {
            "0": [
                0.999663353,
                0.8655843,
                0.5166193,
                0.999956846
            ],
            "1": [
                0.6033725,
                0.8716613
            ],
            "2": [
                0.999999762,
                0.9999958
            ],
            "3": [
                0.9686848,
                0.868965,
                0.999107063,
                0.999995
            ]
        },
        "LineConfidence": 0.1977,
        "X": 415,
        "Y": 123,
        "Width": 363,
        "Height": 52,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "ngayNop": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "phiBaoHiem": {
        "Text": "497000",
        "CharConfidences": [
            0.9999838,
            0.9992749,
            0.9876508,
            0.8746454,
            0.9999883,
            0.99999094,
            0.9999994
        ],
        "WordConfidences": [
            0.863185465
        ],
        "WordCharConfidences": {
            "0": [
                0.9999838,
                0.9992749,
                0.9876508,
                0.8746454,
                0.9999883,
                0.99999094,
                0.9999994
            ]
        },
        "LineConfidence": 0.8632,
        "X": 412,
        "Y": 249,
        "Width": 349,
        "Height": 45,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "phiBaoHiemPhaiNop": {
        "Text": "910700",
        "CharConfidences": [
            0.654399455,
            0.6125229,
            0.998091042,
            0.999785244,
            0.9978067,
            0.9994568,
            0.990974,
            0.7388075,
            0.9224892,
            0.993936241,
            0.9998636,
            0.999997258
        ],
        "WordConfidences": [
            0.3988895,
            0.677315056
        ],
        "WordCharConfidences": {
            "0": [
                0.654399455,
                0.6125229,
                0.998091042,
                0.999785244,
                0.9978067,
                0.9994568
            ],
            "1": [
                0.7388075,
                0.9224892,
                0.993936241,
                0.9998636,
                0.999997258
            ]
        },
        "LineConfidence": 0.2677,
        "X": 411,
        "Y": 297,
        "Width": 371,
        "Height": 47,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "phiBaoHiemPhaiNop1": {
        "Text": "0",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "phiBaoHiemPhaiNop2": {
        "Text": "0",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "nguoiCap": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    },
    "ngayCap": {
        "Text": "24/11/0",
        "CharConfidences": [
            0.586705,
            0.827689052,
            0.0,
            0.9999881,
            0.999958038,
            0.0,
            0.5735699,
            0.6947799,
            0.999969,
            0.983868361,
            0.9996338,
            0.9999919,
            0.999939442,
            0.0,
            0.84710604,
            0.933976054,
            0.7050805,
            0.450029731
        ],
        "WordConfidences": [
            0.485609323,
            0.9999461,
            0.398504823,
            0.9834405,
            0.251046062
        ],
        "WordCharConfidences": {
            "0": [
                0.586705,
                0.827689052
            ],
            "1": [
                0.9999881,
                0.999958038
            ],
            "2": [
                0.5735699,
                0.6947799
            ],
            "3": [
                0.983868361,
                0.9996338,
                0.9999919,
                0.999939442
            ],
            "4": [
                0.84710604,
                0.933976054,
                0.7050805,
                0.450029731
            ]
        },
        "LineConfidence": 0.0478,
        "X": 411,
        "Y": 808,
        "Width": 377,
        "Height": 143,
        "PageWidth": 1600,
        "PageHeight": 1128,
        "PageIndex": 0
    },
    "soPhieu": {
        "Text": "",
        "CharConfidences": [],
        "WordConfidences": [],
        "WordCharConfidences": {},
        "LineConfidence": 0.0,
        "X": 0,
        "Y": 0,
        "Width": 0,
        "Height": 0,
        "PageWidth": 0,
        "PageHeight": 0,
        "PageIndex": 0
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64.`</mark>
{% endhint %}

#### Ví dụ ảnh đầu vào

{% file src="../../.gitbook/assets/bao-hiem-tnds-o-to-500x300.jpg" %}
Mẫu bảo hiểm ô tô
{% endfile %}

#### Ý nghĩa thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

| Trường thông tin                         | Kiểu dữ liệu | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ---------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tên các trường thông tin trong bảo hiểm. | object       | <table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><code>Text</code></td><td>Giá trị text của dòng (hoặc cụm).</td></tr><tr><td><code>X</code></td><td>Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Y</code></td><td>ng độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Width</code></td><td>Chiều rộng của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>Height</code></td><td>Chiều cao của dòng có chữa ký tự Tiếng Việt</td></tr><tr><td><code>PageWidth</code></td><td>Chiều rộng của trang.</td></tr><tr><td><code>PageHeight</code></td><td>Chiều cao của trang.</td></tr><tr><td><code>CharConfidences</code></td><td>Danh sách độ chính xác của các ký tự của giá trị <code>Text</code> (trong <code>LineInfo</code>).</td></tr><tr><td><code>WordConfidences</code></td><td>Danh sách độ chính xác của các từ của giá trị <code>Text</code> (trong <code>LineInfo</code>).</td></tr><tr><td><code>WordCharConfidences</code></td><td>Thông tin về độ chính xác của các ký tự của các từ. <em><strong>Key</strong></em> của thông tin này là chỉ số thứ tự của từ trong <code>Text</code>, <em><strong>Value</strong></em> là danh sách độ chính xác của các ký tự trong từ.</td></tr><tr><td><code>LineConfidence</code></td><td>Độ chính xác của cả dòng <code>Text</code> (trong <code>LineInfo</code>).</td></tr></tbody></table> |
