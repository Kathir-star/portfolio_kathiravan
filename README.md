<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>Kathiravan — Developer & Designer</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#0a0a0a;--bg2:#0f0f0f;--bg3:#141414;--bg4:#1a1a1a;
  --glass:rgba(255,255,255,0.03);--glass2:rgba(255,255,255,0.06);
  --border:rgba(255,255,255,0.07);--border2:rgba(255,255,255,0.13);
  --text:#ffffff;--muted:rgba(255,255,255,0.5);--dim:rgba(255,255,255,0.2);
  --g1:#7c3aed;--g2:#06b6d4;--g3:#10b981;--g4:#f59e0b;
  --glow1:rgba(124,58,237,0.25);--glow2:rgba(6,182,212,0.2);
  --font:'Poppins',sans-serif;--mono:'Space Mono',monospace;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--font);overflow-x:hidden;cursor:none;line-height:1.6}

/* ── CURSOR ── */
#cur{position:fixed;width:10px;height:10px;background:#fff;border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);mix-blend-mode:difference}
#cur2{position:fixed;width:38px;height:38px;border:1.5px solid rgba(124,58,237,.7);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:width .18s,height .18s,border-color .2s}

/* ── PARTICLES ── */
#particles{position:fixed;inset:0;z-index:0;pointer-events:none;opacity:.5}

/* ── GLOW ORBS ── */
.orb{position:fixed;border-radius:50%;filter:blur(140px);pointer-events:none;z-index:0}
.orb1{width:550px;height:550px;background:rgba(124,58,237,.15);top:-180px;left:-120px;animation:of1 10s ease-in-out infinite}
.orb2{width:450px;height:450px;background:rgba(6,182,212,.1);bottom:-120px;right:-80px;animation:of2 12s ease-in-out infinite}
@keyframes of1{0%,100%{transform:translate(0,0)}50%{transform:translate(35px,-25px)}}
@keyframes of2{0%,100%{transform:translate(0,0)}50%{transform:translate(-25px,35px)}}

/* ── LAYOUT ── */
.wrap{max-width:1080px;margin:0 auto;padding:0 48px;position:relative;z-index:2}

