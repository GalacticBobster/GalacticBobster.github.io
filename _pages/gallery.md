---
layout: archive
title: "Gallery"
permalink: /gallery/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}


<div class="collage-wrap">
  <div class="collage-grid">
    <!-- ROW 1 -->
    <div class="photo-item tall"
         style="--r:1;--c:1;--rspan:2;--cspan:2"
         data-img="/images/highlights/cop28.jpeg"
         data-title="UN Climate Conference COP28"
         data-location="Dubai, UAE"
         data-date="December 2023"
         data-desc="At UN Climate Change Conference COP 28, representing University of Michigan">
      <div class="photo-inner">
        <img src="/images/highlights/cop28.jpg" alt="COP28 Dubai">
        <div class="photo-hover">
          <span class="hover-title">COP28, Dubai</span>
          <span class="hover-sub">Dec 2023 · UAE</span>
        </div>
      </div>
    </div>
 
    <div class="photo-item"
         style="--r:1;--c:3;--rspan:1;--cspan:2"
         data-img="/images/highlights/jpl.jpeg"
         data-title="NASA Jet Propulsion Laboratory"
         data-location="Pasadena, California"
         data-date="Summer 2023"
         data-desc="Spent a Summer Working at NASA Jet Propulsion Laboratory">
      <div class="photo-inner">
        <img src="/images/highlights/jpl.jpg" alt="JPL Fellowship">
        <div class="photo-hover">
          <span class="hover-title">NASA JPL Fellowship</span>
          <span class="hover-sub">Summer 2023 · Pasadena</span>
        </div>
      </div>
    </div>
 
    <div class="photo-item"
         style="--r:1;--c:5;--rspan:1;--cspan:2"
         data-img="/images/highlights/juno_award.jpg"
         data-title="NASA Group Achievement Award"
         data-location="Washington D.C."
         data-date="2026"
         data-desc="Recognized with the NASA Group Achievement Award as part of the Juno Radio Occultation Team for contributions to Jupiter science.">
      <div class="photo-inner">
        <img src="/images/highlights/juno_award.jpg" alt="NASA Award">
        <div class="photo-hover">
          <span class="hover-title">NASA Group Award</span>
          <span class="hover-sub">2026 · Juno Team</span>
        </div>
      </div>
    </div>
 
    <!-- ROW 2 -->
    <div class="photo-item"
         style="--r:2;--c:3;--rspan:1;--cspan:1"
         data-img="/images/highlights/niser.jpeg"
         data-title="NISER"
         data-location="Bhubaneshwar"
         data-date="2024–2026"
         data-desc="Invited Seminar at School of Earth and Planetary Sciences, NISER Bhubaneshwar.">
      <div class="photo-inner">
        <img src="/images/highlights/fishermen.jpg" alt="Fisheries project">
        <div class="photo-hover">
          <span class="hover-title">NISER Bhubaneshwar</span>
          <span class="hover-sub">Jatni, India</span>
        </div>
      </div>
    </div>
 
   
    

 
 
  </div><!-- .collage-grid -->
</div><!-- .collage-wrap -->
<!-- LIGHTBOX -->
<div class="lb-overlay" id="lb-overlay" role="dialog" aria-modal="true" aria-label="Photo detail">
  <button class="lb-close" id="lb-close" aria-label="Close">&#x2715;</button>
  <div class="lb-card">
    <div class="lb-img-wrap">
      <img id="lb-img" src="" alt="">
    </div>
    <div class="lb-info">
      <div class="lb-meta">
        <span class="lb-location" id="lb-location"></span>
        <span class="lb-date" id="lb-date"></span>
      </div>
      <h2 class="lb-title" id="lb-title"></h2>
      <p class="lb-desc" id="lb-desc"></p>
    </div>
  </div>
