<img width="375" alt="image" src="https://github.com/Vanmaxohp/MSEC---Baby-Dragon-CTF/assets/90485791/9a14c730-80e5-453e-92f8-26162c635f4a">

Trong bài này khi tải file cònig.py về, ta nhận được một dãy bit

```ct = '10000001010100011010000110010100100000011001100110110001100001011001110010000001101001011100110010000001000110010011000100000101000111011110110110100101110100001101010101111100110011011011100011000001110101001110010110100001011111011010100101010100110101010101000101111101110100001011110101111101110011010010000011000101100110011101000101111101001101001100110111110100100000```

Theo đề bài gợi ý, ta nghĩ ngay đến việc convert dãy bit đó sang string, lên gg search và dùng 1 tool convert thử thì ta nhận được một dãy ký tực không thể đọc được. Lúc này nhìn lại dãy bit, ta thử chia nó ra thành các tổ hợp 8 bit thì thấy thừa ra 6 bit, cảm thấy có gì đó bất thường, để ý thấy 8 bit đầu tiên không thể convert sang 1 ký tự đọc được, ta xoá đi 6 bit đầu tiền và convert lại.
Kết quả nhận được là: `The flag is FLAG{it5_3n0u9h_jU5T_tO_sH1ft_M3} `
