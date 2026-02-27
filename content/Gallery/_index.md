+++
title = 'Gallery'
draft = false
+++

<style>
.gallery-portal {
    padding: 20px 15px;
    max-width: 900px; /* حجم مدروس لتبدو الفيديوهات سينمائية وغير ممطوطة في الكمبيوتر */
    margin: 0 auto;
    direction: rtl;
    font-family: inherit;
}

.cinematic-grid {
    display: flex;
    flex-direction: column; /* إجبار البطاقات لتكون واحدة فوق الأخرى في كل المنصات */
    gap: 30px;
    margin-top: 20px;
}

.cinematic-card {
    position: relative;
    border-radius: 16px;
    overflow: hidden;
    aspect-ratio: 16 / 9; /* أبعاد فيديو قياسية وموحدة تجبر كل الشاشات على نفس التقسيم */
    width: 100%;
    text-decoration: none;
    background: #0a0a0a;
    border: 1px solid rgba(255, 255, 255, 0.08);
    transition: transform 0.4s ease, border-color 0.4s ease, box-shadow 0.4s ease;
}

.cinematic-card:hover {
    transform: translateY(-5px);
    border-color: #e1c443;
    box-shadow: 0 15px 30px rgba(0,0,0,0.5), 0 0 20px rgba(225, 196, 67, 0.15);
}

.cinematic-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
    transition: transform 0.7s ease, filter 0.4s ease;
    filter: brightness(0.6) grayscale(10%);
    pointer-events: none;
}

.cinematic-card:hover .cinematic-video {
    transform: scale(1.03);
    filter: brightness(0.9) grayscale(0%);
}

/* شريط سفلي نظيف جداً لا يغطي الفيديو */
.cinematic-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 2;
    background: linear-gradient(to top, rgba(0, 0, 0, 0.95) 0%, rgba(0, 0, 0, 0.3) 60%, transparent 100%);
    padding: 25px 30px;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
}

.card-title {
    color: #ffffff;
    font-size: 1.6rem;
    font-weight: 800;
    margin: 0;
    text-shadow: 0 2px 8px rgba(0,0,0,0.8);
}

.card-action {
    color: #e1c443;
    font-size: 1.1rem;
    font-weight: bold;
    transition: transform 0.3s;
    display: flex;
    align-items: center;
    gap: 8px;
}

.cinematic-card:hover .card-action {
    transform: translateX(-8px);
}

/* استجابة الهواتف */
@media (max-width: 768px) {
    .gallery-portal {
        padding: 10px 15px;
    }
    .cinematic-overlay {
        padding: 15px 20px;
        flex-direction: row; /* إبقاء العنوان والزر على نفس السطر */
        align-items: center;
    }
    .card-title {
        font-size: 1.2rem;
    }
    .card-action {
        font-size: 0.9rem;
    }
}
</style>
<div class="gallery-portal">
<div class="cinematic-grid">
<a href="/gallery/video/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-video-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/4545435545435.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">فيديوهات وموشن</h2>
<div class="card-action">شاهد الأعمال <span>←</span></div>
</div>
</a>

<a href="/gallery/logo/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-logo-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/logo-preview.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">شعارات وهويات</h2>
<div class="card-action">شاهد الأعمال <span>←</span></div>
</div>
</a>

<a href="/gallery/print/" class="cinematic-card protected-card">
<video class="cinematic-video lazy-video" loop muted playsinline preload="none" poster="/images/poster-print-temp.jpg" controlslist="nodownload" disablepictureinpicture>
<source data-src="/videos/print-preview.mp4" type="video/mp4">
</video>
<div class="cinematic-overlay">
<h2 class="card-title">مطبوعات ومرئيات</h2>
<div class="card-action">شاهد الأعمال <span>←</span></div>
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