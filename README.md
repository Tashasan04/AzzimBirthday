<!-- Save as birthday.html and open in a browser -->
<!doctype html>
<html lang="ms">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Happy Birthday — Special Wish</title>
  <style>
    :root{
      --bg: linear-gradient(180deg,#071126 0%, #04203a 100%);
      --card: rgba(255,255,255,0.04);
      --accent: #FFD166;
      --muted: rgba(255,255,255,0.75);
      --glass: rgba(255,255,255,0.03);
      --radius: 16px;
      font-family: "Nunito", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }
    html,body{height:100%}
    body{
      margin:0;
      background:var(--bg);
      color:#fff;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:24px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    .wrap{
      width:100%;
      max-width:920px;
      border-radius:20px;
      background:linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      box-shadow: 0 18px 60px rgba(2,6,23,0.65);
      padding:20px;
      position:relative;
      overflow:hidden;
      backdrop-filter: blur(6px) saturate(120%);
    }

    header{display:flex;gap:16px;align-items:center}
    .avatar{
      width:80px;height:80px;border-radius:14px;flex:0 0 80px;
      background:linear-gradient(135deg,#ffd166,#ff8a5c);
      display:flex;align-items:center;justify-content:center;font-size:32px;
      color:#081226;font-weight:800;
      box-shadow:0 6px 20px rgba(0,0,0,0.45);
    }
    h1{margin:0;font-size:20px;letter-spacing:0.2px}
    p.lead{margin:4px 0 0;color:var(--muted);font-size:13px}

    .content{
      margin-top:16px;
      min-height:320px;
      display:flex;
      gap:18px;
    }

    /* pages */
    .page {
      flex:1;
      background:var(--card);
      border-radius:12px;
      padding:18px;
      display:none;
      flex-direction:column;
      justify-content:space-between;
    }
    .page.active { display:flex; animation:fadeIn 350ms ease; }
    @keyframes fadeIn { from {opacity:0; transform:translateY(6px)} to {opacity:1; transform:none} }

    .title { font-size:18px; margin:0 0 8px; }
    .txt { color:#fff; line-height:1.5; font-size:15px; min-height:120px; white-space:pre-wrap; }
    .meta{color:var(--muted);font-size:13px}

    .controls { display:flex; gap:8px; align-items:center; justify-content:space-between; margin-top:12px; }
    .btn { border:0; padding:10px 14px; border-radius:10px; font-weight:700; cursor:pointer; background:var(--accent); color:#04203a; }
    .btn.ghost { background:transparent; color:var(--muted); border:1px solid rgba(255,255,255,0.06); padding:8px 12px; }
    .pager { display:flex; gap:8px; align-items:center; }

    /* final right column */
    .side {
      width:300px; flex:0 0 300px;
      background:var(--glass);
      border-radius:12px;
      padding:16px;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      gap:12px;
    }
    .cake{font-size:48px}
    .note{font-size:13px;color:var(--muted);text-align:center}

    footer{margin-top:14px;color:var(--muted);font-size:12px;text-align:center}

    #confetti { position:absolute; inset:0; pointer-events:none; z-index:6; }

    /* typing caret */
    .typing { display:inline-block; border-right:2px solid rgba(255,255,255,0.7); padding-right:6px; animation: blink 1s steps(2) infinite;}
    @keyframes blink { 0%,100%{border-color:transparent} 50%{border-color:rgba(255,255,255,0.7)} }

    @media (max-width:880px){
      .content{flex-direction:column}
      .side{width:100%; order:-1}
    }
  </style>
</head>
<body>
  <canvas id="confetti"></canvas>

  <div class="wrap" role="main" aria-live="polite">
    <header>
      <div class="avatar" id="avatar">A</div>
      <div>
        <h1 id="title">Happy 21th Birthday, <span id="name">Azzim</span> 🎉</h1>
        <p class="lead">This is just a small wish. ✨</p>
      </div>
    </header>

    <div class="content">
      <!-- PAGES LEFT -->
      <div style="flex:1">
        <section id="page1" class="page active" aria-hidden="false">
          <div>
            <h2 class="title">👋 Azzim, اَلسَّلَامُ عَلَيْكُم</h2>
            <div class="txt" id="p1txt">
Err hi? this is my first time wish birthday someone guna website hahaha saja nak kelainan sikit, bosanlah wish dekat chat je. So ni benefit sikit sebab kita IT person huhu.
            </div>
            <div class="meta">From: <strong id="from">Ain</strong></div>
          </div>
          <div class="controls">
            <div class="pager">
              <button class="btn ghost" id="p1prev" disabled>Back</button>
              <button class="btn" id="p1next">Next</button>
            </div>
            <div style="color:var(--muted);font-size:13px">Click and feel the moment.</div>
          </div>
        </section>

        <section id="page2" class="page" aria-hidden="true">
          <div>
            <h2 class="title">SAENGIL CHUKAHAMIDAAA!!</h2>
            <div class="txt" id="p2txt"> Overall thank you sebab buat saya rasa selesa — cara awak hormat & jaga adab sangat saya hargai. Saya doakan supaya Allah permudahkan setiap langkah awak dan lindungi setiap hari hari awak. Heeee...
            </div>
            <div class="meta">Date: <span id="date">10 December 2025</span></div>
          </div>
          <div class="controls">
            <div class="pager">
              <button class="btn ghost" id="p2prev">Back</button>
              <button class="btn" id="p2next">Next</button>
            </div>
            <div style="color:var(--muted);font-size:13px">A little closer…</div>
          </div>
        </section>

        <section id="page3" class="page" aria-hidden="true">
          <div>
            <h2 class="title">Special Wish</h2>
            <div class="txt" id="message">Click *Reveal Wish* to see the full wish.</div>
            <div class="meta">From: <span id="from2">Ain</span></div>
          </div>
          <div class="controls">
            <div class="pager">
              <button class="btn ghost" id="p3prev">Back</button>
              <button class="btn" id="revealBtn">Reveal Wish</button>
            </div>
            <div style="color:var(--muted);font-size:13px">Final page ✨</div>
          </div>
        </section>
      </div>

      <!-- RIGHT SIDE -->
      <aside class="side" aria-hidden="false">
        <div class="cake">🎂</div>
        <div class="note" id="sideNote">Doa Ain, semoga Allah permudahkan urusan Azzim dunia akhirat, semoga perjalanan Azzim untuk memperbaiki diri jadi lebih baik juga dipermudahkan.</div>
        <div style="font-size:12px;color:var(--muted)">Allah tidak akan mengubah nasib sesuatu kaum, hingga mereka mengubah keadaan yang ada pada diri mereka sendiri- Ar-Ra'd: 11 .</div>
      </aside>
    </div>

    <footer>Saengil Chukhahaeee!!!! ✨</footer>
  </div>

  <script>
    /* --------- CUSTOMIZE VALUES --------- */
    const NAME = 'Syed Al Azzim';
    const FROM = 'Ain';
    const DATE = '10 December 2025';
    const FINAL_MESSAGE = "Happy Birthday to you 😊... Semoga panjang umur, diluaskan rezeki seperti mana luasnya lautan. Semoga Allah sentiasa rahmati Azzim dan keluarga. This is something very new for both of us, and I pray that Allah makes this path easy for us, not harder. Percayalah, since kita kenal haritu nama Azzim dah ada dalam doa, cuma sekarang lagi kuat doanya. Semoga Allah permudahkan, insyaAllah.";
    /* ------------------------------------ */

    // populate header/meta
    document.getElementById('name').textContent = NAME;
    document.getElementById('avatar').textContent = (NAME||'A').slice(0,1);
    document.getElementById('from').textContent = FROM;
    document.getElementById('from2').textContent = FROM;
    document.getElementById('date').textContent = DATE;

    // page elements
    const pages = ['page1','page2','page3'].map(id => document.getElementById(id));
    const show = (idx) => {
      pages.forEach((p,i)=>{
        if(i===idx){ p.classList.add('active'); p.setAttribute('aria-hidden','false'); }
        else { p.classList.remove('active'); p.setAttribute('aria-hidden','true'); }
      });
      // trigger typing for page1/page2 when shown
      if (idx === 0) startTypingIfNeeded('p1txt', p1Text, 20);
      if (idx === 1) startTypingIfNeeded('p2txt', p2Text, 20);
    };

    // store original full texts (unchanged)
    const p1Text = document.getElementById('p1txt').textContent.trim();
    const p2Text = document.getElementById('p2txt').textContent.trim();

    // nav
    document.getElementById('p1next').addEventListener('click', ()=> show(1));
    document.getElementById('p2prev').addEventListener('click', ()=> show(0));
    document.getElementById('p2next').addEventListener('click', ()=> show(2));
    document.getElementById('p3prev').addEventListener('click', ()=> show(1));

    // reveal + typing + confetti (only on page3)
    const msgEl = document.getElementById('message');
    const revealBtn = document.getElementById('revealBtn');
    revealBtn.addEventListener('click', () => {
      if (revealBtn.disabled) return;
      revealBtn.disabled = true;
      revealBtn.textContent = 'Revealed ✨';
      startConfetti();
      typeText(FINAL_MESSAGE, msgEl, 26);
    });

    // typing effect with safety (preserve original text exactly)
    function typeText(text, el, speed=24, callback) {
      el.textContent = '';
      let i = 0;
      const cleaned = text.replace(/\r/g, '');
      function step() {
        if (i < cleaned.length) {
          el.textContent += cleaned[i];
          i++;
          setTimeout(step, speed);
        } else {
          el.classList.remove('typing');
          if (callback) callback();
        }
      }
      el.classList.add('typing');
      step();
    }

    // helper to auto-start typing for page1/page2 once per session
    const typedFlags = { p1:false, p2:false };
    function startTypingIfNeeded(id, fullText, speed) {
      const el = document.getElementById(id);
      if (!typedFlags[id]) {
        typedFlags[id] = true;
        typeText(fullText, el, speed);
      }
    }

    // start page1 typing on initial load
    window.addEventListener('load', ()=> {
      // ensure page1 visible then type
      startTypingIfNeeded('p1txt', p1Text, 20);
    });

    /* -------- confetti (simple canvas) -------- */
    const confettiCanvas = document.getElementById('confetti');
    const ctx = confettiCanvas.getContext('2d');
    let confettiPieces = [];
    function resizeCanvas(){ confettiCanvas.width = window.innerWidth; confettiCanvas.height = window.innerHeight; }
    window.addEventListener('resize', resizeCanvas);
    resizeCanvas();

    function createConfetti() {
      confettiPieces = [];
      const count = 90;
      for (let i=0;i<count;i++){
        confettiPieces.push({
          x: Math.random()*confettiCanvas.width,
          y: -Math.random()*confettiCanvas.height,
          r: (Math.random()*6)+4,
          d: Math.random()*count,
          color: ['#FFD166','#EF476F','#06D6A0','#118AB2','#EF9B0F'][Math.floor(Math.random()*5)],
          tilt: Math.random()*10,
          tiltSpeed: Math.random()*0.06+0.02,
          speed: Math.random()*3+2
        });
      }
    }
    function drawConfetti(){
      ctx.clearRect(0,0,confettiCanvas.width, confettiCanvas.height);
      confettiPieces.forEach((p)=>{
        p.y += p.speed;
        p.tilt += p.tiltSpeed;
        if (p.y > confettiCanvas.height + 20) {
          p.y = -10;
          p.x = Math.random()*confettiCanvas.width;
        }
        ctx.save();
        ctx.translate(p.x, p.y);
        ctx.rotate(p.tilt * Math.PI/180);
        ctx.fillStyle = p.color;
        ctx.fillRect(-p.r/2, -p.r/2, p.r, p.r*0.6);
        ctx.restore();
      });
      requestAnimationFrame(drawConfetti);
    }
    let confettiRunning = false;
    function startConfetti(){
      if (confettiRunning) return;
      confettiRunning = true;
      createConfetti();
      drawConfetti();
      // stop after a while
      setTimeout(()=>{ confettiRunning = false; ctx.clearRect(0,0,confettiCanvas.width, confettiCanvas.height); }, 9000);
    }

    // optional quick keyboard nav: ArrowRight = next, ArrowLeft = prev
    window.addEventListener('keydown', (e)=>{
      const activeIndex = pages.findIndex(p => p.classList.contains('active'));
      if (e.key === 'ArrowRight') {
        if (activeIndex < pages.length-1) show(activeIndex+1);
      } else if (e.key === 'ArrowLeft') {
        if (activeIndex > 0) show(activeIndex-1);
      } else if (e.key === 'Enter' && activeIndex === 2) {
        revealBtn.click();
      }
    });

    // small accessibility: focus first next button
    document.getElementById('p1next').focus();
  </script>
</body>
</html>
