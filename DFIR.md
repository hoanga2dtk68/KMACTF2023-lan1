DFIR

`Description`

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/81a83836-01e1-466c-abb0-48e1867fba95)

[Link download challange](https://drive.google.com/file/d/15nuNqTT96vZSLWqKu0DRn2pPGEmYT6PZ/view?usp=sharing)

`Solution`

Mục tiêu bài này là chúng ta cần tìm Computer Name, thời gian xem video hack cuối cùng, thời gian đăng nhập sai cuối cùng

*Computer Name*

Computer Name nằm ở mục SYSTEM chỉ cần search để lấy path và chúng ta vào registry explorer lấy computer name

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/a5e9569b-cdfe-4d2c-a2c8-f83c5eb9eca7)

`Computer Name: DESKTOP-AL3DV8F`

*Thời gian xem video hack cuối cùng*

Mở folder bằng Autopsy và vào mục Web history để tìm và lấy dấu thời gian

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/f3f147e5-e605-445c-b380-2a34fc25aa76)

Nhưng do lệch múi giờ là UTC+7 và UTC nên ta trừ đi 7h

`->21/05/2023-09:04:13`

`Lần đăng nhập thất bại cuối cùng`

Phần này chúng ta cần biết về registry như phần 1 và thông tin này có lưu ở SAM ném lên RegRipper

![image](https://github.com/hoanga2dtk68/KMACTF2023-1/assets/110059218/8adc58c6-4f64-404c-a622-dcecfc6243fb)

Từ file phân tích ra chúng ta có thể thấy lần đăng nhập cuối cùng của user

`09/05/2023-08:17:51`

`Flag: KMACTF{DESKTOP-AL3DV8F_21/05/2023-09:04:13_09/05/2023-08:17:51}`
