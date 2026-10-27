NFC Visit Card — Type 4 HCE

1. Sửa card/index.html: tên + link mạng xã hội.
2. Đưa thư mục card lên HTTPS, ví dụ GitHub Pages.
3. Lấy URL public của index.html.
4. Sửa CARD_URL trong:
   app/src/main/java/com/bruh/nfcvisit/MyHostApduService.java
5. Build APK trong Android Studio.
6. Cài APK lên điện thoại hỗ trợ HCE.
7. Bật NFC.

QUAN TRỌNG:
HCE của Android là ISO-DEP. Bản này triển khai NFC Forum Type 4 Tag NDEF Application
với AID D2760000850101, CC file E103 và NDEF file E104.

Điều này làm điện thoại hoạt động như một Type 4 NDEF tag ở tầng APDU.
Tuy nhiên, Android-to-Android không đảm bảo máy nhận sẽ tự động hiện trình duyệt chỉ
bằng cách chạm như khi quét một NFC tag vật lý. Máy nhận phải hỗ trợ/đọc ISO-DEP Type 4.
Nếu cần trải nghiệm "chạm là mở link" ổn định với mọi điện thoại, NFC tag vật lý vẫn
là phương án tương thích hơn.

Không cần chọn NFC Visit Card trong mục Google Pay. HCE thuộc Host Card Emulation,
không phải thẻ thanh toán.
