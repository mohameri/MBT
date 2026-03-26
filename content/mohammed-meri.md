+++
title = 'السيرة الذاتية ومعرض الأعمال'
description = 'تصفح معرض أعمال وكالة MBT. نقدم خدمات احترافية في صناعة المحتوى، الموشن جرافيك، تصميم الشعارات والهويات البصرية، وإدارة الحسابات لتعزيز علامتك التجارية.'
keywords = 'معرض أعمال, تصميم شعارات, موشن جرافيك, صناعة محتوى, هويات بصرية, وكالة تسويق, MBT'
draft = false
+++

<style>
/* =========================================
إخفاء إجباري للهيدر والفوتر (Desktop + Mobile)
========================================= */
body > header,
body > footer,
header.header, 
footer.footer,
.mobile-bottom-nav,
#whatsapp-modal,
.logo, .nav, #menu {
display: none !important; 
opacity: 0 !important;
visibility: hidden !important;
height: 0 !important;
margin: 0 !important;
padding: 0 !important;
pointer-events: none !important;
}

/* التخلص من المسافات الفارغة */
.main { 
padding-top: 20px !important; 
margin-top: 0 !important; 
min-height: 100vh !important;
}

/* =========================================
إظهار عنوان الصفحة الرئيسي بشكل أنيق
========================================= */
header.entry-header {
display: block !important;
opacity: 1 !important;
visibility: visible !important;
height: auto !important;
text-align: center !important;
margin-bottom: 40px !important;
}
.post-title {
color: #ffffff !important;
font-size: 2.5rem !important;
font-weight: 900 !important;
text-shadow: 0 2px 15px rgba(0,0,0,0.5) !important;
margin: 0 !important;
}

/* إخفاء التفاصيل الزائدة للبوست في ثيم PaperMod */
.page-description, .post-description, .post-entry, .pagination, .post-meta { 
display: none !important; 
}

/* =========================================
تنسيقات الصفحة الأساسية
========================================= */
.gallery-portal { 
padding: 10px 20px 60px; 
max-width: 1000px; 
margin: 0 auto; 
direction: rtl; 
font-family: inherit; 
}

/* =========================================
CV Hero Card (البطاقة الشخصية)
========================================= */
.cv-hero-card {
background: rgba(255, 255, 255, 0.03);
border: 1px solid rgba(225, 196, 67, 0.2);
backdrop-filter: blur(12px);
-webkit-backdrop-filter: blur(12px);
border-radius: 30px;
padding: 30px;
text-align: center;
margin-bottom: 60px;
box-shadow: 0 15px 35px rgba(0,0,0,0.3);
position: relative;
overflow: hidden;
}

.cv-hero-card::before {
content: '';
position: absolute;
top: -50%; left: 50%;
width: 200px; height: 200px;
background: radial-gradient(circle, rgba(225, 196, 67, 0.1) 0%, transparent 70%);
transform: translateX(-50%);
z-index: 0;
pointer-events: none;
}

.cv-info-grid {
display: flex;
flex-wrap: wrap;
justify-content: center;
gap: 15px;
position: relative;
z-index: 1;
}

.cv-info-item {
display: flex;
align-items: center;
gap: 10px;
background: rgba(255, 255, 255, 0.05);
padding: 12px 22px;
border-radius: 50px;
border: 1px solid rgba(255, 255, 255, 0.08);
font-size: 1rem;
color: #ffffff;
transition: all 0.3s ease;
text-decoration: none;
font-weight: bold;
}

.cv-info-item:hover {
border-color: #e1c443;
transform: translateY(-3px);
background: rgba(225, 196, 67, 0.05);
box-shadow: 0 5px 15px rgba(225, 196, 67, 0.1);
}

.cv-icon {
width: 22px;
height: 22px;
fill: #e1c443;
}

/* =========================================
Timeline & Experience (الخط الزمني والخبرات)
========================================= */
.section-heading {
color: #ffffff;
font-size: 2.2rem;
font-weight: 900;
margin-bottom: 40px;
text-align: center;
position: relative;
}

