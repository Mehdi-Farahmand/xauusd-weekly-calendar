<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>XAU/USD — تحلیل اخبار اقتصادی</title>
<link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;600;700;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --g:#C9A84C;--g2:#F5E4A8;--g3:#E8C96A;--g4:#8B6914;
  --bg:#090909;--bg2:#0F0F0F;--bg3:#141414;
  --glass:rgba(255,255,255,0.04);--glass2:rgba(255,255,255,0.07);--glass3:rgba(255,255,255,0.10);
  --gb:rgba(201,168,76,0.08);--gb2:rgba(201,168,76,0.14);
  --border:rgba(255,255,255,0.08);--border2:rgba(201,168,76,0.25);--border3:rgba(255,255,255,0.12);
  --bull:#1DB87A;--bear:#E05252;--neu:#8A8A8A;--warn:#E09340;
  --text:#F0EDE6;--text2:#A8A39A;--text3:#5A5650;
  --shadow:0 8px 32px rgba(0,0,0,0.6);
  --shadow2:0 16px 64px rgba(0,0,0,0.8);
  --glow:0 0 40px rgba(201,168,76,0.15);
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:'Vazirmatn',Tahoma,sans-serif;overflow-x:hidden;min-height:100vh}

.bg-orb{position:fixed;border-radius:50%;pointer-events:none;z-index:0;filter:blur(80px)}
.orb1{width:600px;height:600px;background:radial-gradient(circle,rgba(201,168,76,0.07) 0%,transparent 70%);top:-200px;right:-200px;animation:orbFloat 12s ease-in-out infinite}
.orb2{width:400px;height:400px;background:radial-gradient(circle,rgba(201,168,76,0.05) 0%,transparent 70%);bottom:-100px;left:-100px;animation:orbFloat 16s ease-in-out 4s infinite reverse}
.orb3{width:300px;height:300px;background:radial-gradient(circle,rgba(255,255,255,0.02) 0%,transparent 70%);top:40%;left:30%;animation:orbFloat 20s ease-in-out 2s infinite}
@keyframes orbFloat{0%,100%{transform:translate(0,0) scale(1)}33%{transform:translate(30px,-40px) scale(1.05)}66%{transform:translate(-20px,20px) scale(0.97)}}

/* NAVBAR */
.navbar{position:fixed;top:0;left:0;right:0;z-index:100;height:56px;display:flex;align-items:center;justify-content:space-between;padding:0 24px;
  background:rgba(9,9,9,0.6);backdrop-filter:blur(24px) saturate(180%);-webkit-backdrop-filter:blur(24px) saturate(180%);
  border-bottom:1px solid var(--border);transition:all .3s}
.navbar.scrolled{background:rgba(9,9,9,0.85);box-shadow:0 1px 0 var(--border2),var(--glow)}
.nav-brand{display:flex;align-items:center;gap:10px}
.nav-dot{width:7px;height:7px;border-radius:50%;background:var(--g);box-shadow:0 0 8px var(--g);animation:blink 2s ease-in-out infinite}
@keyframes blink{0%,100%{opacity:1;box-shadow:0 0 10px var(--g),0 0 20px rgba(201,168,76,.3)}50%{opacity:.3;box-shadow:none}}
.nav-name-fa{font-size:14px;font-weight:700;color:var(--text);letter-spacing:.3px}
.nav-name-sub{font-size:10px;color:var(--text3);letter-spacing:1px;margin-top:1px}
.nav-right{display:flex;align-items:center;gap:8px}
.nav-tag{font-size:10px;padding:4px 10px;border-radius:20px;background:var(--gb);color:var(--g3);border:1px solid var(--border2);letter-spacing:.5px;display:none}
@media(min-width:480px){.nav-tag{display:inline-flex}}
.nav-ig{font-size:11px;padding:5px 14px;border-radius:20px;
  background:linear-gradient(135deg,rgba(201,168,76,0.2),rgba(201,168,76,0.08));
  color:var(--g3);font-weight:600;text-decoration:none;letter-spacing:.3px;
  border:1px solid var(--border2);backdrop-filter:blur(8px);transition:all .25s}
