l<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CROWNS-SPORTS | Narração Estilo NFA</title>
<style>
*{box-sizing:border-box}
html,body{margin:0;width:100%;height:100%;background:#050505;color:white;font-family:Arial,Helvetica,sans-serif;overflow:hidden}
body{display:grid;place-items:center}
.player{position:relative;width:min(100vw,56.25vh);height:min(177.78vw,100vh);aspect-ratio:9/16;overflow:hidden;background:#080808}
.bg{position:absolute;inset:-8%;opacity:0;transform:scale(1.14);transition:opacity 1s ease;animation:drift 9s ease-in-out infinite alternate}
.bg.active{opacity:1}
@keyframes drift{from{transform:scale(1.12) translate3d(-1%,0,0)}to{transform:scale(1.28) translate3d(1%,-1%,0)}}
.bg svg{width:100%;height:100%;display:block}
.shade{position:absolute;inset:0;background:linear-gradient(180deg,#03030377 0%,#03030333 35%,#030303aa 72%,#030303ee 100%);z-index:1;pointer-events:none}
header{position:absolute;z-index:4;top:4%;width:100%;text-align:center;font-size:10px;letter-spacing:.36em;color:#f1ce7b;pointer-events:none}
.text{position:absolute;z-index:3;inset:12% 7% 20%;display:grid;place-items:center;text-align:center;pointer-events:none}
.slide{position:absolute;width:100%;padding:5%;opacity:0;transform:translateY(22px);transition:opacity .7s,transform .7s;pointer-events:none;visibility:hidden}
.slide.active{opacity:1;transform:translateY(0);pointer-events:auto;visibility:visible;z-index:5}
.slide button{pointer-events:auto !important;position:relative;z-index:10}
.kicker{font-size:clamp(10px,2.6vw,14px);letter-spacing:.35em;color:#f2c65d;margin-bottom:7%}
h1{font-size:clamp(38px,11vw,70px);line-height:.9;margin:0;text-shadow:0 3px 22px #000,0 0 20px #d69c38}
h1 small{display:block;font-size:.38em;letter-spacing:.42em;color:#f3c45c;margin-top:14px}
h2{font-size:clamp(28px,7.5vw,46px);line-height:1.05;color:#ffe5a0;margin:0 0 7%}
p{font-size:clamp(17px,4.5vw,25px);line-height:1.42;margin:0}
.gold{color:#ffd36d;font-weight:900}
.crown{font-size:clamp(70px,18vw,115px);color:#f6ca62;text-shadow:0 0 30px #f3bd4b;margin-bottom:4%;animation:float 2.5s ease-in-out infinite}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
.rule{height:2px;width:44%;margin:7% auto;background:linear-gradient(90deg,transparent,#f5c85d,transparent)}
.final{font-size:clamp(23px,6.2vw,38px);font-weight:900;line-height:1.25;color:#ffe29a}
footer{position:absolute;z-index:4;bottom:5%;left:7%;right:7%;display:flex;justify-content:space-between;color:#f1d38b;font-size:10px;letter-spacing:.2em;pointer-events:none}
.progress{position:absolute;z-index:5;bottom:0;left:0;height:4px;background:#f1c65d;width:0;pointer-events:none}
.controls{position:absolute;z-index:30;top:8%;right:4%;display:flex;gap:6px}
button{border:1px solid #c59b42;background:#090909c9;color:#ffe3a0;padding:9px 12px;border-radius:20px;font-weight:bold;font-size:10px;cursor:pointer;pointer-events:auto}
.btn-main{background:#f1c65d !important;color:#000 !important;padding:16px 24px;border-radius:30px;font-size:15px;width:100%;margin-top:8%;display:block;box-shadow:0 0 25px #f1c65d88}
.btn-ghost{background:#111 !important;color:#ffe3a0;padding:12px 18px;border-radius:30px;font-size:12px;width:100%;margin-top:8px;display:block}
.start-screen{position:absolute;inset:0;z-index:50;background:radial-gradient(circle at 50% 30%,#2a1e05,#050505 70%);display:grid;place-items:center;text-align:center;padding:10%}
.start-screen.hidden{display:none}
.badge{font-size:10px;letter-spacing:.3em;color:#f1ce7b;border:1px solid #f1ce7b;padding:8px 14px;border-radius:20px}
.pill{display:inline-block;background:#1a1200;border:1px solid #f5c85d;color:#ffd36d;padding:6px 12px;border-radius:20px;font-size:11px;font-weight:900;margin:3px}
.join-page{position:absolute;inset:0;z-index:40;background:linear-gradient(180deg,#1a1200,#050505 70%);display:none;overflow-y:auto;padding:16% 8% 10%;text-align:center}
.join-page.active{display:block}
.join-box{background:#0f0f0f;border:1px solid #f5c85d;border-radius:18px;padding:16px;margin-top:14px;text-align:left}
.join-box input{width:100%;margin-top:8px;padding:13px;border-radius:12px;border:1px solid #333;background:#000;color:#fff;font-size:15px}
.pos-btn{border:1px solid #444;background:#111;color:#fff;padding:10px 14px;border-radius:20px;font-size:12px;font-weight:bold;margin:4px}
.pos-btn.selected{background:#f1c65d !important;color:#000 !important}
.link-box{background:#000;border:1px dashed #f5c85d;border-radius:12px;padding:12px;margin-top:12px;word-break:break-all;font-size:13px;color:#ffd36d}
.narra-box{position:absolute;z-index:6;left:7%;right:7%;bottom:9%;background:#000000b8;border:1px solid #f5c85d66;border-radius:14px;padding:10px 12px;text-align:center;pointer-events:none}
.narra-box small{font-size:10px;letter-spacing:.25em;color:#f1ce7b}
.narra-box p{font-size:14px;line-height:1.35;color:#ffe9b0;margin-top:4px}
</style>
</head>
<body>
<div class="player">
  <div class="bg active"><svg viewBox="0 0 400 700" preserveAspectRatio="xMidYMid slice"><rect width="400" height="700" fill="#14100a"/></svg></div>
  <div class="bg"><svg viewBox="0 0 400 700" preserveAspectRatio="xMidYMid slice"><rect width="400" height="700" fill="#0a0a0a"/></svg></div>
  <div class="bg"><svg viewBox="0 0 400 700" preserveAspectRatio="xMidYMid slice"><rect width="400" height="700" fill="#080808"/></svg></div>
  <div class="bg"><svg viewBox="0 0 400 700" preserveAspectRatio="xMidYMid slice"><rect width="400" height="700" fill="#050505"/></svg></div>
  <div class="shade"></div>
  <header>CROWNS — SPORTS</header>
  <div class="controls">
    <button type="button" id="btnNarra">🎙️ NARRAÇÃO: ON</button>
    <button type="button" id="btnPrev">◀</button>
    <button type="button" id="btnNext">▶</button>
  </div>
  <div class="text">
    <div class="slide active">
      <div class="crown">👑</div><div class="kicker">APRESENTA</div>
      <h1>CROWNS<small>SPORTS</small></h1><div class="rule"></div>
      <p>Nem todo mundo nasce rei.<br><span class="gold">Alguns se tornam.</span></p>
    </div>
    <div class="slide">
      <div class="kicker">【entity-FREE FIRE¦canonical_name=Free Fire】 • COMPETITIVO</div>
      <h2>NÃO É SÓ<br>JOGO</h2>
      <p>É <span class="gold">guerra pela coroa.</span><br>Ranked, sala, campeonato.<br>Quem treina, reina.</p>
      <div style="margin-top:10%"><span class="pill">🔥 4X4</span> <span class="pill">🏆 CAMPEONATO</span> <span class="pill">👑 LINE</span></div>
    </div>
    <div class="slide">
      <div class="kicker">DISCIPLINA • RAÇA • RESPEITO</div>
      <h2>ONDE TUDO<br>COMEÇA</h2>
      <p>Suor no treino.<br>Foco na partida.<br>Ninguém vê o começo,<br>todo mundo vê a <span class="gold">coroa.</span></p>
    </div>
    <div class="slide">
      <div class="crown">👑</div><div class="kicker">🔥 RECRUTAMENTO ABERTO 🔥</div>
      <div class="final">QUER VESTIR<br>A COROA?</div><div class="rule"></div>
      <p>Vagas para Line Competitiva<br>【entity-Free Fire¦canonical_name=Free Fire】 • Suporte • Ruxador</p>
      <button type="button" class="btn-main" id="btnQueroEntrar">👑 QUERO ENTRAR 👑</button>
      <button type="button" class="btn-ghost" id="btnReplay">↻ VER DE NOVO</button>
    </div>
  </div>
  <div class="narra-box"><small>🎙️ NARRAÇÃO ESTILO NFA • EMOCIONANTE</small><p id="narraText">Aperte INICIAR TRAILER para ouvir...</p></div>
  <footer><span>CROWNS-SPORTS</span><span>2026 • TRAILER</span></footer>
  <div class="progress" id="progress"></div>

  <div class="join-page" id="joinPage">
    <div style="font-size:60px">👑</div>
    <h2>BORA REINAR<br>COM A GENTE?</h2>
    <div class="join-box">
      <label>SEU NICK NO 【entity-FREE FIRE¦canonical_name=Free Fire】</label>
      <input id="nick" placeholder="Ex: A05 • Matador" />
      <label style="display:block;margin-top:16px">QUAL SUA POSIÇÃO?</label>
      <div style="margin-top:10px;text-align:center">
        <button type="button" class="pos-btn" data-pos="Ruxador">🔥 Ruxador</button>
        <button type="button" class="pos-btn" data-pos="Suporte">🛡️ Suporte</button>
        <button type="button" class="pos-btn" data-pos="Sniper">🎯 Sniper</button>
        <button type="button" class="pos-btn" data-pos="Granadeiro">💣 Granadeiro</button>
        <button type="button" class="pos-btn" data-pos="Coach / Outro">👑 Coach / Outro</button>
      </div>
      <p id="posEscolhida" style="font-size:13px;color:#ffd36d;text-align:center;margin-top:10px">Escolha sua posição acima 👆</p>
    </div>
    <div class="join-box">
      <label>🔗 LINK DO GRUPO OFICIAL</label>
      <a href="https://chat.whatsapp.com/J8IeB8h3FKW2XETNdArvgM?s=cl&p=a&iam=2" target="_blank" style="text-decoration:none"><div class="link-box">https://chat.whatsapp.com/J8IeB8h3FKW2XETNdArvgM?s=cl&p=a&iam=2<br><b style="color:#fff">👉 CLIQUE AQUI PARA ENTRAR 👈</b></div></a>
      <button type="button" class="btn-main" id="btnGoGroup">ENTRAR NO GRUPO DO WHATSAPP →</button>
      <button type="button" class="btn-ghost" id="btnCopy">📋 COPIAR LINK</button>
    </div>
    <button type="button" class="btn-ghost" id="btnBack">← VOLTAR PARA O TRAILER</button>
  </div>

  <div class="start-screen" id="startScreen">
    <div>
      <div class="badge">TRAILER COM NARRAÇÃO ESTILO NFA</div>
      <div style="font-size:90px;margin:14px 0">👑</div>
      <h1 style="font-size:44px">CROWNS<br><small>SPORTS</small></h1>
      <p style="margin-top:14px;font-size:16px">Narração emocionante, estilo narrador de campeonato.<br>Link do grupo no final.</p>
      <button type="button" class="btn-main" id="btnStart">▶ INICIAR TRAILER COM VOZ</button>
      <button type="button" class="btn-ghost" id="btnTestVoice">🎙️ TESTAR VOZ ESTILO NFA</button>
      <p style="font-size:11px;color:#aaa;margin-top:12px">A voz é gerada pelo navegador no estilo narrador esportivo. Não é a voz do Radão, é uma voz de IA inspirada no estilo dele.</p>
    </div>
  </div>
</div>
<script>
let current=0; const slides=document.querySelectorAll('.slide'); const bgs=document.querySelectorAll('.bg'); const progress=document.getElementById('progress');
let narrationOn=true, started=false, startTime=Date.now(), selectedPos="";
const GROUP_LINK="https://chat.whatsapp.com/J8IeB8h3FKW2XETNdArvgM?s=cl&p=a&iam=2";
// TEXTO REESCRITO ESTILO NARRADOR NFA - EMOCIONANTE, IGUAL O RADÃO FALA
const narrations=[
  "Salve, salve, senhoras e senhores! CROWNS Sports apresenta! Nem todo mundo nasce rei! Alguns... se tornam!",
  "Free Fire competitivo! Não é só jogo, família! É guerra pela coroa! Ranked! Sala! Campeonato! Quem treina... REINA!",
  "Disciplina! Raça! Respeito! É aqui onde tudo começa! Ninguém vê o começo! Todo mundo vê a COROA!",
  "Recrutamento aberto! Quer vestir a coroa?! Clica em quero entrar, escolhe sua posição e vem pro grupo oficial da CROWNS!"
];
function getBestVoice(){ const v=speechSynthesis.getVoices(); return v.find(x=>x.lang==='pt-BR' && x.name.toLowerCase().includes('daniel')) || v.find(x=>x.lang==='pt-BR' && x.name.toLowerCase().includes('google')) || v.find(x=>x.lang==='pt-BR') || v.find(x=>x.lang.includes('pt')); }
function speak(text){
  document.getElementById('narraText').textContent=text;
  if(!narrationOn) return;
  try{
    speechSynthesis.cancel();
    const u=new SpeechSynthesisUtterance(text);
    u.lang='pt-BR'; u.rate=1.05; u.pitch=0.9; u.volume=1;
    const v=getBestVoice(); if(v) u.voice=v;
    speechSynthesis.speak(u);
  }catch(e){}
}
function show(n){ current=(n+slides.length)%slides.length; slides.forEach((s,i)=>s.classList.toggle('active',i===current)); bgs.forEach((b,i)=>b.classList.toggle('active',i===current)); if(started) speak(narrations[current]); }
function nextSlide(){ show(current+1); startTime=Date.now(); }
function prevSlide(){ show(current-1); startTime=Date.now(); }
function toggleNarration(){ narrationOn=!narrationOn; document.getElementById('btnNarra').textContent=narrationOn?'🎙️ NARRAÇÃO: ON':'🔇 NARRAÇÃO: OFF'; if(!narrationOn) speechSynthesis.cancel(); else speak(narrations[current]); }
function testVoice(){ narrationOn=true; speak("Salve, salve, senhoras e senhores! Radão na área? Não! Aqui é CROWNS Sports! É a emoção do emulador! Que bala! Bora reinar com a gente?"); }
function startTrailer(){ document.getElementById('startScreen').classList.add('hidden'); started=true; startTime=Date.now(); show(0); }
function replay(){ closeJoin(); show(0); startTime=Date.now(); }
function openJoin(){ document.getElementById('joinPage').classList.add('active'); speak("Você clicou em quero entrar! Agora escreve seu nick, escolhe sua posição e entra no grupo oficial da CROWNS Sports!"); }
function closeJoin(){ document.getElementById('joinPage').classList.remove('active'); if(started) speak(narrations[current]); }
function selectPos(btn,pos){ selectedPos=pos; document.querySelectorAll('.pos-btn').forEach(b=>b.classList.remove('selected')); btn.classList.add('selected'); document.getElementById('posEscolhida').textContent="Sua posição: "+pos+" ✅"; speak("Posição escolhida: "+pos+"! Que bala! Agora entra no grupo!"); }
function goToGroup(){ const nick=document.getElementById('nick').value.trim(); if(!selectedPos){ alert('Escolhe sua posição primeiro 👑'); return; } if(!nick){ alert('Coloca seu nick primeiro 👑'); return; } speak("Boa, "+nick+"! "+selectedPos+" da CROWNS Sports! Te vejo no grupo!"); setTimeout(()=>window.open(GROUP_LINK,'_blank'),800); }
function copyLink(){ navigator.clipboard.writeText(GROUP_LINK).then(()=>alert('Link copiado! 👑')); }
document.getElementById('btnStart').addEventListener('click',startTrailer);
document.getElementById('btnTestVoice').addEventListener('click',testVoice);
document.getElementById('btnNarra').addEventListener('click',toggleNarration);
document.getElementById('btnPrev').addEventListener('click',prevSlide);
document.getElementById('btnNext').addEventListener('click',nextSlide);
document.getElementById('btnQueroEntrar').addEventListener('click',openJoin);
document.getElementById('btnReplay').addEventListener('click',replay);
document.getElementById('btnGoGroup').addEventListener('click',goToGroup);
document.getElementById('btnCopy').addEventListener('click',copyLink);
document.getElementById('btnBack').addEventListener('click',closeJoin);
document.querySelectorAll('.pos-btn').forEach(btn=>btn.addEventListener('click',()=>selectPos(btn,btn.dataset.pos)));
function loop(){ if(started && !document.getElementById('joinPage').classList.contains('active')){ const e=Date.now()-startTime; progress.style.width=Math.min(100,(e/16000)*100)+'%'; if(e>6000){ show(current+1); startTime=Date.now(); } } requestAnimationFrame(loop); } loop();
</script>
</body>
</html>
