<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>كل عام وأنتِ بألف خير يا رَوْنَد 🌊</title>

<!-- ============================================================
     خط عربي أنيق من Google Fonts
============================================================ -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;900&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">

<style>
  /* ============================================================
     المتغيرات العامة (يمكنك تعديل الألوان من هنا بسهولة)
  ============================================================ */
  :root{
    --navy-deep:   #041224;
    --navy:        #0a2540;
    --royal-blue:  #1447a8;
    --cyan:        #35c9dc;
    --cyan-light:  #9df3ff;
    --glass-bg:    rgba(255,255,255,0.08);
    --glass-border:rgba(255,255,255,0.25);
    --text-light:  #eaf6ff;
  }

  *{ box-sizing:border-box; margin:0; padding:0; }

  html,body{
    height:100%;
    overflow-x:hidden;
    background: radial-gradient(ellipse at top, var(--navy) 0%, var(--navy-deep) 55%, #010810 100%);
    font-family:'Tajawal', sans-serif;
    color:var(--text-light);
  }

  /* ============================================================
     مشهد المحيط الكامل (خلفية + فقاعات + دلفين)
  ============================================================ */
  .ocean-scene{
    position:fixed;
    inset:0;
    z-index:0;
    overflow:hidden;
    pointer-events:none;
  }

  /* طبقات الموج SVG */
  .wave-layer{
    position:absolute;
    bottom:0;
    left:0;
    width:200%;
    height:45vh;
    background-repeat:repeat-x;
    background-size:50% 100%;
  }
  .wave1{ animation:waveMove 18s linear infinite; opacity:0.55; }
  .wave2{ animation:waveMove 12s linear infinite reverse; opacity:0.4; bottom:-10px;}
  .wave3{ animation:waveMove 25s linear infinite; opacity:0.9; bottom:-25px;}

  @keyframes waveMove{
    from{ transform:translateX(0); }
    to{ transform:translateX(-50%); }
  }

  /* فقاعات مائية تطفو للأعلى */
  .bubble{
    position:absolute;
    bottom:-10%;
    border-radius:50%;
    background:radial-gradient(circle at 30% 30%, rgba(255,255,255,0.55), rgba(157,243,255,0.08) 70%);
    border:1px solid rgba(255,255,255,0.25);
    box-shadow:0 0 12px rgba(157,243,255,0.25) inset;
    animation:floatUp linear infinite;
  }
  @keyframes floatUp{
    0%{ transform:translateY(0) translateX(0) scale(0.8); opacity:0; }
    10%{ opacity:0.8; }
    90%{ opacity:0.6; }
    100%{ transform:translateY(-110vh) translateX(var(--drift,20px)) scale(1.1); opacity:0; }
  }

  /* ============================================================
     المحتوى الرئيسي
  ============================================================ */
  .stage{
    position:relative;
    z-index:2;
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    padding:24px;
  }

  .glass-card{
    position:relative;
    width:100%;
    max-width:560px;
    background:var(--glass-bg);
    border:1px solid var(--glass-border);
    border-radius:28px;
    backdrop-filter:blur(18px) saturate(140%);
    -webkit-backdrop-filter:blur(18px) saturate(140%);
    box-shadow:0 8px 40px rgba(0,0,0,0.45), inset 0 1px 0 rgba(255,255,255,0.15);
    padding:44px 32px;
    text-align:center;
    overflow:hidden;
  }

  .glass-card::before{
    content:"";
    position:absolute;
    inset:0;
    background:linear-gradient(135deg, rgba(157,243,255,0.12), transparent 60%);
    pointer-events:none;
  }

  .title-name{
    font-family:'Cairo', sans-serif;
    font-weight:900;
    font-size:clamp(28px, 6vw, 42px);
    background:linear-gradient(90deg, var(--cyan-light), var(--cyan), #cfeaff);
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
    margin-bottom:6px;
    letter-spacing:1px;
  }

  .subtitle{
    font-size:15px;
    color:rgba(234,246,255,0.75);
    margin-bottom:28px;
    letter-spacing:0.5px;
  }

  /* ============================================================
     العد التنازلي - فقاعات دائرية
  ============================================================ */
  #countdown-wrap{
    display:flex;
    justify-content:center;
    gap:14px;
    flex-wrap:wrap;
    transition:opacity 1s ease, transform 1s ease;
  }
  #countdown-wrap.hide{
    opacity:0;
    transform:scale(0.8);
    pointer-events:none;
    height:0;
    overflow:hidden;
    margin:0;
  }

  .time-bubble{
    width:78px;
    height:78px;
    border-radius:50%;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    background:radial-gradient(circle at 35% 30%, rgba(255,255,255,0.25), rgba(20,71,168,0.35) 70%);
    border:1px solid rgba(157,243,255,0.5);
    box-shadow:0 0 20px rgba(53,201,220,0.35), inset 0 0 15px rgba(255,255,255,0.15);
    animation:bob 4s ease-in-out infinite;
  }
  .time-bubble:nth-child(2){ animation-delay:0.4s; }
  .time-bubble:nth-child(3){ animation-delay:0.8s; }
  .time-bubble:nth-child(4){ animation-delay:1.2s; }

  @keyframes bob{
    0%,100%{ transform:translateY(0); }
    50%{ transform:translateY(-8px); }
  }

  .time-num{
    font-family:'Cairo', sans-serif;
    font-weight:700;
    font-size:24px;
    color:#fff;
    text-shadow:0 0 8px rgba(157,243,255,0.7);
  }
  .time-label{
    font-size:11px;
    color:var(--cyan-light);
    margin-top:2px;
  }

  /* ============================================================
     لحظة التهنئة (Reveal)
  ============================================================ */
  #reveal{
    display:none;
    opacity:0;
    transition:opacity 1.8s ease;
  }
  #reveal.show{
    display:block;
    opacity:1;
  }

  .reveal-emoji{
    font-size:46px;
    margin-bottom:14px;
    animation:pulseEmoji 2.4s ease-in-out infinite;
  }
  @keyframes pulseEmoji{
    0%,100%{ transform:scale(1); }
    50%{ transform:scale(1.12); }
  }

  .reveal-line1{
    font-family:'Cairo', sans-serif;
    font-weight:900;
    font-size:clamp(20px, 5vw, 28px);
    color:#fff;
    margin-bottom:14px;
    text-shadow:0 0 18px rgba(53,201,220,0.6);
  }
  .reveal-line2{
    font-size:clamp(15px, 4vw, 18px);
    line-height:1.9;
    color:rgba(234,246,255,0.9);
  }

  /* ============================================================
     زر الصوت
  ============================================================ */
  #sound-toggle{
    position:fixed;
    top:20px;
    left:20px;
    z-index:10;
    width:52px;
    height:52px;
    border-radius:50%;
    border:1px solid var(--glass-border);
    background:var(--glass-bg);
    backdrop-filter:blur(10px);
    -webkit-backdrop-filter:blur(10px);
    font-size:22px;
    cursor:pointer;
    display:flex;
    align-items:center;
    justify-content:center;
    color:var(--cyan-light);
    transition:transform 0.25s ease, box-shadow 0.25s ease;
  }
  #sound-toggle:hover{
    transform:scale(1.08);
    box-shadow:0 0 18px rgba(53,201,220,0.5);
  }
  #sound-toggle.playing{
    box-shadow:0 0 22px rgba(53,201,220,0.8);
  }

  /* ============================================================
     رسالة داخل زجاجة
  ============================================================ */
  #bottle-btn{
    position:fixed;
    bottom:22px;
    left:22px;
    z-index:10;
    font-size:34px;
    background:none;
    border:none;
    cursor:pointer;
    filter:drop-shadow(0 0 10px rgba(53,201,220,0.5));
    animation:bottleFloat 5s ease-in-out infinite;
  }
  @keyframes bottleFloat{
    0%,100%{ transform:translateY(0) rotate(-4deg); }
    50%{ transform:translateY(-10px) rotate(4deg); }
  }

  .modal-overlay{
    position:fixed;
    inset:0;
    background:rgba(2,10,20,0.65);
    backdrop-filter:blur(4px);
    display:flex;
    align-items:center;
    justify-content:center;
    z-index:100;
    opacity:0;
    pointer-events:none;
    transition:opacity 0.35s ease;
    padding:20px;
  }
  .modal-overlay.open{
    opacity:1;
    pointer-events:auto;
  }

  .modal-card{
    max-width:420px;
    width:100%;
    background:var(--glass-bg);
    border:1px solid var(--glass-border);
    border-radius:24px;
    backdrop-filter:blur(20px);
    -webkit-backdrop-filter:blur(20px);
    padding:34px 26px;
    text-align:center;
    transform:scale(0.9) translateY(10px);
    transition:transform 0.35s ease;
    box-shadow:0 10px 50px rgba(0,0,0,0.5);
  }
  .modal-overlay.open .modal-card{
    transform:scale(1) translateY(0);
  }

  .modal-card p{
    font-size:16px;
    line-height:2;
    color:var(--text-light);
    margin:16px 0 24px;
  }

  .modal-close{
    background:linear-gradient(90deg, var(--royal-blue), var(--cyan));
    border:none;
    color:#fff;
    padding:10px 28px;
    border-radius:30px;
    font-family:'Tajawal', sans-serif;
    font-weight:700;
    cursor:pointer;
    font-size:14px;
    box-shadow:0 4px 18px rgba(53,201,220,0.4);
    transition:transform 0.2s ease;
  }
  .modal-close:hover{ transform:translateY(-2px); }

  /* ============================================================
     الدلفين
  ============================================================ */
  .dolphin{
    position:fixed;
    bottom:8%;
    left:-10%;
    font-size:56px;
    z-index:3;
    opacity:0;
    pointer-events:none;
  }
  .dolphin.jump{
    animation:dolphinJump 4s ease-in-out forwards;
  }
  @keyframes dolphinJump{
    0%{ left:-10%; bottom:8%; opacity:0; transform:rotate(-15deg) scaleX(-1); }
    10%{ opacity:1; }
    35%{ bottom:45%; transform:rotate(15deg) scaleX(-1); }
    50%{ bottom:8%; transform:rotate(-10deg) scaleX(-1); }
    70%{ bottom:38%; transform:rotate(15deg) scaleX(-1); }
    85%{ bottom:8%; transform:rotate(-10deg) scaleX(-1); opacity:1;}
    100%{ left:115%; bottom:8%; opacity:0; transform:rotate(-10deg) scaleX(-1); }
  }

  /* ============================================================
     التوقيع
  ============================================================ */
  .signature{
    position:fixed;
    bottom:14px;
    right:18px;
    z-index:10;
    font-family:'Tajawal', sans-serif;
    font-size:13px;
    letter-spacing:2px;
    color:rgba(157,243,255,0.55);
    cursor:default;
    transition:color 0.4s ease, text-shadow 0.4s ease;
  }
  .signature:hover{
    color:var(--cyan-light);
    text-shadow:0 0 10px var(--cyan), 0 0 20px var(--cyan);
  }

  /* ============================================================
     تجاوب مع الشاشات الصغيرة
  ============================================================ */
  @media (max-width:420px){
    .glass-card{ padding:32px 18px; border-radius:22px; }
    .time-bubble{ width:64px; height:64px; }
    .time-num{ font-size:19px; }
    #sound-toggle{ width:44px; height:44px; font-size:18px; }
    #bottle-btn{ font-size:28px; }
  }