.nav-ig:hover{background:linear-gradient(135deg,rgba(201,168,76,0.35),rgba(201,168,76,0.15));box-shadow:0 0 20px rgba(201,168,76,.2);transform:translateY(-1px)}

/* HERO */
.hero{min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:80px 20px 60px;position:relative;z-index:1;overflow:hidden}
.hero-tag{display:inline-flex;align-items:center;gap:8px;
  background:rgba(201,168,76,0.06);border:1px solid rgba(201,168,76,0.2);
  border-radius:100px;padding:7px 18px;font-size:11px;color:var(--g3);letter-spacing:2px;text-transform:uppercase;
  margin-bottom:36px;animation:fadeUp .8s ease both;backdrop-filter:blur(8px)}
.hero-h1{font-size:clamp(44px,8vw,96px);font-weight:900;line-height:.95;letter-spacing:-3px;color:var(--text);animation:fadeUp .9s ease .1s both}
.hero-h1 span{background:linear-gradient(135deg,#8B6914 0%,#C9A84C 35%,#F5E4A8 60%,#C9A84C 80%,#8B6914 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  filter:drop-shadow(0 0 30px rgba(201,168,76,.3))}
.hero-en{font-size:clamp(11px,1.5vw,16px);font-weight:300;color:var(--text3);letter-spacing:8px;text-transform:uppercase;margin-top:16px;animation:fadeUp .9s ease .2s both}
.hero-line{width:1px;height:60px;background:linear-gradient(180deg,transparent,var(--g),transparent);margin:32px auto;animation:fadeIn 1s ease .4s both}
.hero-sub{font-size:15px;color:var(--text2);line-height:2;max-width:420px;animation:fadeUp 1s ease .3s both;margin-bottom:44px}
.hero-cta{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;animation:fadeUp 1s ease .5s both}

.btn-gold{border:none;border-radius:14px;padding:13px 28px;font-size:13px;font-weight:700;cursor:pointer;font-family:'Vazirmatn',sans-serif;
  background:linear-gradient(135deg,rgba(201,168,76,.25),rgba(201,168,76,.1));
  color:var(--g2);border:1px solid rgba(201,168,76,.3);backdrop-filter:blur(12px);
  transition:all .3s;letter-spacing:.3px;position:relative;overflow:hidden}
.btn-gold::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(201,168,76,.15),transparent);opacity:0;transition:opacity .3s}
.btn-gold:hover::before{opacity:1}
.btn-gold:hover{transform:translateY(-2px);box-shadow:0 8px 32px rgba(201,168,76,.2),0 0 0 1px rgba(201,168,76,.4)}
.btn-ghost{background:rgba(255,255,255,0.04);color:var(--text2);border:1px solid var(--border3);border-radius:14px;padding:13px 28px;font-size:13px;font-weight:600;cursor:pointer;font-family:'Vazirmatn',sans-serif;backdrop-filter:blur(8px);transition:all .3s}
.btn-ghost:hover{background:rgba(255,255,255,0.08);border-color:var(--border2);color:var(--text);transform:translateY(-2px)}

.scroll-ind{position:absolute;bottom:32px;left:50%;transform:translateX(-50%);display:flex;flex-direction:column;align-items:center;gap:8px;cursor:pointer;animation:fadeIn 2s ease 1.5s both;opacity:.5}
.scroll-ind:hover{opacity:1}
.scroll-ind span{font-size:9px;color:var(--text3);letter-spacing:3px;text-transform:uppercase}
.scroll-arr{width:1px;height:40px;background:linear-gradient(180deg,var(--g),transparent);animation:scrollGrow 2s ease-in-out infinite}
@keyframes scrollGrow{0%,100%{height:20px;opacity:.3}50%{height:44px;opacity:.8}}

