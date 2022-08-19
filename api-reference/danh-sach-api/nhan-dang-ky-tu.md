---
description: >-
  API Cho phép nhận dạng các files ảnh hoặc pdf chữ in, chữ viết tay Tiếng
  Việt.
---

# Nhận dạng ký tự

## Cài đặt API

{% swagger method="post" path="/rec/img2text" baseUrl="https://ax.cyberapis.com" summary="Nhận dạng ký tự" %}
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

{% swagger-response status="200: OK" description="Chữ viết tay" %}
```javascript
{
    "text": "Hoàng Đức Long"
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Chữ in" %}
```javascript
[
    {
        "Area": "0, 0, 434, 68",
        "LineClusterInfos": [
            [
                {
                    "CharConfidences": [
                        0.99990416,
                        0.940431,
                        0.99968815,
                        0.9996835,
                        0.98426545,
                        0.99969935,
                        0.99986017,
                        0.9891606,
                        0.9999012,
                        0.9999058,
                        0.9999999,
                        0.9999989,
                        0.9995547,
                        0.9999778,
                        0.99999917,
                        0.9999901,
                        0.9999645,
                        0.99996614,
                        0.998262,
                        0.9999702,
                        0.9999989,
                        0.99996805,
                        0.99955267,
                        0.99999964
                    ],
                    "KieuChuViet": 2,
                    "LineConfidence": 0.91180235,
                    "WordCharConfidences": {
                        "0": [
                            0.99990416,
                            0.940431
                        ],
                        "1": [
                            0.9996835,
                            0.98426545,
                            0.99969935,
                            0.99986017
                        ],
                        "2": [
                            0.9999012,
                            0.9999058,
                            0.9999999,
                            0.9999989,
                            0.9995547,
                            0.9999778
                        ],
                        "3": [
                            0.9999901,
                            0.9999645,
                            0.99996614,
                            0.998262
                        ],
                        "4": [
                            0.9999989,
                            0.99996805,
                            0.99955267,
                            0.99999964
                        ]
                    },
                    "WordConfidences": [
                        0.9403409,
                        0.98352057,
                        0.9993384,
                        0.99818283,
                        0.9995193
                    ],
                    "WordInfos": [
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "0, 14, 34, 35",
                            "Index": 0,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "Họ",
                            "hOCR": "<span class='ionex_word' id='w_0_0_0' ione_info='iarea 0 14 34 49; ione_wcf 0'>Họ</span>"
                        },
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "55, 14, 68, 35",
                            "Index": 1,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "tên:",
                            "hOCR": "<span class='ionex_word' id='w_0_0_1' ione_info='iarea 55 14 123 49; ione_wcf 0'>tên:</span>"
                        },
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "144, 14, 102, 35",
                            "Index": 2,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "NGUYỄN",
                            "hOCR": "<span class='ionex_word' id='w_0_0_2' ione_info='iarea 144 14 246 49; ione_wcf 0'>NGUYỄN</span>"
                        },
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "267, 14, 68, 35",
                            "Index": 3,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "HOÀI",
                            "hOCR": "<span class='ionex_word' id='w_0_0_3' ione_info='iarea 267 14 335 49; ione_wcf 0'>HOÀI</span>"
                        },
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "357, 14, 68, 35",
                            "Index": 4,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "LINH",
                            "hOCR": "<span class='ionex_word' id='w_0_0_4' ione_info='iarea 357 14 425 49; ione_wcf 0'>LINH</span>"
                        }
                    ],
                    "Area": "0, 14, 425, 35",
                    "Index": 0,
                    "PageHeight": 68,
                    "PageWidth": 434,
                    "Text": "Họ tên: NGUYỄN HOÀI LINH",
                    "hOCR": "     <span class='ione_line' id='ln_0_0' ione_info=\"iarea 0 14 425 49 0 0 0 0 0\"><span class='ionex_word' id='w_0_0_0' ione_info='iarea 0 14 34 49; ione_wcf 0'>Họ</span> <span class='ionex_word' id='w_0_0_1' ione_info='iarea 55 14 123 49; ione_wcf 0'>tên:</span> <span class='ionex_word' id='w_0_0_2' ione_info='iarea 144 14 246 49; ione_wcf 0'>NGUYỄN</span> <span class='ionex_word' id='w_0_0_3' ione_info='iarea 267 14 335 49; ione_wcf 0'>HOÀI</span> <span class='ionex_word' id='w_0_0_4' ione_info='iarea 357 14 425 49; ione_wcf 0'>LINH</span> \r\n     </span>"
                },
                {
                    "CharConfidences": [
                        0.9972248,
                        0.997771,
                        0.99999475,
                        0.9999783,
                        0.9999976,
                        0.9999995,
                        0.99996936
                    ],
                    "KieuChuViet": 2,
                    "LineConfidence": 0.9949419,
                    "WordCharConfidences": {
                        "0": [
                            0.9972248,
                            0.997771
                        ],
                        "1": [
                            0.9999783,
                            0.9999976,
                            0.9999995,
                            0.99996936
                        ]
                    },
                    "WordConfidences": [
                        0.99500203,
                        0.9999448
                    ],
                    "WordInfos": [
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "0, 22, 26, 30",
                            "Index": 0,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "Họ",
                            "hOCR": "<span class='ionex_word' id='w_0_1_0' ione_info='iarea 0 22 26 52; ione_wcf 0'>Họ</span>"
                        },
                        {
                            "Confidence": 0.800000011920929,
                            "Area": "44, 22, 52, 30",
                            "Index": 1,
                            "PageHeight": 0,
                            "PageWidth": 0,
                            "Text": "tên:",
                            "hOCR": "<span class='ionex_word' id='w_0_1_1' ione_info='iarea 44 22 96 52; ione_wcf 0'>tên:</span>"
                        }
                    ],
                    "Area": "0, 22, 96, 30",
                    "Index": 1,
                    "PageHeight": 68,
                    "PageWidth": 434,
                    "Text": "Họ tên:",
                    "hOCR": "     <span class='ione_line' id='ln_0_1' ione_info=\"iarea 0 22 96 52 0 0 0 0 0\"><span class='ionex_word' id='w_0_1_0' ione_info='iarea 0 22 26 52; ione_wcf 0'>Họ</span> <span class='ionex_word' id='w_0_1_1' ione_info='iarea 44 22 96 52; ione_wcf 0'>tên:</span> \r\n     </span>"
                }
            ]
        ],
        "LineInfos": [
            {
                "CharConfidences": [
                    0.99990416,
                    0.940431,
                    0.99968815,
                    0.9996835,
                    0.98426545,
                    0.99969935,
                    0.99986017,
                    0.9891606,
                    0.9999012,
                    0.9999058,
                    0.9999999,
                    0.9999989,
                    0.9995547,
                    0.9999778,
                    0.99999917,
                    0.9999901,
                    0.9999645,
                    0.99996614,
                    0.998262,
                    0.9999702,
                    0.9999989,
                    0.99996805,
                    0.99955267,
                    0.99999964,
                    1,
                    1,
                    1,
                    0.9972248,
                    0.997771,
                    0.99999475,
                    0.9999783,
                    0.9999976,
                    0.9999995,
                    0.99996936
                ],
                "KieuChuViet": 2,
                "LineConfidence": 0.9071904,
                "WordCharConfidences": {
                    "0": [
                        0.99990416,
                        0.940431
                    ],
                    "1": [
                        0.9996835,
                        0.98426545,
                        0.99969935,
                        0.99986017
                    ],
                    "2": [
                        0.9999012,
                        0.9999058,
                        0.9999999,
                        0.9999989,
                        0.9995547,
                        0.9999778
                    ],
                    "3": [
                        0.9999901,
                        0.9999645,
                        0.99996614,
                        0.998262
                    ],
                    "4": [
                        0.9999989,
                        0.99996805,
                        0.99955267,
                        0.99999964
                    ],
                    "5": [
                        0.9972248,
                        0.997771
                    ],
                    "6": [
                        0.9999783,
                        0.9999976,
                        0.9999995,
                        0.99996936
                    ]
                },
                "WordConfidences": [
                    0.9403409,
                    0.98352057,
                    0.9993384,
                    0.99818283,
                    0.9995193,
                    0.99500203,
                    0.9999448
                ],
                "WordInfos": [
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "0, 14, 34, 35",
                        "Index": 0,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "Họ",
                        "hOCR": "<span class='ionex_word' id='w_0_0_0' ione_info='iarea 0 14 34 49; ione_wcf 0'>Họ</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "55, 14, 68, 35",
                        "Index": 1,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "tên:",
                        "hOCR": "<span class='ionex_word' id='w_0_0_1' ione_info='iarea 55 14 123 49; ione_wcf 0'>tên:</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "144, 14, 102, 35",
                        "Index": 2,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "NGUYỄN",
                        "hOCR": "<span class='ionex_word' id='w_0_0_2' ione_info='iarea 144 14 246 49; ione_wcf 0'>NGUYỄN</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "267, 14, 68, 35",
                        "Index": 3,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "HOÀI",
                        "hOCR": "<span class='ionex_word' id='w_0_0_3' ione_info='iarea 267 14 335 49; ione_wcf 0'>HOÀI</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "357, 14, 68, 35",
                        "Index": 4,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "LINH",
                        "hOCR": "<span class='ionex_word' id='w_0_0_4' ione_info='iarea 357 14 425 49; ione_wcf 0'>LINH</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "0, 22, 26, 30",
                        "Index": 0,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "Họ",
                        "hOCR": "<span class='ionex_word' id='w_0_1_0' ione_info='iarea 0 22 26 52; ione_wcf 0'>Họ</span>"
                    },
                    {
                        "Confidence": 0.800000011920929,
                        "Area": "44, 22, 52, 30",
                        "Index": 1,
                        "PageHeight": 0,
                        "PageWidth": 0,
                        "Text": "tên:",
                        "hOCR": "<span class='ionex_word' id='w_0_1_1' ione_info='iarea 44 22 96 52; ione_wcf 0'>tên:</span>"
                    }
                ],
                "Area": "0, 14, 425, 38",
                "Index": 0,
                "PageHeight": 68,
                "PageWidth": 434,
                "Text": "Họ tên: NGUYỄN HOÀI LINH   Họ tên:",
                "hOCR": "   <div class='ione_blarea' id='bl_0_0' ione_info=\"iarea 0 14 425 52\">\r\n    <p class='ione_prg' id='prg_0_0' ione_info=\"iarea 0 14 425 52\">\r\n     <span class='ione_line' id='ln_0_0' ione_info=\"iarea 0 14 425 49 0 0 0 0 0\"><span class='ionex_word' id='w_0_0_0' ione_info='iarea 0 14 34 49; ione_wcf 0'>Họ</span> <span class='ionex_word' id='w_0_0_1' ione_info='iarea 55 14 123 49; ione_wcf 0'>tên:</span> <span class='ionex_word' id='w_0_0_2' ione_info='iarea 144 14 246 49; ione_wcf 0'>NGUYỄN</span> <span class='ionex_word' id='w_0_0_3' ione_info='iarea 267 14 335 49; ione_wcf 0'>HOÀI</span> <span class='ionex_word' id='w_0_0_4' ione_info='iarea 357 14 425 49; ione_wcf 0'>LINH</span> \r\n     </span>\r\n     <span class='ione_line' id='ln_0_1' ione_info=\"iarea 0 22 96 52 0 0 0 0 0\"><span class='ionex_word' id='w_0_1_0' ione_info='iarea 0 22 26 52; ione_wcf 0'>Họ</span> <span class='ionex_word' id='w_0_1_1' ione_info='iarea 44 22 96 52; ione_wcf 0'>tên:</span> \r\n     </span>\r\n    </p>\r\n   </div>"
            }
        ],
        "PageIndex": 0,
        "PageSize": "434, 68",
        "Text": "Họ tên: NGUYỄN HOÀI LINH   Họ tên:",
        "WordInfos": [
            {
                "Confidence": 0.800000011920929,
                "Area": "0, 14, 34, 35",
                "Index": 0,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "Họ",
                "hOCR": "<span class='ionex_word' id='w_0_0_0' ione_info='iarea 0 14 34 49; ione_wcf 0'>Họ</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "55, 14, 68, 35",
                "Index": 1,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "tên:",
                "hOCR": "<span class='ionex_word' id='w_0_0_1' ione_info='iarea 55 14 123 49; ione_wcf 0'>tên:</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "144, 14, 102, 35",
                "Index": 2,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "NGUYỄN",
                "hOCR": "<span class='ionex_word' id='w_0_0_2' ione_info='iarea 144 14 246 49; ione_wcf 0'>NGUYỄN</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "267, 14, 68, 35",
                "Index": 3,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "HOÀI",
                "hOCR": "<span class='ionex_word' id='w_0_0_3' ione_info='iarea 267 14 335 49; ione_wcf 0'>HOÀI</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "357, 14, 68, 35",
                "Index": 4,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "LINH",
                "hOCR": "<span class='ionex_word' id='w_0_0_4' ione_info='iarea 357 14 425 49; ione_wcf 0'>LINH</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "0, 22, 26, 30",
                "Index": 0,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "Họ",
                "hOCR": "<span class='ionex_word' id='w_0_1_0' ione_info='iarea 0 22 26 52; ione_wcf 0'>Họ</span>"
            },
            {
                "Confidence": 0.800000011920929,
                "Area": "44, 22, 52, 30",
                "Index": 1,
                "PageHeight": 0,
                "PageWidth": 0,
                "Text": "tên:",
                "hOCR": "<span class='ionex_word' id='w_0_1_1' ione_info='iarea 44 22 96 52; ione_wcf 0'>tên:</span>"
            }
        ]
    }
]
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Chữ viết tay và chữ in" %}
```javascript
[
    {
        "Field": "Nơi thường trú/tạm trú",
        "Page": 0,
        "PageWidth": 1110,
        "PageHeight": 105,
        "Line": 0,
        "OrderInLine": 0,
        "Text": "ấp An Bình xã Trung Hòa",
        "CharConfidences": [
            0.997184336,
            0.99994123,
            0.9999869,
            0.999958038,
            0.999954,
            0.999912858,
            0.999770939,
            0.998533,
            0.999984264,
            0.999988556,
            0.6339199,
            0.9953957,
            0.999991536,
            0.9999279,
            0.9997136,
            0.9999906,
            0.999731958,
            0.999974966,
            0.9999993,
            0.9999709,
            0.9996958,
            0.6489433,
            0.99999404
        ],
        "WordConfidences": [
            0.997125745,
            0.999912,
            0.9982771,
            0.9953873,
            0.99941045,
            0.648742
        ],
        "WordCharConfidences": {
            "0": [
                0.997184336,
                0.99994123
            ],
            "1": [
                0.999958038,
                0.999954
            ],
            "2": [
                0.999770939,
                0.998533,
                0.999984264,
                0.999988556
            ],
            "3": [
                0.9953957,
                0.999991536
            ],
            "4": [
                0.9997136,
                0.9999906,
                0.999731958,
                0.999974966,
                0.9999993
            ],
            "5": [
                0.9996958,
                0.6489433,
                0.99999404
            ]
        },
        "LineConfidence": 0.407115638,
        "X": 407,
        "Y": 4,
        "Width": 700,
        "Height": 94
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Lưu ý**: Chỉ cần truyền hoặc <mark style="color:yellow;background-color:yellow;">`fileUrl`</mark> hoặc <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>, nếu truyền cả 2 tham số thì ưu tiên xử lý <mark style="color:yellow;background-color:yellow;">`fileBase64`</mark>.
{% endhint %}

## Thông tin trả về

Kết quả trả về có dạng **JSON** bao gồm các trường thông tin.

### Chữ viết tay

| Trường thông tin | Kiểu dữ liệu | Ghi chú                                      |
| ---------------- | ------------ | -------------------------------------------- |
| `Text`           | string       | Giá trị (nội dung) trường thông tin viết tay |

### Chữ in

| Trường thông tin | Kiểu dữ liệu | Ghi chú                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---------------- | ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Area`           | string       | Các tham số của 1 _Reactangle_ theo tứ tự **X** **Y** **Width** **Height**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `PageIndex`      | number       | Thứ tự của trang, bắt đầu bằng giá trị 0                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `PageSize`       | number       | Kích của trang theo thứ tự **Width** **Height**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `Text`           | string       | Giá trị (nội dung) trường thông tin viết tay                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `LineInfos`      | array object | <table data-header-hidden><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><code>Index</code></td><td>Thứ tự của dòng (hoặc cụm).</td></tr><tr><td><code>Text</code></td><td>Giá trị text của dòng (hoặc cụm).</td></tr><tr><td><code>KieuChuViet</code></td><td>Kiểu chữ viết: 0 = Không xác định, 1 = Chữ viết tay, 2 = Chữ in</td></tr><tr><td><code>Area</code></td><td>Các tham số của 1 <em>Reactangle</em> theo tứ tự <strong>X</strong> <strong>Y</strong> <strong>Width</strong> <strong>Height</strong>.</td></tr><tr><td><code>PageWidth</code></td><td>Chiều rộng của trang.</td></tr><tr><td><code>PageHeight</code></td><td>Chiều cao của trang.</td></tr><tr><td><code>CharConfidences</code></td><td>Danh sách độ chính xác của các ký tự của giá trị <code>Text</code> (trong <code>LineInfo</code>).</td></tr><tr><td><code>WordConfidences</code></td><td>Danh sách độ chính xác của các từ của giá trị <code>Text</code> (trong <code>LineInfo</code>).</td></tr><tr><td><code>WordCharConfidences</code></td><td>Thông tin về độ chính xác của các ký tự của các từ. <em><strong>Key</strong></em> của thông tin này là chỉ số thứ tự của từ trong <code>Text</code>, <em><strong>Value</strong></em> là danh sách độ chính xác của các ký tự trong từ.</td></tr><tr><td><code>LineConfidence</code></td><td>Độ chính xác của cả dòng <code>Text</code> (trong <code>LineInfo</code>).</td></tr></tbody></table> |