.section-heading::after {
content: '';
display: block;
width: 60px;
height: 4px;
background: #e1c443;
margin: 15px auto 0;
border-radius: 5px;
}

.timeline-container {
position: relative;
padding-right: 30px;
margin-top: 30px;
}

/* الخط العمودي */
.timeline-container::before {
content: '';
position: absolute;
top: 0;
bottom: 0;
right: 5px;
width: 2px;
background: rgba(225, 196, 67, 0.2);
border-radius: 2px;
}

.exp-card {
background: rgba(255, 255, 255, 0.02);
border: 1px solid rgba(255, 255, 255, 0.05);
border-radius: 25px;
padding: 35px;
margin-bottom: 50px;
position: relative;
transition: all 0.4s ease;
box-shadow: 0 5px 20px rgba(0,0,0,0.2);
}

.exp-card:hover {
border-color: rgba(225, 196, 67, 0.4);
background: rgba(255, 255, 255, 0.04);
transform: translateX(-5px);
}

/* الدائرة المضيئة على الخط الزمني */
.exp-card::before {
content: '';
position: absolute;
top: 40px;
right: -31px;
width: 14px;
height: 14px;
background: #0a0a0a;
border: 3px solid #e1c443;
border-radius: 50%;
box-shadow: 0 0 10px rgba(225, 196, 67, 0.6);
z-index: 2;
transition: all 0.4s ease;
}

.exp-card:hover::before {
background: #e1c443;
transform: scale(1.3);
}

.exp-header {
display: flex;
flex-direction: column;
gap: 10px;
border-bottom: 1px dashed rgba(255,255,255,0.1);
padding-bottom: 15px;
margin-bottom: 20px;
}

/* إجبار العنوان والتاريخ على نفس السطر */
.exp-title-row {
display: flex;
justify-content: space-between;
align-items: center;
width: 100%;
gap: 10px;
}

.exp-title {
color: #e1c443;
font-size: 1.6rem;
font-weight: 900;
margin: 0;
line-height: 1.2;
}

.exp-date {
background: rgba(225, 196, 67, 0.1);
color: #e1c443;
padding: 6px 15px;
border-radius: 50px;
font-size: 0.95rem;
font-weight: bold;
border: 1px solid rgba(225, 196, 67, 0.3);
white-space: nowrap; /* يمنع نزول النص لسطر ثاني */
flex-shrink: 0; /* يمنع انضغاط التاريخ */
}

.exp-subtitle {
color: #bbbbbb;
font-size: 1.05rem;
font-weight: bold;
display: flex;
align-items: center;
gap: 8px;
}

.exp-list {
list-style: none;
padding: 0;
margin: 0;
}

.exp-list li {
position: relative;
padding-right: 25px;
margin-bottom: 15px;
color: #dddddd;
font-size: 1rem;
line-height: 1.7;
}

.exp-list li:last-child {
margin-bottom: 0;
}

.exp-list li::before {
content: '▹';
position: absolute;
right: 0;
top: 0;
color: #e1c443;
font-size: 1.3rem;
}

.exp-gallery-title {
color: #ffffff;
font-size: 1.2rem;
margin: 35px 0 25px;
font-weight: bold;
text-align: center;
background: linear-gradient(90deg, transparent, rgba(225, 196, 67, 0.1), transparent);
padding: 15px;
border-radius: 10px;
border-top: 1px solid rgba(225, 196, 67, 0.2);
border-bottom: 1px solid rgba(225, 196, 67, 0.2);
}

/* =========================================
Gallery Grid Styles
========================================= */
.cinematic-grid { display: flex; flex-direction: column; gap: 30px; }

.cinematic-card { 
position: relative; border-radius: 25px; overflow: hidden; height: 350px; width: 100%; 
text-decoration: none; background: #0a0a0a; border: 1px solid rgba(255, 255, 255, 0.05); 
box-shadow: 0 10px 30px rgba(0,0,0,0.5); transition: all 0.5s ease; display: block; 
}

.cinematic-video { 
position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; 
filter: brightness(0.6) contrast(1.1); transition: all 0.5s ease; pointer-events: none !important; 
}

