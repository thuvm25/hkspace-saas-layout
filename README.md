# HKSpace SaaS Layout

Layout và UI cho hệ thống SaaS subscription management dựa trên các slide thiết kế.

## Cấu trúc dự án

```
hkspace-saas-layout/
├── custom.css                      # Custom CSS override (Bootstrap 5.3)
├── landing-page.html
├── checkout.html
├── payment.html
├── subscription.html
├── renew-plan.html
├── change-plan-checkout.html
├── add-seat-checkout.html
```

## Công nghệ

- **Bootstrap 5.3** - Framework CSS
- **Custom CSS** - Modern design với gradients, shadows, animations
- **Pure HTML** - Các trang riêng lẻ, không cần backend

## Các màn hình theo Slide

### Slide 1: Landing Page (Pricing Plans)
- File: `landing-page.html`
- Hiển thị 3 gói: Free, Basic, Advanced
- Mỗi gói có thông tin: giá, trial, features
- Nút "Đăng ký" → redirect đến checkout

### Slide 2: Checkout (Registration)
- File: `checkout.html`
- Form đăng ký: Tên, Email, Password
- Thông tin doanh nghiệp/cá nhân
- Chọn phương thức thanh toán: Chuyển khoản/ Momo, Visa/Thẻ
- Invoice hiển thị bên phải với thông tin gói

### Slide 3: Payment Gateway
- File: `payment.html`
- Sidebar: Các phương thức thanh toán
- Form nhập thông tin thẻ ATM
- Card preview real-time
- Order summary bên phải
- Timer countdown

### Slide 4-5: Account Subscription
- File: `subscription.html`
- **Trạng thái Active & Recurring:**
  - Hiển thị thông tin gói đang dùng
  - Next billing date và amount
  - Actions: Ngừng đăng ký, Đổi gói, Hủy
- **Trạng thái Active & No Recurring:**
  - Cảnh báo sẽ hết hạn
  - Actions: Đăng ký lại, Đổi gói, Hủy
- **Trạng thái Ended:**
  - Thông báo không còn gói
  - Hướng dẫn đăng ký lại
- **Seat Management:**
  - Danh sách seats và users
  - Add/Remove seats
  - Assign/Remove users

### Slide 6: Change Plan / Add Seat Checkout
- Files: `change-plan-checkout.html`, `add-seat-checkout.html`
- Form checkout tương tự Slide 2
- Invoice riêng cho từng action:
  - ChangePlanInvoice: Tính toán chênh lệch
  - AddSeatInvoice: Tính toán phí thêm seats

### Slide 7-9: Renew Plan
- File: `renew-plan.html`
- **Payment auto charge:**
  - Hiển thị invoice với thông tin auto charge
  - Thông tin thẻ thanh toán
- **Payment not auto charge:**
  - Invoice với nút thanh toán thủ công
  - Link đến payment page
- **Change Plan:**
  - Hiển thị pricing plans
  - Nút Change để đổi gói
- **Add Seat:**
  - Form chọn số lượng seats
  - Continue → checkout

## Tính năng UI/UX

### Design System
- **Màu sắc:**
  - Primary: #1e3a8a (Dark blue)
  - Secondary: #ea580c (Orange)
  - Accent Purple: #7c3aed
  - Accent Green: #10b981

### Components
- **Pricing Cards:** Orange gradient với rounded corners
- **Invoice Cards:** Tương tự pricing cards, hiển thị thông tin invoice
- **Form Inputs:** Border focus, hints, validation
- **Buttons:** Phân loại theo màu (primary, secondary, danger, purple)
- **Status Badges:** Màu theo trạng thái (paid, new, error)

### Responsive
- Mobile-friendly với Bootstrap grid
- Breakpoints: md (768px), lg (992px)
 
### Lưu ý
- Tất cả các file HTML đều độc lập, có thể mở trực tiếp
- JavaScript được embed trong HTML để xử lý navigation
- CSS được tách riêng trong `custom.css` để dễ maintain

## Notes

- Tất cả text đều bằng tiếng Việt
- Các slide reference được giữ nguyên trong code
- Invoice status: paid, failed, new
- Subscription status: active, ended
- Payment methods: Bank transfer, Card, QR, E-wallet