### Chữ in và chữ viết tay

| Trường thông tin      | Kiểu dữ liệu | Ghi chú                                                                                                                                                                             |
| --------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Field`               | string       | Tên trường bóc tách được từ biểu mẫu                                                                                                                                                |
| `Page`                | number       | Thứ tự của trang, bắt đầu bằng giá trị 0                                                                                                                                            |
| `PageWidth`           | number       | Chiều rộng của trang                                                                                                                                                                |
| `PageHeight`          | number       | Chiều cao của trang                                                                                                                                                                 |
| `Line`                | number       | Thứ tự của dòng, bắt đầu bằng giá trị 0                                                                                                                                             |
| `OrderInLine`         | number       | Thứ tự của trường này trong dòng, bắt đầu bằng 0                                                                                                                                    |
| `Text`                | string       | Giá trị (nội dung) trường thông tin viết tay                                                                                                                                        |
| `CharConfidences`     | array        | Danh sách độ chính xác của các ký tự của giá trị `Text`.                                                                                                                            |
| `WordConfidences`     | array        | Danh sách độ chính xác của các từ của giá trị `Text`.                                                                                                                               |
| `WordCharConfidences` | dictionary   | Thông tin về độ chính xác của các ký tự của các từ. _**Key**_ của thông tin này là chỉ số thứ tự của từ trong `Text`, _**Value**_ là danh sách độ chính xác của các ký tự trong từ. |
| `LineConfidence`      | number       | Độ chính xác của cả dòng `Text`.                                                                                                                                                    |
| `X`                   | number       | Hoành độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                  |
| `Y`                   | number       | Tung độ điểm trên cùng bên trái của dòng có chữa ký tự Tiếng Việt                                                                                                                   |
| `Width`               | number       | Chiều rộng của dòng có chữa ký tự Tiếng Việt                                                                                                                                        |
| `Height`              | number       | Chiều cao của dòng có chữa ký tự Tiếng Việt                                                                                                                                         |