</style>
</head>
<body>

  <!-- ================= مشهد المحيط (خلفية) ================= -->
  <div class="ocean-scene" id="ocean-scene">
    <svg class="wave-layer wave3" viewBox="0 0 1440 200" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M0,100 C240,180 480,20 720,90 C960,160 1200,40 1440,100 L1440,200 L0,200 Z" fill="#041224"></path>
    </svg>
    <svg class="wave-layer wave2" viewBox="0 0 1440 200" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M0,110 C240,40 480,160 720,100 C960,40 1200,150 1440,90 L1440,200 L0,200 Z" fill="#0a2540"></path>
    </svg>
    <svg class="wave-layer wave1" viewBox="0 0 1440 200" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M0,120 C240,60 480,170 720,110 C960,50 1200,140 1440,80 L1440,200 L0,200 Z" fill="#1447a8"></path>
    </svg>
    <!-- الفقاعات تُضاف ديناميكياً عبر JavaScript -->
  </div>

  <!-- ================= زر الصوت ================= -->
  <button id="sound-toggle" title="تشغيل صوت البحر">🌊</button>

  <!-- ================= زر الزجاجة ================= -->
  <button id="bottle-btn" title="رسالة داخل زجاجة">🍾</button>

  <!-- ================= التوقيع ================= -->
  <div class="signature">yt</div>

  <!-- ================= المحتوى الرئيسي ================= -->
  <div class="stage">
    <div class="glass-card">

      <div class="title-name">رَوْنَد 🐬</div>
      <div class="subtitle">العد التنازلي لعيد ميلادكِ يبدأ الآن...</div>

      <!-- العد التنازلي -->
      <div id="countdown-wrap">
        <div class="time-bubble">
          <span class="time-num" id="cd-days">00</span>
          <span class="time-label">يوم</span>
        </div>
        <div class="time-bubble">
          <span class="time-num" id="cd-hours">00</span>
          <span class="time-label">ساعة</span>
        </div>
        <div class="time-bubble">
          <span class="time-num" id="cd-minutes">00</span>
          <span class="time-label">دقيقة</span>
        </div>
        <div class="time-bubble">
          <span class="time-num" id="cd-seconds">00</span>
          <span class="time-label">ثانية</span>
        </div>
      </div>

      <!-- لحظة التهنئة -->
      <div id="reveal">
        <div class="reveal-emoji">🌊🐬💙</div>
        <div class="reveal-line1">كل عام وأنتِ بألف خير يا رَوْنَد 🌊🐬</div>
        <div class="reveal-line2">
          كل عام وأنتِ المهندسة والسند..<br>
          والعيد الجاي إن شاء الله الوضع غير ✨💙
        </div>
      </div>

    </div>
  </div>

  <!-- ================= الدلفين (يظهر عند لحظة الصفر) ================= -->
  <div class="dolphin" id="dolphin">🐬</div>

  <!-- ================= نافذة الرسالة داخل الزجاجة ================= -->
  <div class="modal-overlay" id="modal-overlay">
    <div class="modal-card">
      <div style="font-size:36px;">📜💙</div>
      <p id="bottle-message">
        رَوْنَد يا أقوى مهندسة… انت قد الحلم وفش اشي بصعب عليكِ
        كملي وتخليش اشي يوقفك وان شاء الله ربنا كريم♥️
      </p>
      <button class="modal-close" id="modal-close">إغلاق</button>
    </div>
  </div>

