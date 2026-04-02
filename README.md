<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Gerador de Personagens — Blackmoor FMC</title>
<link href="https://fonts.googleapis.com/css2?family=UnifrakturMaguntia&family=Cinzel:wght@400;600;700&family=Crimson+Text:ital,wght@0,400;0,600;1,400&display=swap" rel="stylesheet">
<style>
:root {
  --ink:#1a0f00; --parchment:#f2e8d0; --parchment-dark:#e8d9b8; --parchment-mid:#eddfc4;
  --blood:#7a1c1c; --rust:#8b3a1a; --gold:#b8860b; --gold-l:#d4a017;
  --shadow:rgba(26,15,0,.4); --border:#8b6914;
}
*{box-sizing:border-box;margin:0;padding:0;}
html{overflow-x:hidden;}
body{
  background:#080401;
  background-image:radial-gradient(ellipse 80% 50% at 50% 0%,#1a0800 0%,transparent 70%);
  min-height:100vh;min-width:100%;display:flex;flex-direction:column;align-items:center;
  padding:0 1rem 5rem;font-family:'Crimson Text',Georgia,serif;color:var(--ink);
}
/* CANDLES */
.cvw{display:flex;justify-content:center;gap:clamp(2.5rem,7vw,7rem);padding-top:1.5rem;margin-bottom:-.5rem;position:relative;z-index:10;}
.cv{display:flex;flex-direction:column;align-items:center;}
.fl{
  width:11px;height:22px;
  background:radial-gradient(ellipse at 50% 85%,#fffde0,#ffd200 35%,#ff7000 75%,transparent);
  border-radius:50% 50% 35% 35%;
  animation:flicker 2s ease-in-out infinite alternate;filter:blur(.4px);
  box-shadow:0 0 6px #ffd200,0 0 18px #ff8800,0 0 35px rgba(255,120,0,.2);
}
.wk{width:2px;height:5px;background:#222;}
.wx{width:18px;background:linear-gradient(160deg,#f5f0e6,#e2dac8 60%,#ccc6b4);border-radius:3px 3px 5px 5px;}
@keyframes flicker{
  0%{transform:skewX(-3deg) scaleY(1.0);opacity:.88;}
  20%{transform:skewX(2deg) scaleY(1.06);opacity:1;}
  45%{transform:skewX(-1deg) scaleY(.93);opacity:.82;}
  70%{transform:skewX(3deg) scaleY(1.04);opacity:.96;}
  100%{transform:skewX(-2deg) scaleY(1.08);opacity:1;}
}
/* CONTAINER */
.wrap{width:100%;max-width:860px;}
/* HERO */
.hero{
  background:var(--parchment);
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.65' numOctaves='3' stitchTiles='stitch'/%3E%3CfeColorMatrix type='saturate' values='0'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23n)' opacity='.07'/%3E%3C/svg%3E");
  border:3px double var(--border);border-top:none;
  padding:2.5rem 2rem 5rem;text-align:center;
  clip-path:polygon(0 0,100% 0,100% 88%,97% 92%,93% 88%,89% 93%,85% 88%,81% 93%,77% 88%,73% 93%,69% 88%,65% 93%,61% 88%,57% 93%,53% 88%,49% 93%,45% 88%,41% 93%,37% 88%,33% 93%,29% 88%,25% 93%,21% 88%,17% 93%,13% 88%,9% 93%,5% 88%,2% 93%,0 89%);
  box-shadow:0 10px 40px var(--shadow),inset 0 0 80px rgba(184,134,11,.06);
}
.hero-tag{font-family:'Cinzel',serif;font-size:clamp(.6rem,1.2vw,.75rem);letter-spacing:.3em;color:var(--rust);text-transform:uppercase;margin-bottom:.5rem;}
.hero-title{font-family:'UnifrakturMaguntia',cursive;font-size:clamp(3rem,7vw,5rem);color:var(--blood);line-height:1;text-shadow:3px 3px 6px rgba(0,0,0,.18);}
.hero-div{margin:.7rem auto;width:55%;height:1px;background:linear-gradient(to right,transparent,var(--border),transparent);position:relative;}
.hero-div::before{content:'✦';position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);color:var(--gold);font-size:.9rem;background:var(--parchment);padding:0 .5rem;}
.hero-q{font-style:italic;font-size:clamp(1rem,2.2vw,1.22rem);color:var(--ink);line-height:1.7;max-width:600px;margin:.5rem auto 0;}
.hero-q em{font-style:normal;color:var(--blood);font-weight:600;}
.hero-q-attr{display:block;font-size:.78rem;color:var(--rust);margin-top:.5rem;letter-spacing:.07em;font-style:normal;}
/* CONTROLS */
.ctrl-bar{
  background:var(--parchment-dark);border:2px solid var(--border);border-top:none;
  padding:1.8rem 2rem;display:flex;flex-wrap:wrap;gap:1.2rem;align-items:flex-end;
  box-shadow:0 6px 24px var(--shadow);
}
.cg{display:flex;flex-direction:column;gap:.3rem;flex:1;min-width:140px;}
.cl{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.22em;color:var(--rust);text-transform:uppercase;}
.ch{font-style:italic;font-size:.75rem;color:#a06030;margin-top:-.1rem;}
.sex-row{display:flex;gap:0;}
.sb{
  flex:1;padding:.45rem .5rem;font-family:'Cinzel',serif;font-size:.7rem;letter-spacing:.07em;
  cursor:pointer;border:1.5px solid var(--border);background:var(--parchment);color:var(--rust);transition:all .17s;white-space:nowrap;
}
.sb:nth-child(1){border-right:none;border-radius:2px 0 0 2px;}
.sb:nth-child(2){border-right:none;border-radius:0;}
.sb:nth-child(3){border-radius:0 2px 2px 0;}
.sb.on{background:var(--rust);color:var(--parchment);border-color:var(--blood);}
.sb:hover:not(.on){background:var(--parchment-mid);}
select{
  font-family:'Crimson Text',serif;font-size:1rem;color:var(--ink);
  background:var(--parchment);border:1.5px solid var(--border);
  padding:.45rem 2rem .45rem .7rem;cursor:pointer;outline:none;
  -webkit-appearance:none;appearance:none;
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%238b6914' stroke-width='2' fill='none'/%3E%3C/svg%3E");
  background-repeat:no-repeat;background-position:right .7rem center;
}
select:hover{border-color:var(--gold);}
.btn-roll{
  font-family:'Cinzel',serif;font-size:.95rem;font-weight:700;letter-spacing:.14em;text-transform:uppercase;
  color:var(--parchment);background:var(--blood);border:2px solid #5a1010;
  padding:.75rem 2.2rem;cursor:pointer;transition:all .17s;flex-shrink:0;
  box-shadow:0 4px 10px rgba(100,15,15,.45),inset 0 1px 0 rgba(255,255,255,.08);
}
.btn-roll:hover{background:#912222;transform:translateY(-1px);box-shadow:0 5px 18px rgba(100,15,15,.6);}
.btn-roll:active{transform:translateY(0);}
/* SHEET */
.sheet{
  display:none;background:var(--parchment);
  background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='500' height='500'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.55' numOctaves='4' stitchTiles='stitch'/%3E%3CfeColorMatrix type='saturate' values='0'/%3E%3C/filter%3E%3Crect width='500' height='500' filter='url(%23n)' opacity='.055'/%3E%3C/svg%3E");
  border:2px solid var(--border);border-top:none;position:relative;overflow:visible;
  box-shadow:0 10px 50px rgba(0,0,0,.55);animation:unfurl .45s cubic-bezier(.22,.68,0,1.2);
}
.sheet.on{display:block;}
@keyframes unfurl{from{opacity:0;transform:scaleY(.96) translateY(-8px);}to{opacity:1;transform:scaleY(1) translateY(0);}}
.corner{position:absolute;font-size:1.4rem;color:var(--border);opacity:.45;pointer-events:none;line-height:1;}
.corner-tl{top:.6rem;left:.8rem;}.corner-tr{top:.6rem;right:.8rem;transform:scaleX(-1);}
.corner-bl{bottom:.6rem;left:.8rem;transform:scaleY(-1);}.corner-br{bottom:.6rem;right:.8rem;transform:scale(-1);}
.wm{position:absolute;bottom:2rem;right:1.5rem;font-family:'UnifrakturMaguntia',cursive;font-size:8rem;color:rgba(139,105,20,.05);pointer-events:none;user-select:none;transform:rotate(-12deg);line-height:1;}
.si{padding:2rem 2.5rem;}
/* CHAR HEADER */
.ch2{text-align:center;padding-bottom:1rem;border-bottom:1px solid var(--border);margin-bottom:1.5rem;}
.cname{font-family:'UnifrakturMaguntia',cursive;font-size:clamp(2.2rem,5vw,3.2rem);color:var(--blood);line-height:1;}
.cep{font-style:italic;color:var(--rust);font-size:1.05rem;margin-top:.2rem;}
.cmeta{display:flex;justify-content:center;flex-wrap:wrap;gap:.7rem;margin-top:.6rem;}
.mt{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.14em;color:var(--rust);text-transform:uppercase;border:1px solid var(--border);padding:.18rem .65rem;background:rgba(184,134,11,.06);}
.ab{display:inline-block;font-family:'Cinzel',serif;font-size:.62rem;letter-spacing:.14em;text-transform:uppercase;border:1px solid;padding:.18rem .65rem;margin-top:.4rem;}
.ab.law{border-color:#3a6b8a;color:#3a6b8a;background:rgba(58,107,138,.07);}
.ab.chaos{border-color:var(--blood);color:var(--blood);background:rgba(122,28,28,.07);}
.ab.neutral{border-color:#5a5a3a;color:#5a5a3a;background:rgba(90,90,58,.07);}
/* GRID */
.sg{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
.fc{grid-column:1/-1;}
/* SAVES WRAP */
.saves-wrap{overflow-x:auto;-webkit-overflow-scrolling:touch;}
/* MOBILE */
@media(max-width:580px){
  body{padding:0 .3rem 4rem;}
  .cvw{gap:clamp(1rem,4vw,2.5rem);padding-top:1rem;}
  .hero{padding:1.2rem .8rem 3rem;}
  .hero-tag{font-size:.52rem;letter-spacing:.12em;}
  .hero-q{font-size:.9rem;line-height:1.6;}
  .ctrl-bar{padding:1rem .8rem;gap:.7rem;}
  .cg{min-width:100%;flex:unset;}
  .btn-roll{width:100%;text-align:center;font-size:.85rem;padding:.7rem 1rem;}
  .si{padding:1rem .8rem;}
  .sg{grid-template-columns:1fr;}
  .cname{font-size:1.8rem;}
  .cmeta{gap:.35rem;}
  .mt{font-size:.55rem;padding:.13rem .4rem;}
  /* Atributos: 2 colunas no mobile pra caber bem */
  .ag{grid-template-columns:repeat(2,1fr);gap:.5rem;}
  .ab2{padding:.5rem .4rem;}
  .av{font-size:1.6rem;}
  .ak{font-size:.56rem;}
  .an{font-size:.66rem;}
  .dvb{font-size:2.2rem;}
  .gold-big{font-size:1.35rem;}
  .dvn{font-size:.76rem;}
  .st2{min-width:320px;font-size:.76rem;}
  .st2 th{font-size:.48rem;padding:.16rem .18rem;}
  .st2 td{font-size:.8rem;padding:.2rem .18rem;}
  .tr2{font-size:.82rem;padding:.4rem .6rem;}
  .tt{font-size:.56rem;}
  .apb{font-size:.84rem;line-height:1.6;}
  .el{font-size:.84rem;line-height:1.75;}
  .wm{font-size:4rem;bottom:1rem;right:.8rem;}
  .corner{font-size:1rem;}
  .sac{padding:.7rem;gap:.5rem;flex-direction:column;align-items:center;}
  .ba{font-size:.62rem;padding:.4rem 1.2rem;width:100%;text-align:center;}
}
.st{font-family:'Cinzel',serif;font-size:.68rem;letter-spacing:.22em;color:var(--rust);text-transform:uppercase;border-bottom:1px solid var(--border);padding-bottom:.25rem;margin-bottom:.7rem;}
/* ATTRS */
.ag{display:grid;grid-template-columns:repeat(3,1fr);gap:.55rem;}
.ab2{border:1.5px solid var(--border);background:var(--parchment-dark);padding:.45rem .35rem;text-align:center;position:relative;animation:rollIn .3s ease-out both;}
.ab2.prime{border-color:var(--gold);background:rgba(184,134,11,.09);}
.ab2.prime::after{content:'★';position:absolute;top:-.45rem;right:-.45rem;color:var(--gold);font-size:.62rem;background:var(--parchment);padding:0 1px;}
@keyframes rollIn{from{opacity:0;transform:scale(1.25);}to{opacity:1;transform:scale(1);}}
.ak{font-family:'Cinzel',serif;font-size:.55rem;letter-spacing:.1em;color:var(--rust);display:block;}
.av{font-family:'Cinzel',serif;font-size:1.75rem;font-weight:700;color:var(--ink);display:block;line-height:1.15;}
.an{font-size:.68rem;color:var(--rust);font-style:italic;display:block;line-height:1.2;}
.good{color:#2a5a18;}.bad{color:var(--blood);}
/* COMBAT */
.sp{display:flex;justify-content:space-between;align-items:baseline;padding:.3rem 0;border-bottom:1px dotted rgba(139,105,20,.3);font-size:.92rem;}
.sp:last-child{border-bottom:none;}
.sl{font-family:'Crimson Text',serif;color:var(--rust);font-size:.86rem;}
.sv2{font-family:'Cinzel',serif;font-weight:600;color:var(--ink);font-size:.92rem;}
/* DV BADGE */
.dvb{font-family:'UnifrakturMaguntia',cursive;font-size:3rem;color:var(--blood);line-height:1;text-shadow:1px 1px 3px rgba(0,0,0,.15);}
.dvl{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.18em;color:var(--rust);text-transform:uppercase;display:block;margin-top:.1rem;}
.dvn{font-size:.8rem;color:var(--rust);font-style:italic;margin-top:.4rem;line-height:1.5;}
.gold-big{font-family:'Cinzel',serif;font-size:1.8rem;font-weight:700;color:var(--gold);}
/* SAVES */
.st2{width:100%;border-collapse:collapse;font-size:.88rem;}
.st2 th{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.1em;color:var(--rust);text-align:center;padding:.2rem .25rem;border-bottom:1px solid var(--border);white-space:nowrap;}
.st2 td{text-align:center;padding:.28rem .25rem;font-family:'Cinzel',serif;font-size:.9rem;font-weight:600;color:var(--ink);}
.st2 tr:nth-child(even) td{background:rgba(139,105,20,.05);}
/* EQUIP */
.el{list-style:none;font-size:.9rem;color:var(--ink);line-height:1.8;}
.el li::before{content:'◆ ';color:var(--rust);font-size:.6rem;}
.el li.wp::before{content:'⚔ ';color:var(--gold);font-size:.65rem;}
.el li.ar::before{content:'🛡 ';font-size:.7rem;}
.el li.ge::before{content:'◈ ';color:var(--gold-l);font-size:.65rem;}
/* TRAITS */
.tr2{border-left:3px solid var(--gold);background:rgba(139,105,20,.055);padding:.5rem .75rem;margin-bottom:.45rem;font-size:.87rem;line-height:1.5;}
.tt{font-family:'Cinzel',serif;font-size:.6rem;letter-spacing:.14em;color:var(--rust);text-transform:uppercase;display:block;margin-bottom:.15rem;}
/* APPEARANCE */
.apb{background:rgba(139,105,20,.05);border:1px dashed var(--border);padding:.75rem .95rem;font-size:.9rem;line-height:1.7;font-style:italic;color:#2a1500;}
.apb strong{font-style:normal;color:var(--rust);}
/* LANGS */
.lp{display:flex;flex-wrap:wrap;gap:.35rem;margin-top:.3rem;}
.lpi{font-family:'Cinzel',serif;font-size:.58rem;letter-spacing:.1em;border:1px solid var(--border);padding:.12rem .45rem;color:var(--rust);background:rgba(184,134,11,.05);text-transform:uppercase;}
/* XP NOTE */
.xn{font-style:italic;color:var(--rust);font-size:.82rem;text-align:center;margin-top:1rem;padding:.5rem;border-top:1px dotted var(--border);}
/* ACTIONS */
.sac{display:flex;gap:1rem;justify-content:center;margin-top:1rem;padding:1rem;border-top:1px solid var(--border);flex-wrap:wrap;}
.ba{font-family:'Cinzel',serif;font-size:.65rem;letter-spacing:.14em;text-transform:uppercase;color:var(--rust);background:transparent;border:1.5px solid var(--border);padding:.38rem 1.1rem;cursor:pointer;transition:all .17s;}
.ba:hover{background:var(--parchment-dark);color:var(--blood);border-color:var(--blood);}
/* FOOTER */
.ft{font-family:'Crimson Text',serif;font-size:.72rem;color:rgba(242,232,208,.28);text-align:center;margin-top:2rem;font-style:italic;}
@media print{
  body{background:white;padding:0;}
  .cvw,.hero,.ctrl-bar,.sac,.ft{display:none!important;}
  .sheet{box-shadow:none;border:1px solid #aaa;}
}
</style>
</head>
<body>

<div class="cvw">
  <div class="cv"><div class="fl"></div><div class="wk"></div><div class="wx" style="height:68px"></div></div>
  <div class="cv"><div class="fl" style="animation-delay:-.9s"></div><div class="wk"></div><div class="wx" style="height:52px"></div></div>
  <div class="cv"><div class="fl" style="animation-delay:-.4s"></div><div class="wk"></div><div class="wx" style="height:74px"></div></div>
  <div class="cv"><div class="fl" style="animation-delay:-1.3s"></div><div class="wk"></div><div class="wx" style="height:46px"></div></div>
  <div class="cv"><div class="fl" style="animation-delay:-.6s"></div><div class="wk"></div><div class="wx" style="height:65px"></div></div>
</div>

<div class="wrap">

  <div class="hero">
    <p class="hero-tag">Gerador de Personagens · Sistema Fantastic Medieval Campaigns · Masmorras de</p>
    <h1 class="hero-title">Blackmoor</h1>
    <div class="hero-div"></div>
    <p class="hero-q">
      Você tem coragem suficiente —<br>
      ou é tolo demais —<br>
      para descer <em>às entranhas do Castelo de Blackmoor?</em><br><br>
      Os que entram raramente voltam.<br>
      Os que voltam, voltam <em>mudados para sempre.</em><br>
      Mas o ouro lá embaixo não tem dono — <em>ainda.</em>
      <span class="hero-q-attr">— Aviso afixado na porta da taverna de Blackmoor</span>
    </p>
  </div>

  <div class="ctrl-bar">
    <div class="cg">
      <span class="cl">Sexo</span>
      <span class="ch">⚀ Aleatório: não escolha nada</span>
      <div class="sex-row">
        <button class="sb on" id="sR" onclick="setSex('R')">⚀ Aleat.</button>
        <button class="sb" id="sM" onclick="setSex('M')">♂ Homem</button>
        <button class="sb" id="sF" onclick="setSex('F')">♀ Mulher</button>
      </div>
    </div>
    <div class="cg">
      <span class="cl">Classe</span>
      <span class="ch">⚀ Aleatório por padrão</span>
      <select id="sc">
        <option value="R">⚀ Aleatório</option>
        <option value="Fighter">⚔️ Guerreiro</option>
        <option value="Mage">🔮 Mago</option>
        <option value="Cleric">✝️ Clérigo</option>
        <option value="Dwarf">🪨 Anão</option>
        <option value="Elf">🌿 Elfo</option>
        <option value="Halfling">🍃 Halfling</option>
      </select>
    </div>
    <div class="cg">
      <span class="cl">Alinhamento</span>
      <span class="ch">⚀ Aleatório por padrão</span>
      <select id="sa">
        <option value="R">⚀ Aleatório</option>
        <option value="Leal">Leal</option>
        <option value="Neutro">Neutro</option>
        <option value="Caótico">Caótico</option>
      </select>
    </div>
    <button class="btn-roll" onclick="gen()">🎲 Invocar Aventureiro</button>
  </div>

  <div class="sheet" id="sheet">
    <div class="wm" id="wm">B</div>
    <div class="corner corner-tl">✦</div><div class="corner corner-tr">✦</div>
    <div class="corner corner-bl">✦</div><div class="corner corner-br">✦</div>
    <div class="si">

      <div class="ch2">
        <div class="cname" id="cn"></div>
        <div class="cep" id="ce"></div>
        <div class="cmeta">
          <span class="mt" id="mc"></span>
          <span class="mt" id="ms"></span>
          <span class="mt">Nível 1</span>
          <span class="mt" id="mr"></span>
          <span class="mt" id="mm"></span>
        </div>
        <div id="mal" style="margin-top:.4rem"></div>
      </div>

      <div class="sg">
        <div>
          <div class="st">Atributos — 3d6 em ordem</div>
          <div class="ag" id="atrs"></div>
          <p style="font-size:.72rem;color:var(--rust);font-style:italic;margin-top:.5rem">★ Requisito Principal</p>
        </div>
        <div>
          <div class="st">Dado de Vida &amp; Combate</div>
          <div style="display:flex;align-items:flex-end;gap:1.2rem;margin-bottom:.6rem">
            <div><div class="dvb" id="dvb">1</div><span class="dvl">Dado(s) de Vida</span></div>
            <div><div class="gold-big" id="cab" style="color:var(--ink)"></div><span class="dvl">Classe de Armadura</span></div>
          </div>
          <div class="dvn" id="dvn"></div>
          <div id="cr" style="margin-top:.7rem"></div>
        </div>

        <div class="fc">
          <div class="st">Salvaguardas — role 1d20 ≥ resultado</div>
          <div class="saves-wrap">
            <table class="st2">
              <thead><tr>
                <th>Morte/Veneno</th><th>Varinhas</th><th>Virar Pedra</th><th>Sopro Dragão</th><th>Cajados/Magia</th>
              </tr></thead>
              <tbody><tr id="svr"></tr></tbody>
            </table>
          </div>
          <p id="svn" style="font-size:.72rem;color:var(--rust);font-style:italic;margin-top:.3rem"></p>
        </div>

        <div>
          <div class="st">Arma &amp; Armadura</div>
          <ul class="el" id="ew"></ul>
          <div class="st" style="margin-top:1rem">Equipamento Inicial</div>
          <ul class="el" id="eg"></ul>
        </div>
        <div>
          <div class="st">Habilidades de Classe</div>
          <div id="tr"></div>
          <div class="st" style="margin-top:1rem">Idiomas</div>
          <div class="lp" id="lg"></div>
        </div>

        <div class="fc">
          <div class="st">Aparência &amp; Traços</div>
          <div class="apb" id="ap"></div>
        </div>
      </div>

      <p class="xn" id="xn"></p>
      <div class="sac">
        <button class="ba" onclick="window.print()">📜 Imprimir Ficha</button>
        <button class="ba" onclick="gen()">🎲 Novo Personagem</button>
      </div>
    </div>
  </div>
</div>

<p class="ft">Sistema: Fantastic Medieval Campaigns — Marcia B. (CC BY-NC-SA 4.0) · Formato: The Dark Tower — Cassio de Miguel · Cenário: Blackmoor — Dave Arneson (1971)</p>

<script>
// ── NAMES ──────────────────────────────────────────────────────
const NM=['Alarico','Beltrano','Cândido','Dravos','Eudes','Fernão','Galvão','Heraldo','Ivar',
 'Jordão','Leandro','Mirando','Naldo','Osvaldo','Peregrino','Quirino','Rodrigo',
 'Sandro','Tancredo','Ulrico','Valdir','Waldo','Zacarias','Brandão','Delfino',
 'Eliano','Fausto','Grimaldo','Humberto','Lindolfo','Magno','Norberto','Odilon',
 'Prudêncio','Raimundo','Silvano','Teodoro','Ubaldo','Valério','Wendel',
 'Adalberto','Balduíno','Clovis','Dagoberto','Estêvão','Filipe','Gonçalo','Henrique'];
const NF=['Aldara','Beatriz','Casilda','Dalva','Ermínia','Filomena','Gonçala','Hortência',
 'Izabel','Jandira','Leonor','Mirela','Natalina','Odete','Perpétua','Rosalba','Sivana',
 'Teonília','Umbelina','Valquíria','Wanda','Ximena','Yara','Zenaide','Branca',
 'Eleonora','Fátima','Genoveva','Hildegarda','Irene','Josefina','Lucinda','Marilda',
 'Nadège','Orlandina','Piedade','Rúbia','Sirlei','Tereza','Vera','Almerinda',
 'Belarmina','Celestina','Dorvalina','Esmeralda','Florinda','Gilberta'];
const EM=['o Destemido','o Proscrito','das Trevas','o Sem-Sorte','de Blackmoor','o Marcado',
 'Mão-de-Ferro','o Errante','o Maldito','da Caverna','o Cicatriz','o Quebrado',
 'Navalha','das Profundezas','o Velho Osso','o Implacável','do Norte','Olho-de-Corvo',
 'o Amaldiçoado','da Forja','o Cobrador','Dentes-de-Lobo','o Espectro','o Desertor'];
const EF=['a Destemida','a Proscrita','das Trevas','a Sem-Sorte','de Blackmoor','a Marcada',
 'Mão-de-Ferro','a Errante','a Maldita','da Caverna','a Cicatriz','a Quebrada',
 'Navalha','das Profundezas','a Velha Osso','a Implacável','do Norte','Olho-de-Corvo',
 'a Amaldiçoada','da Forja','a Cobradora','Dentes-de-Loba','a Espectro','a Desertora'];

// ── APPEARANCE ─────────────────────────────────────────────────
const HAIR={
 M:['cabelos negros curtos e sujos de fuligem','cabelos castanhos ralos presos com cordão de couro',
    'cabelo ruivo e desgrenhado','careca com testa marcada por cicatrizes','cabelos grisalhos e emaranhados',
    'cabelos louros cortados a faca','cabelo escuro preso num nó sujo','topete cor de palha velha',
    'cabelos brancos prematuros e eriçados','têmporas raspadas, resto preso com linho'],
 F:['cabelos negros longos trançados com barbante','cabelos castanhos curtos cortados a faca',
    'cabelos ruivos soltos e oleosos','cabelos grisalhos num coque frouxo',
    'tranças louras desgastadas pelo vento','cabelos escuros sob um lenço encardido',
    'cabelos cor de cobre caindo sobre um ombro','cabelo branco prematuro e fino',
    'cachos castanhos apertados e ressecados','mechas negras cortadas na altura do queixo']};
const EYES=['olhos castanhos fundos e desconfiados','olhos cinzas como pedra molhada',
 'olhos verdes com veia dourada','olhos negros e frios como poço seco',
 'olhos azul-acinzentados de quem viu coisa demais','olho esquerdo mais claro que o direito',
 'olhos âmbar com pupilas sempre contraídas','olhos castanho-avermelhados quase sem brilho',
 'olhos de um verde musgo desgastado','olhos escuros com olheiras permanentes'];
const BUILD={
 M:['compleição larga com pescoço de touro','magro como galho seco mas tenso',
    'ombros desiguais de tanto carregar peso','baixo e compacto com pernas curvadas',
    'alto e com postura inclinada para frente','musculoso mas com barriga proeminente',
    'corpo esguio com mãos desproporcionalmente grandes','de aparência comum — não chama atenção'],
 F:['baixa e sólida como barril','alta e angulosa quase toda cotovelo e joelho',
    'compleição atlética e cicatrizes nas mãos','delgada mas de olhar que intimida',
    'ombros largos e postura de quem não se dobra','mediana em tudo — invisível numa multidão',
    'corpo endurecido por anos de trabalho pesado','aparentemente frágil — enganadora']};
const FACE_M=['rosto quadrado com maxilar pesado','cara longa e triste','bochechas fundas com sombras permanentes',
 'nariz quebrado cicatrizado para o lado','queixo partido por velha garrafada','rosto arredondado sem marca especial',
 'cara tatuada com linhas tribais desbotadas','rosto fino com veias visíveis nas têmporas',
 'bochecha direita marcada por queimadura antiga','maxilar serrado que nunca relaxa completamente'];
const FACE_F=['rosto oval com expressão perpetuamente entediada','maçãs do rosto altas como faca',
 'lábio superior com cicatriz fina','sobrancelhas densas que encontram no meio',
 'queixo proeminente e expressão decidida','rosto redondo de traços tensos',
 'cicatriz vertical no supercílio esquerdo','nariz levemente torto — já foi maior',
 'boca fina que não sorri sem razão','olheiras fundas e permanentes'];
const MARKS=['Nenhuma marca especial.','Cicatriz horizontal no pulso direito que não conta para ninguém.',
 'Um dente de ouro fincado onde havia um dente podre.','Tatuagem desbotada de símbolo que já não sabe o que significa.',
 'Dedo mindinho da mão esquerda dobra em ângulo errado.','Marca de queimadura no antebraço — nunca explica de onde.',
 'Orelha esquerda com a ponta arranhada por uma lâmina.','Calombo no crânio coberto pelo cabelo.',
 'Nenhuma — mas limpa as mãos nas calças com frequência suspeita.','Veias escuras no dorso da mão — talvez só o frio.',
 'Sinal de nascença em forma irregular no pescoço.','Unhas rígidas e escurecidas de quem trabalhou com metal a vida toda.'];
const MANNER=['Fala pouco. Olha demais.','Sorri fácil — e isso é o mais assustador.','Nunca olha nos olhos por mais de três segundos.',
 'Sempre de costas para a parede.','Mexe em algo com os dedos quando está quieto.',
 'Respira fundo antes de qualquer decisão.','Fala rápido demais quando está nervoso.',
 'Carrega algo embrulhado que não mostra para ninguém.','Não faz perguntas. Prefere descobrir na força.',
 'Parece sempre calculando algo.','Ri nos momentos errados.','Nunca diz "não sei" — improvisa.'];

function appar(sex,A){
  const s=sex==='F'?'F':'M';
  const tall=(A.FOR+A.CON)>=22, small=(A.FOR+A.CON)<=13;
  const stat=tall?'de estatura imponente':small?'de pequeno porte':'de altura comum';
  return `<strong>Estatura:</strong> ${stat}, ${pick(BUILD[s])}.<br>
<strong>Rosto:</strong> ${pick(s==='M'?FACE_M:FACE_F)}, ${pick(EYES)}.<br>
<strong>Cabelo:</strong> ${pick(HAIR[s])}.<br>
<strong>Marca:</strong> ${pick(MARKS)}<br>
<strong>Modo de ser:</strong> ${pick(MANNER)}`;
}

// ── GEAR ───────────────────────────────────────────────────────
function gBase(){return['Mochila','Tochas ×6','Ração de viagem (1 semana)','Cantil','Estacas de ferro ×12 + martelo',
 'Corda (15m)','Espelho de aço',pick(['Lanterna + 2 frascos de óleo','Lamparina + 4 frascos de óleo']),
 pick(['Alho (erva protetora)','Belladona','Erva-de-Lobo'])];}
function gMage(){return['Mochila','Tochas ×6','Ração simples (1 semana)',
 'Grimório (24 feitiços, 1º–3º círculo)','Tinta de sépia + pena de corvo','Cantil',
 pick(['Pergaminho em branco ×3','Pergaminho com Sono (pronto para usar)']),
 pick(['Vela de cera negra ×3','Pó de obsidiana em saquinho'])];}
function gCleric(){return['Mochila','Tochas ×6','Ração de viagem (1 semana)','Cantil',
 `Símbolo sagrado de ${pick(['Mitra, o Ordeiro','Set, o Caótico','divindade sem nome'])}`,
 'Água benta ×2 (vidros)','Corda (15m)',
 pick(['Crucifixo de prata','Relíquia sagrada em pano'])];}
function gElf(){return['Mochila','Tochas ×6','Ração élfica (1 semana)','Cantil',
 'Espelho de prata','Corda de seda (15m)',
 pick(['Mapa incompleto da masmorra (duvidoso)','Pedra de toque mágica (fraca)'])];}

// ── CLASSES ────────────────────────────────────────────────────
const CLS={
 Fighter:{label:'Guerreiro',icon:'⚔️',race:'Humano',maxLvl:'∞',hd:'1',
  prime:['FOR'],saves:[12,13,14,15,16],
  wep:()=>{const m=pick(['Espada Longa','Espada','Machado de Batalha','Maça','Mangual','Lança']);
   const r=pick(['Arco Curto (20 flechas)','Besta Leve (30 virotes)','— (sem ranged)']);return[m,r];},
  arm:()=>pick(['Couro (CA 12)','Couro + Escudo (CA 13)','Cota de Malha (CA 14)','Cota de Malha + Escudo (CA 15)']),
  acOf:a=>a.includes('CA 15')?15:a.includes('CA 14')?14:a.includes('CA 13')?13:12,
  gear:gBase,
  traits:[{t:'Todas as armas',d:'Usa qualquer arma e todos os itens mágicos de arma.'},
   {t:'Armadura',d:'Usa qualquer armadura e escudo.'},
   {t:'Combate',d:'Melhora capacidade de ataque a cada 3 níveis. Todo acerto: 1d6 de dano.'},
   {t:'Lorde (Nível 9)',d:'Conquista terras, constrói castelos, cobra 10 PO/habitante/ano.'}],
  langs:()=>['Comum'],
  align:()=>pick(['Leal','Leal','Neutro','Neutro','Caótico']),
  xp:'Próximo nível (Guerreiro): 2.000 XP — principalmente de ouro recuperado.'},
 Mage:{label:'Mago',icon:'🔮',race:'Humano',maxLvl:'∞',hd:'1',
  prime:['INT'],saves:[13,14,13,16,15],
  wep:()=>['Adaga'],
  arm:()=>'Sem armadura (CA 10)',acOf:()=>10,gear:gMage,
  traits:[{t:'Magia (1 feitiço/dia)',d:'Escolha: Sono, Encantar Pessoa, Luz, Proteção Contra o Mal, Ler Magia ou Detectar Magia.'},
   {t:'Armas',d:'Somente adaga. Não pode usar armadura.'},
   {t:'Itens Mágicos',d:'Usa qualquer item mágico exceto armas e armaduras mágicas.'},
   {t:'Pesquisa',d:'Pesquisa novos feitiços em qualquer nível.'},
   {t:'Bruxo (Nível 11)',d:'Fabrica poções, pergaminhos e outros itens mágicos.'}],
  langs:()=>{const p=['Élfico','Anão','Gnomo','Goblin','Dragônico','Infernal','Orc'];
   const n=roll(3)-1,r=['Comum'];for(let i=0;i<n;i++){const l=pick(p.filter(x=>!r.includes(x)));if(l)r.push(l);}return r;},
  align:()=>pick(['Leal','Neutro','Neutro','Caótico','Caótico']),
  xp:'Próximo nível (Vidente): 2.500 XP — Magos avançam devagar mas tornam-se os mais temidos.'},
 Cleric:{label:'Clérigo',icon:'✝️',race:'Humano',maxLvl:'∞',hd:'1',
  prime:['SAB'],saves:[11,12,14,16,15],
  wep:()=>[pick(['Maça','Maça + Escudo','Mangual','Cajado de Batalha','Martelo de Guerra'])],
  arm:()=>pick(['Couro (CA 12)','Couro + Escudo (CA 13)','Cota de Malha (CA 14)','Cota de Malha + Escudo (CA 15)']),
  acOf:a=>a.includes('CA 15')?15:a.includes('CA 14')?14:a.includes('CA 13')?13:12,gear:gCleric,
  traits:[{t:'Sem Magias (Nível 1)',d:'Clérigos só obtêm magias a partir do nível 2.'},
   {t:'Expulsar Mortos-Vivos',d:'1 tentativa por encontro — apresente o símbolo sagrado.'},
   {t:'Armas',d:'Somente contundentes. Sem armas cortantes, sem flechas.'},
   {t:'Armadura',d:'Qualquer armadura, incluindo armaduras mágicas.'},
   {t:'Lei ou Caos (Lama, Nível 7)',d:'Deve se dedicar a um lado. Mudar após Patriarca: perde todos os benefícios.'}],
  langs:()=>['Comum',pick(['Latim Sagrado','Língua da Igreja','Rúnico Divino','Língua dos Ancestrais'])],
  align:()=>pick(['Leal','Leal','Leal','Neutro','Caótico']),
  xp:'Próximo nível (Adepto): 1.500 XP — Clérigos obtêm magias no nível 2.'},
 Dwarf:{label:'Anão',icon:'🪨',race:'Anão',maxLvl:'6',hd:'1',
  prime:['FOR'],saves:[8,9,10,11,12],
  savesNote:'Resistência mágica: +4 níveis efetivos em todas as salvaguardas (nível 1 salva como Guerreiro nível 5).',
  wep:()=>[pick(['Machado de Batalha','Maça','Machadinha','Espada'])],
  arm:()=>pick(['Couro (CA 12)','Couro + Escudo (CA 13)','Cota de Malha (CA 14)','Cota de Malha + Escudo (CA 15)']),
  acOf:a=>a.includes('CA 15')?15:a.includes('CA 14')?14:a.includes('CA 13')?13:12,gear:gBase,
  traits:[{t:'Resistência Mágica',d:'+4 níveis efetivos em TODAS as salvaguardas.'},
   {t:'Sentido da Pedra',d:'Detecta passagens inclinadas, armadilhas, paredes móveis e construções recentes.'},
   {t:'Armas',d:'Todas exceto arco longo e espada de duas mãos.'},
   {t:'Nível Máximo 6',d:'Não pode avançar além do Myrmidon.'}],
  langs:()=>['Comum','Anão','Gnomo','Kobold','Goblin'],
  align:()=>pick(['Leal','Leal','Neutro']),
  xp:'Próximo nível: 2.000 XP. Anões chegam no máximo ao nível 6.'},
 Elf:{label:'Elfo',icon:'🌿',race:'Elfo',maxLvl:'Guerr.4 / Mago 8',hd:'1',
  prime:['FOR','INT'],saves:[12,13,14,15,16],
  wep:()=>{const m=pick(['guerreiro','mago']);
   return m==='guerreiro'?[pick(['Espada Longa','Arco Longo (20 flechas)','Espada + Escudo']),'(modo Guerreiro esta sessão)']:['Adaga','(modo Mago — 1 feitiço disponível)'];},
  arm:()=>pick(['Couro (CA 12)','Couro + Escudo (CA 13)','Cota de Malha (CA 14)']),
  acOf:a=>a.includes('CA 14')?14:a.includes('CA 13')?13:12,gear:gElf,
  traits:[{t:'Troca de Classe',d:'Troca entre Guerreiro e Mago entre sessões — nunca durante aventura.'},
   {t:'Magia e Arma',d:'Usa magia e armas ao mesmo tempo. Usa armadura mágica como Mago.'},
   {t:'Detectar Portas',d:'4/6 ao buscar ativamente; 2/6 ao simplesmente passar pelas portas ocultas.'},
   {t:'Máximo',d:'Nível 4 como Guerreiro, nível 8 como Mago.'}],
  langs:()=>['Comum','Élfico','Orc','Hobgoblin','Gnoll'],
  align:()=>pick(['Leal','Leal','Neutro','Neutro']),
  xp:'Próximo nível: 2.000 XP (Guerreiro) ou 2.500 XP (Mago).'},
 Halfling:{label:'Halfling',icon:'🍃',race:'Halfling',maxLvl:'4',hd:'1',
  prime:['FOR'],saves:[8,9,10,11,12],
  savesNote:'Resistência mágica igual a Anões: +4 níveis efetivos em todas as salvaguardas.',
  wep:()=>[pick(['Espada Curta','Arco Curto (20 flechas)','Arremessadores (20 dardos)','Machadinha'])],
  arm:()=>pick(['Couro (CA 12)','Couro + Escudo (CA 13)','Cota de Malha (CA 14)']),
  acOf:a=>a.includes('CA 14')?14:a.includes('CA 13')?13:12,gear:gBase,
  traits:[{t:'Resistência Mágica',d:'+4 níveis efetivos em todas as salvaguardas, como Anões.'},
   {t:'Precisão de Arremesso',d:'Maior precisão com armas de arremesso entre todas as classes.'},
   {t:'Armas',d:'Todas exceto arco longo e espada de duas mãos.'},
   {t:'Nível Máximo 4',d:'Não pode avançar além do Herói.'}],
  langs:()=>['Comum','Halfling'],
  align:()=>pick(['Leal','Leal','Leal','Neutro']),
  xp:'Próximo nível: 2.000 XP. Halflings ficam no nível 4.'}
};

// ── UTILS ──────────────────────────────────────────────────────
const AN={FOR:'Força',INT:'Inteligência',SAB:'Sabedoria',CON:'Constituição',DES:'Destreza',CAR:'Carisma'};
function roll(n){return Math.floor(Math.random()*n)+1;}
function r3(){return roll(6)+roll(6)+roll(6);}
function pick(a){return a[Math.floor(Math.random()*a.length)];}
function modNote(k,v,isPrime){
  // Requisito principal: mostra bônus de XP
  if(isPrime){
    if(v>=15) return '+10% XP';
    if(v>=13) return '+5% XP';
    return 'Req. Principal';
  }
  if(k==='FOR') return v>=13?'+1 ataque corpo a corpo':v<=8?'-1 ataque':'—';
  if(k==='INT') return v>=13?'+1 idioma extra':v<=8?'Analfabeto':'—';
  if(k==='SAB') return v>=13?'+1 salvaguarda mágica':v<=8?'-1 salvaguarda':'—';
  if(k==='DES') return v>=13?'+1 ataque à distância':v<=8?'-1 ataque à distância':'—';
  if(k==='CON') return v>=15?'+1 pip/DV ao subir':v<=6?'-1 pip/DV':v<=8?'Sobrev. reduzida':'—';
  if(k==='CAR'){
    if(v<=4)  return '1 seguidor, -2 lealdade';
    if(v<=6)  return '2 seguidores, -1 leal.';
    if(v<=9)  return '3 seguidores';
    if(v<=12) return '4 seguidores';
    if(v<=15) return '5 seguidores, +1 leal.';
    if(v<=17) return '6 seguidores, +2 leal.';
    return '12 seguidores, +4 leal.';
  }
  return '—';
}

// ── SEX STATE ──────────────────────────────────────────────────
let sex='R';
function setSex(s){sex=s;['R','M','F'].forEach(x=>document.getElementById('s'+x).classList.toggle('on',x===s));}

// ── GENERATE ───────────────────────────────────────────────────
function gen(){
  const ck=document.getElementById('sc').value;
  const c=ck==='R'?CLS[pick(Object.keys(CLS))]:CLS[ck];
  const sx=sex==='R'?pick(['M','F']):sex;
  const A={FOR:r3(),INT:r3(),SAB:r3(),CON:r3(),DES:r3(),CAR:r3()};
  const gold=(roll(6)+roll(6)+roll(6))*10;
  const ak=document.getElementById('sa').value;
  const align=ak==='R'?c.align():ak;
  const name=sx==='F'?pick(NF):pick(NM);
  const ep=sx==='F'?pick(EF):pick(EM);
  const weps=c.wep(), armor=c.arm(), ac=c.acOf(armor), gear=c.gear();
  const langs=c.langs();
  const bp=Math.max(0,A.INT-10);
  const ep2=['Élfico','Anão','Gnomo','Goblin','Orc','Dragônico','Hobgoblin','Gnoll','Infernal','Halfling'];
  for(let i=0;i<bp;i++){const av=ep2.filter(l=>!langs.includes(l));if(av.length)langs.push(pick(av));}

  // header
  document.getElementById('cn').textContent=name;
  document.getElementById('ce').textContent=ep;
  document.getElementById('mc').textContent=`${c.icon} ${c.label}`;
  document.getElementById('ms').textContent=sx==='M'?'♂ Homem':'♀ Mulher';
  document.getElementById('mr').textContent=c.race;
  document.getElementById('mm').textContent=`Nível máx. ${c.maxLvl}`;
  document.getElementById('wm').textContent=name[0];
  const ac2=align==='Leal'?'law':align==='Caótico'?'chaos':'neutral';
  document.getElementById('mal').innerHTML=`<span class="ab ${ac2}">${align}</span>`;

  // attrs
  let aH='';
  Object.entries(A).forEach(([k,v],i)=>{
    const ip=c.prime.includes(k);
    const note=modNote(k,v,ip);
    const css=v>=15?'good':v<=8?'bad':'';
    aH+=`<div class="ab2${ip?' prime':''}" style="animation-delay:${i*.06}s">
     <span class="ak">${AN[k]}</span>
     <span class="av">${v}</span>
     <span class="an ${css}">${note}</span>
    </div>`;
  });
  document.getElementById('atrs').innerHTML=aH;

  // DV — sem PV, só o dado
  document.getElementById('dvb').textContent=c.hd;
  document.getElementById('cab').textContent=ac;
  let dvn=`<strong>Blackmoor usa apenas Dados de Vida</strong> — não há PV fixos. Você tem <em>${c.hd} DV</em> no nível 1 (role 1d6 ao subir). Cada ferimento grave consome 1 DV.`;
  if(A.CON>=15) dvn+=` CON alta: +1 pip ao rolar DV no próximo nível.`;
  if(A.CON<=6)  dvn+=` CON baixa: -1 pip ao rolar DV (mínimo 1).`;
  dvn+=` Chegou a 0 DV: <strong style="color:var(--blood)">morto</strong>.`;
  document.getElementById('dvn').innerHTML=dvn;

  // combat
  const atk=A.FOR>=13?'+1 (FOR alta)':A.FOR<=8?'-1 (FOR baixa)':'0';
  document.getElementById('cr').innerHTML=`
   <div class="sp"><span class="sl">Bônus de ataque</span><span class="sv2">${atk}</span></div>
   <div class="sp"><span class="sl">Dano por acerto</span><span class="sv2">1d6</span></div>
   <div class="sp"><span class="sl">Ouro inicial</span><span class="sv2" style="color:var(--gold)">${gold} PO</span></div>`;

  // saves
  const sv=c.saves;
  document.getElementById('svr').innerHTML=`<td>${sv[0]}</td><td>${sv[1]}</td><td>${sv[2]}</td><td>${sv[3]}</td><td>${sv[4]}</td>`;
  document.getElementById('svn').textContent=c.savesNote||'';

  // weapons
  document.getElementById('ew').innerHTML=
   weps.map(w=>w.startsWith('(')?`<li>${w}</li>`:`<li class="wp">${w}</li>`).join('')
   +`<li class="ar">${armor}</li>`;

  // gear
  document.getElementById('eg').innerHTML=
   gear.map(g=>`<li>${g}</li>`).join('')
   +`<li class="ge">${gold} peças de ouro (para equipamento adicional)</li>`;

  // traits
  document.getElementById('tr').innerHTML=c.traits.map(t=>`<div class="tr2"><span class="tt">${t.t}</span>${t.d}</div>`).join('');

  // langs
  document.getElementById('lg').innerHTML=langs.map(l=>`<span class="lpi">${l}</span>`).join('');

  // appearance
  document.getElementById('ap').innerHTML=appar(sx,A);

  // xp
  document.getElementById('xn').textContent=c.xp;

  // show
  const sh=document.getElementById('sheet');
  sh.classList.add('on');
  sh.scrollIntoView({behavior:'smooth',block:'start'});
}
</script>
</body>
</html>
