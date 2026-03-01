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
    /* تأثير الهوفر الأساسي للشاشات الكبيرة فقط */
    @media (min-width: 769px) {
        .cinematic-card:hover { 
            transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); 
            box-shadow: 0 20px 40px rgba(0,0,0,0.7), 0 0 30px rgba(225, 196, 67, 0.1); 
        }
        .cinematic-card:hover .card-title {
            animation: pulseGoldBox 1.5s infinite ease-in-out;
        }
        .cinematic-card:active .card-title {
            animation: none;
            color: #1a2855; 
            background: #e1c443; 
            border-color: #e1c443;
            transform: scale(0.95);
        }
        .cinematic-card:hover .reveal-arrow { opacity: 1; transform: translateX(0); }
    }

    /* 3. Video */
    .cinematic-video { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; 
        filter: brightness(0.6) contrast(1.1); transition: transform 1s ease, filter 0.5s ease; pointer-events: none; 
    }
    .cinematic-card:hover .cinematic-video { transform: scale(1.05); filter: brightness(0.8) contrast(1.1); }

    /* 4. Overlay */
    .cinematic-overlay { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; 
        background: rgba(0, 0, 0, 0.3); transition: background 0.5s ease; 
        display: flex; justify-content: center; align-items: center; /* توسيط دقيق 100% */
    }
    .cinematic-card:hover .cinematic-overlay { background: rgba(0, 0, 0, 0.5); }

    /* 5. Title in a Glass Box (مربع الكلمة الزجاجي) */
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
        0% { color: #ffffff; background: rgba(225, 196, 67, 0.1); box-shadow: 0 10px 30px rgba(0,0,0,0.3); border-color: rgba(225, 196, 67, 0.3); }
        50% { color: #e1c443; background: rgba(225, 196, 67, 0.2); box-shadow: 0 10px 40px rgba(225, 196, 67, 0.4); border-color: rgba(225, 196, 67, 0.8); }
        100% { color: #ffffff; background: rgba(225, 196, 67, 0.1); box-shadow: 0 10px 30px rgba(0,0,0,0.3); border-color: rgba(225, 196, 67, 0.3); }
    }

    /* 7. Arrow Position */
    .reveal-arrow {
        color: #e1c443; font-size: 2.8rem; font-weight: bold; text-shadow: 0 0 15px rgba(225, 196, 67, 0.4);
        opacity: 0; transform: translateX(30px); transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
        position: absolute; bottom: 30px; left: 30px;
    }

    /* =========================================
       8. Mobile Customization (تعديلات الهاتف الدقيقة)
       ========================================= */
    @media (max-width: 768px) {
        .gallery-portal { padding: 20px 15px; }
        .cinematic-card {
            height: 220px; /* Wider rectangular format */
            border-radius: 25px;
        }
        .card-title {
            font-size: 1.2rem; /* Reduced font size to prevent overflow */
            padding: 10px 20px; /* Reduced padding for mobile */
            max-width: 95%; /* More generous max-width */
            white-space: nowrap; /* Keep it on one line if possible, but reduced size helps */
        }
        .reveal-arrow { font-size: 2rem; opacity: 0.6; transform: translateX(0); bottom: 15px; left: 15px; }

        /* Subtle style for when a card passes through the central target area */
        .cinematic-card.in-focus {
            border-color: rgba(225, 196, 67, 0.6) !important; /* Brighter gold border */
            box-shadow: 0 5px 15px rgba(225, 196, 67, 0.1) !important; /* Subtle gold shadow */
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
    // Existing lazy-video script
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

    // New script for mobile highlighting on pass
    const galleryCards = document.querySelectorAll('.cinematic-card');
    const highlightArea = document.querySelector('.cinematic-grid'); // Highlight central card relative to this container

    // Function to calculate IntersectionObserver threshold based on screen height
    function getMobileThreshold() {
        return window.innerHeight * 0.4; // Target central 40% of screen
    }

    if ('IntersectionObserver' in window) {
        // Highlighting observer
        const highlightObserver = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    // Find the first and last card to handle edge cases smoothly
                    const cards = Array.from(galleryCards);
                    const isFirstCard = entry.target === cards[0];
                    const isLastCard = entry.target === cards[cards.length - 1];

                    // Check if card is roughly in the center of the viewport
                    const rect = entry.target.getBoundingClientRect();
                    const viewHeight = window.innerHeight;
                    const centralTarget = getMobileThreshold();
                    const cardCenterY = rect.top + rect.height / 2;

                    // Clear previous highlights
                    galleryCards.forEach(c => c.classList.remove('in-focus'));

                    // Add highlight to central card
                    if (isFirstCard || isLastCard || (cardCenterY > centralTarget && cardCenterY < (viewHeight - centralTarget))) {
                        entry.target.classList.add('in-focus');
                    }

                }
            });
        }, {
            root: null, // Use viewport
            rootMargin: `-${getMobileThreshold()}px 0px -${getMobileThreshold()}px 0px`, // Inward margin creates target area
            threshold: 0 // Trigger on any entry/exit
        });

        // Start observing cards for highlighting
        galleryCards.forEach(card => {
            highlightObserver.observe(card);
        });
    }

    // Existing contextmenu protection
    const protectedCards = document.querySelectorAll('.protected-card');
    protectedCards.forEach(card => {
        card.addEventListener('contextmenu', function(e) {
            e.preventDefault();
        });
    });
});
</script>