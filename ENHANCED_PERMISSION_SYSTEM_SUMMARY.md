# Enhanced Permission System for Jail and Suspension Commands

## تم بنجاح - Successfully Completed! ✅

لقد تم تحديث نظام الصلاحيات بحيث يمكن للأدوار المحددة بـ `!setrolestaff` و `!setrolestaffs` و `!setroleadmin` استخدام أوامر الـ jail والـ suspension.

The permission system has been successfully updated so that roles set with `!setrolestaff`, `!setrolestaffs`, and `!setroleadmin` can use jail and suspension commands.

## Changes Made / التغييرات المُطبقة

### 1. Jail Commands (jail_commands.py)

**Enhanced `is_authorized_staff()` method to check multiple role sources:**
- ✅ config.json verification.staff_role_ids (set by `!setrolestaff`)
- ✅ staff_roles.json (set by `!setstaffroles`) 
- ✅ admin_roles.json (set by `!setroleadmin`)
- ✅ jail_data.json staff_role_id (legacy support)

### 2. Suspension Commands (verification_commands.py)

**Enhanced `is_staff_member()` method to check multiple role sources:**
- ✅ config.json verification.staff_role_ids (set by `!setrolestaff`)
- ✅ staff_roles.json (set by `!setstaffroles`)
- ✅ admin_roles.json (set by `!setroleadmin`)

**Added new commands:**
- ✅ `!setrolestaff @role1 @role2` - Sets staff roles for verification/suspension/jail commands
- ✅ `!setrolestaffs @role1 @role2` - Alias for setrolestaff
- ✅ `!setroleadmin @role1 @role2` - Sets admin roles for all moderation commands

## Usage Examples / أمثلة الاستخدام

```bash
# Set staff roles that can use jail and suspension commands
!setrolestaff @Moderator @Helper @Support

# Alternative alias
!setrolestaffs @Moderator @Helper @Support

# Set admin roles that can use all commands
!setroleadmin @Admin @SuperAdmin

# Check existing staff roles (from staff_roles_cmd.py)
!showstaffroles
!showadminroles
```

## Permission Hierarchy / تسلسل الصلاحيات

1. **Bot Owner** (highest) - Can use all commands
2. **Admin Roles** (`!setroleadmin`) - Can use all moderation commands
3. **Staff Roles** (`!setrolestaff`/`!setstaffroles`) - Can use jail/suspension/verification commands
4. **Guild Administrators** - Can use suspension commands (existing Discord permissions)

## Commands Available to Staff Roles / الأوامر المتاحة للأدوار

### Jail Commands (أوامر الـ Jail)
- `!jail @user reason` - Jail a user
- `!unjail @user reason` - Unjail a user
- `!tempjail @user 1h reason` - Temporarily jail a user
- `!listjailed` - List all jailed users
- `!jailinfo @user` - Get jail information for a user
- `!checkjail @user` - Check if a user is jailed

### Suspension Commands (أوامر التعليق)
- `!sus @user reason` - Suspend a user
- `!removesus @user reason` - Remove suspension from a user
- `!listsus` - List all suspended users
- `!checksus @user` - Check if a user is suspended

### Verification Commands (أوامر التحقق)
- `!vb @user` - Verify as boy
- `!vg @user` - Verify as girl
- `!resetverif @user` - Reset verification
- And other verification commands...

## Technical Details / التفاصيل التقنية

### Files Modified:
1. **jail_commands.py** - Enhanced permission checking for jail commands
2. **verification_commands.py** - Enhanced permission checking for suspension commands + added new management commands
3. **test_permission_system.py** - Updated test documentation

### Role Storage Locations:
- **config.json** `verification.staff_role_ids` - Used by `!setrolestaff`
- **staff_roles.json** - Used by `!setstaffroles` (existing command)
- **admin_roles.json** - Used by `!setroleadmin`
- **jail_data.json** `settings.staff_role_id` - Legacy jail-specific role (still supported)

### Backward Compatibility:
- ✅ All existing role configurations continue to work
- ✅ Legacy jail staff role still supported
- ✅ Existing `!setstaffroles` command unaffected
- ✅ Guild administrator permissions still work for suspension commands

## Status: READY FOR USE / الحالة: جاهز للاستخدام

The system is now fully integrated and ready for production use. Users with roles set by any of the three commands (`!setrolestaff`, `!setrolestaffs`, `!setroleadmin`) can now use jail and suspension commands as requested.

النظام الآن متكامل بالكامل وجاهز للاستخدام. المستخدمون الذين لديهم أدوار محددة بأي من الأوامر الثلاثة يمكنهم الآن استخدام أوامر الـ jail والـ suspension كما هو مطلوب.