---
widget: blank
headless: true
active: true
weight: 5000
title: ""
---

<style>
  /* 화면 양옆으로 꽉 차게 만드는 래퍼(컨테이너 여백 무시) */
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
  /* 높이 ↑ : 필요시 수치만 더 키워도 됨 */
  .dda-slider .slides{position:relative;height:clamp(160px, 18vw, 300px);} 
  .dda-slider img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;opacity:0;transition:opacity .6s ease}
  .dda-slider img.active{opacity:1}
  .dda-slider .ctrl{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,.35);border:none;color:#fff;font-size:22px;padding:8px 12px;cursor:pointer;border-radius:8px}
  .dda-slider .prev{left:12px}
  .dda-slider .next{right:12px}
  .dda-slider .dots{position:absolute;left:0;right:0;bottom:10px;display:flex;gap:6px;justify-content:center}
  .dda-slider .dot{width:8px;height:8px;border-radius:50%;background:rgba(255,255,255,.5);cursor:pointer}
  .dda-slider .dot.active{background:#fff}
</style>

<div class="dda-bleed">
  <div class="dda-slider" id="ddaSlider">
    <div class="slides">
      <!-- 1 -->
      <div class="slide">
        <img src="/uploads/hero/ai-purple-01.jpg" alt="Beyond Code – Purple Abstract" class="active">
        <div class="overlay active"></div>
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
  const imgs = Array.from(root.querySelectorAll('img'));
  const dotsWrap = root.querySelector('.dots');
  let i = 0, timer = null;
  const INTERVAL = 2000;

  imgs.forEach((_, idx)=>{
    const d = document.createElement('span');
    d.className = 'dot' + (idx===0 ? ' active' : '');
    d.addEventListener('click', ()=>go(idx, true));
    dotsWrap.appendChild(d);
  });
  const dots = Array.from(dotsWrap.querySelectorAll('.dot'));

  function show(idx){
    imgs.forEach((im,k)=>im.classList.toggle('active', k===idx));
    dots.forEach((d,k)=>d.classList.toggle('active', k===idx));
  }
  function go(idx, manual=false){
    i = (idx + imgs.length) % imgs.length;
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

  root.addEventListener('mouseenter', stop);
  root.addEventListener('mouseleave', start);

  show(0);
  start();
})();
</script>