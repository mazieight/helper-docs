# نظام Auto-Rename الجديد
## Auto-Rename System Guide

### نظرة عامة / Overview
نظام تلقائي لإعادة تسمية المستخدمين عندما ينضمون للسيرفر بإضافة tag محدد قبل اسمهم.
Automatic system to rename users when they join the server by adding a specific tag before their username.

### الأوامر المتوفرة / Available Commands

#### 1. تفعيل النظام / Enable System
```
!setautorename 𝑇𝑤✗
```
- يفعل النظام ويضبط الـ tag
- Enables the system and sets the tag

#### 2. إلغاء تفعيل النظام / Disable System  
```
!disableautorename
```
- يلغي تفعيل النظام
- Disables the system

#### 3. عرض الإعدادات / Show Settings
```
!autorenameinfo
```
- يعرض الإعدادات الحالية
- Shows current settings

#### 4. اختبار النظام / Test System
```
!testautorename @user
```
- يختبر النظام على مستخدم محدد
- Tests the system on a specific user

### مثال على الاستخدام / Usage Example

#### الإعداد / Setup
```
!setautorename 𝑇𝑤✗
```

#### النتيجة / Result
عندما ينضم المستخدم `laylay98` للسيرفر:
When user `laylay98` joins the server:

**قبل / Before:** `laylay98`
**بعد / After:** `𝑇𝑤✗ laylay98`

### الصلاحيات المطلوبة / Required Permissions

#### للبوت / For Bot:
- `Manage Nicknames` - لتغيير أسماء المستخدمين
- `Manage Nicknames` - to change user nicknames

#### للمستخدم / For User:
- `Administrator` - لاستخدام أوامر الإعداد
- `Administrator` - to use setup commands

### ملفات الكونفيج / Config Files
يتم حفظ الإعدادات في:
Settings are saved in:
```
data/{guild_id}/auto_rename.json
```

#### هيكل الملف / File Structure:
```json
{
    "enabled": true,
    "prefix": "𝑇𝑤✗",
    "format": "𝑇𝑤✗ {username}"
}
```

### المميزات / Features
✅ **تلقائي**: يعمل فور انضمام المستخدم
✅ **قابل للتخصيص**: يمكن تغيير الـ tag
✅ **آمن**: يتطلب صلاحيات الإدارة
✅ **قابل للاختبار**: أمر اختبار منفصل

✅ **Automatic**: Works immediately when user joins
✅ **Customizable**: Can change the tag
✅ **Secure**: Requires admin permissions  
✅ **Testable**: Separate test command

### ملاحظات مهمة / Important Notes

1. **أولوية الصلاحيات**: البوت لا يمكنه إعادة تسمية المالك أو الأعضاء ذوي الصلاحيات الأعلى
   **Permission Priority**: Bot cannot rename owner or members with higher permissions

2. **حد الطول**: أسماء Discord لها حد أقصى 32 حرف
   **Length Limit**: Discord nicknames have a 32 character limit

3. **الأحرف الخاصة**: تأكد من أن الـ tag يحتوي أحرف مدعومة
   **Special Characters**: Make sure the tag contains supported characters

### استكشاف الأخطاء / Troubleshooting

#### المشكلة: البوت لا يغير الاسم
**الحل:**
- تأكد من صلاحية `Manage Nicknames` للبوت
- تأكد من أن البوت أعلى في الترتيب من المستخدم

#### Problem: Bot doesn't change nickname
**Solution:**
- Ensure bot has `Manage Nicknames` permission
- Ensure bot is higher in role hierarchy than user