<script>
/* ================================================================
   ⚙️ إعدادات يسهل تعديلها
   ================================================================ */

// 1) تاريخ انتهاء العد التنازلي — عدّلي التاريخ والوقت هنا (سنة-شهر-يوم T ساعة:دقيقة:ثانية)
const TARGET_DATE = new Date("2026-08-16T00:00:00");

// 2) نصوص التهنئة يمكن تعديلها مباشرة داخل عناصر HTML أعلاه:
//    .reveal-line1  و  .reveal-line2

// 3) رسالة الزجاجة يمكن تعديلها من العنصر #bottle-message أعلاه

/* ================================================================
   العد التنازلي
   ================================================================ */
const cdDays = document.getElementById('cd-days');
const cdHours = document.getElementById('cd-hours');
const cdMinutes = document.getElementById('cd-minutes');
const cdSeconds = document.getElementById('cd-seconds');
const countdownWrap = document.getElementById('countdown-wrap');
const revealEl = document.getElementById('reveal');
const dolphinEl = document.getElementById('dolphin');

let revealed = false;

function pad(n){ return String(n).padStart(2,'0'); }

function updateCountdown(){
  const now = new Date();
  const diff = TARGET_DATE - now;

  if(diff <= 0 && !revealed){
    triggerReveal();
    return;
  }
  if(diff <= 0) return;

  const days = Math.floor(diff / (1000*60*60*24));
  const hours = Math.floor((diff / (1000*60*60)) % 24);
  const minutes = Math.floor((diff / (1000*60)) % 60);
  const seconds = Math.floor((diff / 1000) % 60);

  cdDays.textContent = pad(days);
  cdHours.textContent = pad(hours);
  cdMinutes.textContent = pad(minutes);
  cdSeconds.textContent = pad(seconds);
}

