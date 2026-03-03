+++
title = 'شعارات و هويات بصرية'
description = 'معرض أعمال MBT في تصميم الشعارات والهويات البصرية المتكاملة.'
keywords = 'تصميم شعار, هوية بصرية, براندنج, MBT, تصميم جرافيك'
draft = false
+++

<style>
    /* تصغير عنوان الصفحة الرئيسي في الهاتف لمعرض الشعارات */
    @media (max-width: 768px) {
        .page-header h1, 
        .entry-header h1 {
            font-size: 1.2rem !important;
            line-height: 1.3 !important;
        }
    }
    
    /* =========================================
       1. الإعدادات الأساسية وشبكة Grid بدلاً من Masonry
       ========================================= */
    .page-description, .post-description { display: none !important; }
    .logo-gallery-container { 
        padding: 40px 20px; 
        max-width: 1300px; 
        margin: 0 auto; 
        direction: rtl; 
    }
    
    /* التعديل هنا: استخدام Grid للترتيب الأفقي */
    .mbt-logo-grid { 
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 25px;
        align-items: center; /* لتوسيط الشعارات ذات الارتفاعات المختلفة */
    }

    /* =========================================
       2. كروت الصور 
       ========================================= */
    .logo-thumb-card { 
        position: relative; 
        border-radius: 20px; 
        overflow: hidden; 
        
        height: max-content !important; 
        aspect-ratio: auto !important;
        padding: 0 !important;
        background: transparent !important; 
        
        box-shadow: 0 10px 30px rgba(0,0,0,0.3); 
        cursor: pointer; 
        display: block !important; 
        text-decoration: none; 
        
        /* التعديل هنا: إعدادات الحركة للظهور عند النزول */
        opacity: 0;
        transform: translateY(40px);
        transition: transform 0.6s cubic-bezier(0.25, 0.8, 0.25, 1), opacity 0.6s ease-out, box-shadow 0.4s ease, background 0.4s ease;
    }

    /* الكلاس الذي سيتم إضافته عبر JS عند ظهور العنصر في الشاشة */
    .logo-thumb-card.show {
        opacity: 1;
        transform: translateY(0);
    }

    .thumb-image { 
        display: block !important; 
        margin: 0 !important;
        padding: 0 !important;
        width: 100% !important; 
        height: auto !important; 
        object-fit: cover !important; 
        z-index: 1; 
        transition: transform 0.8s ease, filter 0.5s ease; 
        pointer-events: none; 
    }

    .zoom-icon-glass { 
        position: absolute; 
        top: 50%; left: 50%; 
        transform: translate(-50%, -50%) scale(0.9); 
        width: 60px; height: 60px; 
        background: rgba(225, 196, 67, 0.15); 
        backdrop-filter: blur(10px); 
        -webkit-backdrop-filter: blur(10px); 
        border: 1px solid rgba(225, 196, 67, 0.4); 
        border-radius: 50%; 
        display: flex; align-items: center; justify-content: center; 
        opacity: 0; 
        transition: all 0.4s ease; 
        z-index: 2; 
        pointer-events: none; 
    }
    .zoom-icon-glass::after { 
        content: "🔍"; 
        font-size: 1.5rem; 
        text-shadow: 0 0 15px rgba(225, 196, 67, 0.5); 
    }
    
    @media (min-width: 769px) {
        .logo-thumb-card.show:hover { 
            transform: translateY(-8px); 
            box-shadow: 0 15px 40px rgba(0,0,0,0.6), 0 0 25px rgba(225, 196, 67, 0.15); 
            background: rgba(20, 20, 20, 0.4) !important; 
        }
        .logo-thumb-card.show:hover .thumb-image { 
            transform: scale(1.03); 
        }
        .logo-thumb-card.show:hover .zoom-icon-glass { 
            transform: translate(-50%, -50%) scale(1); 
            opacity: 1; 
        }
    }

    /* =========================================
       3. عارض الصور (Lightbox) المطور
       ========================================= */
    .mbt-lightbox { 
        display: none; 
        position: fixed; 
        top: 0; left: 0; right: 0; bottom: 0; 
        background: rgba(5, 5, 5, 0.95); 
        backdrop-filter: blur(15px);
        -webkit-backdrop-filter: blur(15px);
        z-index: 999999; 
        align-items: center; justify-content: center; 
        opacity: 0; 
        transition: opacity 0.4s ease; 
        overflow: hidden;
    }
    .mbt-lightbox.active { display: flex; opacity: 1; }

    .lb-top-bar { 
        position: absolute; top: 0; left: 0; right: 0; padding: 20px 30px; 
        display: flex; justify-content: space-between; align-items: center; z-index: 100; 
    }
    .lb-controls { display: flex; gap: 15px; direction: ltr; }
    
    .lb-icon-btn, .lightbox-close { 
        width: 45px; height: 45px; 
        background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.2); 
        border-radius: 50%; color: #fff; display: flex; align-items: center; justify-content: center; 
        font-size: 1.2rem; cursor: pointer; transition: all 0.3s; 
        backdrop-filter: blur(5px); -webkit-backdrop-filter: blur(5px);
    }
    .lb-icon-btn:hover, .lightbox-close:hover { 
        background: #e1c443; color: #000; border-color: #e1c443; transform: scale(1.1); 
    }

    .lb-nav { 
        position: absolute; top: 50%; transform: translateY(-50%); 
        background: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.1); color: #fff; 
        width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; 
        font-size: 1.2rem; cursor: pointer; z-index: 100; transition: all 0.3s; 
        backdrop-filter: blur(5px); -webkit-backdrop-filter: blur(5px);
        direction: ltr !important; 
    }
    .lb-nav:hover { background: #e1c443; color: #000; border-color: #e1c443; transform: translateY(-50%) scale(1.1); }
    .right-nav { right: 20px; }
    .left-nav { left: 20px; }

    .lightbox-content-wrapper { 
        width: 100vw; height: 100vh; 
        display: flex; align-items: center; justify-content: center;
        position: relative; 
    }
    
    .lightbox-image { 
        max-width: 90vw; max-height: 85vh; 
        object-fit: contain; 
        transition: transform 0.1s ease-out; 
        transform-origin: center center; 
        cursor: grab; 
        user-select: none; 
        -webkit-user-drag: none;
        filter: drop-shadow(0 10px 30px rgba(0,0,0,0.5));
    }
    .lightbox-image:active { cursor: grabbing; }

    /* التعديل هنا: تحويل Grid إلى عمودين في الهواتف */
    @media (max-width: 992px) { .mbt-logo-grid { grid-template-columns: repeat(2, 1fr); } }
    
    @media (max-width: 768px) {
        .page-header h1, 
        .entry-header h1,
        .post-title {
            font-size: 1.2rem !important;
            white-space: nowrap !important;
            overflow: hidden !important;
            text-overflow: ellipsis !important;
            line-height: 1.3 !important;
            margin-bottom: 10px !important;
        }
    }
</style>

<div class="logo-gallery-container">
    <div class="mbt-logo-grid" id="mbt-logo-grid"></div>
</div>

<div class="mbt-lightbox" id="image-lightbox"><div class="lb-top-bar"><div class="lb-controls"><button class="lb-icon-btn" id="lb-play" onclick="window.toggleSlideshow()" title="تشغيل تلقائي">▶</button><button class="lb-icon-btn" onclick="window.resetZoom()" title="استعادة الحجم الأصلي">⛶</button></div><div class="lightbox-close" onclick="window.closeImageModal()" title="إغلاق">✕</div></div><button class="lb-nav right-nav" onclick="window.prevImage(event)">&#10095;</button><button class="lb-nav left-nav" onclick="window.nextImage(event)">&#10094;</button><div class="lightbox-content-wrapper" id="lb-wrapper"><img id="lb-image-viewer" class="lightbox-image" src="" alt="MBT Identity"></div></div>

<script>
// ==========================================
// 1. قائمة الصور 
// ==========================================
const myLogos = [
    "645654654.png", "546456456456.png", "56547567rr.png", "6457568.png",
    "46546546.png", "شعار.png", "6456546546uu.png", "457657568uy.png",
    "546546546.png", "5454543545.png", "75756567567.png", "بروفايل.png",
    "tyu676.png", "64575756rtg.png", "655765egrgr.png", "57566bhh.png",
    "535435.png", "rgtry776.png", "tytuyuii.png", "5654654654.png",
    "76768798hg١.png", "4565.png", "47575.png", "5656567.png",
    "4645757.png", "6567686.png", "575676uc.png", "hyuyiuiui88.png",
    "756767.png", "576ght.png", "45454.png", "556uyu.png",
];

const r2_base = "https://media.mbt.ad/";
const imageList = myLogos.map(file => r2_base + file);

let currentIndex = 0;
let slideshowInterval = null;
let isPlaying = false;
let scale = 1;
let isDragging = false;
let startX, startY, translateX = 0, translateY = 0;

// ==========================================
// 2. دوال التحكم بالنافذة 
// ==========================================
window.openImageModal = function(index) {
    currentIndex = index;
    const lbImage = document.getElementById('lb-image-viewer');
    if(lbImage) lbImage.src = imageList[currentIndex];
    window.resetZoom();
    const lightbox = document.getElementById('image-lightbox');
    if(lightbox) lightbox.classList.add('active');
    document.body.style.overflow = 'hidden';
};

window.closeImageModal = function() {
    const lightbox = document.getElementById('image-lightbox');
    if(lightbox) lightbox.classList.remove('active');
    document.body.style.overflow = 'auto';
    if(isPlaying) window.toggleSlideshow(); 
    setTimeout(() => { 
        const lbImage = document.getElementById('lb-image-viewer');
        if(lbImage) lbImage.src = ""; 
        window.resetZoom(); 
    }, 400);
};

window.nextImage = function(e) {
    if(e) e.stopPropagation();
    currentIndex = (currentIndex + 1) % imageList.length;
    const lbImage = document.getElementById('lb-image-viewer');
    if(lbImage) lbImage.src = imageList[currentIndex];
    window.resetZoom();
};

window.prevImage = function(e) {
    if(e) e.stopPropagation();
    currentIndex = (currentIndex - 1 + imageList.length) % imageList.length;
    const lbImage = document.getElementById('lb-image-viewer');
    if(lbImage) lbImage.src = imageList[currentIndex];
    window.resetZoom();
};

window.toggleSlideshow = function(e) {
    if(e) e.stopPropagation();
    const btn = document.getElementById('lb-play');
    if (isPlaying) {
        clearInterval(slideshowInterval);
        if(btn) btn.innerHTML = '▶';
        isPlaying = false;
    } else {
        slideshowInterval = setInterval(() => window.nextImage(), 3000); 
        if(btn) btn.innerHTML = '⏸';
        isPlaying = true;
    }
};

window.resetZoom = function(e) {
    if(e) e.stopPropagation();
    scale = 1; translateX = 0; translateY = 0;
    const lbImage = document.getElementById('lb-image-viewer');
    if(lbImage) lbImage.style.transform = `translate(${translateX}px, ${translateY}px) scale(${scale})`;
};

function applyTransform() {
    const lbImage = document.getElementById('lb-image-viewer');
    if(lbImage) lbImage.style.transform = `translate(${translateX}px, ${translateY}px) scale(${scale})`;
}

// ==========================================
// 3. بناء المعرض وإضافة تأثير الظهور الذكي
// ==========================================
function buildLogoGallery() {
    const gridContainer = document.getElementById('mbt-logo-grid');
    if (!gridContainer || gridContainer.innerHTML.trim() !== "") return; 

    // تم إزالة style="animation-delay" لحل مشكلة التأخير
    imageList.forEach((fullImageUrl, index) => {
        const cardHTML = `
            <a href="javascript:void(0);" onclick="window.openImageModal(${index})" class="logo-thumb-card protected-item">
                <img class="thumb-image" src="${fullImageUrl}" loading="lazy" alt="MBT Logo Design">
                <div class="zoom-icon-glass"></div>
            </a>
        `;
        gridContainer.insertAdjacentHTML('beforeend', cardHTML);
    });

    document.querySelectorAll('.protected-item, .lightbox-image').forEach(item => {
        item.oncontextmenu = e => e.preventDefault();
        item.ondragstart = e => e.preventDefault();
    });

    // تفعيل تأثير الظهور عند الوصول للصور (Intersection Observer)
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('show');
                observer.unobserve(entry.target); // إيقاف المراقبة بعد ظهورها
            }
        });
    }, { threshold: 0.1 }); // تظهرเมื่อ يظهر 10% منها في الشاشة

    document.querySelectorAll('.logo-thumb-card').forEach(card => {
        observer.observe(card);
    });
}

