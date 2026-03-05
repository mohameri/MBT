---
title: "تصميم الشعارات"
description: "اختر الباقة التي تتناسب مع حجم مشروعك وتطلعاتك المستقبلية."
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
max-width: 1000px;
margin: -120px auto 60px; 
position: relative;
z-index: 10;
direction: rtl;
padding: 0 20px;
}

.pricing-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
gap: 30px;
}

.price-card {
background: rgba(20, 20, 20, 0.85);
border: 1px solid rgba(255, 255, 255, 0.08);
backdrop-filter: blur(15px);
-webkit-backdrop-filter: blur(15px);
border-radius: 25px;
padding: 40px 30px;
display: flex;
flex-direction: column;
transition: transform 0.4s ease, border-color 0.4s ease;
box-shadow: 0 15px 35px rgba(0,0,0,0.4);
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
}

.package-name {
font-size: 1.5rem;
color: #fff;
margin-bottom: 30px;
font-weight: bold;
text-align: center;
}

.price-shortcode-wrapper {
display: flex;
justify-content: center;
align-items: center;
margin-bottom: 35px;
padding: 15px;
background: rgba(0,0,0,0.3);
border-radius: 15px;
border: 1px dashed rgba(255,255,255,0.1);
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
margin-bottom: 26px;
position: relative;
padding-right: 36px;
line-height: 1.8;
display: block;
}

.features-list li strong {
color: #fff;
font-weight: bold;
}

.features-list li::before {
content: "✓";
position: absolute;
right: 0;
top: 0;
color: #e1c443;
font-weight: bold;
background: rgba(225, 196, 67, 0.1);
width: 24px;
height: 24px;
display: flex;
align-items: center;
justify-content: center;
border-radius: 50%;
}

.price-btn {
display: block;
text-align: center;
padding: 15px;
border-radius: 12px;
font-weight: bold;
text-decoration: none;
transition: all 0.3s ease;
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

.swipe-indicator {
display: none;
}

@keyframes swipeHint {
0%, 100% { transform: translateX(0); }
50% { transform: translateX(-8px); }
}

@media (max-width: 768px) {
.hero-title { font-size: 2.2rem; }
.pricing-wrapper { margin-top: -50px; padding: 0; }
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
flex: 0 0 88%; 
scroll-snap-align: center;
}
.price-card.premium { transform: scale(1); }
.price-card.premium:hover { transform: translateY(-5px); }
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
<video class="hero-video" autoplay loop muted playsinline poster="/images/poster-logo-temp.jpg">
<source src="/videos/6767.mp4" type="video/mp4">
</video>
<div class="hero-content">
<h1 class="hero-title">تصميم <span>الشعارات</span></h1>
<p class="hero-desc">اختر الباقة التي تتناسب مع حجم مشروعك وتطلعاتك المستقبلية.</p>
</div>
</div>

<div class="pricing-wrapper">
<div class="pricing-grid">

<div class="price-card">
<h3 class="package-name">الباقة الاقتصادية</h3>

<div class="price-shortcode-wrapper">
{{< price 15000 >}}
</div>

<ul class="features-list">
<li><strong>الهدف:</strong> إنجاز عملي وسريع يلبي تطلعاتك بشكل مباشر.</li>
<li><strong>آلية التصميم:</strong> تصميم مستوحى من رؤيتك؛ اختر نموذجاً من سابقة أعمالنا، أو أرسل لنا تصميماً يعجبك وسنقوم بإنشاء شعار مقارب لأسلوبه.</li>
<li><strong>النتيجة:</strong> شعار أنيق، مباشر، ومناسب لبدء مشروعك فوراً.</li>
</ul>

<a href="https://wa.me/9647872840590?text=مرحباً، أود طلب الباقة الاقتصادية لتصميم الشعار" class="price-btn btn-outline wa-trigger-link">اطلب الآن</a>
</div>

<div class="price-card premium">
<div class="popular-badge">باقة التميز</div>
<h3 class="package-name">الباقة الاحترافية</h3>

<div class="price-shortcode-wrapper">
{{< price 45000 >}}
</div>

<ul class="features-list">
<li><strong>الهدف:</strong> بناء هوية بصرية فريدة تعكس قوة علامتك التجارية وتفردها.</li>
<li><strong>آلية التصميم:</strong> ابتكار 4 نماذج حصرية بأفكار غير مطروقة ومصممة خصيصاً لك من الصفر.</li>
<li><strong>المرونة:</strong> حرية كاملة في التعديلات والإضافات على النماذج حتى نصل معاً إلى النتيجة التي ترضيك 100%.</li>
<li><strong>النتيجة:</strong> شعار احترافي متكامل يميزك بقوة عن المنافسين.</li>
</ul>

<a href="https://wa.me/9647872840590?text=مرحباً، أود طلب الباقة الاحترافية لتصميم الشعار" class="price-btn btn-solid wa-trigger-link">ابدأ مشروعك الاحترافي</a>
</div>

</div>

<div class="swipe-indicator">
👈 اسحب لرؤية المزيد
</div>
</div>