/* ── NAV ── */
nav{position:fixed;top:0;left:0;right:0;z-index:100;padding:0 48px;height:64px;display:flex;align-items:center;justify-content:space-between;background:rgba(10,10,10,.9);backdrop-filter:blur(20px);border-bottom:1px solid var(--border)}
.nav-brand{font-family:var(--font);font-size:15px;font-weight:700;letter-spacing:.04em;color:#ffffff;text-decoration:none;display:flex;align-items:center;gap:9px;text-shadow:0 0 20px rgba(124,58,237,.6)}
.nbdot{width:7px;height:7px;background:var(--g3);border-radius:50%;flex-shrink:0;animation:pulse 2s infinite}
@keyframes pulse{0%,100%{opacity:1;box-shadow:0 0 0 0 rgba(16,185,129,.5)}60%{opacity:.5;box-shadow:0 0 0 6px transparent}}
.nav-links{display:flex;gap:4px}
.nav-links a{font-size:12px;font-weight:500;letter-spacing:.05em;color:var(--muted);text-decoration:none;padding:7px 16px;border-radius:20px;transition:all .2s}
.nav-links a:hover{color:#fff;background:var(--glass2)}

/* ── BANNER ── */
.banner-wrap{position:relative;z-index:2;padding-top:64px}
.banner-wrap img{width:100%;display:block;max-height:240px;object-fit:cover;object-position:center 40%}
.banner-fade{position:absolute;inset:0;background:linear-gradient(to bottom,transparent 30%,var(--bg) 100%)}

/* ── HERO ── */
.hero{padding:52px 0 96px;position:relative;z-index:2}
.hero-inner{display:grid;grid-template-columns:1fr 400px;gap:64px;align-items:start}

.hero-greet{display:flex;align-items:center;gap:10px;margin-bottom:16px;animation:fadeUp .6s both}
.hero-greet img{width:30px;height:30px}
.hero-greet span{font-family:var(--mono);font-size:11px;letter-spacing:.2em;color:var(--muted)}
@keyframes fadeUp{from{opacity:0;transform:translateY(22px)}to{opacity:1;transform:translateY(0)}}

/* ── NAME — single word, pure white, visible ── */
.hname{
  font-size:clamp(52px,7vw,90px);
  font-weight:900;
  line-height:.95;
  letter-spacing:-.02em;
  margin-bottom:18px;
  color:#ffffff;
  text-shadow:0 0 40px rgba(255,255,255,.15),0 0 80px rgba(124,58,237,.25);
  animation:fadeUp .65s .06s both
}
.hname-accent{
  display:block;
  background:linear-gradient(135deg,#ffffff 0%,rgba(200,180,255,1) 40%,var(--g2) 100%);
  -webkit-background-clip:text;
  -webkit-text-fill-color:transparent;
  background-clip:text;
  animation:fadeUp .65s .12s both
}

.htype{font-family:var(--mono);font-size:12px;color:var(--muted);letter-spacing:.1em;margin-bottom:26px;min-height:18px;animation:fadeUp .65s .2s both}
.htype span{color:var(--g2);border-right:2px solid var(--g2);padding-right:2px;animation:blink .85s infinite}
@keyframes blink{0%,100%{border-color:var(--g2)}50%{border-color:transparent}}

.hbio{font-size:15.5px;color:rgba(255,255,255,.55);line-height:1.82;margin-bottom:28px;max-width:500px;animation:fadeUp .65s .26s both}
.hbio strong{color:#ffffff;font-weight:600}

.hbadges{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:28px;animation:fadeUp .65s .32s both}
.hbadge{font-family:var(--mono);font-size:10px;letter-spacing:.1em;padding:5px 14px;border-radius:20px;background:var(--glass);border:1px solid var(--border2);color:rgba(255,255,255,.55);transition:all .22s;cursor:default}
.hbadge:hover{background:var(--glass2);color:#fff;border-color:rgba(255,255,255,.25)}

.hcta{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:24px;animation:fadeUp .65s .38s both}
.btn-g{display:inline-flex;align-items:center;gap:8px;padding:12px 28px;border-radius:8px;text-decoration:none;background:linear-gradient(135deg,var(--g1),var(--g2));color:#fff;font-weight:600;font-size:13px;letter-spacing:.02em;transition:all .25s;box-shadow:0 0 24px rgba(124,58,237,.35);cursor:none}
.btn-g:hover{transform:translateY(-2px);box-shadow:0 10px 32px rgba(124,58,237,.5)}
.btn-o{display:inline-flex;align-items:center;gap:8px;padding:12px 28px;border-radius:8px;text-decoration:none;background:transparent;border:1px solid var(--border2);color:rgba(255,255,255,.6);font-weight:500;font-size:13px;transition:all .25s;cursor:none}
.btn-o:hover{color:#fff;border-color:rgba(255,255,255,.3);background:var(--glass2);transform:translateY(-2px)}

.hcounter{animation:fadeUp .65s .44s both}
.hcounter img{border-radius:4px;opacity:.65}

/* ── HERO RIGHT ── */
.hero-right{display:flex;flex-direction:column;gap:16px;animation:fadeUp .7s .14s both}
.hgif{width:100%;border-radius:16px;display:block;border:1px solid rgba(124,58,237,.3);box-shadow:0 0 48px rgba(124,58,237,.18)}

.term{background:var(--bg2);border:1px solid var(--border);border-radius:12px;padding:20px;font-family:var(--mono);font-size:11.5px;position:relative;overflow:hidden}
.term::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--g1),var(--g2),transparent)}
.tdots{display:flex;gap:6px;margin-bottom:14px}
.tdots span{width:10px;height:10px;border-radius:50%}
.tdots .tr{background:#ff5f57}.tdots .ty{background:#febc2e}.tdots .tg{background:#28c840}
.tl{line-height:1.9;color:rgba(255,255,255,.4)}
.tl .k{color:#c792ea}.tl .s{color:#c3e88d}.tl .v{color:#82aaff}.tl .p{color:var(--g2)}
.tcur{display:inline-block;width:7px;height:13px;background:var(--g3);vertical-align:middle;animation:blink .9s infinite}

/* ── SECTION HEAD ── */
.sec{padding:88px 0;position:relative;z-index:2}
.shead{display:flex;align-items:center;gap:16px;margin-bottom:52px}
.snum{font-family:var(--mono);font-size:10px;color:var(--g1);letter-spacing:.25em;background:rgba(124,58,237,.1);border:1px solid rgba(124,58,237,.2);padding:4px 10px;border-radius:4px}
.stitle{font-size:clamp(26px,3vw,38px);font-weight:800;letter-spacing:-.02em;color:#ffffff}
.sline{flex:1;height:1px;background:linear-gradient(90deg,var(--border2),transparent)}

/* ── ABOUT ── */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:44px}
.atext{font-size:15.5px;color:rgba(255,255,255,.5);line-height:1.85}
.atext strong{color:#ffffff;font-weight:600}
.atext p+p{margin-top:16px}

.acards{display:flex;flex-direction:column;gap:8px}
.acard{background:var(--glass);border:1px solid var(--border);border-radius:10px;padding:15px 20px;display:flex;justify-content:space-between;align-items:center;transition:all .25s}
.acard:hover{background:var(--glass2);border-color:var(--border2);transform:translateX(5px)}
.aclab{font-family:var(--mono);font-size:9px;letter-spacing:.18em;color:rgba(255,255,255,.25)}
.acval{font-size:13px;font-weight:600;color:#ffffff;text-align:right}
.acval.g{color:var(--g3)}

/* ── SKILLS ── */
.skills-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.skill-card{background:var(--glass);border:1px solid var(--border);border-radius:14px;padding:24px;transition:all .3s;position:relative;overflow:hidden;cursor:default}
.skill-card::before{content:'';position:absolute;inset:0;border-radius:14px;background:linear-gradient(135deg,rgba(124,58,237,.07),rgba(6,182,212,.04));opacity:0;transition:opacity .3s}
.skill-card:hover{border-color:rgba(124,58,237,.4);transform:translateY(-5px);box-shadow:0 16px 48px rgba(124,58,237,.12);background:var(--glass2)}
.skill-card:hover::before{opacity:1}
.sk-ico{font-size:20px;margin-bottom:10px;position:relative;z-index:1}
.sk-name{font-family:var(--mono);font-size:9px;letter-spacing:.2em;color:rgba(255,255,255,.3);margin-bottom:12px;position:relative;z-index:1}
.sk-img{display:block;height:34px;position:relative;z-index:1}
.stags{display:flex;flex-wrap:wrap;gap:5px;margin-top:6px;position:relative;z-index:1}
.stag{font-family:var(--mono);font-size:9px;letter-spacing:.08em;padding:3px 8px;border-radius:20px;background:rgba(255,255,255,.04);border:1px solid var(--border);color:rgba(255,255,255,.3)}

/* ── PROJECTS ── */
.projects-wrap{display:flex;flex-direction:column;gap:12px}
.pcard{background:var(--glass);border:1px solid var(--border);border-radius:16px;padding:28px 32px;display:grid;grid-template-columns:52px 1fr auto;gap:24px;align-items:center;transition:all .3s;position:relative;overflow:hidden;cursor:default}
.pcard::before{content:'';position:absolute;left:0;top:0;bottom:0;width:3px;border-radius:0 2px 2px 0;background:linear-gradient(180deg,var(--g1),var(--g2));transform:scaleY(0);transform-origin:bottom;transition:transform .4s cubic-bezier(.16,1,.3,1)}
.pcard:hover::before{transform:scaleY(1)}
.pcard:hover{background:var(--glass2);border-color:rgba(124,58,237,.3);transform:translateX(5px);box-shadow:0 8px 40px rgba(0,0,0,.3)}
.pnum{width:48px;height:48px;border-radius:12px;background:linear-gradient(135deg,rgba(124,58,237,.18),rgba(6,182,212,.15));border:1px solid rgba(124,58,237,.3);display:flex;align-items:center;justify-content:center;font-family:var(--mono);font-size:13px;font-weight:700;color:var(--g1)}
.pname{font-size:19px;font-weight:700;letter-spacing:-.01em;margin-bottom:5px;color:#ffffff}
.pdesc{font-size:13.5px;color:rgba(255,255,255,.48);line-height:1.65;margin-bottom:12px}
.ptags{display:flex;gap:5px;flex-wrap:wrap}
.ptag{font-family:var(--mono);font-size:9px;letter-spacing:.1em;padding:3px 9px;border-radius:20px;background:rgba(255,255,255,.04);border:1px solid var(--border);color:rgba(255,255,255,.3)}
.pact{display:flex;flex-direction:column;align-items:flex-end;gap:8px;min-width:110px}
.plnk{font-family:var(--mono);font-size:10px;letter-spacing:.1em;padding:9px 16px;border-radius:8px;text-decoration:none;border:1px solid var(--border2);color:rgba(255,255,255,.55);transition:all .2s;white-space:nowrap;background:var(--glass);cursor:none;display:block}
.plnk:hover{color:#fff;background:var(--glass2);border-color:rgba(255,255,255,.25)}
.phw{font-family:var(--mono);font-size:10px;letter-spacing:.1em;padding:9px 16px;border-radius:8px;border:1px solid var(--border);color:rgba(255,255,255,.25);background:var(--glass);display:block}
.pupc{font-family:var(--mono);font-size:10px;letter-spacing:.1em;padding:9px 16px;border-radius:8px;border:1px solid rgba(245,158,11,.3);color:var(--g4);background:rgba(245,158,11,.07);display:block}

/* ── GITHUB ── */
.gh-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}
.gh-grid img{width:100%;border-radius:12px;border:1px solid var(--border);display:block}

/* ── FOCUS ── */
.focus-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.fcard{background:var(--glass);border:1px solid var(--border);border-radius:14px;padding:26px 20px;transition:all .3s;position:relative;overflow:hidden;cursor:default}
.fcard::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--g1),var(--g2));transform:scaleX(0);transform-origin:left;transition:transform .4s cubic-bezier(.16,1,.3,1)}
.fcard:hover::before{transform:scaleX(1)}
.fcard:hover{background:var(--glass2);border-color:var(--border2);transform:translateY(-4px);box-shadow:0 12px 30px rgba(124,58,237,.12)}
.fdot{width:8px;height:8px;background:var(--g3);border-radius:50%;margin-bottom:16px;animation:pulse 2s infinite}
.ftitle{font-size:15px;font-weight:700;margin-bottom:5px;color:#ffffff}
.fsub{font-family:var(--mono);font-size:9px;color:rgba(255,255,255,.28);letter-spacing:.1em;line-height:1.6}

/* ── CONNECT ── */
.conn-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.ccard{background:var(--glass);border:1px solid var(--border);border-radius:14px;padding:28px 22px;text-decoration:none;display:flex;flex-direction:column;gap:10px;transition:all .3s;cursor:none;position:relative;overflow:hidden}
.ccard:hover{transform:translateY(-5px);box-shadow:0 20px 48px rgba(0,0,0,.35);border-color:var(--border2)}
.ccard::after{content:'';position:absolute;inset:0;border-radius:14px;opacity:0;transition:opacity .3s;pointer-events:none}
.ccard.li::after{background:linear-gradient(135deg,rgba(10,102,194,.14),transparent)}
.ccard.ig::after{background:linear-gradient(135deg,rgba(225,48,108,.14),transparent)}
.ccard.ct::after{background:linear-gradient(135deg,rgba(16,185,129,.14),transparent)}
.ccard:hover::after{opacity:1}
.cico{width:44px;height:44px;border-radius:11px;display:flex;align-items:center;justify-content:center;font-size:15px;font-weight:800;font-family:var(--mono);position:relative;z-index:1}
.cico.li{background:rgba(10,102,194,.2);color:#5aacf0;border:1px solid rgba(10,102,194,.3)}
.cico.ig{background:rgba(225,48,108,.2);color:#f472b6;border:1px solid rgba(225,48,108,.3)}
.cico.ct{background:rgba(16,185,129,.2);color:var(--g3);border:1px solid rgba(16,185,129,.3)}
.clabel{font-size:15px;font-weight:700;color:#ffffff;position:relative;z-index:1}
.csub{font-family:var(--mono);font-size:9px;color:rgba(255,255,255,.28);letter-spacing:.1em;position:relative;z-index:1}
.carr{font-size:16px;color:rgba(255,255,255,.22);position:relative;z-index:1;margin-top:auto;transition:all .2s;align-self:flex-end}
.ccard:hover .carr{color:#fff;transform:translate(3px,-3px)}

/* ── DIVIDER ── */
.gdiv{height:1px;background:linear-gradient(90deg,transparent,var(--g1),var(--g2),transparent);opacity:.3;position:relative;z-index:2}

/* ── QUOTE ── */
.quote-sec{padding:72px 0;position:relative;z-index:2}
.qinner{background:var(--glass);border:1px solid var(--border);border-radius:20px;padding:52px;text-align:center;position:relative;overflow:hidden}
.qinner::before{content:'';position:absolute;inset:0;border-radius:20px;background:linear-gradient(135deg,rgba(124,58,237,.1),rgba(6,182,212,.06));pointer-events:none}
.qinner::after{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,var(--g1),var(--g2),transparent)}
.qmark{font-size:72px;font-family:Georgia,serif;color:var(--g1);line-height:.4;opacity:.22;margin-bottom:20px;position:relative;z-index:1}
.qtext{font-size:clamp(18px,2.2vw,26px);font-weight:700;letter-spacing:-.01em;line-height:1.45;margin-bottom:18px;position:relative;z-index:1;color:#ffffff}
.qattr{font-family:var(--mono);font-size:10px;color:rgba(255,255,255,.25);letter-spacing:.22em;position:relative;z-index:1}

/* ── COFFEE ── */
.coffee-wrap{text-align:center;padding:16px 0 60px;position:relative;z-index:2}
.coffee-label{font-family:var(--mono);font-size:10px;letter-spacing:.2em;color:rgba(255,255,255,.22);margin-bottom:14px}
.coffee-btn{display:inline-flex;align-items:center;gap:10px;background:linear-gradient(135deg,#f59e0b,#fbbf24);color:#1a0a00;font-weight:700;font-size:13px;letter-spacing:.03em;padding:12px 30px;border-radius:10px;text-decoration:none;transition:all .25s;box-shadow:0 0 20px rgba(245,158,11,.22);cursor:none}
.coffee-btn:hover{transform:translateY(-3px);box-shadow:0 10px 32px rgba(245,158,11,.38)}

/* ── FOOTER ── */
footer{border-top:1px solid var(--border);padding:28px 0;display:flex;justify-content:space-between;align-items:center;position:relative;z-index:2}
.f1{font-family:var(--font);font-size:13px;font-weight:600;letter-spacing:.04em;color:rgba(255,255,255,.6)}
.f2{font-family:var(--mono);font-size:10px;color:rgba(255,255,255,.2);letter-spacing:.15em}
.f3{font-family:var(--mono);font-size:10px;color:rgba(255,255,255,.2);letter-spacing:.12em}

/* ── SCROLL REVEAL ── */
.rv{opacity:0;transform:translateY(22px);transition:opacity .7s ease,transform .7s ease}
.rv.in{opacity:1;transform:translateY(0)}
.rvl{opacity:0;transform:translateX(-22px);transition:opacity .7s ease,transform .7s ease}
.rvl.in{opacity:1;transform:translateX(0)}
.rvr{opacity:0;transform:translateX(22px);transition:opacity .7s ease,transform .7s ease}
.rvr.in{opacity:1;transform:translateX(0)}
.sg>*{opacity:0;transform:translateY(18px);transition:opacity .5s ease,transform .5s ease}
.sg.in>*:nth-child(1){opacity:1;transform:none;transition-delay:.04s}
.sg.in>*:nth-child(2){opacity:1;transform:none;transition-delay:.1s}
.sg.in>*:nth-child(3){opacity:1;transform:none;transition-delay:.16s}
.sg.in>*:nth-child(4){opacity:1;transform:none;transition-delay:.22s}
.sg.in>*:nth-child(5){opacity:1;transform:none;transition-delay:.28s}
.sg.in>*:nth-child(6){opacity:1;transform:none;transition-delay:.34s}

/* ── RESPONSIVE ── */
@media(max-width:900px){
  .wrap{padding:0 22px}
  nav{padding:0 22px}
  .hero-inner{grid-template-columns:1fr}
  .hero-right{order:-1}
  .hgif{max-height:200px;object-fit:cover;width:100%}
  .about-grid,.skills-grid,.gh-grid,.conn-grid{grid-template-columns:1fr}
  .focus-grid{grid-template-columns:1fr 1fr}
  .pcard{grid-template-columns:1fr;gap:14px}
  .pact{flex-direction:row;align-items:center;min-width:auto}
  .qinner{padding:32px 22px}
  footer{flex-direction:column;gap:10px;text-align:center}
}
@media(max-width:600px){
  .focus-grid,.skills-grid{grid-template-columns:1fr}
  .hname{font-size:clamp(42px,11vw,72px)}
}
</style>
</head>
<body>

<div id="cur"></div>
<div id="cur2"></div>
<canvas id="particles"></canvas>
<div class="orb orb1"></div>
<div class="orb orb2"></div>

<!-- NAV -->
<nav>
  <a href="#" class="nav-brand"><span class="nbdot"></span>KATHIRAVAN</a>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- BANNER -->
<div class="banner-wrap">
  <img src="https://user-images.githubusercontent.com/22107794/139580686-887df369-edb8-4bc8-b607-4fbf6d7e4866.gif" alt="Banner"/>
  <div class="banner-fade"></div>
</div>

<!-- HERO -->
<section class="hero">
  <div class="wrap">
    <div class="hero-inner">

      <!-- LEFT -->
      <div>
        <div class="hero-greet">
          <img src="https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif" alt="wave"/>
          <span>HEY THERE, I'M</span>
        </div>

        <!-- Single clean name, no split, white + glow -->
        <div class="hname">KATHIRAVAN</div>
        <div class="hname hname-accent" style="margin-top:-8px;margin-bottom:18px;font-size:clamp(20px,3vw,34px);font-weight:700;letter-spacing:.01em">Developer &amp; Designer.</div>

        <div class="htype"><span id="typer"></span></div>

        <p class="hbio">
          <strong>ECE student</strong> building at the intersection of circuits and code.
          I design clean UIs, ship full-stack web apps, and wire up real IoT hardware —
          all while running <strong>Artlane Diaries</strong>, my creative startup.
          Still learning. Always shipping.
        </p>

        <div class="hbadges">
          <span class="hbadge">🌍 India</span>
          <span class="hbadge">⚡ ECE + Dev + Design</span>
          <span class="hbadge">🤝 Open to Collab</span>
          <span class="hbadge">📚 Always Learning</span>
        </div>

        <div class="hcta">
          <a href="#projects" class="btn-g">View Projects →</a>
          <a href="https://www.linkedin.com/in/kathiravan-v-160555395" target="_blank" class="btn-o">LinkedIn ↗</a>
        </div>

        <div class="hcounter">
          <img src="https://komarev.com/ghpvc/?username=Kathir-star&style=flat-square&color=7c3aed&label=Profile+Views" alt="views"/>
        </div>
      </div>

      <!-- RIGHT -->
      <div class="hero-right">
        <!-- Coding / soldering themed dev GIF -->
        <img class="hgif"
          src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif"
          alt="Developer coding animation"/>
        <div class="term">
          <div class="tdots"><span class="tr"></span><span class="ty"></span><span class="tg"></span></div>
          <div class="tl"><span class="k">const</span> dev = {</div>
          <div class="tl">&nbsp;&nbsp;name:&nbsp;<span class="s">"Kathiravan"</span>,</div>
          <div class="tl">&nbsp;&nbsp;stack:&nbsp;<span class="v">["ECE","MERN","IoT"]</span>,</div>
          <div class="tl">&nbsp;&nbsp;mode:&nbsp;<span class="p">learning</span>&nbsp;+&nbsp;<span class="p">shipping</span>,</div>
          <div class="tl">&nbsp;&nbsp;goal:&nbsp;<span class="s">"build real things"</span></div>
          <div class="tl">};&nbsp;<span class="tcur"></span></div>
        </div>
      </div>

    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- ABOUT -->
<section class="sec" id="about">
  <div class="wrap">
    <div class="shead rv"><span class="snum">01</span><h2 class="stitle">About Me</h2><div class="sline"></div></div>
    <div class="about-grid">
      <div class="atext rvl">
        <p>I'm pursuing <strong>Electronics & Communication Engineering</strong> — but I've never stayed inside one box. I build IoT systems with real sensors and microcontrollers, then context-switch to designing web UIs that feel sharp and intentional.</p>
        <p>Somewhere at the intersection of <strong>hardware and software</strong>, between circuits and interfaces, I found my thing. I care about how systems work at the low level and how they feel at the user level.</p>
        <p>I've completed <strong>Python and Advanced Java</strong> and I'm actively growing across the MERN stack, embedded systems, and UI/UX. I also run <strong>Artlane Diaries</strong> — a creative startup blending art with emotion and design.</p>
        <p>The mindset: learn hard, build honestly, ship consistently.</p>
      </div>
      <div class="acards sg rvr">
        <div class="acard"><span class="aclab">DEGREE</span><span class="acval">B.E. Electronics &amp; Comm.</span></div>
        <div class="acard"><span class="aclab">LOCATION</span><span class="acval">India 🇮🇳</span></div>
        <div class="acard"><span class="aclab">COMPLETED</span><span class="acval">Python + Advanced Java</span></div>
        <div class="acard"><span class="aclab">FOCUS</span><span class="acval">IoT · Full Stack · UI/UX</span></div>
        <div class="acard"><span class="aclab">STARTUP</span><span class="acval">Artlane Diaries — Founder</span></div>
        <div class="acard"><span class="aclab">STATUS</span><span class="acval g">● Learning + Building</span></div>
      </div>
    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- SKILLS -->
<section class="sec" id="skills">
  <div class="wrap">
    <div class="shead rv"><span class="snum">02</span><h2 class="stitle">Skills</h2><div class="sline"></div></div>
    <div class="skills-grid sg">
      <div class="skill-card">
        <div class="sk-ico">💻</div><div class="sk-name">PROGRAMMING</div>
        <img class="sk-img" src="https://skillicons.dev/icons?i=html,css,js,python,c,typescript&theme=dark" alt="Programming"/>
      </div>
      <div class="skill-card">
        <div class="sk-ico">⚙️</div><div class="sk-name">FRAMEWORKS</div>
        <img class="sk-img" src="https://skillicons.dev/icons?i=react,nodejs,express,django,flutter,tailwind&theme=dark" alt="Frameworks"/>
      </div>
      <div class="skill-card">
        <div class="sk-ico">🔌</div><div class="sk-name">ECE / IoT</div>
        <div class="stags">
          <span class="stag">ESP32</span><span class="stag">MQ3</span><span class="stag">MPU6050</span>
          <span class="stag">IR Sensor</span><span class="stag">ESP-NOW</span><span class="stag">Embedded C</span>
          <span class="stag">Automation</span><span class="stag">Telegram Bot</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="sk-ico">🗄️</div><div class="sk-name">DATABASES</div>
        <img class="sk-img" src="https://skillicons.dev/icons?i=mongodb,firebase,mysql,postgresql&theme=dark" alt="Databases"/>
      </div>
      <div class="skill-card">
        <div class="sk-ico">🎨</div><div class="sk-name">DESIGN</div>
        <div class="stags">
          <span class="stag">UI/UX Design</span><span class="stag">Figma</span>
          <span class="stag">Graphic Design</span><span class="stag">Digital Art</span>
          <span class="stag">Web Design</span><span class="stag">Prototyping</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="sk-ico">🧰</div><div class="sk-name">TOOLS</div>
        <img class="sk-img" src="https://skillicons.dev/icons?i=git,figma,vscode,postman,androidstudio&theme=dark" alt="Tools"/>
      </div>
    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- PROJECTS -->
<section class="sec" id="projects">
  <div class="wrap">
    <div class="shead rv"><span class="snum">03</span><h2 class="stitle">Projects</h2><div class="sline"></div></div>
    <div class="projects-wrap">

      <div class="pcard rv">
        <div class="pnum">01</div>
        <div>
          <div class="pname">Level Up</div>
          <div class="pdesc">A self-growth fitness PWA with an AI coach persona, Indian food database, bodyweight programs across goals and experience levels, and voice I/O. Built and deployed live.</div>
          <div class="ptags"><span class="ptag">HTML/CSS/JS</span><span class="ptag">PWA</span><span class="ptag">AI Coach</span><span class="ptag">Live</span></div>
        </div>
        <div class="pact"><a href="https://kathir-star.github.io/levelup.github.io/" target="_blank" class="plnk">VISIT ↗</a></div>
      </div>

      <div class="pcard rv">
        <div class="pnum">02</div>
        <div>
          <div class="pname">RYDEX Smart Helmet</div>
          <div class="pdesc">IoT safety system on two ESP32s via ESP-NOW. Detects alcohol (MQ3), accidents (MPU6050), and helmet state (IR). Sends real-time Telegram alerts with GPS on trigger.</div>
          <div class="ptags"><span class="ptag">ESP32</span><span class="ptag">ESP-NOW</span><span class="ptag">MQ3</span><span class="ptag">MPU6050</span><span class="ptag">IoT</span><span class="ptag">C++</span></div>
        </div>
        <div class="pact"><span class="phw">HARDWARE</span></div>
      </div>

      <div class="pcard rv">
        <div class="pnum">03</div>
        <div>
          <div class="pname">Artlane Diaries</div>
          <div class="pdesc">Creative startup offering custom hand-drawn portraits, personalized gifts, and memory-based artworks. Blending emotional storytelling with intentional design. Founder & designer.</div>
          <div class="ptags"><span class="ptag">Creative Startup</span><span class="ptag">UI/UX</span><span class="ptag">Art</span><span class="ptag">Design</span></div>
        </div>
        <div class="pact"><span class="pupc">UPCOMING ⟶</span></div>
      </div>

    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- GITHUB -->
<section class="sec">
  <div class="wrap">
    <div class="shead rv"><span class="snum">04</span><h2 class="stitle">GitHub</h2><div class="sline"></div></div>
    <div class="gh-grid rv">
      <img src="https://streak-stats.demolab.com?user=Kathir-star&theme=dark&hide_border=true&background=0a0a0a&ring=7c3aed&fire=06b6d4&currStreakLabel=aaaacc&sideLabels=555577&dates=444466" alt="GitHub Streak"/>
      <img src="https://github-readme-stats.vercel.app/api?username=Kathir-star&show_icons=true&theme=dark&hide_border=true&bg_color=0a0a0a&title_color=ffffff&icon_color=7c3aed&text_color=555577" alt="GitHub Stats"/>
    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- FOCUS -->
<section class="sec">
  <div class="wrap">
    <div class="shead rv"><span class="snum">05</span><h2 class="stitle">Current Focus</h2><div class="sline"></div></div>
    <div class="focus-grid sg">
      <div class="fcard"><div class="fdot"></div><div class="ftitle">Full Stack</div><div class="fsub">MERN STACK<br/>DEEPENING BACKEND</div></div>
      <div class="fcard"><div class="fdot" style="animation-delay:.4s"></div><div class="ftitle">IoT Systems</div><div class="fsub">ESP32 + SENSORS<br/>REAL HARDWARE BUILDS</div></div>
      <div class="fcard"><div class="fdot" style="animation-delay:.8s"></div><div class="ftitle">Artlane Diaries</div><div class="fsub">CREATIVE STARTUP<br/>GROWING THE BRAND</div></div>
      <div class="fcard"><div class="fdot" style="animation-delay:1.2s"></div><div class="ftitle">Daily Reps</div><div class="fsub">CODE EVERY DAY<br/>CONSISTENCY COMPOUNDS</div></div>
    </div>
  </div>
</section>

<div class="gdiv"></div>

<!-- CONNECT -->
<section class="sec" id="contact">
  <div class="wrap">
    <div class="shead rv"><span class="snum">06</span><h2 class="stitle">Connect</h2><div class="sline"></div></div>
    <div class="conn-grid sg">
      <a href="https://www.linkedin.com/in/kathiravan-v-160555395" target="_blank" class="ccard li">
        <div class="cico li">in</div>
        <div class="clabel">LinkedIn</div>
        <div class="csub">PROFESSIONAL NETWORK</div>
        <div class="carr">↗</div>
      </a>
      <a href="https://www.instagram.com/_kathir_offlx/" target="_blank" class="ccard ig">
        <div class="cico ig">ig</div>
        <div class="clabel">Instagram</div>
        <div class="csub">@_KATHIR_OFFLX</div>
        <div class="carr">↗</div>
      </a>
      <a href="https://drive.google.com/drive/folders/1kFMHmtgHhTsYsVkYpgP-EQe8S88Vsmxq" target="_blank" class="ccard ct">
        <div class="cico ct">↓</div>
        <div class="clabel">Certificates</div>
        <div class="csub">GOOGLE DRIVE</div>
        <div class="carr">↗</div>
      </a>
    </div>
  </div>
</section>

<!-- QUOTE -->
<div class="quote-sec">
  <div class="wrap">
    <div class="qinner rv">
      <div class="qmark">"</div>
      <div class="qtext">Keep building. Keep learning.<br/>One step every day.</div>
      <div class="qattr">— THE CODE I LIVE BY</div>
    </div>
  </div>
</div>

<!-- COFFEE -->
<div class="coffee-wrap rv">
  <div class="coffee-label">IF MY WORK HELPED YOU</div>
  <a href="#" class="coffee-btn">☕ Buy Me a Coffee</a>
</div>

<!-- FOOTER -->
<div class="wrap">
  <footer class="rv">
    <span class="f1">KATHIRAVAN</span>
    <span class="f2">CIRCUITS TO CODE ⚡</span>
    <span class="f3">INDIA · 2025</span>
  </footer>
</div>

<script>
/* ── Cursor ── */
const cur=document.getElementById('cur'),cur2=document.getElementById('cur2');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px'});
(function loop(){rx+=(mx-rx)*.13;ry+=(my-ry)*.13;cur2.style.left=rx+'px';cur2.style.top=ry+'px';requestAnimationFrame(loop)})();
document.querySelectorAll('a,button,.pcard,.skill-card,.fcard,.ccard,.acard').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur2.style.width='58px';cur2.style.height='58px';cur2.style.borderColor='rgba(6,182,212,.55)'});
  el.addEventListener('mouseleave',()=>{cur2.style.width='38px';cur2.style.height='38px';cur2.style.borderColor='rgba(124,58,237,.7)'});
});

/* ── Scroll reveal ── */
const io=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting){x.target.classList.add('in');io.unobserve(x.target)}})},{threshold:.08});
document.querySelectorAll('.rv,.rvl,.rvr,.sg').forEach(el=>io.observe(el));

/* ── Typewriter ── */
const phrases=['Full Stack Developer.','UI/UX Designer.','ECE Engineer.','IoT Builder.','Creative Founder.'];
let pi=0,ci=0,del=false;
const typer=document.getElementById('typer');
function type(){
  const w=phrases[pi];
  if(!del){typer.textContent=w.slice(0,++ci);if(ci===w.length){del=true;setTimeout(type,1900);return}}
  else{typer.textContent=w.slice(0,--ci);if(ci===0){del=false;pi=(pi+1)%phrases.length;setTimeout(type,350);return}}
  setTimeout(type,del?55:90);
}
setTimeout(type,800);

/* ── Particles ── */
const canvas=document.getElementById('particles'),ctx=canvas.getContext('2d');
let W,H,pts=[];
function resize(){W=canvas.width=innerWidth;H=canvas.height=innerHeight}
resize();
window.addEventListener('resize',()=>{resize();init()});
function init(){
  pts=[];
  const n=Math.floor(W*H/15000);
  for(let i=0;i<n;i++)pts.push({x:Math.random()*W,y:Math.random()*H,vx:(Math.random()-.5)*.26,vy:(Math.random()-.5)*.26,r:Math.random()*1.2+.4});
}
init();
(function draw(){
  ctx.clearRect(0,0,W,H);
  pts.forEach(p=>{
    p.x+=p.vx;p.y+=p.vy;
    if(p.x<0||p.x>W)p.vx*=-1;
    if(p.y<0||p.y>H)p.vy*=-1;
    ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);
    ctx.fillStyle='rgba(124,58,237,.38)';ctx.fill();
  });
  for(let i=0;i<pts.length;i++)for(let j=i+1;j<pts.length;j++){
    const dx=pts[i].x-pts[j].x,dy=pts[i].y-pts[j].y,d=Math.hypot(dx,dy);
    if(d<105){
      ctx.beginPath();ctx.moveTo(pts[i].x,pts[i].y);ctx.lineTo(pts[j].x,pts[j].y);
      ctx.strokeStyle=`rgba(124,58,237,${.16*(1-d/105)})`;ctx.lineWidth=.5;ctx.stroke();
    }
  }
  requestAnimationFrame(draw);
})();
</script>
</body>
</html>
