+++
title = 'فيديوهات و موشن'
description = 'شاهد أعمال MBT في صناعة الفيديو والموشن جرافيك.'
keywords = 'مونتاج, فيديوهات, موشن جرافيك, تصوير, MBT'
draft = false
+++

<style>
    .page-description, .post-description { display: none !important; }
    .video-gallery-container { padding: 40px 20px; max-width: 1300px; margin: 0 auto; direction: rtl; }
    
    .mbt-video-grid { column-count: 3; column-gap: 25px; }
    
    .video-thumb-card { break-inside: avoid; margin-bottom: 25px; position: relative; border-radius: 20px; overflow: hidden; background: #0a0a0a; border: 1px solid rgba(255, 255, 255, 0.05); box-shadow: 0 10px 30px rgba(0,0,0,0.5); cursor: pointer; transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1); display: block; text-decoration: none; }
    .video-thumb-card.h { aspect-ratio: 16 / 9; }
    .video-thumb-card.v { aspect-ratio: 9 / 16; }
    
    .thumb-video { position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: cover; z-index: 1; filter: brightness(0.7); transition: transform 0.8s ease, filter 0.5s ease; pointer-events: none; }
    
    .play-icon-glass { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%) scale(0.9); width: 60px; height: 60px; background: rgba(225, 196, 67, 0.15); backdrop-filter: blur(10px); -webkit-backdrop-filter: blur(10px); border: 1px solid rgba(225, 196, 67, 0.4); border-radius: 50%; display: flex; align-items: center; justify-content: center; opacity: 0.8; transition: all 0.4s ease; z-index: 2; pointer-events: none; }
    .play-icon-glass::after { content: "▶"; color: #e1c443; font-size: 1.5rem; margin-left: -4px; text-shadow: 0 0 15px rgba(225, 196, 67, 0.5); }
    
    @media (min-width: 769px) {
        .video-thumb-card:hover { transform: translateY(-8px); border-color: rgba(225, 196, 67, 0.4); box-shadow: 0 15px 40px rgba(0,0,0,0.7), 0 0 20px rgba(225, 196, 67, 0.1); }
        .video-thumb-card:hover .thumb-video { transform: scale(1.05); filter: brightness(0.9); }
        .video-thumb-card:hover .play-icon-glass { transform: translate(-50%, -50%) scale(1.1); background: rgba(225, 196, 67, 0.25); opacity: 1; }
    }

    /* Lightbox */
    .mbt-lightbox { display: none; position: fixed; inset: 0; background: rgba(5, 5, 5, 0.98); z-index: 999999; align-items: center; justify-content: center; opacity: 0; transition: opacity 0.4s ease; }
    .mbt-lightbox.active { display: flex; opacity: 1; }
    
    .lightbox-close { position: absolute; top: 25px; right: 25px; width: 45px; height: 45px; background: rgba(255,255,255,0.1); border-radius: 50%; color: #fff; font-size: 1.2rem; display: flex; align-items: center; justify-content: center; cursor: pointer; z-index: 10; transition: all 0.3s; }
    .lightbox-close:hover { background: #e1c443; color: #000; transform: rotate(90deg); }
    
    .lightbox-content-wrapper { width: 95%; max-width: 1200px; position: relative; box-shadow: 0 25px 60px rgba(0,0,0,0.8); transform: scale(0.95); transition: transform 0.4s cubic-bezier(0.25, 0.8, 0.25, 1); border-radius: 10px; overflow: hidden; background: transparent; }
    .mbt-lightbox.active .lightbox-content-wrapper { transform: scale(1);}
    
    .lightbox-video { width: 100%; max-height: 85vh; display: block; object-fit: contain; }
    .protection-shield { position: absolute; inset: 0; z-index: 2; cursor: pointer; }
    
    .custom-controls-bar { position: absolute; bottom: 0; left: 0; right: 0; padding: 25px; background: linear-gradient(to top, rgba(0,0,0,0.8) 0%, transparent 100%); z-index: 3; display: flex; gap: 20px; justify-content: center; opacity: 0; transition: opacity 0.4s ease; }
    .control-btn { background: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.2); color: #fff; border-radius: 50%; cursor: pointer; backdrop-filter: blur(5px); transition: all 0.3s; width: 55px; height: 55px; display: flex; align-items: center; justify-content: center; font-size: 1.6rem; padding: 0; }
    .control-btn:hover { background: #e1c443; color: #000; border-color: #e1c443; transform: scale(1.1); }
    
    @media (max-width: 992px) { .mbt-video-grid { column-count: 2; } }
    @media (max-width: 768px) {
        /* استهداف كل الكلاسات الممكنة للعناوين في PaperMod */
        .page-header h1, 
        .entry-header h1,
        .post-title {
            font-size: 1.2rem !important; /* حجم الخط الصغير */
            white-space: nowrap !important; /* إجبار النص على البقاء في سطر واحد */
            overflow: hidden !important; /* إخفاء أي جزء يخرج عن الشاشة */
            text-overflow: ellipsis !important; /* وضع ثلاث نقاط (...) إذا كانت شاشة الهاتف صغيرة جداً */
            line-height: 1.3 !important;
            margin-bottom: 10px !important;
        }
    }
</style>

<div class="video-gallery-container">
    <div class="mbt-video-grid" id="mbt-dynamic-grid"></div>
</div>

<div class="mbt-lightbox" id="main-lightbox">
    <div class="lightbox-close" onclick="closeVideoModal()">✕</div>
    <div class="lightbox-content-wrapper">
        <video id="lb-video-player" class="lightbox-video" controlslist="nodownload noremoteplayback nofullscreen" disablepictureinpicture playsinline></video>
        <div class="protection-shield" id="video-shield" onclick="handleVideoClick()"></div>
        <div class="custom-controls-bar" id="controls-bar">
            <button class="control-btn" onclick="restartVideo()" title="إعادة من البداية"><img src="/icons/restart.svg" class="mbt-icon"></button>
            <button class="control-btn" id="custom-play-btn" onclick="toggleVideoPlay()" title="إيقاف / تشغيل">
    <img src="/icons/pause.svg" class="mbt-icon" alt="pause">
</button>
            <button class="control-btn" id="custom-mute-btn" onclick="toggleVideoMute()" title="الصوت">🔊</button>
        </div>
    </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", () => {
    // 1. بناء المعرض دفعة واحدة
    const myVideos = [
        { file: "55756868.mp4", type: "v" },
        { file: "454543545h78435.mp4", type: "v" },
        { file: "2134535465.mp4", type: "v" },
        { file: "6456456.mp4", type: "h" },
        { file: "5435.mp4", type: "h" },
        { file: "٣٧٣٧٨٣.mp4", type: "v" },
        { file: "798685754.mp4", type: "v" },
        { file: "6876785785.mp4", type: "h" },
        { file: "23423737878543.mp4", type: "v" },
        { file: "54345435435.mp4", type: "v" },
        { file: "697764.mp4", type: "v" },
        { file: "444567.mp4", type: "h" }
    ];
    
    const r2_base = "https://media.mbt.ad/";
    const gridContainer = document.getElementById('mbt-dynamic-grid');
    
    let htmlContent = "";
    myVideos.forEach(vid => {
        const highResUrl = r2_base + vid.file;
        const lowResUrl = r2_base + vid.file.replace('.mp4', '-low.mp4');
        
        htmlContent += `
        <a href="javascript:void(0);" onclick="openVideoModal('${highResUrl}')" class="video-thumb-card ${vid.type} protected-item">
            <video class="thumb-video lazy-thumb" loop muted playsinline preload="none" data-src="${lowResUrl}"></video>
            <div class="play-icon-glass"></div>
        </a>`;
    });
    gridContainer.innerHTML = htmlContent;

    // 2. التحميل الذكي والتشغيل عند التحويم/اللمس
    const lazyThumbs = document.querySelectorAll('.lazy-thumb');
    let currentlyPlaying = null;
    
    if ('IntersectionObserver' in window) {
        const thumbObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                const video = entry.target;
                if (entry.isIntersecting) {
                    if (!video.src && video.dataset.src) {
                        video.src = video.dataset.src;
                        video.load();
                    }
                } else {
                    video.pause();
                    if (currentlyPlaying === video) currentlyPlaying = null;
                }
            });
        }, { rootMargin: "100px", threshold: 0.1 }); 
        
        lazyThumbs.forEach(v => thumbObserver.observe(v));
    }

    const thumbCards = document.querySelectorAll('.video-thumb-card');
    thumbCards.forEach(card => {
        const video = card.querySelector('.thumb-video');
        let pressTimer;

        const startPreview = () => {
            if (currentlyPlaying && currentlyPlaying !== video) currentlyPlaying.pause();
            video.play().catch(() => {});
            currentlyPlaying = video;
        };
        const stopPreview = () => video.pause();

        card.addEventListener('mouseenter', startPreview);
        card.addEventListener('mouseleave', stopPreview);
        card.addEventListener('touchstart', () => pressTimer = setTimeout(startPreview, 100), { passive: true });
        card.addEventListener('touchend', () => { clearTimeout(pressTimer); stopPreview(); });
        card.addEventListener('touchmove', () => { clearTimeout(pressTimer); stopPreview(); }, { passive: true });
    });

    // 3. حماية المحتوى
    document.querySelectorAll('.protected-item, .protection-shield, #lb-video-player').forEach(item => {
        item.oncontextmenu = e => e.preventDefault();
        item.ondragstart = e => e.preventDefault();
    });

    // إغلاق المودال عند الضغط خارجه
    const lightbox = document.getElementById('main-lightbox');
    if (lightbox) {
        lightbox.addEventListener('click', e => {
            if (e.target === lightbox) closeVideoModal();
        });
    }
});

