# SAFE NET 4A — bản tích hợp AI

## Cấu trúc thư mục

```text
SAFE_NET_4A_AI/
├── public/
│   └── index.html
├── netlify/
│   └── functions/
│       └── chat.mjs
├── netlify.toml
└── README.md
```

## Triển khai trên Netlify

1. Đưa toàn bộ thư mục này lên một GitHub repository (nên nhờ giáo viên hỗ trợ).
2. Trên Netlify, chọn Add new site → Import an existing project và kết nối repository.
3. Kiểm tra Build settings:
   - Build command: để trống (website tĩnh).
   - Publish directory: `public`.
   - Functions directory: `netlify/functions` (đã khai báo trong `netlify.toml`).
4. Vào Site configuration → Environment variables, thêm:
   - `OPENAI_API_KEY`: API key do giáo viên quản lý.
   - `OPENAI_MODEL`: tùy chọn; nếu bỏ trống, function dùng `gpt-4.1-mini`.
5. Lưu biến môi trường và deploy lại website.

## Kiểm tra

Mở website đã deploy, gửi thử một tin nhắn rồi gửi tiếp một câu hỏi liên quan.
Nếu AI nhớ đúng ngữ cảnh, kết nối nhiều lượt đang hoạt động.

## Bảo mật

- Tuyệt đối không đặt API key trong `index.html`, JavaScript phía trình duyệt,
  GitHub repository hoặc gửi key trong cuộc trò chuyện.
- Giáo viên quản lý API key, quyền truy cập và giới hạn chi phí.
- Không nhập dữ liệu nhận dạng cá nhân hoặc thông tin nhạy cảm của học sinh.
- `store: false` được gửi trong yêu cầu Responses API; vẫn cần đọc chính sách dữ liệu
  của nhà cung cấp và cấu hình tài khoản trước khi đưa vào sử dụng thật.
- Đây là công cụ hỗ trợ giáo dục, không thay thế người lớn đáng tin cậy hay chuyên gia.
