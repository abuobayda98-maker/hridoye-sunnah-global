# Hridoye Sunnah — Global Edition 🌍

Global-ready responsive Islamic Progressive Web App (PWA), Ultra Modern Galaxy + Royal Gold / cosmic-glass UI. Bengali interface with multilingual AI script output and international city/country prayer lookup.

## চালানো
- `index.html` সরাসরি খুললে বেশিরভাগ UI কাজ করবে, তবে PWA install/offline-এর জন্য HTTPS বা localhost প্রয়োজন।
- লোকাল সার্ভার: `python -m http.server 8000` তারপর `http://localhost:8000` খুলুন।
- অনলাইনে PWA চালাতে সব ফাইল HTTPS static hosting-এ আপলোড করুন।

## ফিচার
- হোম ড্যাশবোর্ড ও bottom navigation
- Gemini API key/model settings, API test এবং script generation
- স্ক্রিপ্ট লাইব্রেরি: search, edit, copy, favorites
- নমুনা হাদিস লাইব্রেরি: search, copy, favorites
- Global prayer times via AlAdhan API using configurable city + country; optional GPS-based prayer times
- Qibla bearing calculator based on GPS coordinates
- AI output language setting: Bengali, English, Arabic, Urdu, Indonesian, Turkish
- লোকাল ডেটা-ভিত্তিক demo admin panel, add/delete script/hadith, JSON import/export
- service worker, web manifest, install prompt, responsive mobile UI

## গুরুত্বপূর্ণ সীমাবদ্ধতা
- হাদিস লাইব্রেরিতে নমুনা ডেটা আছে এবং চাইলে অনলাইন Hadith API থেকে সর্বোচ্চ ২৫০টি এন্ট্রি লোড করার চেষ্টা করে। সংস্করণ/অনুবাদ সবসময় বাংলায় নাও হতে পারে; প্রকাশের আগে মূল কিতাব/বিশ্বস্ত আলেমের মাধ্যমে আরবি, অনুবাদ, নম্বর ও মান যাচাই করুন।
- Prayer times use AlAdhan API and configurable city/country or optional GPS. If API/network fails, a fallback/demo display may appear. Confirm timings with a local mosque; calculation methods differ.
- The app interface is still primarily Bengali; multilingual selection applies to AI-generated scripts, not every navigation label yet.
- Qibla feature displays bearing from true north, not a live compass needle; use a compass app/device calibration to orient yourself.
- Admin PIN শুধু client-side demo protection; production authentication নয়।
- Gemini API key এই client-only prototype-এ browser localStorage-এ থাকে এবং API call সরাসরি browser থেকে যায়। Public production app-এ API key backend/server environment-এ রাখুন; rate limit, auth এবং moderation যোগ করুন।
- বর্তমান logo `assets/logo.svg` একটি temporary vector mark। আপনার আসল uploaded logo এই build session-এ উপলব্ধ না থাকায় সেটি বসানো যায়নি। আসল লোগো ফাইলকে `assets/logo.svg` নামে প্রতিস্থাপন করুন (অথবা HTML-এ logo path আপডেট করুন)।
- বাংলা ফন্টের জন্য Google Fonts নেটওয়ার্ক সংযোগ থাকলে সুন্দর দেখাবে; fallback font রাখা আছে।

## প্রোডাকশনের আগে
1. আসল লোগো বসান।
2. পূর্ণাঙ্গ, লাইসেন্স-উপযোগী ও যাচাইকৃত হাদিস ডেটা আমদানি করুন।
3. prayer calculation/API সংযোগ করুন।
4. backend API proxy দিয়ে Gemini key সুরক্ষিত রাখুন।
5. admin login ও database-কে server-side করুন.


## লাইভ ডেটা উৎস
- Prayer timings: AlAdhan API (`api.aladhan.com`), শহর-ভিত্তিক গণনা; স্থানীয় মসজিদের সময়ের সঙ্গে পার্থক্য হতে পারে.
- Hadith fetch: `fawazahmed0/hadith-api` CDN; নেটওয়ার্ক/edition availability-এর ওপর নির্ভরশীল.


## Global Edition changes
- International city/country fields instead of Bangladesh-only lookup.
- Optional device geolocation for prayer times and Qibla bearing; permission is requested only after the user taps the location feature.
- AI output language options: Bengali, English, Arabic, Urdu, Indonesian and Turkish.
- Updated PWA branding and cache version.


## Free launch
See `DEPLOY-GLOBAL-BN.md` for step-by-step GitHub Pages deployment and Android PWA installation. A GitHub Pages workflow is included at `.github/workflows/pages.yml`.
