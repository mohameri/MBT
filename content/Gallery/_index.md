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

    /* 3. Video */
    .cinematic-video { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; 
        filter: brightness(0.6) contrast(1.1); transition: transform 1s ease, filter 0.5s ease; pointer-events: none; 
    }

    /* 4. Overlay - سر السنترة المثالية هنا */
    .cinematic-overlay { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; 
        background: rgba(0, 0, 0, 0.3); transition: background 0.5s ease; 
        display: flex; justify-content: center; align-items: center; /* توسيط دقيق 100% */
    }

    /* 5. Title in a Glass Box */
    .card-title {
        background: rgba(225, 196, 67, 0.1);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        border: 1px solid rgba(225, 196, 67, 0.3);
        padding: 18px 50px;
        border-radius: 50px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.3);
        color: #ffffff; 
        font-size: 2.2rem; 
        font-weight: 900; 
        margin: 0; 
        text-shadow: 0 2px 10px rgba(0,0,0,0.5); 
        text-align: center; 
        transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
    }

    /* 6. Arrow Position */
    .reveal-arrow {
        color: #e1c443; font-size: 2.8rem; font-weight: bold; text-shadow: 0 0 15px rgba(225, 196, 67, 0.4);
        opacity: 0; transform: translateX(30px); transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
        position: absolute; bottom: 30px; left: 30px;
    }

    /* =========================================
       تأثيرات الشاشات الكبيرة (الكمبيوتر) فقط
       ========================================= */
    @media (min-width: 769px) {
        .cinematic-card:hover { 
            transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); 
            box-shadow: 0 20px 40px rgba(0,0,0,0.7), 0 0 30px rgba(225, 196, 67, 0.1); 
        }
        .cinematic-card:hover .cinematic-video { transform: scale(1.05); filter: brightness(0.8) contrast(1.1); }
        .cinematic-card:hover .cinematic-overlay { background: rgba(0, 0, 0, 0.5); }
        .cinematic-card:hover .reveal-arrow { opacity: 1; transform: translateX(0); }
        
        @keyframes pulseGoldBox {
            0% { color: #ffffff; background: rgba(225, 196, 67, 0.1); box-shadow: 0 10px 30px rgba(0,0,0,0.3); border-color: rgba(225, 196, 67, 0.3); }
            50% { color: #e1c443; background: rgba(225, 196, 67, 0.2); box-shadow: 0 10px 40px rgba(225, 196, 67, 0.4); border-color: rgba(225, 196, 67, 0.8); }
            100% { color: #ffffff; background: rgba(225, 196, 67, 0.1); box-shadow: 0 10px 30px rgba(0,0,0,0.3); border-color: rgba(225, 196, 67, 0.3); }
        }
        .cinematic-card:hover .card-title { animation: pulseGoldBox 1.5s infinite ease-in-out; }
        .cinematic-card:active .card-title {
            animation: none; color: #1a2855; background: #e1c443; border-color: #e1c443; transform: scale(0.95);
        }
    }

    /* =========================================
       تخصيص الهاتف المحمول (تصغير دقيق وتأثير التمرير)
       ========================================= */
    @media (max-width: 768px) {
        .gallery-portal { padding: 20px 15px; }
        .cinematic-grid { gap: 25px; }
        .cinematic-card { height: 200px; border-radius: 20px; }
        
        .card-title { 
            font-size: 1.1rem; /* خط أصغر ومناسب */
            padding: 10px 25px; /* بوكس أصغر وملموم */
            white-space: nowrap; /* إجبار النص على البقاء بسطر واحد */
            max-width: 90%; /* حماية إضافية لمنع الخروج من الشاشة */
        }
        .reveal-arrow { font-size: 1.6rem; opacity: 0.8; transform: translateX(0); bottom: 12px; left: 15px; }

        /* التأثير السحري عند مرور الكارت بمنتصف الشاشة أثناء النزول */
        .cinematic-card.in-focus {
            border-color: rgba(225, 196, 67, 0.4);
        }
        .cinematic-card.in-focus .cinematic-video {
            filter: brightness(0.8) contrast(1.1); /* تفتيح الفيديو ناعم */
        }
        .cinematic-card.in-focus .card-title {
            background: rgba(225, 196, 67, 0.2);
            border-color: rgba(225, 196, 67, 0.8);
            color: #e1c443; /* النص يصبح ذهبي */
            box-shadow: 0 5px 20px rgba(225, 196, 67, 0.3);
            transform: scale(1.03); /* الكلمة تبرز قليلاً */
        }
    }
</style>

<div class="gallery-portal">
<div class="cinematic-grid">

<a href="/gallery/video/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-video-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/45.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">فيديوهات و موشن</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/logo/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-logo-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/778.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">شعارات و هويات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

<a href="/gallery/print/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-print-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/911.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">مطبوعات و مرئيات</h2>
<div class="reveal-arrow">←</div>
</div>
</a>

</div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
    // 1. تشغيل الفيديو الذكي (Lazy Load)
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

    // 2. سكريبت الهاتف: تفعيل التأثير الذهبي عند وصول الكارت لمنتصف الشاشة
    if (window.innerWidth <= 768 && 'IntersectionObserver' in window) {
        const galleryCards = document.querySelectorAll('.cinematic-card');
        
        // إنشاء منطقة تركيز وهمية في منتصف الشاشة
        const focusObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('in-focus');
                } else {
                    entry.target.classList.remove('in-focus');
                }
            });
        }, {
            // سالب 35% من فوق وجوه يعني المنطقة الفعالة هي 30% بمنتصف الشاشة فقط
            rootMargin: "-35% 0px -35% 0px",
            threshold: 0
        });

        galleryCards.forEach(card => {
            focusObserver.observe(card);
        });
    }

    // 3. حماية الفيديوهات من النقر كليك يمين
    const protectedCards = document.querySelectorAll('.protected-card');
    protectedCards.forEach(card => {
        card.addEventListener('contextmenu', function(e) {
            e.preventDefault();
        });
    });
});
</script>