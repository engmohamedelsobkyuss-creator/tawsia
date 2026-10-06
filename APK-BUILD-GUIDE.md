# توصيه — بناء الـ APK

## الملفات المطلوبة في نفس المجلد
- index.html       ← التطبيق الكامل
- manifest.json    ← معلومات التطبيق  
- sw.js            ← Service Worker
- icon-192.png     ← أيقونة (من icon-generator.html)
- icon-512.png     ← أيقونة كبيرة
- capacitor.config.json

## خطوات البناء (مرة واحدة)

### المطلوب تثبيته أولاً
1. Node.js — من nodejs.org
2. Android Studio — من developer.android.com/studio
3. Java JDK 17 — من adoptium.net

### الأوامر
```bash
# في مجلد الملفات
npm install

# أضف Android
npx cap add android
npx cap sync

# افتح في Android Studio
npx cap open android
```

### في Android Studio
1. انتظر Gradle Sync يخلص
2. Build → Generate Signed Bundle/APK
3. اختار APK
4. أنشئ Keystore جديد
5. Build

## بديل أسرع — PWA Builder (بدون كود)
1. ارفع الملفات على GitHub Pages (مجاني)
2. افتح pwabuilder.com
3. أدخل الرابط
4. اضغط Package for stores → Android
5. حمّل APK جاهز في دقيقتين ✅

## بديل ثالث — Bubblewrap CLI
```bash
npm i -g @bubblewrap/cli
bubblewrap init --manifest https://your-site.com/manifest.json
bubblewrap build
```
