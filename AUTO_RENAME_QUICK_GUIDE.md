# نظام Auto-Rename - الأوامر السريعة
## Quick Auto-Rename Commands

### الإعداد السريع / Quick Setup

#### 1. تفعيل النظام
```
!setautorename 𝑇𝑤✗
```
**النتيجة:** البوت سيضيف `𝑇𝑤✗` قبل اسم كل مستخدم جديد

#### 2. عرض الحالة
```
!autorenameinfo
```
**النتيجة:** يعرض إذا كان النظام مفعل وما هو الـ tag المستخدم

#### 3. اختبار النظام
```
!testautorename @username
```
**النتيجة:** يجرب تغيير اسم المستخدم المحدد

#### 4. إلغاء التفعيل
```
!disableautorename
```
**النتيجة:** يوقف النظام

### مثال على الاستخدام / Usage Example

```
Admin: !setautorename 𝑇𝑤✗
Bot: ✅ Auto-rename system enabled with tag "𝑇𝑤✗"

[User "laylay98" joins server]
Bot: 🏷️ Auto-renamed laylay98 to '𝑇𝑤✗ laylay98'
```

### الصلاحيات المطلوبة / Required Permissions
- **للمستخدم:** Administrator
- **للبوت:** Manage Nicknames

### ملاحظات سريعة / Quick Notes
✅ يعمل تلقائياً عند انضمام المستخدمين الجدد
✅ يمكن تغيير الـ tag في أي وقت  
✅ يمكن اختبار النظام قبل الاستخدام
✅ يمكن إيقافه في أي وقت

❌ لا يمكن إعادة تسمية المالك أو الأعضاء ذوي الصلاحيات العالية
❌ حد أقصى 32 حرف لاسم المستخدم