// 4. دوال التحكم بالـ Lightbox مبسطة
let controlsTimeout;
const lbVideo = document.getElementById('lb-video-player');
const playBtn = document.getElementById('custom-play-btn');
const muteBtn = document.getElementById('custom-mute-btn');
const controlsBar = document.getElementById('controls-bar');
const lightbox = document.getElementById('main-lightbox');

window.showControlsBar = () => {
    if(!controlsBar) return;
    controlsBar.style.opacity = '1';
    clearTimeout(controlsTimeout);
    controlsTimeout = setTimeout(() => controlsBar.style.opacity = '0', 3000);
};

window.handleVideoClick = () => {
    if (!controlsBar) return;
    if (controlsBar.style.opacity === '1') {
        // إذا كانت الأزرار ظاهرة، يتم إخفاؤها فوراً وإلغاء المؤقت
        controlsBar.style.opacity = '0';
        clearTimeout(controlsTimeout);
    } else {
        // إذا كانت مخفية، يتم إظهارها وتشغيل مؤقت الاختفاء
        showControlsBar();
    }
};

window.openVideoModal = (url) => {
    if (!lightbox || !lbVideo) return;
    lbVideo.src = url;
    lightbox.classList.add('active');
    showControlsBar();
    lbVideo.play().then(() => playBtn.innerHTML = '<img src="/icons/pause.svg" class="mbt-icon" alt="pause">').catch(() => playBtn.innerHTML = '<img src="/icons/play.svg" class="mbt-icon" alt="play">');
};