/* CLOCKS BAR — only 2 clocks, centered */
.clocks-bar{position:relative;z-index:1;padding:16px 20px;display:flex;justify-content:center;gap:0;
  background:rgba(255,255,255,0.02);backdrop-filter:blur(20px);-webkit-backdrop-filter:blur(20px);
  border-top:1px solid var(--border);border-bottom:1px solid var(--border)}
.clock-item{text-align:center;padding:0 40px;border-right:1px solid var(--border)}
.clock-item:last-child{border-right:none}
.clock-city{font-size:9px;letter-spacing:2px;color:var(--text3);text-transform:uppercase;margin-bottom:4px;display:flex;align-items:center;justify-content:center;gap:5px}
.clock-time{font-family:'SF Mono',Courier,monospace;font-size:15px;font-weight:700;color:var(--g3);letter-spacing:1.5px}

/* شیر و خورشید flag inline SVG */
.lion-flag{display:inline-block;vertical-align:middle}

.gold-div{height:1px;background:linear-gradient(90deg,transparent,rgba(201,168,76,0.2),transparent);position:relative;z-index:1}

section{position:relative;z-index:1;padding:72px 20px}
.container{max-width:960px;margin:0 auto}
.sec-label{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--g3);margin-bottom:12px;font-weight:700}
.sec-title{font-size:clamp(24px,4vw,36px);font-weight:900;line-height:1.15;color:var(--text);margin-bottom:8px}
.sec-sub{font-size:13px;color:var(--text2);line-height:1.8;max-width:500px}

.reveal{opacity:0;transform:translateY(28px);transition:opacity .7s ease,transform .7s ease}
.reveal.in{opacity:1;transform:none}

.week-header{display:grid;grid-template-columns:repeat(5,1fr);gap:10px;margin-bottom:12px}
.week-day-btn{
  background:var(--glass);border:1px solid var(--border);border-radius:16px;padding:16px 8px 14px;
  text-align:center;cursor:pointer;transition:all .3s;position:relative;overflow:hidden;
  backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px)}
.week-day-btn::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,0.06),transparent);opacity:0;transition:opacity .3s}
.week-day-btn:hover::before{opacity:1}
.week-day-btn:hover{border-color:rgba(201,168,76,.3);transform:translateY(-3px);box-shadow:var(--shadow),0 0 0 1px rgba(201,168,76,.15)}
.week-day-btn.active{border-color:rgba(201,168,76,.4);background:rgba(201,168,76,.06);box-shadow:0 0 30px rgba(201,168,76,.1),0 0 0 1px rgba(201,168,76,.2)}
.week-day-btn.active .wd-name{color:var(--g3)}
.wd-greg{font-size:9px;color:var(--text3);letter-spacing:1.5px;margin-bottom:5px;text-transform:uppercase}
.wd-name{font-size:12px;font-weight:700;color:var(--text2);margin-bottom:5px;transition:color .3s}
.wd-shamsi{font-size:10px;color:var(--text3);margin-bottom:10px;font-weight:500}
.wd-dots{display:flex;gap:3px;justify-content:center;flex-wrap:wrap}
.wd-dot{width:7px;height:7px;border-radius:50%}
.wd-dot.h{background:var(--bear);box-shadow:0 0 4px rgba(224,82,82,.5)}
.wd-dot.m{background:var(--warn);box-shadow:0 0 4px rgba(224,147,64,.4)}
.wd-dot.l{background:var(--text3);opacity:.4}

.day-panel{
  background:rgba(255,255,255,0.03);border:1px solid var(--border3);border-radius:24px;overflow:hidden;
  box-shadow:var(--shadow2),inset 0 1px 0 rgba(255,255,255,0.06);
  backdrop-filter:blur(24px);-webkit-backdrop-filter:blur(24px);transition:all .35s}
.day-panel-header{padding:24px 24px 20px;
  background:linear-gradient(135deg,rgba(201,168,76,0.05),rgba(255,255,255,0.02));
  border-bottom:1px solid var(--border)}
