# Hridoye Sunnah Global — Free launch steps (বাংলা)

## কী প্রস্তুত আছে
- Galaxy + Royal Gold theme, responsive UI
- Static website + installable PWA structure
- Prayer time lookup and Qibla bearing tools
- GitHub Pages workflow included

## Step 1 — GitHub account / repository
1. GitHub-এ সাইন ইন করুন এবং `New repository` চাপুন।
2. Repository name দিন `hridoye-sunnah-global`।
3. Public নির্বাচন করে `Create repository` চাপুন।
4. এই ZIP extract করুন, তারপর ভেতরের সব ফাইল ও `.github` ফোল্ডার repository-তে upload করুন। `.github/workflows/pages.yml` যেন বাদ না পড়ে।
5. `Commit changes` করুন।

## Step 2 — Free hosting চালু করুন
1. Repository-তে `Settings → Pages` খুলুন।
2. Build and deployment source হিসেবে `GitHub Actions` নির্বাচন করুন।
3. `Actions` tab-এ deployment workflow শেষ হওয়া পর্যন্ত অপেক্ষা করুন।
4. সফল হলে Pages-এর URL-এ ওয়েবসাইট পাবেন; সাধারণত `https://YOUR-USERNAME.github.io/hridoye-sunnah-global/`। URL-টি GitHub দেখাবে—নিজে অনুমান করবেন না।

## Step 3 — Android-এ ইনস্টল
1. Android ফোনে Chrome-এ লাইভ HTTPS URL খুলুন।
2. মেনু `⋮` → `Install app` অথবা `Add to Home screen` চাপুন।
3. ইনস্টল হলে অ্যাপ আইকন থেকে খুলুন। PWA ইনস্টল করা Android APK নয়; Play Store-এ প্রকাশিত অ্যাপও নয়।

## Step 4 — launch-এর আগে অবশ্যই পরীক্ষা
- মোবাইল/ডেস্কটপে layout, navigation, offline cache এবং install পরীক্ষা করুন।
- Prayer times স্থানীয় মসজিদের timetable-এর সঙ্গে মিলিয়ে নিন; calculation method অনুযায়ী পার্থক্য হতে পারে।
- Hadith text, Arabic, translation, reference ও grading নির্ভরযোগ্য প্রকাশনা/যোগ্য আলেমের মাধ্যমে যাচাই করুন।
- আসল logo থাকলে `assets/logo.svg` প্রতিস্থাপন করুন।

## Security / production warning
এটি static client-side PWA। বর্তমান Gemini API key browser storage-এ থাকে—public launch-এ ব্যক্তিগত/গোপন key ব্যবহার করবেন না। Production AI feature-এর জন্য server-side proxy (যেমন Cloudflare Worker) ও secret environment variable লাগবে। Demo admin panel নিরাপদ server-side authentication নয়; এতে গোপন/ব্যক্তিগত ডেটা রাখবেন না। User data এই static version-এ device-এর localStorage-এ থাকে, তাই অন্য device-এ স্বয়ংক্রিয় sync হবে না।

## Free hosting note
GitHub Pages static site হোস্ট করে; এটি database বা secret server backend নয়। Repository Public হলে source code-ও public থাকবে।
