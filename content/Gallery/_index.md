+++
title = 'Gallery'
description = 'تصفح معرض أعمال وكالة MBT. نقدم خدمات احترافية في صناعة المحتوى، الموشن جرافيك، تصميم الشعارات والهويات البصرية، وإدارة الحسابات لتعزيز علامتك التجارية.'
keywords = 'معرض أعمال, تصميم شعارات, موشن جرافيك, صناعة محتوى, هويات بصرية, وكالة تسويق, MBT'
draft = false
+++

<style>
    /* 1. Reset & Global */
    .page-description, .post-description { display: none !important; }
    .gallery-portal { padding: 40px 20px; max-width: 1000px; margin: 0 auto; direction: rtl; font-family: inherit; }
    .cinematic-grid { display: flex; flex-direction: column; gap: 40px; }

    /* 2. Card Basics */
    .cinematic-card { 
        position: relative; border-radius: 35px; overflow: hidden; height: 450px; width: 100%; 
        text-decoration: none; background: #0a0a0a; border: 1px solid rgba(255, 255, 255, 0.05); 
        box-shadow: 0 10px 30px rgba(0,0,0,0.5); transition: all 0.5s cubic-bezier(0.25, 0.8, 0.25, 1); display: block; 
    }
    .cinematic-card:hover { 
        transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); 
        box-shadow: 0 20px 40px rgba(0,0,0,0.7), 0 0 30px rgba(225, 196, 67, 0.1); 
    }

    /* 3. Video */
    .cinematic-video { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; 
        filter: brightness(0.6) contrast(1.1); transition: transform 1s ease, filter 0.5s ease; pointer-events: none; 
    }
    .cinematic-card:hover .cinematic-video { transform: scale(1.05); filter: brightness(0.8) contrast(1.1); }

    /* 4. Overlay - هنا سر السنترة المثالية (Flexbox) */
    .cinematic-overlay { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; 
        background: rgba(0, 0, 0, 0.3); transition: background 0.5s ease; 
        display: flex; justify-content: center; align-items: center; /* توسيط دقيق 100% */
    }
    .cinematic-card:hover .cinematic-overlay { background: rgba(0, 0, 0, 0.5); }

    /* 5. Title in a Glass Box */
    .card-title {
        /* البوكس الزجاجي الذهبي */
        background: rgba(225, 196, 67, 0.1);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        border: 1px solid rgba(225, 196, 67, 0.3);
        padding: 18px 50px;
        border-radius: 50px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        
        /* النص */
        color: #ffffff; 
        font-size: 2.2rem; 
        font-weight: 900; 
        margin: 0; 
        text-shadow: 0 2px 10px rgba(0,0,0,0.5); 
        
        /* ضبط المقاسات */
        text-align: center; 
        width: max-content; 
        max-width: 90%;
        transition: all 0.3s ease;
    }

    /* 6. Pulsation Animation for Box & Text */
    @keyframes pulseGoldBox {
        0% { 
            color: #ffffff; 
            background: rgba(225, 196, 67, 0.1); 
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            border-color: rgba(225, 196, 67, 0.3);
        }
        50% { 
            color: #e1c443; 
            background: rgba(225, 196, 67, 0.2); 
            box-shadow: 0 10px 40px rgba(225, 196, 67, 0.4);
            border-color: rgba(225, 196, 67, 0.8);
        }
        100% { 
            color: #ffffff; 
            background: rgba(225, 196, 67, 0.1); 
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            border-color: rgba(225, 196, 67, 0.3);
        }
    }

    .cinematic-card:hover .card-title {
        animation: pulseGoldBox 1.5s infinite ease-in-out;
    }
    
    /* ومضة قوية وحركة زر عند النقر */
    .cinematic-card:active .card-title {
        animation: none;
        color: #1a2855; 
        background: #e1c443; 
        border-color: #e1c443;
        transform: scale(0.95); /* تأثير الضغطة بدون التأثير على التوسيط */
    }

    /* 7. Arrow Position */
    .reveal-arrow {
        color: #e1c443; font-size: 2.8rem; font-weight: bold; text-shadow: 0 0 15px rgba(225, 196, 67, 0.4);
        opacity: 0; transform: translateX(30px); transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
        position: absolute; bottom: 30px; left: 30px; /* السهم محمي بمكانه */
    }
    .cinematic-card:hover .reveal-arrow { opacity: 1; transform: translateX(0); }

    /* 8. Mobile Customization */
    @media (max-width: 768px) {
        .gallery-portal { padding: 20px 15px; }
        .cinematic-card { height: 280px; border-radius: 25px; }
        .card-title { 
            font-size: 1.4rem; 
            padding: 12px 30px; 
            white-space: nowrap; 
        }
        .reveal-arrow { font-size: 2rem; opacity: 0.6; transform: translateX(0); bottom: 15px; left: 15px; }
    }
</style>

<div class="gallery-portal">
<div class="cinematic-grid">

<a href="/gallery/video/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-video-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/45.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">فيديوهات وموشن</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/logo/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-logo-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/778.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">شعارات وهويات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/print/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-print-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/911.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">مطبوعات ومرئيات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

</div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    const lazyVideos = document.querySelectorAll('.lazy-video');
    if ('IntersectionObserver' in window) {
        const videoObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                const video = entry.target;
                if (entry.isIntersecting) {
                    const source = video.querySelector('source');
                    if (source && !source.src) {
                        source.src = source.dataset.src;
                        video.load();
                    }
                    video.play().catch(() => {});
                } else {
                    video.pause();
                }
            });
        }, { threshold: 0.2 });
        lazyVideos.forEach(video => {
            videoObserver.observe(video);
        });
    }

    const protectedCards = document.querySelectorAll('.protected-card');
    protectedCards.forEach(card => {
        card.addEventListener('contextmenu', function(e) {
            e.preventDefault();
        });
    });
});
</script>