window.closeVideoModal = () => {
    if (!lightbox) return;
    lightbox.classList.remove('active');
    clearTimeout(controlsTimeout);
    setTimeout(() => {
        if(lbVideo) { lbVideo.pause(); lbVideo.src = ""; }
    }, 400);
};

window.toggleVideoPlay = () => {
    if (!lbVideo) return;
    lbVideo.paused ? lbVideo.play() : lbVideo.pause();
    if(playBtn) {
        // تغيير مسار الصورة بناءً على حالة الفيديو
        const iconPath = lbVideo.paused ? "/icons/play.svg" : "/icons/pause.svg";
        playBtn.innerHTML = `<img src="${iconPath}" class="mbt-icon">`;
    }
    showControlsBar();
};

window.toggleVideoMute = () => {
    if (!lbVideo || !muteBtn) return;
    lbVideo.muted = !lbVideo.muted;
    muteBtn.innerText = lbVideo.muted ? "🔇" : "🔊";
    showControlsBar();
};

window.restartVideo = () => {
    if (!lbVideo) return;
    lbVideo.currentTime = 0;
    lbVideo.play();
    if(playBtn) playBtn.innerHTML = '<img src="/icons/pause.svg" class="mbt-icon" alt="pause">';
    showControlsBar();
};
</script>