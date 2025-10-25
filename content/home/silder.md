---
widget: blank
headless: true
active: true
weight: 5000
title: ""
---

<style>
  /* 화면 양옆으로 꽉 차게 */
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

  /* 슬라이더 */
  .dda-slider{position:relative;width:100%;margin:0;border-radius:0;overflow:hidden}
  .dda-slider .slides{position:relative;height:clamp(160px, 18vw, 300px)}

  /* 각 슬라이드(이미지+오버레이+캡션를 하나로 묶어 페이드) */
  .dda-slider .slide{
    position:absolute; inset:0;
    opacity:0; transition:opacity .6s ease;
  }
  .dda-slider .slide.active{opacity:1}

  /* 이미지 */
  .dda-slider .slide img{
    position:absolute; inset:0; width:100%; height:100%;
    object-fit:cover;
  }

  /* 투명도 오버레이 */
  .dda-slider .overlay{
    position:absolute; inset:0; z-index:2;
    background:linear-gradient(180deg, rgba(0,0,0,.25), rgba(0,0,0,.45));
  }

  /* 텍스트 오버레이 */
  .dda-slider .caption{
    position:absolute; z-index:3;
    left:8%; bottom:14%;
    color:#fff; font-weight:700;
    text-shadow:0 2px 6px rgba(0,0,0,.4);
  }
  .dda-slider .caption h2{margin:0 0 .3rem; font-size:clamp(1rem, 2.2vw, 1.7rem)}
  .dda-slider .caption p{margin:0; font-size:clamp(.8rem, 1.2vw, 1rem); opacity:.9}

  /* 컨트롤/도트 */
  .dda-slider .ctrl{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,.35);border:none;color:#fff;font-size:22px;padding:8px 12px;cursor:pointer;border-radius:8px;z-index:4}
  .dda-slider .prev{left:12px}
  .dda-slider .next{right:12px}
  .dda-slider .dots{position:absolute;left:0;right:0;bottom:10px;display:flex;gap:6px;justify-content:center;z-index:4}
  .dda-slider .dot{width:8px;height:8px;border-radius:50%;background:rgba(255,255,255,.5);cursor:pointer}
  .dda-slider .dot.active{background:#fff}
</style>

<div class="dda-bleed">
  <div class="dda-slider" id="ddaSlider">
    <div class="slides">
      <!-- 1 -->
      <div class="slide active">
        <img src="/uploads/hero/ai-purple-01.jpg" alt="Beyond Code – Purple Abstract">
        <div class="overlay"></div>
        <div class="caption">
          <h2>코드와 상상력의 경계를 넘다</h2>
          <p>Beyond Code, Into Imagination</p>
        </div>
      </div>
      <!-- 2 -->
      <div class="slide">
        <img src="/uploads/hero/ai-network-edges-02.jpg" alt="Collaborative Intelligence">
        <div class="overlay"></div>
        <div class="caption">
          <h2>협력하는 지능</h2>
          <p>Collaborative Intelligence at the Edge</p>
        </div>
      </div>
      <!-- 3 -->
      <div class="slide">
        <img src="/uploads/hero/edge-cloud-bridge-03.jpg" alt="Edge–Cloud Bridge">
        <div class="overlay"></div>
        <div class="caption">
          <h2>엣지와 클라우드를 잇다</h2>
          <p>Bridging Edge & Cloud for AI</p>
        </div>
      </div>
      <!-- 4 -->
      <div class="slide">
        <img src="/uploads/hero/purple-city-dawn-04.jpg" alt="Create with Curiosity">
        <div class="overlay"></div>
        <div class="caption">
          <h2>호기심으로 만드는 미래</h2>
          <p>Created by Curiosity</p>
        </div>
      </div>
    </div>
    <button class="ctrl prev" aria-label="Previous">‹</button>
    <button class="ctrl next" aria-label="Next">›</button>
    <div class="dots"></div>
  </div>
</div>

<script>
(function(){
  const root = document.getElementById('ddaSlider');
  if(!root) return;

  const slides = Array.from(root.querySelectorAll('.slide'));
  const dotsWrap = root.querySelector('.dots');
  let i = 0, timer = null;
  const INTERVAL = 3000; // 🔄 자동 전환 간격(ms)

  // 도트 생성
  slides.forEach((_, idx)=>{
    const d = document.createElement('span');
    d.className = 'dot' + (idx===0 ? ' active' : '');
    d.addEventListener('click', ()=>go(idx, true));
    dotsWrap.appendChild(d);
  });
  const dots = Array.from(dotsWrap.querySelectorAll('.dot'));

  function show(idx){
    slides.forEach((el,k)=>el.classList.toggle('active', k===idx));
    dots.forEach((d,k)=>d.classList.toggle('active', k===idx));
  }
  function go(idx, manual=false){
    i = (idx + slides.length) % slides.length;
    show(i);
    if (manual) restart();
  }
  function next(){ go(i+1); }
  function prev(){ go(i-1); }

  root.querySelector('.next').addEventListener('click', ()=>go(i+1, true));
  root.querySelector('.prev').addEventListener('click', ()=>go(i-1, true));

  function start(){ stop(); timer = setInterval(next, INTERVAL); }
  function stop(){ if (timer) { clearInterval(timer); timer = null; } }
  function restart(){ start(); }

  // 호버 시 일시정지
  root.addEventListener('mouseenter', stop);
  root.addEventListener('mouseleave', start);

  show(0);
  start();
})();
</script>
