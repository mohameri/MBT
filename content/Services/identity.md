---
title: "الهوية البصرية"
description: "اختر باقة الهوية التي تناسب مشروعك."
---

<style>
.post-title, .entry-header, .page-title, .post-header { display: none !important; }

.cinematic-hero {
position: relative;
width: 100vw;
left: 50%;
right: 50%;
margin-left: -50vw;
margin-right: -50vw;
height: 65vh;
min-height: 400px;
display: flex;
align-items: center;
justify-content: center;
text-align: center;
overflow: hidden;
margin-top: -30px;
margin-bottom: 60px;
}

.hero-video {
position: absolute;
top: 0; left: 0; width: 100%; height: 100%;
object-fit: cover;
object-position: top center; 
z-index: 1;
filter: brightness(0.4) contrast(1.1);
pointer-events: none;
-webkit-mask-image: linear-gradient(to bottom, black 85%, transparent 100%);
mask-image: linear-gradient(to bottom, black 85%, transparent 100%);
}

.hero-content {
position: relative;
z-index: 2;
padding: 0 20px;
max-width: 800px;
transform: translateY(-20px); 
}

.hero-title {
color: #fff;
font-size: clamp(2.5rem, 6vw, 4rem);
font-weight: 900;
margin-bottom: 20px;
text-shadow: 0 4px 20px rgba(0,0,0,0.8);
white-space: nowrap;
}

.hero-title span {
color: #e1c443;
}

.hero-desc {
color: #ddd;
font-size: 1.1rem;
line-height: 1.6;
text-shadow: 0 2px 10px rgba(0,0,0,0.8);
}

.pricing-wrapper {
max-width: 1150px; 
margin: -120px auto 60px; 
position: relative;
z-index: 10;
direction: rtl;
padding: 0 20px;
}

/* إعدادات الكمبيوتر (Desktop) - متجاورة دائماً */
.pricing-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 30px;
}

.price-card {
background: rgba(20, 20, 20, 0.85);
border: 1px solid rgba(255, 255, 255, 0.08);
backdrop-filter: blur(15px);
-webkit-backdrop-filter: blur(15px);
border-radius: 25px;
padding: 35px 25px; 
display: flex;
flex-direction: column;
transition: transform 0.4s ease, border-color 0.4s ease;
box-shadow: 0 15px 35px rgba(0,0,0,0.4);
overflow: hidden;
}

.price-card:hover {
transform: translateY(-8px);
border-color: rgba(225, 196, 67, 0.3);
}

.price-card.premium {
background: linear-gradient(180deg, rgba(26, 40, 85, 0.9) 0%, rgba(20, 20, 20, 0.95) 100%);
border: 1px solid rgba(225, 196, 67, 0.4);
box-shadow: 0 15px 40px rgba(0,0,0,0.6), inset 0 0 20px rgba(225, 196, 67, 0.05);
transform: scale(1.02);
}

.price-card.premium:hover {
transform: scale(1.02) translateY(-8px);
border-color: #e1c443;
}

.popular-badge {
position: absolute;
top: -15px;
left: 50%;
transform: translateX(-50%);
background: #e1c443;
color: #1a2855;
padding: 6px 20px;
border-radius: 50px;
font-weight: 800;
font-size: 0.85rem;
box-shadow: 0 5px 15px rgba(225, 196, 67, 0.4);
white-space: nowrap;
}

.package-name {
font-size: clamp(0.75rem, 1.8vw + 0.5rem, 1.25rem);
color: #fff;
margin-bottom: 20px;
font-weight: bold;
text-align: center;
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
width: 100%;
}

.light-text {
font-weight: 400;
font-size: 0.9em;
opacity: 0.85;
}

.price-shortcode-wrapper {
display: flex;
justify-content: center;
align-items: center;
margin-bottom: 25px;
padding: 8px;
background: rgba(0,0,0,0.3);
border-radius: 15px;
border: 1px dashed rgba(255,255,255,0.1);
width: 100%;
box-sizing: border-box;
overflow: hidden; 
}

.price-shortcode-wrapper * {
white-space: nowrap !important; 
font-size: clamp(0.7rem, 2vw + 0.5rem, 1.2rem) !important; 
margin: 0 !important;
}

.custom-price-text {
color: #e1c443 !important;
font-weight: bold;
}

.price-card.premium .price-shortcode-wrapper {
background: rgba(0,0,0,0.4);
border-color: rgba(225, 196, 67, 0.3);
}

.features-list {
list-style: none;
padding: 0;
margin: 0 0 35px 0;
flex-grow: 1;
}

.features-list li {
color: #ccc;
font-size: 0.95rem;
margin-bottom: 12px;
line-height: 1.6;
display: block;
padding-right: 0; 
text-align: right;
}

.features-list li strong {
color: #fff;
font-weight: bold;
}

.price-btn {
display: block;
text-align: center;
padding: 12px;
border-radius: 12px;
font-weight: bold;
text-decoration: none;
transition: all 0.3s ease;
white-space: nowrap;
font-size: clamp(0.75rem, 1.5vw + 0.5rem, 1rem);
}

.btn-outline {
border: 1px solid #777;
color: #fff;
}

.btn-outline:hover {
background: #fff;
color: #000;
}

.btn-solid {
background: #e1c443;
color: #1a2855;
}

.btn-solid:hover {
background: #fff;
}

/* =========================================
   إعدادات مؤشر السحب (مخفي في الديسكتوب)
   ========================================= */
