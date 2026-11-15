<!doctype html>
<html lang="uz">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>Ibrohim — portfolio</title>
<meta name="description" content="Ibrohim: karate, rus tili va maktabdagi yutuqlar.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Onest:wght@400;600&family=Unbounded:wght@500;800&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@900&text=%E7%A9%BA%E6%89%8B" rel="stylesheet">
<style>
:root{--ink:#0f1b2d;--ink2:#16263d;--gi:#f3f1ec;--red:#e03b2f;--gold:#d9b25f;--steel:#8c9ab0;--line:rgba(243,241,236,.16);color-scheme:dark}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;background:var(--ink);color:var(--gi);font:400 1.0625rem/1.65 Onest,system-ui,sans-serif}
a{color:inherit}
:focus-visible{outline:2px solid var(--gold);outline-offset:3px}

/* nav */
.nav{position:fixed;z-index:10;top:0;left:0;right:0;display:flex;justify-content:space-between;align-items:center;padding:calc(.9rem + env(safe-area-inset-top,0px)) clamp(1.25rem,5vw,4rem) .9rem;background:rgba(15,27,45,.72);backdrop-filter:blur(10px)}
.nav b{font:800 1rem Unbounded,sans-serif}
.nav ul{display:flex;gap:clamp(.8rem,2.5vw,2rem);list-style:none;margin:0;padding:0;font-size:.95rem}
.nav a{text-decoration:none;color:var(--steel)}
.nav a:hover{color:var(--gi)}

/* hero */
.hero{position:relative;height:100svh;min-height:560px;overflow:hidden}
#c{position:absolute;inset:0;width:100%;height:100%;touch-action:pan-y;cursor:grab}
#c:active{cursor:grabbing}
.hero-text{position:absolute;left:clamp(1.25rem,5vw,4rem);bottom:clamp(5rem,13vh,8rem);pointer-events:none;max-width:90%}
.say{margin:0 0 .6rem;color:var(--gold);font-weight:600}
h1{margin:0;font:800 clamp(3rem,12vw,9rem)/.9 Unbounded,sans-serif;letter-spacing:-.03em;display:flex;overflow:hidden;padding-bottom:.08em}
h1 span{display:inline-block;animation:drop .9s cubic-bezier(.2,.8,.2,1) both;animation-delay:calc(var(--i)*70ms + 200ms)}
@keyframes drop{from{transform:translateY(110%) rotate(8deg)}to{transform:none}}
.tag{margin:1.1rem 0 0;font-size:clamp(1.05rem,2.2vw,1.4rem);max-width:30ch}
.tools{position:absolute;right:clamp(1.25rem,5vw,4rem);bottom:clamp(1.5rem,4vh,2.5rem);display:flex;gap:.5rem;align-items:center}
.tools p{margin:0 .8rem 0 0;font-size:.85rem;color:var(--steel);text-align:right}
.tools button{width:2.6rem;height:2.6rem;border-radius:50%;border:1px solid var(--line);background:rgba(15,27,45,.6);color:var(--gi);font:600 1.1rem Onest,sans-serif;cursor:pointer}
.tools button:hover{border-color:var(--gold);color:var(--gold)}
.no3d .hero::after{content:"";position:absolute;right:12%;top:22%;width:min(40vw,360px);aspect-ratio:1;border-radius:50%;background:var(--red)}
@media(max-width:700px){.tools p{display:none}}

/* sections */
section{padding:clamp(4rem,10vw,8rem) clamp(1.25rem,5vw,4rem);border-top:1px solid var(--line)}
.wrap{max-width:1150px;margin:0 auto;display:grid;grid-template-columns:minmax(0,1fr) minmax(0,2fr);gap:clamp(1.5rem,5vw,4rem)}
@media(max-width:800px){.wrap{grid-template-columns:1fr}}
h2{margin:0;font:500 clamp(1.7rem,3.8vw,2.8rem)/1.1 Unbounded,sans-serif;letter-spacing:-.02em}
.lead{font-size:clamp(1.2rem,2.4vw,1.7rem);line-height:1.45;margin:0 0 2rem;max-width:34ch}
.body p{max-width:62ch;color:#cfd5de}

/* about facts */
.facts{list-style:none;margin:2.5rem 0 0;padding:0}
.facts li{display:grid;grid-template-columns:minmax(0,1fr) minmax(0,1.4fr);gap:1rem;align-items:baseline;padding:1.1rem 0;border-top:1px solid var(--line)}
.facts strong{font:500 clamp(1.1rem,2.2vw,1.5rem) Unbounded,sans-serif}
.facts span{color:#cfd5de}
@media(max-width:600px){.facts li{grid-template-columns:1fr;gap:.2rem}}

/* karate */
.certs{display:flex;gap:1rem;overflow-x:auto;scroll-snap-type:x mandatory;padding:.5rem 0 1rem;margin-top:2rem}
figure{flex:0 0 min(78vw,290px);margin:0;scroll-snap-align:start}
.frame{aspect-ratio:3/4;display:grid;place-items:center;overflow:hidden;border:1px solid rgba(217,178,95,.55);border-radius:2px;background:var(--ink2);cursor:zoom-in}
.frame img{width:100%;height:100%;object-fit:cover}
.empty .frame{cursor:default}
.empty img{display:none}
.kanji{display:none;font:900 6rem "Noto Serif JP",serif;color:var(--gold);opacity:.45}
.empty .kanji{display:block}
figcaption{margin-top:.6rem;font-size:.95rem;color:var(--steel)}

/* oshpazlik */
.cooks figure{flex-basis:min(86vw,420px)}
.cooks .frame{aspect-ratio:4/3}

/* russian */
.phrase{display:block;width:100%;text-align:left;background:none;border:0;border-top:1px solid var(--line);color:inherit;padding:1.2rem 0;font:inherit;cursor:pointer}
.phrase:last-child{border-bottom:1px solid var(--line)}
.ru{display:block;font:600 clamp(1.3rem,2.8vw,1.9rem)/1.25 Onest,sans-serif}
.uz{display:block;max-height:0;opacity:0;overflow:hidden;color:var(--gold);transition:max-height .35s,opacity .35s,margin .35s}
.phrase[aria-pressed="true"] .uz{max-height:4rem;opacity:1;margin-top:.5rem}
.phrase:hover .ru{color:var(--red)}
.note{color:var(--steel);font-size:.95rem;margin:1rem 0 0}

/* school */
.subjects{list-style:none;margin:2rem 0 0;padding:0;display:flex;flex-wrap:wrap;gap:.5rem 1.8rem}
.subjects li{font:500 clamp(1.05rem,2.2vw,1.5rem) Unbounded,sans-serif;border-bottom:2px solid transparent;transition:border-color .2s,color .2s}
.subjects li:hover{border-color:var(--red);color:var(--gold)}

/* contact */
.links a{display:block;font:800 clamp(1.8rem,5vw,3.6rem)/1.15 Unbounded,sans-serif;text-decoration:none;padding:.2rem 0;transition:color .2s,padding-left .2s}
.links a:hover{color:var(--red);padding-left:.6rem}
footer{padding:2rem clamp(1.25rem,5vw,4rem);border-top:1px solid var(--line);color:var(--steel);font-size:.9rem}

dialog{border:0;background:transparent;padding:0;max-width:92vw;max-height:92vh}
dialog::backdrop{background:rgba(5,10,18,.85)}
dialog img{display:block;max-width:92vw;max-height:90vh;border-radius:2px}

@media(prefers-reduced-motion:reduce){html{scroll-behavior:auto}h1 span{animation:none}*{transition:none!important}}
</style>
</head>
<body>

<nav class="nav" aria-label="Asosiy menyu">
  <b>Ibrohim</b>
  <ul>
    <li><a href="#haqida">Haqida</a></li>
    <li><a href="#karate">Karate</a></li>
    <li><a href="#oshpazlik">Oshpazlik</a></li>
    <li><a href="#rus">Rus tili</a></li>
    <li><a href="#maktab">Maktab</a></li>
    <li><a href="#aloqa">Aloqa</a></li>
  </ul>
</nav>

<header class="hero">
  <canvas id="c" tabindex="0" aria-label="3D model. Sichqoncha bilan sudrab aylantiring."></canvas>
  <div class="hero-text">
    <p class="say">Salom, men</p>
    <h1 aria-label="Ibrohim"><span style="--i:0">I</span><span style="--i:1">b</span><span style="--i:2">r</span><span style="--i:3">o</span><span style="--i:4">h</span><span style="--i:5">i</span><span style="--i:6">m</span></h1>
    <p class="tag">Karate, rus tili va maktabdagi yaxshi baholar.</p>
  </div>
  <div class="tools">
    <p>Sudrab aylantiring</p>
    <button id="zin" aria-label="Yaqinlashtirish">+</button>
    <button id="zout" aria-label="Uzoqlashtirish">−</button>
    <button id="zreset" aria-label="Boshlang‘ich holat">↺</button>
  </div>
</header>

<main>
<section id="haqida">
  <div class="wrap">
    <h2>Haqida</h2>
    <div class="body">
      <p class="lead">Ibrohim karate bilan shug‘ullanadi, rus tilini yaxshi biladi va maktabda barcha fanlardan yaxshi baho oladi.</p>
      <p>Bu sahifada uning asosiy yutuqlari jamlangan: karate sertifikatlari, rus tilidagi bilimi va maktabdagi natijalari.</p>
      <ul class="facts">
        <li><strong>Karate</strong><span>Sertifikatlar olgan</span></li>
        <li><strong>Oshpazlik</strong><span>Master-klasslardan 3 ta sharafnoma</span></li>
        <li><strong>Rus tili</strong><span>Yaxshi biladi</span></li>
        <li><strong>Maktab</strong><span>Barcha fanlardan yaxshi baholar</span></li>
      </ul>
    </div>
  </div>
</section>

<section id="karate">
  <div class="wrap">
    <h2>Karate</h2>
    <div class="body">
      <p class="lead">Karate intizom, sabr va o‘ziga ishonchni o‘rgatadi.</p>
      <p>Ibrohim karate bo‘yicha mashg‘ulotlarga qatnashgan va sertifikatlar olgan. Sertifikatni kattalashtirib ko‘rish uchun ustiga bosing.</p>
      <div class="certs" id="certs" tabindex="0" aria-label="Karate sertifikatlari"></div>
    </div>
  </div>
</section>

<section id="oshpazlik">
  <div class="wrap">
    <h2>Oshpazlik</h2>
    <div class="body">
      <p class="lead">Kichik oshpaz: master-klasslardan sharafnomalar.</p>
      <p>Ibrohim Aristorante school’dagi «Маленький повар» master-klasslarida qatnashib, uchta sharafnoma olgan. Kattalashtirish uchun rasmga bosing.</p>
      <div class="certs cooks" tabindex="0" aria-label="Oshpazlik sharafnomalari"><figure><div class="frame"><img src="img/povar-1.jpg" alt="«Маленький повар» sharafnomasi: Pitsa tayyorlash master-klassi" loading="lazy"></div><figcaption>Pitsa tayyorlash master-klassi</figcaption></figure><figure><div class="frame"><img src="img/povar-2.jpg" alt="«Маленький повар» sharafnomasi: Desert tayyorlash master-klassi" loading="lazy"></div><figcaption>Desert tayyorlash master-klassi</figcaption></figure><figure><div class="frame"><img src="img/povar-3.jpg" alt="«Маленький повар» sharafnomasi: Master-klass sharafnomasi" loading="lazy"></div><figcaption>Master-klass sharafnomasi</figcaption></figure></div>
    </div>
  </div>
</section>

<section id="rus">
  <div class="wrap">
    <h2>Rus tili</h2>
    <div class="body">
      <p class="lead">Ibrohim rus tilida erkin gaplashadi.</p>
      <div id="phrases"></div>
      <p class="note">Jumlani bosing — o‘zbekcha tarjimasi chiqadi.</p>
    </div>
  </div>
</section>

<section id="maktab">
  <div class="wrap">
    <h2>Maktab</h2>
    <div class="body">
      <p class="lead">Hamma fanlardan yaxshi baholar.</p>
      <p>Ibrohim maktabda har bir fanga e’tibor bilan yondashadi va barcha fanlar bo‘yicha yaxshi natijalarga erishgan.</p>
      <ul class="subjects">
        <li>Matematika</li><li>Ona tili</li><li>Rus tili</li><li>Ingliz tili</li><li>Fizika</li><li>Kimyo</li><li>Biologiya</li><li>Tarix</li><li>Geografiya</li><li>Informatika</li><li>Jismoniy tarbiya</li>
      </ul>
    </div>
  </div>
</section>

<section id="aloqa">
  <div class="wrap">
    <h2>Aloqa</h2>
    <div class="links">
      <a href="#" id="tg">Telegram</a>
      <a href="#" id="ig">Instagram</a>
      <a href="#" id="gh">GitHub</a>
    </div>
  </div>
</section>
</main>

<footer>© <span id="y"></span> Ibrohim</footer>

<dialog id="lb"><img alt="Sertifikat"></dialog>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
/* ===== Sahifa mazmuni ===== */
document.getElementById('y').textContent=new Date().getFullYear();

// Sertifikatlar: rasmlarni img/karate-1.jpg, img/karate-2.jpg ... deb saqlang
const CERT_COUNT=4;
const certs=document.getElementById('certs'), lb=document.getElementById('lb');
for(let i=1;i<=CERT_COUNT;i++){
  const f=document.createElement('figure');
  f.innerHTML='<div class="frame"><img src="img/karate-'+i+'.jpg" alt="Karate sertifikati '+i+'" loading="lazy"><span class="kanji" aria-hidden="true">空手</span></div><figcaption>Sertifikat '+i+'</figcaption>';
  const img=f.querySelector('img');
  img.addEventListener('error',()=>f.classList.add('empty'));
  f.querySelector('.frame').addEventListener('click',()=>{if(f.classList.contains('empty'))return;lb.querySelector('img').src=img.src;lb.showModal();});
  certs.appendChild(f);
}
lb.addEventListener('click',()=>lb.close());
document.querySelectorAll('.cooks .frame').forEach(fr=>fr.addEventListener('click',()=>{const im=fr.querySelector('img');lb.querySelector('img').src=im.currentSrc||im.src;lb.showModal();}));

const phrases=[
  ['Привет! Меня зовут Иброхим.','Salom! Mening ismim Ibrohim.'],
  ['Я хорошо говорю по-русски.','Men ruscha yaxshi gapiraman.'],
  ['Я занимаюсь каратэ.','Men karate bilan shug‘ullanaman.'],
  ['Я хорошо учусь в школе.','Men maktabda yaxshi o‘qiyman.'],
  ['Спасибо за внимание!','E’tiboringiz uchun rahmat!']
];
const box=document.getElementById('phrases');
phrases.forEach(([ru,uz])=>{
  const b=document.createElement('button');
  b.className='phrase';b.setAttribute('aria-pressed','false');
  b.innerHTML='<span class="ru" lang="ru">'+ru+'</span><span class="uz">'+uz+'</span>';
  b.addEventListener('click',()=>b.setAttribute('aria-pressed',b.getAttribute('aria-pressed')==='true'?'false':'true'));
  box.appendChild(b);
});

/* Aloqa havolalarini o‘zingiznikiga almashtiring */
document.getElementById('tg').href='https://t.me/';
document.getElementById('ig').href='https://instagram.com/';
document.getElementById('gh').href='https://github.com/';

/* ===== 3D model ===== */
(function(){
  const hero=document.querySelector('.hero'), canvas=document.getElementById('c');
  const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  let renderer;
  try{ if(!window.THREE) throw 0; renderer=new THREE.WebGLRenderer({canvas,antialias:true,alpha:true}); }
  catch(e){ document.body.classList.add('no3d'); return; }
  renderer.setPixelRatio(Math.min(devicePixelRatio,2));

  const scene=new THREE.Scene();
  const camera=new THREE.PerspectiveCamera(45,1,.1,100);
  scene.add(new THREE.AmbientLight(0xffffff,.55));
  const key=new THREE.DirectionalLight(0xffffff,1.1); key.position.set(3,4,5); scene.add(key);
  const redL=new THREE.PointLight(0xe03b2f,2,20); redL.position.set(-4,-2,3); scene.add(redL);
  const goldL=new THREE.PointLight(0xd9b25f,1.4,20); goldL.position.set(4,-3,-1); scene.add(goldL);

  const stage=new THREE.Group(); scene.add(stage);

  // Qizil quyosh disk (yapon bayrog‘i / karate ruhi)
  const sun=new THREE.Mesh(new THREE.CircleGeometry(2.7,80),new THREE.MeshBasicMaterial({color:0xe03b2f}));
  sun.position.z=-2.5; stage.add(sun);

  // Asosiy model: kamar tuguniga o‘xshash tugun
  const pivot=new THREE.Group(); stage.add(pivot);
  const knot=new THREE.Mesh(
    new THREE.TorusKnotGeometry(1.15,.36,240,40,2,3),
    new THREE.MeshStandardMaterial({color:0xf3f1ec,metalness:.3,roughness:.22})
  );
  pivot.add(knot);

  // Aylanuvchi oltin halqalar
  const spinners=[];
  [[2.2,.5,0,.006],[2.75,-.7,.9,-.004]].forEach(([r,tx,ty,sp])=>{
    const tilt=new THREE.Group(); tilt.rotation.set(tx,ty,0);
    const spin=new THREE.Group(); tilt.add(spin);
    spin.add(new THREE.Mesh(new THREE.TorusGeometry(r,.012,12,220),new THREE.MeshBasicMaterial({color:0xd9b25f})));
    for(let k=0;k<8;k++){
      const a=k/8*Math.PI*2;
      const gem=new THREE.Mesh(new THREE.OctahedronGeometry(.1),new THREE.MeshStandardMaterial({color:0xd9b25f,metalness:.7,roughness:.25}));
      gem.position.set(Math.cos(a)*r,Math.sin(a)*r,0); spin.add(gem);
    }
    pivot.add(tilt); spinners.push([spin,sp]);
  });

  // Yulduz changi
  const N=600, pos=new Float32Array(N*3);
  for(let i=0;i<N;i++){
    const r=5+Math.random()*7,a=Math.random()*6.283,b=Math.acos(2*Math.random()-1);
    pos[i*3]=r*Math.sin(b)*Math.cos(a); pos[i*3+1]=r*Math.sin(b)*Math.sin(a); pos[i*3+2]=r*Math.cos(b)-4;
  }
  const sg=new THREE.BufferGeometry(); sg.setAttribute('position',new THREE.BufferAttribute(pos,3));
  const stars=new THREE.Points(sg,new THREE.PointsMaterial({color:0xd9b25f,size:.03,transparent:true,opacity:.7}));
  scene.add(stars);

  // Zoom va o‘lcham
  let baseZ=7, zoomOff=0, baseY=0;
  const clamp=(v,a,b)=>Math.max(a,Math.min(b,v));
  const targetZ=()=>clamp(baseZ+zoomOff,4,13);
  function resize(){
    const w=hero.clientWidth,h=hero.clientHeight,asp=w/h;
    renderer.setSize(w,h,false); camera.aspect=asp; camera.updateProjectionMatrix();
    const wide=asp>1.15;
    stage.position.x=wide?1.9:0; baseY=wide?0:1.2; baseZ=asp<.8?9.5:7;
  }
  resize(); camera.position.z=targetZ();
  addEventListener('resize',resize);

  // Sichqoncha / sensor bilan boshqarish
  const pts=new Map(); let drag=false,lx=0,ly=0,vx=0,vy=0,pinch=0;
  canvas.addEventListener('pointerdown',e=>{
    canvas.setPointerCapture(e.pointerId); pts.set(e.pointerId,{x:e.clientX,y:e.clientY});
    drag=true; lx=e.clientX; ly=e.clientY; vx=vy=0;
    if(pts.size===2){const [a,b]=[...pts.values()];pinch=Math.hypot(a.x-b.x,a.y-b.y);}
  });
  canvas.addEventListener('pointermove',e=>{
    if(!pts.has(e.pointerId))return;
    pts.set(e.pointerId,{x:e.clientX,y:e.clientY});
    if(pts.size===2){
      const [a,b]=[...pts.values()],d=Math.hypot(a.x-b.x,a.y-b.y);
      zoomOff=clamp(zoomOff-(d-pinch)*.02,-3,6); pinch=d; return;
    }
    const dx=e.clientX-lx, dy=e.clientY-ly; lx=e.clientX; ly=e.clientY;
    vy=dx*.01; pivot.rotation.y+=vy;
    if(e.pointerType==='mouse'){vx=dy*.01; pivot.rotation.x=clamp(pivot.rotation.x+vx,-1.3,1.3);}
  });
  const end=e=>{pts.delete(e.pointerId); if(!pts.size)drag=false;};
  canvas.addEventListener('pointerup',end); canvas.addEventListener('pointercancel',end);
  canvas.addEventListener('wheel',e=>{ if(!(e.ctrlKey||e.metaKey))return; e.preventDefault(); zoomOff=clamp(zoomOff+e.deltaY*.004,-3,6); },{passive:false});
  canvas.addEventListener('keydown',e=>{
    if(e.key==='ArrowLeft')vy=-.05; if(e.key==='ArrowRight')vy=.05;
    if(e.key==='ArrowUp')pivot.rotation.x=clamp(pivot.rotation.x-.15,-1.3,1.3);
    if(e.key==='ArrowDown')pivot.rotation.x=clamp(pivot.rotation.x+.15,-1.3,1.3);
  });
  document.getElementById('zin').onclick=()=>zoomOff=clamp(zoomOff-1.2,-3,6);
  document.getElementById('zout').onclick=()=>zoomOff=clamp(zoomOff+1.2,-3,6);
  document.getElementById('zreset').onclick=()=>{zoomOff=0;vx=vy=0;pivot.rotation.set(.15,0,0);};
  pivot.rotation.x=.15;

  // Ekranda ko‘rinmasa chizmaymiz
  let visible=true; new IntersectionObserver(([en])=>visible=en.isIntersecting).observe(hero);
  const clock=new THREE.Clock();
  (function frame(){
    requestAnimationFrame(frame); if(!visible)return;
    const t=clock.getElapsedTime();
    if(!drag){
      pivot.rotation.y+=vy; vy*=.94;
      if(!reduce && Math.abs(vy)<.003) pivot.rotation.y+=.004;
      pivot.rotation.x+=(.15-pivot.rotation.x)*.01;
    }
    if(!reduce){
      stage.position.y=baseY+Math.sin(t*.8)*.12;
      spinners.forEach(([s,sp])=>s.rotation.z+=sp);
      stars.rotation.y=t*.01;
    } else stage.position.y=baseY;
    camera.position.z+=(targetZ()-camera.position.z)*.08;
    renderer.render(scene,camera);
  })();
})();
</script>
</body>
</html>
