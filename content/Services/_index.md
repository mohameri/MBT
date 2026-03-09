+++
title = 'الخدمات والأسعار'
description = 'تصفح باقات وخدمات وكالة MBT المتكاملة. نقدم حلولاً احترافية في التصميم، البرمجة، والمونتاج بأسعار تنافسية.'
keywords = 'خدمات تصميم, أسعار التصميم, باقات MBT, موشن جرافيك, إدارة حسابات'
draft = false
+++

<style>
.page-header, .post-title, .entry-header, .page-title, .post-header, .page-description, .post-description, .post-entry, .pagination {
display: none !important;
}
.store-hero {
text-align: center;
padding: 20px 10px 20px;
direction: rtl;
}
.store-hero h1 {
font-size: clamp(1.4rem, 3vw, 1.8rem);
color: #fff;
font-weight: 800;
margin: 0;
text-shadow: 0 4px 10px rgba(0,0,0,0.5);
}
.store-hero h1 span {
color: #e1c443;
}
.store-container {
max-width: 1200px;
margin: 0 auto 80px;
padding: 0 15px;
direction: rtl;
}
.store-grid {
display: grid;
grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
gap: 12px;
}
.store-item {
background: #111111;
border: 1px solid rgba(255, 255, 255, 0.05);
border-radius: 10px;
display: flex;
flex-direction: column;
text-decoration: none;
overflow: hidden;
transition: all 0.3s ease;
box-shadow: 0 4px 10px rgba(0,0,0,0.3);
}
.store-item:hover {
transform: translateY(-4px);
border-color: rgba(225, 196, 67, 0.4);
box-shadow: 0 8px 20px rgba(225, 196, 67, 0.15);
}
.item-media {
width: 100%;
aspect-ratio: 16 / 9;
background: #000;
position: relative;
overflow: hidden;
border-bottom: 1px solid rgba(255, 255, 255, 0.03);
}
.item-media img, .item-media video {
width: 100%;
height: 100%;
object-fit: cover;
transition: transform 0.4s ease;
}
.store-item:hover .item-media img,
.store-item:hover .item-media video {
transform: scale(1.08);
}
.item-content {
padding: 10px;
display: flex;
flex-direction: column;
flex-grow: 1;
align-items: center;
overflow: hidden; 
}
.item-title {
color: #ffffff;
font-size: 0.75rem;
font-weight: 500;
margin: 0 0 8px 0;
text-align: center;
transition: color 0.3s;
line-height: 1.3;
width: 100%;
}
.store-item:hover .item-title {
color: #e1c443;
}
.item-price-box {
width: 100%;
background: rgba(255, 255, 255, 0.02);
border: 1px solid rgba(255, 255, 255, 0.04);
border-radius: 6px;
padding: 6px 8px;
margin-top: auto;
transition: all 0.3s;
}
.store-item:hover .item-price-box {
background: rgba(225, 196, 67, 0.05);
border-color: rgba(225, 196, 67, 0.2);
}
.price-box-title {
color: #888;
font-size: 0.65rem;
font-weight: bold;
display: block;
margin-bottom: 6px;
border-bottom: 1px dashed rgba(255, 255, 255, 0.1);
padding-bottom: 4px;
text-align: right;
}
.price-row {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 3px;
}
.price-row:last-child {
margin-bottom: 0;
}
.price-word {
color: #aaa;
font-size: 0.7rem;
}
.price-display {
color: #e1c443;
font-size: 0.8rem;
font-weight: bold;
direction: ltr;
}
@media (max-width: 768px) {
.store-grid {
grid-template-columns: repeat(2, 1fr);
gap: 10px;
}
.item-title { font-size: 0.65rem; margin-bottom: 6px; }
.item-price-box { padding: 4px 6px; }
.price-box-title { font-size: 0.6rem; margin-bottom: 4px; padding-bottom: 3px; }
.price-word { font-size: 0.65rem; }
.price-display { font-size: 0.75rem; }
}
</style>

<div class="store-hero">
<h1>الخدمات <span>والأسعار</span></h1>
</div>

<div class="store-container">
<div class="store-grid">

<a href="/services/logo/" class="store-item">
<div class="item-media">
<img src="/images/6564.png" alt="تصميم الشعارات">
</div>
<div class="item-content">
<h3 class="item-title">تصميم الشعارات</h3>
<div class="item-price-box">
<span class="price-box-title">السعر:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="15000">15,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="45000">45,000 د.ع</span>
</div>
</div>
</div>
</a>

<a href="/services/identity/" class="store-item">
<div class="item-media">
<img src="/images/324555.png" alt="الهويات البصرية">
</div>
<div class="item-content">
<h3 class="item-title">الهويات البصرية</h3>
<div class="item-price-box">
<span class="price-box-title">السعر:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="50000">30,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="150000">60,000 د.ع</span>
</div>
</div>
</div>
</a>

<a href="/services/video-editing/" class="store-item">
<div class="item-media">
<video autoplay loop muted playsinline poster="/images/poster-editing.jpg">
<source src="/videos/editing-preview.mp4" type="video/mp4">
</video>
</div>
<div class="item-content">
<h3 class="item-title">مونتاج الفيديو</h3>
<div class="item-price-box">
<span class="price-box-title">السعر:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="15000">15,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="60000">60,000 د.ع</span>
</div>
</div>
</div>
</a>

<a href="/services/motion/" class="store-item">
<div class="item-media">
<video autoplay loop muted playsinline poster="/images/poster-motion.jpg">
<source src="/videos/motion-preview.mp4" type="video/mp4">
</video>
</div>
<div class="item-content">
<h3 class="item-title">الموشن جرافيك</h3>
<div class="item-price-box">
<span class="price-box-title">السعر:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="25000">25,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="150000">150,000 د.ع</span>
</div>
</div>
</div>
</a>

<a href="/services/web/" class="store-item">
<div class="item-media">
<img src="/images/service-web.jpg" alt="تصميم المواقع">
</div>
<div class="item-content">
<h3 class="item-title">تصميم وبرمجة المواقع</h3>
<div class="item-price-box">
<span class="price-box-title">السعر:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="100000">100,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="500000">500,000 د.ع</span>
</div>
</div>
</div>
</a>

<a href="/services/social/" class="store-item">
<div class="item-media">
<img src="/images/service-social.jpg" alt="إدارة الحسابات">
</div>
<div class="item-content">
<h3 class="item-title">إدارة الحسابات</h3>
<div class="item-price-box">
<span class="price-box-title">الاشتراك الشهري:</span>
<div class="price-row">
<span class="price-word">من</span>
<span class="price-display" data-base-price="150000">150,000 د.ع</span>
</div>
<div class="price-row">
<span class="price-word">إلى</span>
<span class="price-display" data-base-price="300000">300,000 د.ع</span>
</div>
</div>
</div>
</a>

</div>
</div>