.swipe-indicator {
display: none;
transition: opacity 0.4s ease;
}

.swipe-indicator.hidden-indicator {
opacity: 0;
pointer-events: none;
}

@keyframes swipeHint {
0%, 100% { transform: translateX(0); }
50% { transform: translateX(-8px); }
}

/* =========================================
   إعدادات الموبايل (سلايدر مع إظهار جزء من البطاقة الثانية)
   ========================================= */
@media (max-width: 768px) {
.hero-title { font-size: 2.2rem; }
.pricing-wrapper { margin-top: -110px; padding: 0; }

/* تحويل الشبكة إلى سلايدر أفقي */
.pricing-grid {
display: flex;
flex-wrap: nowrap;
overflow-x: auto;
scroll-snap-type: x mandatory;
gap: 15px;
padding: 20px;
scrollbar-width: none; 
-ms-overflow-style: none; 
}
.pricing-grid::-webkit-scrollbar { display: none; }

.price-card {
flex: 0 0 85%; /* العرض 85% لترك مساحة 15% للبطاقة التالية للظهور */
scroll-snap-align: center;
padding: 30px 20px; 
}

.price-card.premium { transform: scale(1); }
.price-card.premium:hover { transform: translateY(-3px); }
.popular-badge { font-size: 0.7rem; padding: 4px 12px; top: -12px; }

/* إظهار مؤشر السحب */
.swipe-indicator {
display: flex;
align-items: center;
justify-content: center;
gap: 8px;
color: #e1c443;
font-size: 0.95rem;
margin-top: -10px;
margin-bottom: 30px;
animation: swipeHint 1.5s infinite ease-in-out;
}
}
</style>

<div class="cinematic-hero">
<video class="hero-video" autoplay loop muted playsinline poster="/images/poster-brand-temp.jpg">
<source src="/videos/brand-hero.mp4" type="video/mp4">
</video>
<div class="hero-content">
<h1 class="hero-title">تصميم <span>الهوية</span></h1>
<p class="hero-desc">اختر باقة الهوية التي تناسب مشروعك.</p>
</div>
</div>

<div class="pricing-wrapper">
<div class="pricing-grid">

<div class="price-card">
<h3 class="package-name">تنسيق الهوية <span class="light-text">(بدون شعار)</span></h3>

<div class="price-shortcode-wrapper">
{{< price 30000 >}}
</div>

<ul class="features-list">
<li>لمن يمتلك شعاراً ويريد ترتيب هويته.</li>
<li>توحيد الألوان والخطوط لتعزيز احترافيتك</li>
<li>تصميم المطبوعات الأساسية للمشروع</li>
<li>قوالب سوشيال ميديا جاهزة للاستخدام</li>
<li>عرض تطبيقات واقعية (Mockups) جذابة</li>
</ul>

<a href="https://wa.me/9647872840590?text=مرحباً، أود طلب باقة (تنسيق الهوية) لتطوير عملي" class="price-btn btn-outline wa-trigger-link">اطلب الآن</a>
</div>

<div class="price-card premium">
<div class="popular-badge">الأكثر طلباً</div>
<h3 class="package-name">التأسيس الشامل <span class="light-text">(مع شعار)</span></h3>

<div class="price-shortcode-wrapper">
{{< price 60000 >}}
</div>

<ul class="features-list">
<li>لبناء علامة تجارية قوية من الصفر.</li>
<li><strong>(تشمل جميع ميزات تنسيق الهوية) +</strong></li>
<li>تصميم شعار احترافي يعكس رؤيتك</li>
<li>تقديم خيارات متعددة للشعار للمقارنة</li>
<li>تجهيز الشعار بوضعيات تناسب كل المنصات</li>
<li>تطبيقات بصرية إضافية مخصصة لمجالك</li>
</ul>

<a href="https://wa.me/9647872840590?text=مرحباً، أود طلب باقة (التأسيس الشامل) لبناء هويتي" class="price-btn btn-solid wa-trigger-link">ابدأ التأسيس</a>
</div>

<div class="price-card">
<h3 class="package-name">الباقة المخصصة</h3>

<div class="price-shortcode-wrapper">
<span class="custom-price-text">تُحدد حسب المتطلبات</span>
</div>

<ul class="features-list">
<li>للمشاريع ذات الاحتياجات الخاصة.</li>
<li><strong>(اختيار مرن من الميزات السابقة) +</strong></li>
<li>دمج خدمات الوكالة (مونتاج، موشن جرافيك...)</li>
<li>توحيد النمط الفني لكل مخرجاتك المرئية</li>
<li>أولوية في التنفيذ والدعم المستمر</li>
<li>خصم حصري يتناسب مع حجم طلبك</li>
</ul>

<a href="https://wa.me/9647872840590?text=مرحباً، أود مناقشة تفاصيل (الباقة المخصصة) للهوية البصرية" class="price-btn btn-outline wa-trigger-link">تواصل للمناقشة</a>
</div>

</div>

<div class="swipe-indicator">
👈 اسحب لرؤية المزيد
</div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
const grid = document.querySelector(".pricing-grid");
const indicator = document.querySelector(".swipe-indicator");

if (grid && indicator) {
grid.addEventListener("scroll", function() {
if (Math.abs(grid.scrollLeft) > 10) {
indicator.classList.add("hidden-indicator");
} else {
indicator.classList.remove("hidden-indicator");
}
});
}
});
</script>