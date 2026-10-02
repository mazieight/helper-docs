# تحديث أصحاب البوت - Multiple Owners Update
## Bot Owners Update Summary

### التحديثات المطبقة / Applied Updates

#### 1. تحديث ملفات owners.json / Updated owners.json Files
جميع ملفات owners.json تحتوي الآن على كلا المالكين:
All owners.json files now contain both owners:

**السيرفرات / Servers:**
- `[IDENTIFIER REDACTED]/owners.json` ✅
- `[IDENTIFIER REDACTED]/owners.json` ✅  
- `[IDENTIFIER REDACTED]/owners.json` ✅

**المحتوى / Content:**
```json
[
    [IDENTIFIER REDACTED],  // المالك الأساسي / Primary Owner
    [IDENTIFIER REDACTED]  // المالك الثاني / Secondary Owner
]
```

#### 2. تحديث أمر !join / Updated !join Command
**الملف:** `owner_join_command.py`
```python
# قبل / Before
if ctx.author.id != [IDENTIFIER REDACTED]:

# بعد / After  
if ctx.author.id not in [[IDENTIFIER REDACTED], [IDENTIFIER REDACTED]]:
```

#### 3. تحديث نظام الصلاحيات / Updated Permission System
**الملف:** `staff_roles_cmd.py`

**الـ Decorators المحدثة / Updated Decorators:**
- `config_staff_only()`
- `config_admin_only()`
- `config_staff_or_admin_only()`

```python
# قبل / Before
if ctx.author.id == [IDENTIFIER REDACTED]:

# بعد / After
if ctx.author.id in [[IDENTIFIER REDACTED], [IDENTIFIER REDACTED]]:
```

### النتائج / Results
✅ **كلا المالكين يمكنهما الآن:**
- استخدام أمر `!join`
- تجاوز جميع فحوصات الصلاحيات
- الوصول لجميع أوامر الإدارة

✅ **Both owners can now:**
- Use `!join` command
- Bypass all permission checks
- Access all admin commands

### المالكين المسموحين / Authorized Owners
1. **[IDENTIFIER REDACTED]** - المالك الأساسي / Primary Owner
2. **[IDENTIFIER REDACTED]** - المالك الثاني / Secondary Owner

### الأوامر المتاحة / Available Commands
- `!join` - الانضمام للـ voice channel
- `!setstaff` - تعيين أدوار المساعدين
- `!setadmin` - تعيين أدوار الإدارة
- `!showstaff` - عرض أدوار المساعدين
- `!showadmin` - عرض أدوار الإدارة
- جميع أوامر المالك الأخرى / All other owner commands