// ==========================================
// 4. ربط أحداث التكبير والسحب
// ==========================================
setTimeout(() => {
    const lbWrapper = document.getElementById('lb-wrapper');
    const lbImage = document.getElementById('lb-image-viewer');
    const lightbox = document.getElementById('image-lightbox');

    if(lbWrapper && lbImage) {
        lbWrapper.addEventListener('wheel', (e) => {
            e.preventDefault();
            const delta = e.deltaY < 0 ? 1 : -1;
            scale += delta * 0.15; 
            scale = Math.min(Math.max(1, scale), 5); 
            if(scale === 1) { translateX = 0; translateY = 0; } 
            applyTransform();
        });

        lbWrapper.addEventListener('mousedown', (e) => {
            if (scale > 1 && e.target === lbImage) {
                isDragging = true;
                startX = e.clientX - translateX;
                startY = e.clientY - translateY;
            }
        });
        window.addEventListener('mousemove', (e) => {
            if (isDragging) {
                e.preventDefault();
                translateX = e.clientX - startX;
                translateY = e.clientY - startY;
                applyTransform();
            }
        });
        window.addEventListener('mouseup', () => { isDragging = false; });

        let initialDistance = null;
        let initialScale = 1;

        lbWrapper.addEventListener('touchstart', (e) => {
            if (e.touches.length === 2) {
                initialDistance = Math.hypot(e.touches[0].clientX - e.touches[1].clientX, e.touches[0].clientY - e.touches[1].clientY);
                initialScale = scale;
            } else if (e.touches.length === 1 && scale > 1 && e.target === lbImage) {
                isDragging = true;
                startX = e.touches[0].clientX - translateX;
                startY = e.touches[0].clientY - translateY;
            }
        });

        lbWrapper.addEventListener('touchmove', (e) => {
            if (e.touches.length === 2) {
                e.preventDefault(); 
                const currentDistance = Math.hypot(e.touches[0].clientX - e.touches[1].clientX, e.touches[0].clientY - e.touches[1].clientY);
                const delta = currentDistance / initialDistance;
                scale = Math.min(Math.max(1, initialScale * delta), 5);
                if(scale === 1) { translateX = 0; translateY = 0; }
                applyTransform();
            } else if (e.touches.length === 1 && isDragging) {
                e.preventDefault();
                translateX = e.touches[0].clientX - startX;
                translateY = e.touches[0].clientY - startY;
                applyTransform();
            }
        });

        lbWrapper.addEventListener('touchend', () => { isDragging = false; });
    }

    if(lightbox) {
        lightbox.addEventListener('click', function(e) {
            if (e.target === this || e.target.id === 'lb-wrapper') {
                window.closeImageModal();
            }
        });
    }
}, 300);

buildLogoGallery();
</script>