# نظام Auto-Rename منفصل لكل Guild
## Guild-Specific Auto-Rename System

### كيف يعمل النظام / How It Works

كل سيرفر (Guild) له إعدادات auto-rename منفصلة ومستقلة تماماً عن السيرفرات الأخرى.
Each server (Guild) has completely separate and independent auto-rename settings from other servers.

### أمثلة عملية / Practical Examples

#### السيرفر الأول: Gaming Community
```bash
Admin: !setautorename [GAMER]
Bot: ✅ Auto-rename enabled with tag "[GAMER]"

# عضو جديد ينضم:
User "ali123" joins → "[GAMER] ali123"
User "sara456" joins → "[GAMER] sara456"
```

#### السيرفر الثاني: VIP Club  
```bash
Admin: !setautorename 💎VIP
Bot: ✅ Auto-rename enabled with tag "💎VIP"

# عضو جديد ينضم:
User "ali123" joins → "💎VIP ali123"
User "sara456" joins → "💎VIP sara456"
```

#### السيرفر الثالث: Study Group
```bash
Admin: !setautorename 📚Student
Bot: ✅ Auto-rename enabled with tag "📚Student"

# عضو جديد ينضم:
User "ali123" joins → "📚Student ali123"
User "sara456" joins → "📚Student sara456"
```

#### السيرفر الرابع: معطل النظام
```bash
Admin: !disableautorename
Bot: 🔴 Auto-rename disabled

# عضو جديد ينضم:
User "ali123" joins → "ali123" (لا تغيير)
User "sara456" joins → "sara456" (لا تغيير)
```

### هيكل الملفات / File Structure

```
data/
├── [IDENTIFIER REDACTED]/          # Gaming Community
│   └── auto_rename.json
│       {
│         "enabled": true,
│         "prefix": "[GAMER]",
│         "format": "[GAMER] {username}"
│       }
│
├── [IDENTIFIER REDACTED]/          # VIP Club
│   └── auto_rename.json
│       {
│         "enabled": true,
│         "prefix": "💎VIP",
│         "format": "💎VIP {username}"
│       }
│
├── [IDENTIFIER REDACTED]/          # Study Group
│   └── auto_rename.json
│       {
│         "enabled": true,
│         "prefix": "📚Student",
│         "format": "📚Student {username}"
│       }
│
└── [IDENTIFIER REDACTED]/          # معطل النظام
    └── auto_rename.json
        {
          "enabled": false,
          "prefix": "",
          "format": "{username}"
        }
```

### المميزات / Features

✅ **مستقل لكل سيرفر**: كل سيرفر له إعداداته الخاصة
✅ **Independent per server**: Each server has its own settings

✅ **إعدادات مختلفة**: يمكن لكل سيرفر استخدام tag مختلف
✅ **Different settings**: Each server can use a different tag

✅ **تحكم منفصل**: يمكن تفعيل/إلغاء النظام لكل سيرفر بشكل منفصل
✅ **Separate control**: Can enable/disable system for each server separately

✅ **لا تداخل**: تغيير إعدادات سيرفر لا يؤثر على الآخرين
✅ **No interference**: Changing one server's settings doesn't affect others

### أمر التحقق السريع / Quick Check Command

للتحقق من حالة النظام في أي سيرفر:
To check system status in any server:

```bash
!autorenameinfo
```

**سيعرض:**
- حالة النظام (مفعل/معطل)
- الـ tag المستخدم
- مثال على النتيجة

### ملاحظة مهمة / Important Note

نفس المستخدم يمكن أن يكون له أسماء مختلفة في سيرفرات مختلفة:
The same user can have different names in different servers:

**المستخدم "laylay98":**
- في Gaming Server: `[GAMER] laylay98`
- في VIP Club: `💎VIP laylay98`  
- في Study Group: `📚Student laylay98`
- في سيرفر آخر: `laylay98` (بدون تغيير)
