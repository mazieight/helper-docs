# أوامر Emoji & Sticker الجديدة
## New Emoji & Sticker Commands

### نظرة عامة / Overview
نظام شامل لإدارة الـ emojis والـ stickers في السيرفر مع واجهة سهلة الاستخدام.
Comprehensive system for managing emojis and stickers in the server with user-friendly interface.

### الأوامر المتوفرة / Available Commands

#### 📥 إضافة المحتوى / Adding Content

##### إضافة Emoji:
```
!addemoji <name> <url>
!addemoji <name> (مع attachment)
```
**مثال:**
```
!addemoji cool_face https://example.com/emoji.png
!addemoji happy (مع إرفاق صورة)
```

##### إضافة Sticker:
```
!addsticker <name> [description] (مع attachment)
```
**مثال:**
```
!addsticker happy_cat This is a happy cat sticker
```

#### 🗑️ حذف المحتوى / Removing Content

##### حذف Emoji:
```
!removeemoji <emoji>
!removeemoji <emoji_name>
```
**مثال:**
```
!removeemoji :cool_face:
!removeemoji cool_face
```

##### حذف Sticker:
```
!removesticker <sticker_name>
```
**مثال:**
```
!removesticker happy_cat
```

#### 📋 عرض المحتوى / Listing Content

##### عرض جميع الـ Emojis:
```
!listemojis
```
**النتيجة:** قائمة مقسمة لصفحات تعرض جميع emojis السيرفر

##### عرض جميع الـ Stickers:
```
!liststickers
```
**النتيجة:** قائمة تعرض جميع stickers السيرفر

#### ℹ️ معلومات مفصلة / Detailed Information

##### معلومات Emoji:
```
!emojiinfo <emoji>
!emojiinfo <emoji_name>
```
**النتيجة:** معلومات تفصيلية عن الـ emoji (تاريخ الإنشاء، ID، الخ)

### الصيغ المدعومة / Supported Formats

#### للـ Emojis:
- **PNG** - الأكثر شيوعاً
- **JPG/JPEG** - للصور العادية  
- **GIF** - للـ animated emojis
- **WEBP** - صيغة حديثة
- **الحد الأقصى:** 256KB

#### للـ Stickers:
- **PNG** - للصور الثابتة
- **APNG** - للصور المتحركة  
- **GIF** - للرسوم المتحركة
- **JSON (Lottie)** - للرسوم المتحركة المتقدمة
- **الحد الأقصى:** 500KB

### الصلاحيات المطلوبة / Required Permissions

#### للمستخدم / For User:
- **Manage Emojis** - لأوامر الـ emojis
- **Manage Emojis and Stickers** - لأوامر الـ stickers

#### للبوت / For Bot:
- **Manage Emojis** - لإضافة/حذف emojis
- **Manage Emojis and Stickers** - لإضافة/حذف stickers

### أمثلة عملية / Practical Examples

#### إضافة emoji من رابط:
```
User: !addemoji twx_logo https://cdn.example.com/logo.png
Bot: ✅ Emoji Added Successfully
     Emoji: :twx_logo:
     Name: twx_logo
     ID: 123456789
```

#### إضافة sticker من ملف:
```
User: !addsticker cute_cat This is our server mascot
     [مع إرفاق ملف PNG]
Bot: ✅ Sticker Added Successfully
     Name: cute_cat
     Description: This is our server mascot
     ID: 987654321
```

#### عرض معلومات emoji:
```
User: !emojiinfo :twx_logo:
Bot: [Embed يعرض معلومات تفصيلية]
     - Name: twx_logo
     - ID: 123456789
     - Animated: No
     - Created: 2025-08-29 15:30:00
     - Server: The World V2
```

### الوصول من نظام المساعدة / Help System Access

#### من القائمة التفاعلية:
```
!help → اختر "😀 Emoji & Stickers"
```

#### النتيجة:
- شرح شامل لجميع الأوامر
- أمثلة عملية
- الصيغ المدعومة
- الصلاحيات المطلوبة

### مميزات النظام / System Features

✅ **سهولة الاستخدام**: أوامر بسيطة ومفهومة
✅ **Easy to use**: Simple and understandable commands

✅ **أمان**: فحص صلاحيات قبل التنفيذ
✅ **Secure**: Permission checks before execution

✅ **معلومات شاملة**: تفاصيل كاملة عن كل emoji/sticker
✅ **Comprehensive info**: Complete details about each emoji/sticker

✅ **تنظيم جميل**: embeds منسقة وجذابة
✅ **Beautiful organization**: Well-formatted and attractive embeds

✅ **دعم متعدد الصيغ**: جميع الصيغ الشائعة مدعومة
✅ **Multi-format support**: All common formats supported

### ملاحظات مهمة / Important Notes

1. **حدود السيرفر**: كل سيرفر له حد أقصى من emojis/stickers
   **Server limits**: Each server has a maximum limit for emojis/stickers

2. **حجم الملفات**: احترم الحد الأقصى للحجم
   **File sizes**: Respect maximum size limits

3. **الأذونات**: تأكد من وجود الصلاحيات المناسبة
   **Permissions**: Ensure proper permissions are available

4. **الجودة**: استخدم صور عالية الجودة للحصول على أفضل نتيجة
   **Quality**: Use high-quality images for best results
