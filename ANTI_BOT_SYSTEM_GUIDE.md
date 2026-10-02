# 🤖 نظام الحماية من البوتات / Anti-Bot Security System

## الوصف / Description

نظام أمان متقدم يحمي خادمك من البوتات غير المرغوب فيها والمضافة بدون إذن. يسمح فقط لمالك الخادم بإضافة البوتات الجديدة.

An advanced security system that protects your server from unwanted and unauthorized bots. Only allows server owner to add new bots.

## ✨ المميزات / Features

### 🔍 المراقبة الذكية / Smart Monitoring
- مراقبة تلقائية لجميع البوتات الجديدة
- فحص فوري لمن أضاف البوت
- تحليل سجل التدقيق (Audit Log)

### 👥 نظام الصلاحيات / Permission System
- **مسموح / Allowed:**
  - 👑 مالك الخادم فقط / Server Owner only

- **ممنوع / Blocked:**
  - 🚫 جميع المستخدمين الآخرين / All other users
  - ⚠️ الموظفين والإداريين / Staff and admins
  - 🔒 أي شخص ليس المالك / Anyone who is not the owner

### 📊 التسجيل المتقدم / Advanced Logging
- تسجيل جميع محاولات إضافة البوتات
- إشعار الأشخاص المخالفين
- توثيق الإضافات المصرح بها

## 🚀 كيفية الاستخدام / How to Use

### 1. تفعيل النظام / Enable System
```
!antbots on
```

### 2. إيقاف النظام / Disable System
```
!antbots off
```

### 3. عرض الحالة / Show Status
```
!antbots status
```

## 🔧 الأوامر المتاحة / Available Commands

| الأمر / Command | الوصف / Description | الصلاحيات / Permissions |
|---|---|---|
| `!antbots [on/off/status]` | تشغيل/إيقاف نظام الحماية من البوتات | Admin only |
| `!securitystatus` | عرض تقرير شامل عن جميع أنظمة الأمان | Manage Guild |

### أمثلة أخرى / Other Examples
```bash
!antbots enable    # تفعيل
!antbots تفعيل     # تفعيل بالعربية
!antbots disable   # إيقاف
!antbots إيقاف     # إيقاف بالعربية
!antibot on        # باستخدام الاختصار
!botprotection on  # باستخدام الاسم البديل
```

## ⚡ سير العمل / Workflow

عند انضمام بوت جديد للخادم:
When a new bot joins the server:

1. **فحص النوع** - التأكد من أن العضو الجديد بوت
   **Type Check** - Verify the new member is a bot

2. **فحص التفعيل** - التحقق من تفعيل نظام الحماية
   **System Check** - Verify anti-bot system is enabled

3. **البحث عن المُضيف** - فحص سجل التدقيق لمعرفة من أضاف البوت
   **Find Inviter** - Check audit log to find who added the bot

4. **فحص الصلاحيات** - التحقق من صلاحيات المُضيف
   **Permission Check** - Verify inviter's permissions

5. **اتخاذ الإجراء** - السماح أو الطرد حسب الصلاحيات
   **Take Action** - Allow or kick based on permissions

6. **التسجيل** - توثيق الإجراء في قناة السجلات
   **Logging** - Document action in log channel

## 🎮 أمثلة عملية / Practical Examples

### المثال 1: تفعيل النظام
```
Admin: !antbots on
Bot: ✅ تم تفعيل نظام الحماية من البوتات!
```

### المثال 2: محاولة إضافة بوت (مستخدم عادي)
```
[User adds a bot]
Bot: [طرد البوت فوراً + تحذير المستخدم + تسجيل الإجراء]
```

### المثال 3: محاولة إضافة بوت (موظف/إداري)
```
[Staff/Admin adds a bot]
Bot: [طرد البوت فوراً + تحذير "فقط المالك يستطيع" + تسجيل الإجراء]
```

### المثال 4: إضافة بوت (مالك الخادم)
```
[Owner adds a bot]
Bot: [السماح للبوت بالبقاء + تسجيل الإضافة المصرح بها]
```

## 🛡️ مستويات الحماية / Protection Levels

### 🟢 المستوى الأخضر - مصرح به / Green Level - Authorized
- **👑 مالك الخادم فقط** - صلاحية كاملة لإضافة أي بوت