video::-webkit-media-controls, video::-webkit-media-controls-enclosure, video::-webkit-media-controls-panel { 
display: none !important; 
}

.cinematic-overlay { 
position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; 
background: rgba(0, 0, 0, 0.3); display: flex; justify-content: center; align-items: center; 
}

.card-title {
background: rgba(225, 196, 67, 0.1); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
border: 1px solid rgba(225, 196, 67, 0.3); padding: 15px 40px; border-radius: 50px;
color: #fff; font-size: 1.8rem; font-weight: 900; margin: 0; text-align: center; transition: all 0.4s ease;
}

.reveal-arrow {
color: #e1c443; font-size: 2.5rem; font-weight: bold; position: absolute; bottom: 25px; left: 25px;
opacity: 0; transform: translateX(30px); transition: all 0.4s ease;
}

/* =========================================
Responsive Design (Mobile)
========================================= */
@media (min-width: 769px) {
.cinematic-card:hover { transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); box-shadow: 0 20px 40px rgba(0,0,0,0.7); }
.cinematic-card:hover .cinematic-video { transform: scale(1.05); filter: brightness(0.8); }
.cinematic-card:hover .reveal-arrow { opacity: 1; transform: translateX(0); }
.cinematic-card:hover .card-title { background: rgba(225, 196, 67, 0.2); border-color: rgba(225, 196, 67, 0.8); color: #e1c443; }
}

