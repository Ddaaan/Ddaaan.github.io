---
widget: blank
headless: true
active: true
weight: 15
title: ""
---

<style>
  .dda-slider{position:relative;max-width:1200px;margin:0 auto;border-radius:12px;overflow:hidden}
  .dda-slider .slides{position:relative;height:360px}
  .dda-slider img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;opacity:0;transition:opacity .6s ease}
  .dda-slider img.active{opacity:1}
  .dda-slider .ctrl{position:absolute;top:50%;transform:translateY(-50%);background:rgba(0,0,0,.35);border:none;color:#fff;font-size:22px;padding:8px 12px;cursor:pointer;border-radius:8px}
  .dda-slider .prev{left:12px}
  .dda-slider .next{right:12px}
  .dda-slider .dots{position:absolute;left:0;right:0;bottom:10px;display:flex;gap:6px;justify-content:center}
  .dda-slider .dot{width:8px;height:8px;border-radius:50%;background:rgba(255,255,255,.5);cursor:pointer}
  .dda-slider .dot.active{background:#fff}
</style>

<div class="dda-slider" id="ddaSlider">
  <div class="slides">
    <img src="/uploads/slider1.jpg" alt="slide 1" class="active">
    <img src="/uploads/slider2.jpg" alt="slide 2">
    <img src="/uploads/slider3.jpg" alt="slide 3">
  </div>
  <button class="ctrl prev" aria-label="Previous">‹</button>
  <button class="ctrl next" aria-label="Next">›</button>
  <div class="dots"></div>
</div>

<script>
(function(){
  const root = document.getElementById('ddaSlider');
  if(!root) return;
  const imgs = Array.from(root.querySelectorAll('img'));
  const dotsWrap = root.querySelector('.dots');
  let i = 0, timer = null;
  const INTERVAL = 2000; //이미지 슬라이더 넘어가는 시간

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