### 🔴 المستوى الأحمر - مرفوض / Red Level - Rejected
- **🚫 جميع المستخدمين الآخرين** - ممنوع من إضافة البوتات
- **⚠️ الموظفين والإداريين** - ممنوع من إضافة البوتات (حماية صارمة)
- **🔒 الأعضاء الجدد** - حماية إضافية من الإضافات العشوائية
- **🤖 البوتات المجهولة** - طرد فوري إذا لم يُعثر على المُضيف

## 🔒 الأمان والخصوصية / Security & Privacy

### الحماية المتقدمة / Advanced Protection
- ✅ مراقبة فورية للبوتات الجديدة
- ✅ فحص سجل التدقيق بدقة
- ✅ نظام صلاحيات متعدد المستويات
- ✅ حماية من البوتات الضارة والسبام

### الخصوصية / Privacy
- ❌ لا يتدخل في البوتات الموجودة مسبقاً
- ❌ لا يخزن معلومات حساسة
- ✅ يسجل فقط الإجراءات الأمنية المهمة
- ✅ شفافية كاملة في التسجيل

## 🛠️ متطلبات البوت / Bot Requirements

### الصلاحيات المطلوبة / Required Permissions
- **Kick Members** - لطرد البوتات غير المصرح بها
- **View Audit Log** - لمعرفة من أضاف البوت
- **Send Messages** - لإرسال الإشعارات والتحذيرات
- **Manage Guild** - للوصول لإعدادات الخادم (اختياري)

### ترتيب الأدوار / Role Hierarchy
- يجب أن تكون رتبة البوت أعلى من البوتات المراد حمايتها منها
- تأكد من عدم وجود صلاحيات "Administrator" للبوتات الأخرى

## 🔍 استكشاف الأخطاء / Troubleshooting

### المشكلة: النظام لا يطرد البوتات
**الحلول:**
1. تأكد من تفعيل النظام: `!antbots status`
2. تحقق من صلاحية "Kick Members"
3. تأكد من أن رتبة البوت أعلى من البوت المراد طرده
4. تحقق من ترتيب الأدوار في إعدادات الخادم

### المشكلة: لا يمكن معرفة من أضاف البوت
**الحلول:**
1. تأكد من صلاحية "View Audit Log"
2. تحقق من إعدادات سجل التدقيق في الخادم
3. قد يحدث تأخير بسيط - النظام يحاول عدة مرات

### المشكلة: يطرد بوتات الموظفين
**الحلول:**
1. تأكد من صحة إعداد الأدوار: `!showstaff` و `!showadmin`
2. تحقق من أن الموظف لديه الدور الصحيح
3. راجع ملفات الإعدادات في `/data/[guild_id]/`

## 🆕 التحديثات المستقبلية / Future Updates

### قيد التطوير / In Development
- 🔄 قائمة بيضاء للبوتات المصرح بها
- 📊 إحصائيات مفصلة عن البوتات
- ⏰ نظام تنبيه متقدم للإضافات المشبوهة
- 🎯 فحص سمعة البوتات قبل السماح لها

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

## 🔗 الأنظمة المرتبطة / Related Systems

### نظام منع روابط الدعوة / Anti-Invite System
- يمكن استخدامه مع `!antinvite on`
- حماية شاملة من الروابط والبوتات
- نفس نظام الصلاحيات والاستثناءات

### نظام إدارة الأدوار / Role Management System
- `!setstaff @role` - لتحديد أدوار الموظفين
- `!setadmin @role` - لتحديد أدوار الإداريين
- `!showstaff` و `!showadmin` - لعرض الأدوار الحالية

---

## 🔐 ملاحظات أمنية مهمة / Important Security Notes

⚠️ **تحذير:** تأكد من صحة إعداد أدوار الموظفين والإداريين قبل تفعيل النظام لتجنب منع الإضافات المرغوبة.

⚠️ **Warning:** Make sure staff and admin roles are properly configured before enabling the system to avoid blocking desired additions.

✅ **نصيحة:** استخدم `!securitystatus` بانتظام للتأكد من عمل جميع أنظمة الحماية بشكل صحيح.

✅ **Tip:** Use `!securitystatus` regularly to ensure all protection systems are working properly.

🔧 **إعداد مُوصى:** قم بتفعيل كلا النظامين `!antinvite on` و `!antbots on` للحماية الشاملة.

🔧 **Recommended Setup:** Enable both systems `!antinvite on` and `!antbots on` for comprehensive protection.

---

**🌟 By Piwpiw Helper | نظام الحماية المتقدم من البوتات 🤖**
