+++
title = 'معرض اعمالنا'
description = 'تصفح معرض أعمال وكالة MBT. نقدم خدمات احترافية في صناعة المحتوى، الموشن جرافيك، تصميم الشعارات والهويات البصرية، وإدارة الحسابات لتعزيز علامتك التجارية.'
keywords = 'معرض أعمال, تصميم شعارات, موشن جرافيك, صناعة محتوى, هويات بصرية, وكالة تسويق, MBT'
draft = false
+++

<style>
    /* Reset & Base */
    .page-description, .post-description { display: none !important; }
    .gallery-portal { padding: 40px 20px; max-width: 1000px; margin: 0 auto; direction: rtl; font-family: inherit; }
    .cinematic-grid { display: flex; flex-direction: column; gap: 40px; }

    /* Cards */
    .cinematic-card { 
        position: relative; border-radius: 35px; overflow: hidden; height: 450px; width: 100%; 
        text-decoration: none; background: #0a0a0a; border: 1px solid rgba(255, 255, 255, 0.05); 
        box-shadow: 0 10px 30px rgba(0,0,0,0.5); transition: all 0.5s ease; display: block; 
    }

    /* Video & Hidden Browser Controls (الحل الجذري للمشكلة) */
    .cinematic-video { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; 
        filter: brightness(0.6) contrast(1.1); transition: all 0.5s ease; pointer-events: none; 
    }
    video::-webkit-media-controls, video::-webkit-media-controls-enclosure { display: none !important; }

    /* Overlay & Titles */
    .cinematic-overlay { 
        position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; 
        background: rgba(0, 0, 0, 0.3); display: flex; justify-content: center; align-items: center; 
    }
    .card-title {
        background: rgba(225, 196, 67, 0.1); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px);
        border: 1px solid rgba(225, 196, 67, 0.3); padding: 18px 50px; border-radius: 50px;
        color: #fff; font-size: 2.2rem; font-weight: 900; margin: 0; text-align: center; transition: all 0.4s ease;
    }
    .reveal-arrow {
        color: #e1c443; font-size: 2.8rem; font-weight: bold; position: absolute; bottom: 30px; left: 30px;
        opacity: 0; transform: translateX(30px); transition: all 0.4s ease;
    }

    /* Desktop Hover Effects */
    @media (min-width: 769px) {
        .cinematic-card:hover { transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); box-shadow: 0 20px 40px rgba(0,0,0,0.7); }
        .cinematic-card:hover .cinematic-video { transform: scale(1.05); filter: brightness(0.8); }
        .cinematic-card:hover .reveal-arrow { opacity: 1; transform: translateX(0); }
        .cinematic-card:hover .card-title { background: rgba(225, 196, 67, 0.2); border-color: rgba(225, 196, 67, 0.8); color: #e1c443; }
    }

    /* Mobile Adjustments */
    @media (max-width: 768px) {
        .gallery-portal { padding: 20px 15px; }
        .cinematic-grid { gap: 20px; }
        .cinematic-card { height: 200px; border-radius: 20px; }
        .card-title { font-size: 15px !important; padding: 10px 22px !important; background: rgba(225, 196, 67, 0.05) !important; }
        .reveal-arrow { font-size: 1.5rem !important; opacity: 0.8; transform: translateX(0); bottom: 12px; left: 15px; }
        
        .cinematic-card.in-focus { border-color: rgba(225, 196, 67, 0.3) !important; }
        .cinematic-card.in-focus .cinematic-video { filter: brightness(0.8) !important; }
        .cinematic-card.in-focus .card-title { background: rgba(225, 196, 67, 0.15) !important; color: #e1c443 !important; transform: scale(1.02); }
    }
</style>

<div class="gallery-portal">
    <div class="cinematic-grid">
        <a href="/gallery/video/" class="cinematic-card">
            <video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-video-temp.jpg" disablepictureinpicture>
                <source data-src="/videos/45.mp4" type="video/mp4">
            </video>
            <div class="cinematic-overlay">
                <h2 class="card-title">فيديوهات و موشن</h2>
                <div class="reveal-arrow">←</div>
            </div>
        </a>

        <a href="/gallery/logo/" class="cinematic-card">
            <video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-logo-temp.jpg" disablepictureinpicture>
                <source data-src="/videos/6767.mp4" type="video/mp4">
            </video>
            <div class="cinematic-overlay">
                <h2 class="card-title">شعارات و هويات</h2>
                <div class="reveal-arrow">←</div>
            </div>
        </a>

        <a href="/gallery/print/" class="cinematic-card">
            <video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-print-temp.jpg" disablepictureinpicture>
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
document.addEventListener("DOMContentLoaded", () => {
    // 1. Lazy Load Videos (Optimized)
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

    // 2. Mobile Focus Effect (Optimized)
    if (window.innerWidth <= 768 && 'IntersectionObserver' in window) {
        const focusObs = new IntersectionObserver(entries => {
            entries.forEach(e => e.target.classList.toggle('in-focus', e.isIntersecting));
        }, { rootMargin: "-35% 0px", threshold: 0 });
        document.querySelectorAll('.cinematic-card').forEach(c => focusObs.observe(c));
    }
});
</script>