@media (max-width: 768px) {
.gallery-portal { padding: 10px 15px; }
.post-title { font-size: 1.8rem !important; }
.section-heading { font-size: 1.8rem; margin-bottom: 30px; }
.cv-hero-card { padding: 20px 15px; border-radius: 20px; margin-bottom: 40px; }
.cv-info-grid { flex-direction: column; gap: 10px; align-items: stretch; }
.cv-info-item { justify-content: center; padding: 12px 15px; font-size: 0.95rem; }
.timeline-container { padding-right: 20px; margin-top: 20px; }
.timeline-container::before { right: 2px; }
.exp-card { padding: 25px 15px; border-radius: 20px; margin-bottom: 35px; }
.exp-card::before { right: -25px; width: 12px; height: 12px; top: 30px; }
.exp-title { font-size: 1.15rem; } /* تصغير العنوان قليلاً ليناسب التاريخ بجانبه */
.exp-date { padding: 4px 10px; font-size: 0.8rem; }
.exp-subtitle { font-size: 0.95rem; }
.exp-list li { font-size: 0.9rem; margin-bottom: 12px; }
.cinematic-grid { gap: 20px; }
.cinematic-card { height: 200px; border-radius: 20px; }
.card-title { font-size: 15px !important; padding: 10px 22px !important; background: rgba(225, 196, 67, 0.05) !important; }
.reveal-arrow { font-size: 1.5rem !important; opacity: 0.8; transform: translateX(0); bottom: 12px; left: 15px; }
.cinematic-card.in-focus { border-color: rgba(225, 196, 67, 0.3) !important; }
.cinematic-card.in-focus .cinematic-video { filter: brightness(0.8) !important; }
.cinematic-card.in-focus .card-title { background: rgba(225, 196, 67, 0.15) !important; color: #e1c443 !important; transform: scale(1.02); }
.mobile-bottom-nav, div[class*="mobile-bottom-nav"] { display: none !important; }
}
</style>

<div class="gallery-portal">

<div class="cv-hero-card">
<div class="cv-info-grid">

<div class="cv-info-item">
<svg class="cv-icon" viewBox="0 0 24 24">
<path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm0 2c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"/>
</svg>
<span>محمد ميري مهدي</span>
</div>

<a href="mailto:Mohammed-meri@mbt.ad" class="cv-info-item">
<svg class="cv-icon" viewBox="0 0 24 24">
<path d="M20 4H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
</svg>
<span dir="ltr">Mohammed-meri@mbt.ad</span>
</a>

<a href="tel:07814300387" class="cv-info-item">
<svg class="cv-icon" viewBox="0 0 24 24">
<path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
</svg>
<span dir="ltr">0781 430 0387</span>
</a>

<div class="cv-info-item">
<svg class="cv-icon" viewBox="0 0 24 24">
<path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
</svg>
<span>الديوانية</span>
</div>

<div class="cv-info-item">
<svg class="cv-icon" viewBox="0 0 24 24">
<path d="M19 4h-1V2h-2v2H8V2H6v2H5c-1.11 0-1.99.9-1.99 2L3 20c0 1.1.89 2 2 2h14c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 16H5V10h14v10z"/>
</svg>
<span>2002</span>
</div>

</div>
</div>

<h3 class="section-heading">الخبرة العملية</h3>

<div class="timeline-container">



<div class="exp-card">
<div class="exp-header">
<div class="exp-title-row">
<h4 class="exp-title">مصمم كرافيك</h4>
<span class="exp-date">2024 - 2025</span>
</div>
<div class="exp-subtitle">🏢 لشركتي برواز ومرايا - النجف</div>
</div>
<ul class="exp-list">
<li>تصميم وتجهيز الملفات والمخططات الخاصة بأعمال الـ CNC اليدوية.</li>
<li>تصميم المطبوعات الورقية التجارية والمؤسسية، بما في ذلك النماذج والفورمات الرسمية وغيرها من المتطلبات الورقية.</li>
</ul>

<div class="exp-gallery-title">نماذج من أعمالي</div>

<div class="cinematic-grid">
<a href="/gallery/cnc/" class="cinematic-card">
<img src="/images/cnc-work.png" alt="أعمال الـ CNC" class="cinematic-video" loading="lazy">
<div class="cinematic-overlay">
<h2 class="card-title">أعمال الـ CNC</h2>
<div class="reveal-arrow">←</div>
</div>
</a>
</div>
</div>

<div class="exp-card">
<div class="exp-header">
<div class="exp-title-row">
<h4 class="exp-title">فريلانسر: تصميم ومونتاج</h4>
<span class="exp-date">2025 - 2026</span>
</div>
<div class="exp-subtitle"></div>
</div>
<ul class="exp-list">
<li>تصميم الهويات البصرية، الشعارات، وإنتاج الموشن جرافيك.</li>
<li>خبرة اظافية بتطوير وبناء مواقع ويب متكاملة وسريعة الاستجابة باستخدام (Hugo) وتخصيص القوالب مع كتابة أكواد CSS/HTML للواجهات.</li>
<li>خبرة بإنتاج، تحرير، ومعالجة المحتوى المرئي والصوتي باستخدام حزمة Adobe (Premiere Pro, After Effects, Photoshop, Illustrator, Audition).</li>
</ul>

<div class="exp-gallery-title">نماذج من أعمالي</div>

<div class="cinematic-grid">

<a href="/gallery/logo-m/" class="cinematic-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-logo-temp.jpg" disablepictureinpicture>
<source data-src="/videos/6767.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">شعارات و هويات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/print-m/" class="cinematic-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-print-temp.jpg" disablepictureinpicture>
<source data-src="/videos/911.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">مطبوعات و مرئيات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/video-m/" class="cinematic-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-video-temp.jpg" disablepictureinpicture>
<source data-src="/videos/45.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">فيديوهات و موشن</h2>
<div class="reveal-arrow">←</div>
</div>
</a>
</div>
</div>

</div> </div>

<script>
document.addEventListener("DOMContentLoaded", () => {
if ('IntersectionObserver' in window) {
const obs = new IntersectionObserver(entries => {
entries.forEach(e => {
const v = e.target, src = v.querySelector('source');
if (e.isIntersecting) {
if (src && !src.src) { src.src = src.dataset.src; v.load(); }
v.play().catch(()=>{});
} else { v.pause(); }
});
}, { threshold: 0.2 });
document.querySelectorAll('.lazy-video').forEach(v => obs.observe(v));
}

if (window.innerWidth <= 768 && 'IntersectionObserver' in window) {
const focusObs = new IntersectionObserver(entries => {
entries.forEach(e => e.target.classList.toggle('in-focus', e.isIntersecting));
}, { rootMargin: "-35% 0px", threshold: 0 });
document.querySelectorAll('.cinematic-card').forEach(c => focusObs.observe(c));
}
});
</script>