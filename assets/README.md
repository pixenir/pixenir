# Pixenir অ্যাসেট রিপোজিটরি (Asset Repository)

এই রিপোজিটরিতে Pixenir প্রোজেক্টের জন্য প্রয়োজনীয় বিভিন্ন স্ট্যাটিক অ্যাসেট (Static Assets) যেমন: CSS, JavaScript, ছবি (PNG, JPG, SVG) ইত্যাদি রাখা হয়েছে।

এই ফাইলগুলো আপনার ওয়েবসাইটে সরাসরি ব্যবহার করার জন্য নিচের নির্দেশিকা অনুসরণ করুন।

## কেন সরাসরি GitHub লিঙ্ক কাজ করে না?

সরাসরি GitHub-এর `raw.githubusercontent.com` লিঙ্ক ব্যবহার করলে ব্রাউজার নিরাপত্তার কারণে অনেক ফাইল (যেমন CSS, JS) ব্লক করে দেয়। কারণ GitHub এই ফাইলগুলোকে সঠিক `Content-Type` হেডার (যেমন `text/css` বা `application/javascript`) দিয়ে পাঠায় না।

এই সমস্যার সহজ সমাধান হলো **jsDelivr** ব্যবহার করা। এটি একটি ফ্রি CDN যা GitHub রিপোজিটরি থেকে ফাইল নিয়ে সঠিক ফরম্যাটে পরিবেশন করে।

---

## ব্যবহারের নিয়ম: jsDelivr লিঙ্ক তৈরি

যেকোনো ফাইলের জন্য jsDelivr লিঙ্ক তৈরি করার ফরম্যাটটি খুবই সহজ।

**আপনার রিপোজিটরির জন্য ফরম্যাট:**
```
https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/<ফাইল-এর-সম্পূর্ণ-পাথ>
```

-   `pixenir/pixenir`: আপনার `ইউজারনেম/রিপোজিটরির-নাম`।
-   `@main`: আপনার ব্রাঞ্চের নাম। আপনি চাইলে অন্য ব্রাঞ্চও ব্যবহার করতে পারেন।
-   `<ফাইল-এর-সম্পূর্ণ-পাথ>`: রিপোজিটরির ভেতর ফাইলের অবস্থান (যেমন: `assets/css/style.css`)

---

## বিভিন্ন ধরনের ফাইল ব্যবহারের উদাহরণ

নিচে আপনার রিপোজিটরির বিভিন্ন ধরনের ফাইল কীভাবে লিঙ্ক করবেন তার উদাহরণ দেওয়া হলো।

### ১. CSS ফাইল (.css)

আপনার HTML ফাইলের `<head>` ট্যাগের ভেতরে `<link>` ট্যাগ ব্যবহার করুন।

**উদাহরণ:**
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/fonts/font.css">
```

### ২. JavaScript ফাইল (.js)

আপনার HTML ফাইলের `<body>` ট্যাগের শেষে `<script>` ট্যাগ ব্যবহার করুন। শেষে ব্যবহার করলে পেইজ লোড দ্রুত হয়।

**উদাহরণ:**
```html
<!-- ধরে নেওয়া যাক আপনার একটি script.js ফাইল আছে assets/js/ ফোল্ডারে -->
<script src="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/js/script.js"></script>
```

### ৩. ছবি (.png, .jpg, .jpeg, .gif)

ছবি দেখানোর জন্য HTML-এ `<img>` ট্যাগ অথবা CSS-এ `background-image` ব্যবহার করুন।

**HTML-এ ব্যবহারের উদাহরণ:**
```html
<!-- ধরে নেওয়া যাক আপনার একটি logo.png ফাইল আছে assets/images/ ফোল্ডারে -->
<img src="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/images/logo.png" alt="Pixenir লোগো">
```

**CSS-এ ব্যবহারের উদাহরণ:**
```css
.hero-banner {
    /* ধরে নেওয়া যাক আপনার একটি background.jpg ফাইল আছে assets/images/ ফোল্ডারে */
    background-image: url('https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/images/background.jpg');
    background-size: cover;
    background-position: center;
}
```

### ৪. ভেক্টর গ্রাফিক্স (.svg)

SVG ফাইল ছবি হিসেবে (`<img>` ট্যাগ) অথবা সরাসরি কোড হিসেবে ব্যবহার করা যায়। লিঙ্ক করার জন্য `<img>` ট্যাগই সবচেয়ে সহজ।

**উদাহরণ:**
```html
<!-- ধরে নেওয়া যাক আপনার একটি icon.svg ফাইল আছে assets/icons/ ফোল্ডারে -->
<img src="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/icons/icon.svg" alt="আইকন" width="50">
```

---

## সম্পূর্ণ HTML উদাহরণ

নিচে সব ধরনের ফাইল একসাথে ব্যবহার করে একটি সম্পূর্ণ উদাহরণ দেখানো হলো।

```html
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pixenir অ্যাসেট ব্যবহারের উদাহরণ</title>

    <!-- CSS ফাইল লিঙ্ক করা -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/fonts/font.css">
    
    <style>
        body {
            font-family: 'Noto Serif Bengali', sans-serif;
        }
        .header {
            padding: 20px;
            text-align: center;
            border-bottom: 1px solid #eee;
        }
        .logo {
            max-width: 150px;
        }
        .banner {
            height: 300px;
            background-image: url('https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/images/background.jpg'); /* একটি কাল্পনিক ফাইল */
            background-size: cover;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2em;
        }
    </style>
</head>
<body>

    <header class="header">
        <!-- PNG ছবি লিঙ্ক করা -->
        <img class="logo" src="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/images/logo.png" alt="লোগো"> <!-- একটি কাল্পনিক ফাইল -->
    </header>

    <main>
        <div class="banner">
            <h1>স্বাগতম!</h1>
        </div>
        <article style="padding: 20px;">
            <p>এই পেইজটি jsDelivr CDN ব্যবহার করে GitHub থেকে অ্যাসেট লোড করছে।</p>
        </article>
    </main>

    <!-- JavaScript ফাইল লিঙ্ক করা (body-র শেষে) -->
    <script src="https://cdn.jsdelivr.net/gh/pixenir/pixenir@main/assets/js/script.js"></script> <!-- একটি কাল্পনিক ফাইল -->

</body>
</html>
```
