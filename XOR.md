<img width="373" alt="image" src="https://github.com/Vanmaxohp/MSEC---Baby-Dragon-CTF/assets/90485791/34426a7c-f500-475e-92b6-db8b464d9f34">

Trong bài này, khi tải output.txt về ta sẽ nhận được 1 dãy hex như sau:

`0x7112f78c5d4f524f35edb74957785d2fd690484a535428dca879404b4f24edee0704061d6093ee07045a`

Mở file chal.py ra thì thấy đoan code:
```
from pwn import xor
from Cryptodome.Util.number import *
import secrets
from flag import flag

key = secrets.token_bytes(7)
print(key)

flag = xor(flag, key)

with open("output.txt", "w") as f:
    f.write(hex(bytes_to_long(flag)))
```

Từ đoạn code, ta biết rằng chương trình sẽ sinh ngẫu nhiên một key có kích thước 7 bit, sau đó xor với flag, sau đó chuyển thành số nguyên dàu và sau đó là dãy hex.
Từ hint 1 ta biết được flag có dang: MSEC{something_here_!!!} Ta nghĩ ngay đến việc XOR 5 ký tự đầu `MSEC{` với 5 byte đầu của ciphertext để có được 5 byte đầu của key, XOR 2 ký tự cuối `!}` với 2 byte cuối của ciphertext đễ có được 2 byte cuối của key
Đầu tiên, chuyển `MSEC{` và `!}` thành dạng hex bằng vài tool online, sau đó xor bằng máy tính CASIO, ta có được key là `3C 41 B2 CF 26 25 27`.
Cuối cùng dùng tool decode xor trên trang dcode.fr, ta có được flag
`MSEC{just_xor_and_nothing_else_!!!!!!!!!!}`