function triggerReveal(){
  revealed = true;
  countdownWrap.classList.add('hide');
  setTimeout(()=>{
    revealEl.classList.add('show');
  }, 600);

  // إطلاق أنيميشن الدلفين
  dolphinEl.classList.add('jump');
  setTimeout(()=>{ dolphinEl.classList.remove('jump'); }, 4000);

  // تكرار قفزة الدلفين كل فترة بعد الظهور
  setInterval(()=>{
    dolphinEl.classList.add('jump');
    setTimeout(()=>{ dolphinEl.classList.remove('jump'); }, 4000);
  }, 9000);
}

updateCountdown();
setInterval(updateCountdown, 1000);

/* ================================================================
   الفقاعات المتصاعدة (تُنشأ باستمرار)
   ================================================================ */
const oceanScene = document.getElementById('ocean-scene');

function spawnBubble(){
  const bubble = document.createElement('div');
  bubble.className = 'bubble';

  const size = Math.random() * 26 + 8; // 8px - 34px
  const left = Math.random() * 100;
  const duration = Math.random() * 8 + 7; // 7s - 15s
  const drift = (Math.random() * 80 - 40) + 'px';

  bubble.style.width = size + 'px';
  bubble.style.height = size + 'px';
  bubble.style.left = left + '%';
  bubble.style.setProperty('--drift', drift);
  bubble.style.animationDuration = duration + 's';

  oceanScene.appendChild(bubble);

  setTimeout(()=>{ bubble.remove(); }, duration * 1000 + 500);
}