.dph-top{display:flex;justify-content:space-between;align-items:flex-start;flex-wrap:wrap;gap:14px;margin-bottom:14px}
.dph-date{display:flex;flex-direction:column;gap:4px}
.dph-day{font-size:20px;font-weight:900;color:var(--text)}
.dph-dates{font-size:11px;color:var(--text3);display:flex;gap:12px}
.dph-badge{font-size:10px;padding:5px 14px;border-radius:20px;font-weight:700;letter-spacing:.5px;backdrop-filter:blur(8px)}
.dph-badge.bull{background:rgba(29,184,122,.1);color:#1DB87A;border:1px solid rgba(29,184,122,.2)}
.dph-badge.bear{background:rgba(224,82,82,.1);color:#E05252;border:1px solid rgba(224,82,82,.2)}
.dph-badge.neu{background:rgba(138,138,138,.1);color:var(--neu);border:1px solid rgba(138,138,138,.2)}
.bias-pills{display:flex;gap:6px;flex-wrap:wrap}
.bias-pill{font-size:10px;padding:4px 11px;border-radius:20px;font-weight:700;border:1px solid;backdrop-filter:blur(8px)}
.bp-bull{background:rgba(29,184,122,.07);color:#1DB87A;border-color:rgba(29,184,122,.2)}
.bp-bear{background:rgba(224,82,82,.07);color:#E05252;border-color:rgba(224,82,82,.2)}
.bp-neu{background:rgba(138,138,138,.07);color:var(--neu);border-color:rgba(138,138,138,.2)}

.ev-table{width:100%;border-collapse:collapse}
.ev-table th{font-size:9px;letter-spacing:2px;text-transform:uppercase;color:var(--text3);padding:12px 14px;text-align:right;font-weight:700;background:rgba(255,255,255,0.02);border-bottom:1px solid var(--border)}
.ev-row{border-bottom:1px solid rgba(255,255,255,0.04);transition:background .2s;cursor:default;animation:rowIn .4s ease both}
@keyframes rowIn{from{opacity:0;transform:translateX(-6px)}to{opacity:1;transform:none}}
.ev-row:hover{background:rgba(201,168,76,0.04)}
.ev-row td{padding:12px 14px;font-size:12px;text-align:right;vertical-align:middle}
.ev-name{font-weight:600;color:var(--text);line-height:1.4;font-size:12px}
.ev-name-sub{font-size:10px;color:var(--text3);font-weight:400;margin-top:2px}
.imp-badge{display:inline-flex;align-items:center;font-size:10px;font-weight:700;padding:3px 8px;border-radius:6px}
.imp-h{background:rgba(224,82,82,.1);color:#E05252;border:1px solid rgba(224,82,82,.15)}
.imp-m{background:rgba(224,147,64,.1);color:var(--warn);border:1px solid rgba(224,147,64,.15)}
.imp-l{background:rgba(138,138,138,.08);color:var(--neu);border:1px solid rgba(138,138,138,.12)}
.cur-badge{font-size:10px;font-weight:700;padding:3px 8px;border-radius:6px;letter-spacing:.5px}
.cur-usd{background:rgba(29,184,122,.1);color:#1DB87A;border:1px solid rgba(29,184,122,.15)}
.cur-jpy{background:rgba(55,138,221,.1);color:#5B9FE0;border:1px solid rgba(55,138,221,.15)}
.cur-eur{background:rgba(130,110,230,.1);color:#9B8FE0;border:1px solid rgba(130,110,230,.15)}
.xau-up{color:var(--bull);font-weight:700;font-size:11px}
.xau-dn{color:var(--bear);font-weight:700;font-size:11px}
.xau-ne{color:var(--neu);font-weight:600;font-size:11px}
.ev-num{font-family:'SF Mono',monospace;font-size:11px;color:var(--text2)}
.ev-time{font-family:'SF Mono',Courier,monospace;font-size:11px;color:var(--g3);font-weight:700}

.summary-wrap{display:grid;grid-template-columns:1fr 1fr;gap:14px;padding:18px;background:rgba(0,0,0,0.2);border-top:1px solid var(--border)}
@media(max-width:580px){.summary-wrap{grid-template-columns:1fr}}
.sum-card{background:rgba(255,255,255,0.03);border-radius:14px;padding:16px;border:1px solid var(--border);backdrop-filter:blur(8px)}
.sum-card-title{font-size:9px;font-weight:700;color:var(--text3);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px}
.sum-text{font-size:12px;color:var(--text2);line-height:1.9}
.sum-chain{display:flex;flex-direction:column}
.sc-item{display:flex;align-items:flex-start;gap:10px}
.sc-dot{width:7px;height:7px;border-radius:50%;background:var(--g);flex-shrink:0;margin-top:5px;box-shadow:0 0 6px rgba(201,168,76,.5)}
.sc-line{width:1px;height:18px;background:linear-gradient(180deg,rgba(201,168,76,.4),transparent);margin:0 0 0 3px}
.sc-text{padding-bottom:14px}
.sc-step{font-size:9px;font-weight:700;color:var(--g3);letter-spacing:1.5px;text-transform:uppercase}
.sc-val{font-size:11px;color:var(--text2);margin-top:3px;line-height:1.6}

.prob-row{display:flex;height:28px;border-radius:10px;overflow:hidden;margin-top:10px;background:rgba(255,255,255,0.04)}
.prob-bull{background:linear-gradient(90deg,#0E6E50,#1DB87A);display:flex;align-items:center;justify-content:center;color:#fff;font-size:10px;font-weight:700;transition:width 1.2s cubic-bezier(.4,0,.2,1)}
.prob-neu{background:linear-gradient(90deg,#555,#8A8A8A);display:flex;align-items:center;justify-content:center;color:#fff;font-size:10px;font-weight:700;transition:width 1.2s cubic-bezier(.4,0,.2,1) .1s}
.prob-bear{background:linear-gradient(90deg,#8B2020,#E05252);display:flex;align-items:center;justify-content:center;color:#fff;font-size:10px;font-weight:700;transition:width 1.2s cubic-bezier(.4,0,.2,1) .2s}

.tg-outer{padding:18px;border-top:1px solid var(--border)}
.tg-label{font-size:9px;font-weight:700;color:var(--text3);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px}
.tg-card{background:rgba(23,33,43,0.9);border-radius:16px;padding:18px;font-family:'Vazirmatn',sans-serif;border:1px solid rgba(255,255,255,0.06);position:relative;backdrop-filter:blur(12px)}
.tg-hdr{display:flex;align-items:center;gap:10px;margin-bottom:14px;padding-bottom:12px;border-bottom:1px solid rgba(255,255,255,.05)}
.tg-av{width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,var(--g),var(--g4));display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:#fff;flex-shrink:0}
.tg-ch{font-size:12px;font-weight:700;color:#E0E8F0}
.tg-vs{font-size:9px;color:#3A4A5A;margin-top:1px}
.tg-body{font-size:12px;line-height:2;color:#A0B8C8;white-space:pre-wrap;direction:rtl;text-align:right}
.tg-ts{font-size:9px;color:#2A3A4A;text-align:left;margin-top:10px;direction:ltr}
.copy-btn{position:absolute;top:12px;left:12px;background:rgba(201,168,76,.12);border:1px solid rgba(201,168,76,.25);color:var(--g3);font-size:10px;padding:4px 10px;border-radius:8px;cursor:pointer;font-family:'Vazirmatn',sans-serif;transition:all .2s;backdrop-filter:blur(8px)}
.copy-btn:hover{background:rgba(201,168,76,.22);box-shadow:0 0 12px rgba(201,168,76,.15)}

.analysis-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
.an-card{
  background:var(--glass);border:1px solid var(--border);border-radius:16px;padding:20px;
  transition:all .3s;backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);
  position:relative;overflow:hidden}
.an-card::before{content:'';position:absolute;inset:0;background:linear-gradient(135deg,rgba(255,255,255,0.04),transparent);opacity:0;transition:opacity .3s}
.an-card:hover::before{opacity:1}
.an-card:hover{border-color:rgba(201,168,76,.25);transform:translateY(-3px);box-shadow:var(--shadow),0 0 30px rgba(201,168,76,.08)}
.an-icon{width:38px;height:38px;border-radius:12px;background:rgba(201,168,76,.08);border:1px solid rgba(201,168,76,.15);display:flex;align-items:center;justify-content:center;font-size:18px;margin-bottom:14px}
.an-title{font-size:13px;font-weight:700;margin-bottom:6px;color:var(--text)}
.an-desc{font-size:11px;color:var(--text2);line-height:1.8}

footer{border-top:1px solid var(--border);text-align:center;padding:44px 20px;position:relative;z-index:1;
  background:rgba(255,255,255,0.01);backdrop-filter:blur(8px)}
footer a{color:var(--g3);text-decoration:none;font-weight:600;transition:color .2s}
footer a:hover{color:var(--g2)}

@keyframes fadeUp{from{opacity:0;transform:translateY(18px)}to{opacity:1;transform:none}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@media(max-width:600px){
  .week-header{grid-template-columns:repeat(2,1fr)}
  .ev-table th:nth-child(5),.ev-table th:nth-child(6),.ev-table th:nth-child(7),
  .ev-row td:nth-child(5),.ev-row td:nth-child(6),.ev-row td:nth-child(7){display:none}
  .clock-item{padding:0 24px}
}
</style>
</head>
<body>
<div class="bg-orb orb1"></div>
<div class="bg-orb orb2"></div>
<div class="bg-orb orb3"></div>

<!-- NAVBAR -->
<nav class="navbar" id="navbar">
  <div class="nav-brand">
    <span class="nav-dot"></span>
    <div>
      <div class="nav-name-fa">تحلیل اخبار اقتصادی</div>
      <div class="nav-name-sub">Economic News Analysis</div>
    </div>
  </div>
  <div class="nav-right">
    <span class="nav-tag">XAU/USD</span>
    <a href="https://www.instagram.com/Farahmand.design" target="_blank" class="nav-ig">Mehdi Farahmand ↗</a>
  </div>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-tag"><span class="nav-dot" style="width:5px;height:5px;margin-left:4px"></span>تحلیل بنیادی زنده · هفتگی</div>
  <div>
    <div class="hero-h1">تقویم <span>اقتصادی</span></div>
    <div class="hero-h1">طلا <span>XAU/USD</span></div>
  </div>
  <div class="hero-en">Weekly Gold Analysis</div>
  <div class="hero-line"></div>
  <p class="hero-sub">هر هفته تحلیل جامع رویدادهای اقتصادی با تأثیر بر طلا<br>به وقت تهران · تقویم شمسی و میلادی</p>
  <div class="hero-cta">
    <button class="btn-gold" onclick="document.getElementById('calendar').scrollIntoView({behavior:'smooth'})">مشاهده تقویم هفتگی ↓</button>
    <button class="btn-ghost" onclick="document.getElementById('about').scrollIntoView({behavior:'smooth'})">روش تحلیل</button>
  </div>
  <div class="scroll-ind" onclick="document.getElementById('calendar').scrollIntoView({behavior:'smooth'})">
    <span>scroll</span>
    <div class="scroll-arr"></div>
  </div>
</section>

<!-- CLOCKS — فقط تهران و نیویورک -->
<div class="clocks-bar" id="clocks">

  <!-- پرچم شیر و خورشید -->
  <div class="clock-item">
    <div class="clock-city">
      <svg class="lion-flag" width="20" height="14" viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
        <!-- سه نوار: سبز، سفید، قرمز -->
        <rect width="300" height="200" fill="#239F40"/>
        <rect y="66" width="300" he
