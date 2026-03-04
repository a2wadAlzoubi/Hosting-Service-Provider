Awad Alzo'ubi, [12/25/2025 2:16 AM]
🌐 Internet Service Provider System API
📌 نظرة عامة
Internet Service Provider System API 
هو نظام واجهة خلفية متكاملة باستخدام Asp.NetCore API
يهدف إلى إدارة عمليات مزود خدمة الإنترنت  بشكل مركزي ومرن 

العملاء(Customer)
الاشتراكات(Subscription)
الخطط والباقات(ProviderPlan)
السيرفرات(ComputerServer)
الفواتير(Bill)
طرق الدفع(PaymentMethode)
طلبات الدفع (QR / Screenshots)
الدعم الفني(Support)
تم تصميم الـ API وفق معايير 
RESTful Architecture مع توثيق كامل باستخدام Swagger (OpenAPI).
🧱 التقنيات المستخدمة
ASP.NET Core Web API
Entity Framework Core
SQL Server
Swagger / OpenAPI
Serilog
RESTful API Design
DTOs & Pagination
CRUD and Soft Delete
Status Management (Enums)
📂 بنية المشروع 
نسخ التعليمات البرمجية

├── Controllers
├── Models
├── DTOs
├── Services
├── Repositories
├── Data
│   └── DbContext
├── Enums
├── Program.cs
└── appsettings.json
🔐 المصادقة (Authentication)
تيجيل دخول العملاء عبر:
نسخ التعليمات البرمجية
POST /api/Customer/login
يدعم التمييز بين:
مستخدم عادي
مدير (Admin)
⚠️ يمكن لاحقًا توسيعه لإضافة JWT Authentication.
📑 الوحدات الأساسية (Modules)
👤 Customer
إدارة العملاء وحساباتهم.
أهم العمليات:
إضافة / تحديث / حذف (Soft Delete)
عرض جميع العملاء (Pagination)
تسجيل الدخول
جلب الاشتراكات والدعم الفني الخاص بالعميل
Endpoints مثال:
GET    /api/Customer/getall/{pageNumber}/{pageSize}
POST   /api/Customer/add
PUT    /api/Customer/update
DELETE /api/Customer/softdelete/{customerId}
POST   /api/Customer/login
📦 Subscription
إدارة اشتراكات العملاء.
الخصائص:
ربط العميل بخطة وسيرفر
تحديد فترة الاشتراك
حالات الاشتراك (Active – Suspended – Cancelled)
Endpoints:
POST   /api/Subscription/add
PUT    /api/Subscription/update
GET    /api/Subscription/get/{subscriptionId}
DELETE /api/Subscription/delete/{subscriptionId}
PATCH  /api/Subscription/attachcustomer/{customerId}/to/{subscriptionId}
🧾 Bill
إدارة الفواتير والمدفوعات.
يدعم:
حالات الفاتورة (Unpaid – Paid – Overdue – Rejected)
ربط الفاتورة باشتراك وطريقة دفع
حساب المبلغ المتبقي
Endpoints:
GET    /api/Bill/getall/{pageNumber}/{pageSize}
POST   /api/Bill/add
PUT    /api/Bill/update
GET    /api/Bill/get/{billId}
PATCH  /api/Bill/paidit/{billId}
PATCH  /api/Bill/overdueit/{billId}
💳 Payment Method
إدارة طرق الدفع (Cash – Bank – Online…).
Endpoints:
GET    /api/PaymentMethode/getall/{pageNumber}/{pageSize}
POST   /api/PaymentMethode/add
PUT    /api/PaymentMethode/update
DELETE /api/PaymentMethode/delete/{paymentMethodeId}
📸 Payment Request
إدارة طلبات الدفع المرفقة (صور / QR).
يدعم:
رفع إثبات دفع
حالات الطلب (Pending – Approved – Rejected)
Endpoints:
POST   /api/PaymentRequest/add/{billId}
PATCH  /api/PaymentRequest/appeoved/{billId}
PATCH  /api/PaymentRequest/reject/{billId}
GET    /api/PaymentRequest/pendingpayments
🖥️ Computer Server
إدارة سيرفرات الاستضافة.
الخصائص:
تفعيل / تعطيل السيرفر
ربط السيرفر بخطة أو اشتراك
Endpoints:
GET    /api/server/getall/{pageNumber}/{pageSize}
POST   /api/server/add
PUT    /api/server/update
DELETE /api/server/delete/{serverId}
PATCH  /api/server/active/{serverId}
PATCH  /api/server/deactive/{serverId}
📊 Provider Plan
إدارة باقات الإنترنت.
تشمل:
السرعة
السعة التخزينية
السعر الشهري
مستوى الخطة (Diamond / Gold / Silver / Bronze)
Endpoints:
GET    /api/ProviderPlan/getall/{pageNumber}/{pageSize}
POST   /api/ProviderPlan/add
PUT    /api/ProviderPlan/update
DELETE /api/ProviderPlan/delete/{planId}
🛠️ Support
إدارة طلبات الدعم الفني.
حالات الدعم:
New
InProgress
Closed
Endpoints:
GET    /api/Support/getall/{pageNumber}/{pageSize}
POST   /api/Support/add
PUT    /api/Support/update
DELETE /api/Support/delete/{supportId}
📘 التوثيق (Swagger)
بعد تشغيل المشروع يمكنك الوصول إلى التوثيق الكامل عبر:
نسخ التعليمات البرمجية

https://localhost:{PORT}/swagger

⚙️ طريقة التشغيل
المتطلبات
.NET 9 أو أحدث
SQL Server
الخطوات

git clone <repository-url>
cd InternetServiceProviderSystem
dotnet restore
dotnet run
🧪 الميزات التقنية
✔ Pagination
✔ Soft Delete
✔ Enum Status Management
✔ Clean RESTful APIs
✔ Swagger Documentation
✔ Ready for JWT Integration
📈 قابلية التطوير
إضافة JWT Authentication
Role-Based Authorization
Logging & Monitoring
Payment Gateway Integration
Frontend (Angular / React)
👨‍💻 المطور
Name: ِAwad Aloubi
Email: alzoubiawad123@gmail.com