</div>
<style>
/* ── Variables ── */
.collage-wrap {
  --gap: 6px;
  --radius: 4px;
  --cell: 160px;
  margin: 2rem 0 3rem;
}
/* ── Grid ── */
.collage-grid {
  display: grid;
  grid-template-columns: repeat(6, var(--cell));
  grid-auto-rows: var(--cell);
  gap: var(--gap);
}
.photo-item {
  grid-row: var(--r) / span var(--rspan, 1);
  grid-column: var(--c) / span var(--cspan, 1);
  border-radius: var(--radius);
  overflow: hidden;
  cursor: pointer;
  position: relative;
}
.photo-inner {
  width: 100%; height: 100%;
  position: relative;
}
.photo-inner img {
  width: 100%; height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.45s cubic-bezier(0.25,0.46,0.45,0.94),
              filter 0.3s ease;
  filter: saturate(0.85);
}
.photo-item:hover .photo-inner img {
  transform: scale(1.06);
  filter: saturate(1.1);
}
/* Hover label */
.photo-hover {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.72) 0%, transparent 55%);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 12px;
  opacity: 0;
  transition: opacity 0.25s ease;
}
.photo-item:hover .photo-hover { opacity: 1; }
.hover-title {
  color: #fff;
  font-size: 0.78rem;
  font-weight: 600;
  font-family: inherit;
  line-height: 1.2;
}
.hover-sub {
  color: rgba(255,255,255,0.7);
  font-size: 0.65rem;
  margin-top: 2px;
  font-family: monospace;
  letter-spacing: 0.04em;
}
/* Placeholder when no image */
.photo-inner img[src="/images/highlights/cop28.jpg"]:not([complete]),
.photo-inner img {
  background: #e8e4dc;
}
/* ── Lightbox ── */
.lb-overlay {
  position: fixed;
  inset: 0;
  background: rgba(10,9,8,0.88);
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1.5rem;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.25s ease;
  backdrop-filter: blur(4px);
}
.lb-overlay.active {
  opacity: 1;
  pointer-events: all;
}
.lb-close {
  position: absolute;
  top: 1.25rem; right: 1.25rem;
  background: rgba(255,255,255,0.12);
  border: none;
  color: white;
  font-size: 1.1rem;
  width: 36px; height: 36px;
  border-radius: 50%;
  cursor: pointer;
  display: flex; align-items: center; justify-content: center;
  transition: background 0.2s;
}
.lb-close:hover { background: rgba(255,255,255,0.25); }
.lb-card {
  background: #faf7f2;
  border-radius: 6px;
  overflow: hidden;
  display: flex;
  max-width: 820px;
  width: 100%;
  max-height: 90vh;
  box-shadow: 0 32px 80px rgba(0,0,0,0.5);
  transform: translateY(16px) scale(0.97);
  transition: transform 0.3s cubic-bezier(0.34,1.56,0.64,1);
}
.lb-overlay.active .lb-card {
  transform: translateY(0) scale(1);
}
.lb-img-wrap {
  flex: 0 0 55%;
  min-height: 360px;
  background: #e0dbd0;
  overflow: hidden;
}
.lb-img-wrap img {
  width: 100%; height: 100%;
  object-fit: cover;
  display: block;
}
.lb-info {
  flex: 1;
  padding: 2rem 1.75rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  overflow-y: auto;
}
.lb-meta {
  display: flex;
  flex-direction: column;
  gap: 2px;
  margin-bottom: 0.75rem;
}
.lb-location {
  font-family: monospace;
  font-size: 0.65rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #c8410a;
  font-weight: 600;
}
.lb-date {
  font-family: monospace;
  font-size: 0.62rem;
  letter-spacing: 0.1em;
  color: #7a7268;
  text-transform: uppercase;
}
.lb-title {
  font-size: 1.2rem;
  font-weight: 700;
  line-height: 1.25;
  color: #0f0e0c;
  margin: 0 0 0.85rem;
}
.lb-desc {
  font-size: 0.9rem;
  line-height: 1.7;
  color: #3a3730;
  margin: 0;
}
/* ── Responsive ── */
@media (max-width: 1060px) {
  .collage-wrap { --cell: 130px; }
}
@media (max-width: 860px) {
  .collage-wrap { --cell: 105px; --gap: 4px; }
  .hover-title { font-size: 0.65rem; }
  .hover-sub { display: none; }
}
@media (max-width: 700px) {
  .collage-grid {
    grid-template-columns: repeat(2, 1fr);
    grid-auto-rows: 140px;
  }
  .photo-item {
    grid-row: auto !important;
    grid-column: auto !important;
  }
  .lb-card { flex-direction: column; }
  .lb-img-wrap { flex: 0 0 200px; min-height: 200px; }
}
</style>
 
<script>
(function() {
  const overlay = document.getElementById('lb-overlay');
  const closeBtn = document.getElementById('lb-close');
  function openLightbox(item) {
    document.getElementById('lb-img').src      = item.dataset.img      || '';
    document.getElementById('lb-img').alt      = item.dataset.title    || '';
    document.getElementById('lb-title').textContent    = item.dataset.title    || '';
    document.getElementById('lb-location').textContent = item.dataset.location || '';
    document.getElementById('lb-date').textContent     = item.dataset.date     || '';
    document.getElementById('lb-desc').textContent     = item.dataset.desc     || '';
    overlay.classList.add('active');
    document.body.style.overflow = 'hidden';
    closeBtn.focus();
  }
  function closeLightbox() {
    overlay.classList.remove('active');
    document.body.style.overflow = '';
  }
  document.querySelectorAll('.photo-item').forEach(function(item) {
    item.addEventListener('click', function() { openLightbox(item); });
    item.addEventListener('keydown', function(e) {
      if (e.key === 'Enter' || e.key === ' ') openLightbox(item);
    });
    item.setAttribute('tabindex', '0');
    item.setAttribute('role', 'button');
  });
  closeBtn.addEventListener('click', closeLightbox);
  overlay.addEventListener('click', function(e) {
    if (e.target === overlay) closeLightbox();
  });
  document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape') closeLightbox();
  });
})();
</script>

