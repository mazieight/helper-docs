# نظام الصلاحيات الجديد - دليل الاستخدام
## New Permission System - Usage Guide

### نظرة عامة / Overview
تم تطوير نظام صلاحيات مرن يعتمد على الأدوار المحددة في الكونفيج بدلاً من صلاحيات Discord.
A flexible permission system that relies on config-defined roles instead of Discord permissions.

### أنواع الـ Decorators المتوفرة / Available Decorator Types

#### 1. الـ Decorators التقليدية / Traditional Decorators
- `@staff_only()` - يتحقق من صلاحيات Discord + الأدوار المحددة في الكونفيج
- `@staff_or_admin_only()` - يتحقق من صلاحيات Discord + الأدوار المحددة في الكونفيج

#### 2. الـ Decorators الجديدة (فقط الكونفيج) / New Decorators (Config Only)  
- `@config_staff_only()` - يتحقق فقط من الأدوار المحددة في الكونفيج
- `@config_admin_only()` - يتحقق فقط من الأدوار المحددة في الكونفيج
- `@config_staff_or_admin_only()` - يتحقق فقط من الأدوار المحددة في الكونفيج

### الوظائف المحدثة / Updated Functions

#### is_staff() و is_admin()
```python
is_staff(user, require_config_role_only=False)
is_admin(user, require_config_role_only=False)
```

**Parameters:**
- `user`: المستخدم للتحقق منه
- `require_config_role_only`: 
  - `False` (افتراضي): يتحقق من صلاحيات Discord + الكونفيج
  - `True`: يتحقق فقط من الأدوار المحددة في الكونفيج

### الأوامر المحدثة / Updated Commands

#### أوامر إدارة الأدوار / Role Management Commands
- `!setstaff @role1 @role2` - يستخدم `@config_admin_only()`
- `!setadmin @role1 @role2` - يستخدم `@config_admin_only()`
- `!showstaff` - يستخدم `@config_staff_or_admin_only()`
- `!showadmin` - يستخدم `@config_staff_or_admin_only()`

### استثناء المالك / Owner Exception
المالك (ID: [IDENTIFIER REDACTED]) يمكنه استخدام جميع الأوامر بغض النظر عن تكوين الأدوار.
The owner (ID: [IDENTIFIER REDACTED]) can use all commands regardless of role configuration.

### سيناريوهات الاستخدام / Usage Scenarios

#### 1. الإعداد الأولي / Initial Setup
```
Owner: !setadmin @AdminRole
Owner: !setstaff @ModeratorRole @HelperRole
```

#### 2. التحقق من الأدوار / Checking Roles
```
Any admin/staff: !showadmin
Any admin/staff: !showstaff
```

#### 3. إضافة أدوار جديدة / Adding New Roles
```
Admin user: !setstaff @NewModRole
Admin user: !setadmin @NewAdminRole
```

### مميزات النظام الجديد / New System Features

✅ **مرونة أكبر**: لا يحتاج المستخدم لصلاحيات Discord ليكون admin/staff
✅ **أمان محسن**: التحكم الكامل في من يمكنه استخدام الأوامر
✅ **سهولة الإدارة**: تعديل الأدوار دون تغيير صلاحيات Discord
✅ **توافق مع النظام القديم**: الـ decorators التقليدية لا تزال تعمل

### ملاحظات مهمة / Important Notes

1. **الأولوية للمالك**: المالك يمكنه استخدام جميع الأوامر دائماً
2. **لا توجد أدوار محددة**: إذا لم تكن هناك أدوار محددة، فقط المالك يمكنه الوصول
3. **التوافق**: النظام القديم والجديد يعملان جنباً إلى جنب
4. **الأمان**: الأوامر الحساسة تستخدم فقط الكونفيج الآن

### المتطلبات / Requirements
- تأكد من أن `guild_data_utils.py` يعمل بشكل صحيح
- تأكد من وجود ملفات الكونفيج للسيرفرات
- تحديث أي أوامر إضافية لاستخدام النظام الجديد حسب الحاجة
