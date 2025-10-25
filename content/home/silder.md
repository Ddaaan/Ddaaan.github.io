---
widget: blank
headless: true
active: true
weight: 5000
title: ""
---

<style>
  /* 화면 양옆으로 꽉 차는 래퍼 */
  .dda-bleed{
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    width: 100vw;
    background: transparent; 
    padding: 0;  
    overflow: hidden;
  }

  /* ============================
     슬라이더 (낮은 높이 버전)
     ============================ */
  .dda-slider {
    position: relative;
    width: 100%;
    margin: 0;
    border-radius: 0;
    overflow: hidden;
  }
  .dda-slider .slides {
    position: relative;
    height: clamp(160px, 18vw, 300px);
  }

  /* 이미지 페이드 전환 */
  .dda-slider img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0;
    transition: opacity 0.6s ease;
  }
  .dda-slider img.active { opacity: 1; }

  /* 컨트롤 버튼 */
  .dda-slider .ctrl {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(0, 0, 0, 0.35);
    border: none;
    color: #fff;
    font-size: 22px;
    padding: 8px 12px;
    cursor: pointer;
    border-radius: 8px;
    z-index: 4;
    line-height: 1;
  }
  .dda-slider .prev { left: 12px; }
  .dda-slider .next { right: 12px; }

  /* 도트 네비게이션 */
  .dda-slider .dots {
    position: absolute;
    left: 0; right: 0; bottom: 10px;
    display: flex; gap: 6px;
    justify-content: center;
    z-index: 4;
  }
  .dda-slider .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.5);
    cursor: pointer;
  }
  .dda-slider .dot.active { background: #fff; }

  /* 투명 오버레이 */
  .dda-slider .overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(0,0,0,0.25), rgba(0,0,0,0.45));
    z-index: 2;
    opacity: 0;
    transition: opacity 0.6s ease;
  }
  .dda-slider .overlay.active { opacity: 1; }

  /* 텍스트 오버레이 */
  .dda-slider .caption {
    position: absolute;
    z-index: 3;
    bottom: 14%;
    left: 8%;
    color: #fff;
    text-shadow: 0 2px 6px rgba(0,0,0,.4);
    font-weight: 700;
  }
  .dda-slider .caption h2 {
    font-size: clamp(1rem, 2.2vw, 1.7rem);
    margin: 0 0 .3rem;
  }
  .dda-slider .caption p {
    font-size: clamp(.8rem, 1.2vw, 1rem);
    margin: 0; opacity: .9;
  }
</style>

<div id="ddaSlider" class="dda-slider dda-bleed">
  <!-- 컨트롤 -->
  <button class="ctrl prev" aria-label="Previous slide" type="button">&#10094;</button>
  <button class="ctrl next" aria-label="Next slide" type="button">&#10095;</button>

  <div class="slides">
    <!-- 1. 보라빛 감성: 코드와 상상력 -->
    <div class="slide">
      <img src="/uploads/hero/ai-purple-01.jpg" alt="Beyond Code – Purple Abstract">
      <div class="overlay"></div>
      <div class="caption">
        <h2>코드와 상상력의 경계를 넘다</h2>
        <p>Beyond Code, Into Imagination</p>
      </div>
    </div>

    <!-- 2. AI의 세계: 협력 지능 -->
    <div class="slide">
      <img src="/uploads/hero/ai-network-edges-02.jpg" alt="Collaborative Intelligence across devices">
      <div class="overlay"></div>
      <div class="caption">
        <h2>협력하는 지능</h2>
        <p>Collaborative Intelligence at the Edge</p>
      </div>
    </div>

    <!-- 3. 오프로딩/엣지-클라우드 -->
    <div class="slide">
      <img src="/uploads/hero/edge-cloud-bridge-03.jpg" alt="Edge–Cloud Offloading Bridge">
      <div class="overlay"></div>
      <div class="caption">
        <h2>엣지와 클라우드를 잇다</h2>
        <p>Bridging Edge & Cloud for AI</p>
      </div>
    </div>

    <!-- 4. 개발자 브랜드: 호기심으로 만든다 -->
    <div class="slide">
      <img src="/uploads/hero/purple-city-dawn-04.jpg" alt="Create with Curiosity">
      <div class="overlay"></div>
      <div class="caption">
        <h2>호기심으로 만드는 미래</h2>
        <p>Created by Curiosity</p>
      </div>
    </div>
  </div>

  <!-- 도트 네비게이션 -->
  <div class="dots" role="tablist" aria-label="Slide navigation"></div>
</div>

<script>
(function(){
  const root = document.getElementById('ddaSlider');
  if (!root) return;

  const slideEls = Array.from(root.querySelectorAll('.slide'));
  const imgEls   = slideEls.map(s => s.querySelector('img'));
  const ovlEls   = slideEls.map(s => s.querySelector('.overlay'));
  const dotsWrap = root.querySelector('.dots');
  const btnPrev  = root.querySelector('.prev');
  const btnNext  = root.querySelector('.next');

  let i = 0, timer = null;
  const INTERVAL = 3000;

  // 도트 생성
  slideEls.forEach((_, idx) => {
    const d = document.createElement('button');
    d.className = 'dot' + (idx === 0 ? ' active' : '');
    d.type = 'button';
    d.setAttribute('aria-label', `Go to slide ${idx+1}`);
    d.addEventListener('click', () => go(idx, true));
    dotsWrap.appendChild(d);
  });
  const dotEls = Array.from(dotsWrap.querySelectorAll('.dot'));

  function show(idx){
    imgEls.forEach((im,k) => im.classList.toggle('active', k === idx));
    ovlEls.forEach((ov,k) => ov.classList.toggle('active', k === idx));
    dotEls.forEach((d,k) => d.classList.toggle('active', k === idx));
  }

  function go(idx, manual=false){
    i = (idx + imgEls.length) % imgEls.length;
    show(i);
    if (manual) restart();
  }

  function next(){ go(i + 1); }
  function prev(){ go(i - 1); }

  function start(){ stop(); timer = setInterval(next, INTERVAL); }
  function stop(){ if (timer) { clearInterval(timer); timer = null; } }
  function restart(){ start(); }

  // 이벤트 바인딩
  btnNext.addEventListener('click', () => go(i + 1, true));
  btnPrev.addEventListener('click', () => go(i - 1, true));
  root.addEventListener('mouseenter', stop);
  root.addEventListener('mouseleave', start);

  // 키보드 접근성
  root.addEventListener('keydown', (e) => {
    if (e.key === 'ArrowRight') { go(i + 1, true); }
    if (e.key === 'ArrowLeft')  { go(i - 1, true); }
  });
  root.tabIndex = 0;

  // 탭이 다른 곳으로 전환될 때 자동재생 일시정지
  document.addEventListener('visibilitychange', () => {
    if (document.hidden) stop(); else start();
  });

  // 첫 프레임 렌더
  show(0);
  start();
})();
</script>
