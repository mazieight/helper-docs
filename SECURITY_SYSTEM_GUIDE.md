# 🛡️ نظام الأمان ضد روابط الدعوة / Anti-Invite Security System

## الوصف / Description

نظام أمان متقدم يحمي خادمك من روابط دعوة Discord غير المصرح بها. يقوم النظام بحذف الرسائل التي تحتوي على روابط دعوة تلقائياً وطرد المستخدمين الذين ينشرونها (باستثناء الموظفين والإداريين).

An advanced security system that protects your server from unauthorized Discord invite links. The system automatically deletes messages containing invite links and kicks users who post them (except staff and admins).

## ✨ المميزات / Features

### 🔍 الكشف الذكي / Smart Detection
- يكتشف جميع أنواع روابط Discord
- يدعم الروابط المختصرة والمخصصة
- فحص دقيق باستخدام Regex patterns

### 👥 الاستثناءات / Exemptions
- الموظفين المحددين بـ `!setstaff`
- الإداريين المحددين بـ `!setadmin`
- المستخدمين بصلاحيات إدارية في Discord

### 📊 التسجيل المتقدم / Advanced Logging
- تسجيل جميع الإجراءات الأمنية
- إرسال تحذير للمستخدم عبر الرسائل الخاصة
- إشعار مؤقت في القناة

## 🚀 كيفية الاستخدام / How to Use

### 1. تفعيل النظام / Enable System
```
!antinvite on
```

### 2. إيقاف النظام / Disable System
```
!antinvite off
```

### 3. عرض الحالة / Show Status
```
!antinvite status
```
أو / or
```
!securitystatus
```

## 🔧 الأوامر المتاحة / Available Commands

| الأمر / Command | الوصف / Description | الصلاحيات / Permissions |
|---|---|---|
| `!antinvite [on/off/status]` | تشغيل/إيقاف نظام منع الروابط | Admin only |
| `!securitystatus` | عرض تقرير شامل عن الأمان | Manage Guild |

### أمثلة أخرى / Other Examples
```bash
!antinvite enable    # تفعيل
!antinvite تفعيل     # تفعيل بالعربية
!antinvite disable   # إيقاف
!antinvite إيقاف     # إيقاف بالعربية
```

## 🎯 الروابط المكتشفة / Detected Links

النظام يكتشف هذه الأنواع من الروابط:
The system detects these types of links:

- `discord.gg/ABC123`
- `discordapp.com/invite/XYZ789`
- `discord.com/invite/SERVER123`
- `dsc.gg/SHORT456`
- `invite.gg/CUSTOM789`

## ⚡ سير العمل / Workflow

عند اكتشاف رابط دعوة:
When an invite link is detected:

1. **فحص الصلاحيات** - التحقق من أن المستخدم ليس موظف/إداري
   **Permission Check** - Verify user is not staff/admin

2. **حذف الرسالة** - إزالة الرسالة فوراً
   **Delete Message** - Remove message immediately

3. **إرسال تحذير** - رسالة خاصة للمستخدم
   **Send Warning** - Private message to user

4. **طرد المستخدم** - إزالة من الخادم
   **Kick User** - Remove from server

5. **تسجيل الإجراء** - توثيق في قناة السجلات
   **Log Action** - Document in log channel

6. **إشعار القناة** - رسالة مؤقتة (10 ثواني)
   **Channel Notification** - Temporary message (10 seconds)

## 🔒 الأمان والخصوصية / Security & Privacy

### الحماية المتقدمة / Advanced Protection
- ✅ لا يتأثر بالروابط في الكود أو النص المنسق
- ✅ يتجاهل رسائل البوتات
- ✅ لا يعالج الأوامر (التي تبدأ بـ !)
- ✅ حماية من التفعيل الخاطئ

### الخصوصية / Privacy
- ❌ لا يخزن محتوى الرسائل
- ❌ لا يتدخل في الرسائل الخاصة
- ✅ يسجل فقط الإجراءات الأمنية المهمة

## 🛠️ متطلبات البوت / Bot Requirements

### الصلاحيات المطلوبة / Required Permissions
- **Kick Members** - لطرد المستخدمين
- **Manage Messages** - لحذف الرسائل
- **View Audit Log** - لتسجيل الأحداث
- **Send Messages** - لإرسال الإشعارات

### التحقق من الصلاحيات / Check Permissions
استخدم `!securitystatus` للتحقق من صلاحيات البوت
Use `!securitystatus` to check bot permissions

## 🎮 أمثلة عملية / Practical Examples

### المثال 1: تفعيل النظام
```
Admin: !antinvite on
Bot: ✅ تم تفعيل نظام الأمان ضد روابط الدعوة!
```

### المثال 2: محاولة نشر رابط (مستخدم عادي)
```
User: Join my server! discord.gg/ABC123
Bot: [حذف الرسالة + طرد المستخدم + تسجيل الإجراء]
```

### المثال 3: نشر رابط (موظف)
```
Staff: Join our partner server discord.gg/PARTNER
Bot: [لا يتخذ أي إجراء - مسموح للموظفين]
```

## 🔍 استكشاف الأخطاء / Troubleshooting

### المشكلة: النظام لا يعمل
**الحل:**
1. تأكد من تفعيل النظام: `!antinvite status`
2. تحقق من صلاحيات البوت: `!securitystatus`
3. تأكد من أن البوت في المرتبة الصحيحة في التسلسل الهرمي

### المشكلة: لا يمكن طرد المستخدمين
**الحل:**
1. تحقق من صلاحية "Kick Members"
2. تأكد من أن رتبة البوت أعلى من رتبة المستخدم
3. راجع إعدادات الخادم

### المشكلة: الروابط لا تُكتشف
**الحل:**
1. تأكد من أن الرابط من الأنواع المدعومة
2. تحقق من تفعيل النظام
3. تأكد من أن المستخدم ليس موظف/إداري

## 🆕 التحديثات المستقبلية / Future Updates

### قيد التطوير / In Development
- 🔄 قائمة بيضاء للخوادم المصرح بها
- 🎯 كشف أنواع أخرى من الروابط الضارة
- 📊 إحصائيات مفصلة عن الأمان
- ⏰ نظام إنذار متقدم

### طلب ميزات / Feature Requests
يمكنك طلب ميزات جديدة من خلال:
You can request new features via:
- التواصل مع المطور Laylay98
- اقتراحات في خادم الدعم

## 📞 الدعم والمساعدة / Support & Help

للحصول على مساعدة إضافية:
For additional help:

- **المطور:** Laylay98 👾
- **الفريق:** Piwpiw Helper
- **الأوامر:** `!help security` للمزيد من التفاصيل

---

## 🔐 ملاحظات أمنية مهمة / Important Security Notes

⚠️ **تحذير:** هذا النظام مصمم للحماية من الروابط غير المصرح بها. تأكد من تحديد الموظفين بشكل صحيح لتجنب قيود غير مرغوبة.

⚠️ **Warning:** This system is designed to protect against unauthorized links. Make sure to properly configure staff roles to avoid unwanted restrictions.

✅ **نصيحة:** استخدم `!securitystatus` بانتظام للتأكد من أن جميع الأنظمة تعمل بشكل صحيح.

✅ **Tip:** Use `!securitystatus` regularly to ensure all systems are working properly.

---

**🌟 By Piwpiw Helper | نظام الأمان المتقدم 🛡️**
