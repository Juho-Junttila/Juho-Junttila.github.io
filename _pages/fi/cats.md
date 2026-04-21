---
layout: archive
title: ""
permalink: /fi/cats/
author_profile: false
lang: fi
en_url: /cats/
---

<style>
.cats-heading {
  font-family: "Cormorant Garamond", serif;
  font-size: 32px;
  font-weight: 400;
  color: oklch(22% 0.01 75);
  margin-bottom: 32px;
  letter-spacing: -0.01em;
  line-height: 1;
  margin-top: 0;
}

.cat-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 14px;
}

.cat-cell {
  aspect-ratio: 4/3;
  border-radius: 2px;
  overflow: hidden;
  cursor: zoom-in;
  background: oklch(94.5% 0.013 78);
}

.cat-cell img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.3s ease;
}

.cat-cell:hover img {
  transform: scale(1.03);
}

.cat-lightbox {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 300;
  background: rgba(14,10,6,0.85);
  backdrop-filter: blur(10px);
  align-items: center;
  justify-content: center;
  padding: 24px;
}

.cat-lightbox.open {
  display: flex;
}

.cat-lightbox img {
  max-width: 90vw;
  max-height: 85vh;
  object-fit: contain;
  border-radius: 2px;
}

.cat-lb-btn {
  position: fixed;
  top: 50%;
  transform: translateY(-50%);
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: rgba(255,255,255,0.1);
  border: none;
  color: #fff;
  font-size: 32px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: serif;
  line-height: 1;
}

.cat-lb-btn:hover {
  background: rgba(255,255,255,0.2);
}

.cat-lb-prev { left: 24px; }
.cat-lb-next { right: 24px; }
</style>

<h1 class="cats-heading">Kissat</h1>

<div class="cat-grid" id="catGrid">
  <div class="cat-cell" onclick="openLightbox(0)"><img src="/images/kissat1.jpeg" alt="Kissokuva 1"></div>
  <div class="cat-cell" onclick="openLightbox(1)"><img src="/images/kissat2.jpeg" alt="Kissokuva 2"></div>
  <div class="cat-cell" onclick="openLightbox(2)"><img src="/images/kissat5.JPG" alt="Kissokuva 3"></div>
  <div class="cat-cell" onclick="openLightbox(3)"><img src="/images/kissat6.jpeg" alt="Kissokuva 4"></div>
  <div class="cat-cell" onclick="openLightbox(4)"><img src="/images/kissat7.jpeg" alt="Kissokuva 5"></div>
</div>

<div class="cat-lightbox" id="catLightbox" onclick="closeLightbox(event)">
  <img id="lbImg" src="" alt="Kissokuva">
  <button class="cat-lb-btn cat-lb-prev" onclick="event.stopPropagation(); prevPhoto()">&#8249;</button>
  <button class="cat-lb-btn cat-lb-next" onclick="event.stopPropagation(); nextPhoto()">&#8250;</button>
</div>

<script>
var CAT_IMGS = [
  '/images/kissat1.jpeg',
  '/images/kissat2.jpeg',
  '/images/kissat5.JPG',
  '/images/kissat6.jpeg',
  '/images/kissat7.jpeg'
];
var currentIdx = 0;

function openLightbox(i) {
  currentIdx = i;
  document.getElementById('lbImg').src = CAT_IMGS[i];
  document.getElementById('catLightbox').classList.add('open');
  document.body.style.overflow = 'hidden';
}

function closeLightbox(e) {
  if (e.target === document.getElementById('catLightbox') || e.target === document.getElementById('lbImg')) {
    document.getElementById('catLightbox').classList.remove('open');
    document.body.style.overflow = '';
  }
}

function prevPhoto() {
  currentIdx = (currentIdx - 1 + CAT_IMGS.length) % CAT_IMGS.length;
  document.getElementById('lbImg').src = CAT_IMGS[currentIdx];
}

function nextPhoto() {
  currentIdx = (currentIdx + 1) % CAT_IMGS.length;
  document.getElementById('lbImg').src = CAT_IMGS[currentIdx];
}

document.addEventListener('keydown', function(e) {
  var lb = document.getElementById('catLightbox');
  if (!lb.classList.contains('open')) return;
  if (e.key === 'ArrowLeft') prevPhoto();
  if (e.key === 'ArrowRight') nextPhoto();
  if (e.key === 'Escape') { lb.classList.remove('open'); document.body.style.overflow = ''; }
});
</script>