setInterval(spawnBubble, 450);
// دفعة أولى من الفقاعات عند التحميل
for(let i=0;i<10;i++){ setTimeout(spawnBubble, i*200); }

/* ================================================================
   صوت البحر — Web Audio API (ضوضاء بحر اصطناعية ناعمة)
   ================================================================ */
let audioCtx = null;
let noiseSource = null;
let filterNode = null;
let gainNode = null;
let isPlaying = false;

function createOceanSound(){
  audioCtx = new (window.AudioContext || window.webkitAudioContext)();

  const bufferSize = 2 * audioCtx.sampleRate;
  const noiseBuffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
  const output = noiseBuffer.getChannelData(0);
  for(let i=0;i<bufferSize;i++){
    output[i] = Math.random() * 2 - 1;
  }

  noiseSource = audioCtx.createBufferSource();
  noiseSource.buffer = noiseBuffer;
  noiseSource.loop = true;

  filterNode = audioCtx.createBiquadFilter();
  filterNode.type = 'lowpass';
  filterNode.frequency.value = 500;

  gainNode = audioCtx.createGain();
  gainNode.gain.value = 0.0;

  noiseSource.connect(filterNode);
  filterNode.connect(gainNode);
  gainNode.connect(audioCtx.destination);

  noiseSource.start(0);

  // تموّج لطيف في شدة الصوت لمحاكاة الأمواج
  let t = 0;
  setInterval(()=>{
    if(!isPlaying) return;
    t += 0.02;
    const wave = 0.06 + Math.sin(t) * 0.03;
    gainNode.gain.setTargetAtTime(wave, audioCtx.currentTime, 0.5);
    filterNode.frequency.setTargetAtTime(450 + Math.sin(t*0.5)*150, audioCtx.currentTime, 0.5);
  }, 200);
}

const soundToggle = document.getElementById('sound-toggle');
soundToggle.addEventListener('click', ()=>{
  if(!audioCtx){
    createOceanSound();
  }
  if(audioCtx.state === 'suspended'){
    audioCtx.resume();
  }

  isPlaying = !isPlaying;
  soundToggle.classList.toggle('playing', isPlaying);
  soundToggle.textContent = isPlaying ? '🔊' : '🌊';

  if(!isPlaying){
    gainNode.gain.setTargetAtTime(0, audioCtx.currentTime, 0.3);
  }
});

/* ================================================================
   رسالة داخل زجاجة (Modal)
   ================================================================ */
const bottleBtn = document.getElementById('bottle-btn');
const modalOverlay = document.getElementById('modal-overlay');
const modalClose = document.getElementById('modal-close');

bottleBtn.addEventListener('click', ()=>{
  modalOverlay.classList.add('open');
});
modalClose.addEventListener('click', ()=>{
  modalOverlay.classList.remove('open');
});
modalOverlay.addEventListener('click', (e)=>{
  if(e.target === modalOverlay){
    modalOverlay.classList.remove('open');
  }
});
</script>

</body>
</html>
