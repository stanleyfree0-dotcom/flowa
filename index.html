# -*- coding: utf-8 -*-
"""FlowaVault — сайт + защищённая CRM. Запуск: нажмите Run в Pydroid 3 (нужен pip-пакет flask)."""
import os, re, time, sqlite3, secrets, json
from flask import Flask, request, session, jsonify, Response, abort
from werkzeug.security import generate_password_hash, check_password_hash

PORT = int(os.environ.get("PORT", 8080))
BASE = os.path.dirname(os.path.abspath(__file__)) if "__file__" in globals() else os.getcwd()
DB = os.path.join(BASE, "flowavault.db")
KEYF = os.path.join(BASE, "flowavault.key")
STATUSES = ["Ожидает подтверждения", "Подтверждён", "Выкуплен", "Склад в Китае", "В пути", "Прибыл", "Выдан"]
ALPHA = "ABCDEFGHJKLMNPQRSTUVWXYZ23456789"

PUBLIC = r'''<!DOCTYPE html>
<html lang="ru"><head><meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>FlowaVault — выкуп и доставка из Китая от $3.9/кг</title>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@500;700&family=Manrope:wght@400;600;800&display=swap" rel="stylesheet">
<style nonce="{{N}}">
:root{--bg:#07070f;--bg2:#0e0e1c;--tx:#f2f1ff;--mu:#9b9ab8;--a:#7c5cff;--b:#19e3c5;--g:#ffb547;--ln:#ffffff1a;--card:#ffffff08;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:light){:root:not([data-theme="dark"]){--bg:#07070f}}
html{scroll-behavior:smooth;scroll-padding-top:env(safe-area-inset-top,0px)}
*{box-sizing:border-box;margin:0}
body{background:var(--bg);color:var(--tx);font:400 16px/1.6 Manrope,system-ui,sans-serif;overflow-x:hidden}
h1,h2,h3,.lg{font-family:Unbounded,Manrope,system-ui,sans-serif;line-height:1.1}
.w{max-width:1120px;margin:auto;padding:0 20px}
section{padding:96px 0;position:relative}
h2{font-size:clamp(26px,4vw,42px);margin-bottom:14px}
.sub{color:var(--mu);max-width:560px;margin-bottom:44px}
.gr{background:linear-gradient(100deg,var(--b),var(--a) 60%,var(--g));-webkit-background-clip:text;background-clip:text;color:transparent;background-size:200%;animation:sh 6s linear infinite}
@keyframes sh{to{background-position:200%}}
nav{position:fixed;top:env(safe-area-inset-top,0px);left:0;right:0;z-index:50;backdrop-filter:blur(14px);background:#07070fb3;border-bottom:1px solid var(--ln)}
nav .w{display:flex;align-items:center;justify-content:space-between;height:64px}
.logo{display:flex;gap:10px;align-items:center;font:700 18px Unbounded,sans-serif;color:var(--tx);text-decoration:none}
nav a.l{color:var(--mu);text-decoration:none;margin-left:22px;font-size:14px}nav a.l:hover{color:var(--tx)}
.btn{display:inline-block;border:0;cursor:pointer;color:#06060d;font:800 15px Manrope;padding:14px 26px;border-radius:99px;background:linear-gradient(100deg,var(--b),var(--a));text-decoration:none;box-shadow:0 0 30px #7c5cff55;transition:.25s}
.btn{position:relative;overflow:hidden}.btn:after{content:"";position:absolute;top:0;left:-60%;width:40%;height:100%;background:linear-gradient(100deg,transparent,#ffffff77,transparent);transform:skewX(-20deg);animation:sw 3.8s infinite}@keyframes sw{to{left:140%}}.btn:hover{transform:translateY(-3px) scale(1.03);box-shadow:0 8px 44px #19e3c577}
.btn.o{background:none;color:var(--tx);border:1px solid var(--ln);box-shadow:none}
.hero{min-height:100vh;display:flex;align-items:center;padding-top:110px;overflow:hidden}
.hero:before,.hero:after{content:"";position:absolute;width:520px;height:520px;border-radius:50%;filter:blur(110px);opacity:.35;animation:fl 12s ease-in-out infinite}
.hero:before{background:var(--a);top:-120px;left:-120px}.hero:after{background:var(--b);bottom:-160px;right:-80px;animation-delay:-6s}
@keyframes fl{50%{transform:translate(60px,40px) scale(1.15)}}
.hg{display:grid;grid-template-columns:1.05fr 1fr;gap:30px;align-items:center;position:relative;z-index:2}
.tag{display:inline-flex;gap:8px;align-items:center;border:1px solid var(--ln);background:var(--card);padding:7px 16px;border-radius:99px;font-size:13px;color:var(--mu);margin-bottom:22px}
.tag i{width:8px;height:8px;border-radius:50%;background:var(--b);box-shadow:0 0 12px var(--b);animation:pu 1.6s infinite}
@keyframes pu{50%{opacity:.3}}
h1{font-size:clamp(34px,5.6vw,68px);margin-bottom:22px}
.hero p.lead{color:var(--mu);font-size:18px;max-width:480px;margin-bottom:34px}
.hero .bt{display:flex;gap:14px;flex-wrap:wrap}
.scene{width:100%;height:auto;overflow:visible}
.fl1{animation:bob 5s ease-in-out infinite}.fl2{animation:bob 6.5s ease-in-out -2s infinite}.fl3{animation:bob 7s ease-in-out -4s infinite}
@keyframes bob{50%{transform:translateY(-14px) rotate(2deg)}}
.dash{stroke-dasharray:6 8;animation:da 1.4s linear infinite}@keyframes da{to{stroke-dashoffset:-28}}
.ring{transform-origin:center;transform-box:fill-box;animation:rg 2.4s ease-out infinite}@keyframes rg{from{transform:scale(.4);opacity:.9}to{transform:scale(2.4);opacity:0}}
#pg{position:fixed;top:0;left:0;height:3px;width:0;z-index:99;background:linear-gradient(90deg,var(--b),var(--a),var(--g));box-shadow:0 0 12px var(--b)}.tw{animation:tw 3s ease-in-out infinite}@keyframes tw{50%{opacity:.1}}.chips{display:flex;gap:18px;flex-wrap:wrap;margin-top:28px;color:var(--mu);font-size:14px}.chips span:before{content:"✓ ";color:var(--b);font-weight:800}.scene{transition:transform .25s ease-out}#intro{position:fixed;inset:0;z-index:300;background:radial-gradient(circle at 50% 40%,#1a1240,#07070f 70%);display:flex;flex-direction:column;align-items:center;justify-content:center;gap:26px;transition:clip-path 1s cubic-bezier(.7,0,.2,1),opacity .4s .7s;clip-path:circle(150% at 50% 50%)}
#intro.out{clip-path:circle(0% at 50% 50%);opacity:0;pointer-events:none}
#intro svg{width:96px;height:96px;filter:drop-shadow(0 0 24px #7c5cff)}
#intro path{stroke-dasharray:140;stroke-dashoffset:140;animation:dr 1.4s .1s forwards}@keyframes dr{to{stroke-dashoffset:0}}
#intro .nm{font:700 clamp(30px,8vw,64px) Unbounded,sans-serif;letter-spacing:.02em;display:flex}
#intro .nm span{opacity:0;transform:translateY(40px) rotateX(70deg);animation:up .7s cubic-bezier(.2,.9,.2,1) forwards}
@keyframes up{to{opacity:1;transform:none}}
#intro .tg{color:var(--mu);letter-spacing:.35em;font-size:12px;text-transform:uppercase;opacity:0;animation:up .8s 1.5s forwards}
#intro .bar{width:180px;height:3px;background:#ffffff1a;border-radius:9px;overflow:hidden}#intro .bar i{display:block;height:100%;width:0;background:linear-gradient(90deg,var(--b),var(--a));animation:ld 2.3s .2s ease-out forwards}@keyframes ld{to{width:100%}}
body.lk{overflow:hidden}
.mq{border-block:1px solid var(--ln);overflow:hidden;padding:18px 0;background:var(--bg2)}
.mq div{display:flex;gap:60px;width:max-content;animation:mq 26s linear infinite;font:700 22px Unbounded;color:#ffffff40;white-space:nowrap}
@keyframes mq{to{transform:translateX(-50%)}}
.st{display:grid;grid-template-columns:repeat(4,1fr);gap:16px}
.cd{background:var(--card);border:1px solid var(--ln);border-radius:24px;padding:28px;transition:.35s;position:relative;overflow:hidden}
.cd{background:radial-gradient(260px circle at var(--mx,50%) var(--my,-40%),#19e3c52a,transparent 65%),var(--card)}.cd:hover{transform:translateY(-8px);border-color:#7c5cff88;background:#7c5cff10}
.st .cd{padding:26px 18px;text-align:center}.st .cd b{display:block;font:700 clamp(24px,3.2vw,36px) Unbounded;margin-bottom:8px;white-space:nowrap;line-height:1.2;padding:2px 0}.st .cd small{color:var(--mu);font-size:14px;line-height:1.35;display:block}
.cd .ic{font-size:34px;margin-bottom:14px;display:inline-block;animation:bob 4s ease-in-out infinite}
.g3{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.cd h3{font-size:18px;margin-bottom:10px}.cd p{color:var(--mu);font-size:15px}
.calc{display:grid;grid-template-columns:1fr 1fr;gap:30px;align-items:center}
input,select,textarea{width:100%;background:#ffffff0d;border:1px solid var(--ln);color:var(--tx);padding:14px 16px;border-radius:14px;font:inherit;outline:0;margin-bottom:12px}
input:focus,select:focus,textarea:focus{border-color:var(--b);box-shadow:0 0 0 3px #19e3c522}
select option{background:#14142a}
input[type=range]{padding:0;accent-color:var(--b);height:6px}
.big{font:700 clamp(44px,7vw,76px) Unbounded}
.steps{display:grid;grid-template-columns:repeat(5,1fr);gap:14px;counter-reset:s;position:relative}
.steps .cd{padding:22px}.steps .cd:before{counter-increment:s;content:"0" counter(s);font:700 30px Unbounded;color:var(--a);display:block;margin-bottom:10px}
.rev{opacity:0;transform:translateY(40px);transition:1s cubic-bezier(.2,.8,.2,1)}.rev.on{opacity:1;transform:none}
.trk{display:flex;gap:10px;flex-wrap:wrap}.trk input{flex:1;min-width:200px;margin:0}
.tl{display:flex;margin-top:28px;gap:0;overflow-x:auto;padding-bottom:10px}
.tl div{flex:1;min-width:92px;text-align:center;font-size:12px;color:var(--mu);position:relative}
.tl div:before{content:"";display:block;width:18px;height:18px;border-radius:50%;background:#ffffff1f;margin:0 auto 8px;position:relative;z-index:1}
.tl div:after{content:"";position:absolute;top:8px;left:50%;width:100%;height:2px;background:#ffffff1f}.tl div:last-child:after{display:none}
.tl .d{color:var(--tx)}.tl .d:before{background:var(--b);box-shadow:0 0 16px var(--b)}.tl .d:after{background:var(--b)}
.tl .c:before{animation:pu 1s infinite}
details{background:var(--card);border:1px solid var(--ln);border-radius:18px;padding:20px 24px;margin-bottom:12px;cursor:pointer}
summary{font-weight:800;list-style:none}summary:after{content:"+";float:right;color:var(--b);font-size:22px;transition:.3s}details[open] summary:after{transform:rotate(45deg)}
details p{color:var(--mu);margin-top:12px}
.fm{display:grid;grid-template-columns:1fr 1fr;gap:12px 14px}.fm .f{grid-column:1/-1}
.ok{display:none;text-align:center;padding:30px}.ok .code{font:700 38px Unbounded;color:var(--b);margin:12px 0}
footer{border-top:1px solid var(--ln);padding:44px 0;color:var(--mu);font-size:14px}
footer .w{display:flex;justify-content:space-between;gap:20px;flex-wrap:wrap}
footer a{color:var(--tx);text-decoration:none}
#own{position:fixed;right:18px;bottom:calc(18px + env(safe-area-inset-bottom,0px));z-index:60;display:none}
#crm{position:fixed;inset:0;z-index:100;background:var(--bg);display:none;overflow:auto;padding:calc(20px + env(safe-area-inset-top,0px)) 20px 40px}
#crm.on{display:block}
.tabs{display:flex;gap:8px;margin:18px 0}.tabs button{padding:10px 20px;border-radius:99px;border:1px solid var(--ln);background:none;color:var(--mu);cursor:pointer;font:600 14px Manrope}.tabs .on{background:var(--a);color:#fff;border-color:var(--a)}
.ord{display:grid;grid-template-columns:1fr auto;gap:12px;margin-bottom:12px}.ord small{color:var(--mu);display:block}.ord select{margin:0;width:auto}
.pill{display:inline-block;font-size:12px;padding:3px 12px;border-radius:99px;background:#ffb54722;color:var(--g)}
.kp{display:grid;grid-template-columns:repeat(3,1fr);gap:12px}
@media(max-width:860px){.hg,.calc{grid-template-columns:1fr}.st,.steps{grid-template-columns:1fr 1fr}.g3{grid-template-columns:1fr}.fm{grid-template-columns:1fr}nav a.l{display:none}section{padding:64px 0}}
@media(prefers-reduced-motion:reduce){*{animation:none!important;transition:none!important}.rev{opacity:1;transform:none}}
</style></head><body>
<div id="intro"><svg viewBox="0 0 40 40"><path d="M20 2 37 11v18L20 38 3 29V11z" fill="none" stroke="url(#lg)" stroke-width="2"/><path d="M9 21c4-7 7 7 11 0s7 7 11 0" fill="none" stroke="url(#lg)" stroke-width="2.4" stroke-linecap="round"/></svg><div class="nm gr" id="inm"></div><div class="tg">Выкуп из Китая · от $3.9/кг</div><div class="bar"><i></i></div></div><div id="pg"></div><nav><div class="w"><a class="logo" href="#top"><svg width="34" height="34" viewBox="0 0 40 40"><defs><linearGradient id="lg" x1="0" x2="1" y1="0" y2="1"><stop stop-color="#19e3c5"/><stop offset="1" stop-color="#7c5cff"/></linearGradient></defs><path d="M20 2 37 11v18L20 38 3 29V11z" fill="none" stroke="url(#lg)" stroke-width="2.5"/><path d="M9 21c4-7 7 7 11 0s7 7 11 0" fill="none" stroke="url(#lg)" stroke-width="3" stroke-linecap="round"/></svg>FlowaVault</a>
<div><a class="l" href="#calc">Расчёт</a><a class="l" href="#how">Как работаем</a><a class="l" href="#track">Статус посылки</a><a class="l" href="#faq">FAQ</a><a class="btn" style="margin-left:22px;padding:10px 20px" href="#order">Оставить заявку</a></div></div></nav>

<header class="hero" id="top"><div class="w hg">
<div><div class="tag"><i></i>Доставка в Беларусь и Россию</div>
<h1>Выкуп из Китая. <span class="gr">Доставка по $3.9/кг.</span></h1>
<p class="lead">Закажите с Taobao, 1688, Poizon и Pinduoduo за пару минут. Следите за каждым шагом посылки прямо на сайте — без чатов и догадок.</p>
<div class="bt"><a class="btn" href="#order">Оставить заявку</a><a class="btn o" href="#calc">Рассчитать доставку</a></div><div class="chips"><span>от $3.9/кг</span><span>Беларусь и Россия</span><span>Статусы онлайн</span></div></div>
<svg class="scene" viewBox="0 0 560 460" aria-label="Маршрут посылки из Китая">
<defs><linearGradient id="rt" x1="0" x2="1"><stop stop-color="#19e3c5"/><stop offset="1" stop-color="#7c5cff"/></linearGradient>
<radialGradient id="gl"><stop stop-color="#7c5cff" stop-opacity=".5"/><stop offset="1" stop-color="#7c5cff" stop-opacity="0"/></radialGradient></defs>
<circle cx="280" cy="230" r="220" fill="url(#gl)"/>
<g id="dots" fill="#ffffff26"></g><g id="stars" fill="#fff"></g>
<path id="rp" class="dash" d="M90 330Q250 40 470 150" fill="none" stroke="url(#rt)" stroke-width="3" stroke-linecap="round"/>
<g><circle class="ring" cx="90" cy="330" r="14" fill="none" stroke="#19e3c5" stroke-width="2"/><circle cx="90" cy="330" r="7" fill="#19e3c5"/><text x="60" y="362" fill="#9b9ab8" font-size="13" font-family="Manrope">Гуанчжоу</text></g>
<g><circle class="ring" cx="470" cy="150" r="14" fill="none" stroke="#7c5cff" stroke-width="2" style="animation-delay:-1s"/><circle cx="470" cy="150" r="7" fill="#7c5cff"/><text x="436" y="182" fill="#9b9ab8" font-size="13" font-family="Manrope">Минск</text></g><path id="rp2" class="dash" d="M90 330Q300 450 478 296" fill="none" stroke="#ffb547" stroke-width="3" stroke-linecap="round" opacity=".8"/><g><circle class="ring" cx="478" cy="296" r="14" fill="none" stroke="#ffb547" stroke-width="2" style="animation-delay:-.5s"/><circle cx="478" cy="296" r="7" fill="#ffb547"/><text x="440" y="328" fill="#9b9ab8" font-size="13" font-family="Manrope">Москва</text></g><g transform="scale(.8)"><path d="M-16 0 12 0 4-6-4-6zM-4 0-12 12-8 12 4 0zM-4 0-12-12-8-12 4 0zM-14 0-18-6-15-6-10 0z" fill="#ffd27d"/><animateMotion dur="7s" begin="-3s" repeatCount="indefinite" rotate="auto"><mpath href="#rp2"/></animateMotion></g>
<g><path d="M-16 0 12 0 4-6-4-6zM-4 0-12 12-8 12 4 0zM-4 0-12-12-8-12 4 0zM-14 0-18-6-15-6-10 0z" fill="#fff"/><animateMotion dur="6s" repeatCount="indefinite" rotate="auto"><mpath href="#rp"/></animateMotion></g>
<g class="fl1"><path d="M150 210 190 190 230 210 190 230z" fill="#ffb547"/><path d="M150 210v40l40 20v-40z" fill="#e08a1c"/><path d="M230 210v40l-40 20v-40z" fill="#ffd27d"/><path d="M170 220 210 200" stroke="#fff6" stroke-width="3"/></g>
<g class="fl2"><path d="M330 290 366 272 402 290 366 308z" fill="#19e3c5"/><path d="M330 290v34l36 18v-34z" fill="#0fa58f"/><path d="M402 290v34l-36 18v-34z" fill="#7ff5e0"/></g>
<g class="fl3"><path d="M390 60 414 48 438 60 414 72z" fill="#7c5cff"/><path d="M390 60v26l24 12V72z" fill="#5a3de0"/><path d="M438 60v26l-24 12V72z" fill="#a48fff"/></g>
<g class="fl2"><rect x="46" y="120" width="104" height="44" rx="14" fill="#ffffff12" stroke="#ffffff30"/><text x="62" y="148" fill="#fff" font-size="14" font-weight="700" font-family="Manrope">$3.9 / кг</text></g>
<g class="fl1"><rect x="380" y="372" width="140" height="44" rx="14" fill="#ffffff12" stroke="#ffffff30"/><text x="396" y="400" fill="#19e3c5" font-size="14" font-weight="700" font-family="Manrope">● Посылка в пути</text></g>
</svg></div></header>

<div class="mq"><div><span>TAOBAO</span><span>1688</span><span>POIZON</span><span>PINDUODUO</span><span>WEIDIAN</span><span>TAOBAO</span><span>1688</span><span>POIZON</span><span>PINDUODUO</span><span>WEIDIAN</span></div></div>

<section><div class="w"><div class="st rev">
<div class="cd"><b class="gr" data-n="3.9" data-p="$" data-d="1">0</b><small>за 1 кг доставки</small></div>
<div class="cd"><b class="gr" data-n="5">0</b><small>маркетплейсов Китая</small></div>
<div class="cd"><b class="gr" data-n="2">0</b><small>страны: Беларусь и Россия</small></div>
<div class="cd"><b class="gr">24/7</b><small>связь в Telegram</small></div></div>
<div class="g3 rev" style="margin-top:18px">
<div class="cd"><div class="ic">💸</div><h3>Самая низкая цена</h3><p>Доставка от $3.9/кг — без скрытых наценок и сюрпризов на выдаче.</p></div>
<div class="cd"><div class="ic">🛰️</div><h3>Статус на сайте</h3><p>Мы почти единственные с личным кабинетом отслеживания: каждый этап виден онлайн.</p></div>
<div class="cd"><div class="ic">🛡️</div><h3>Проверка товара</h3><p>Осматриваем покупку на складе в Китае до отправки и пишем, если что-то не так.</p></div></div></div></section>

<section id="calc" style="background:var(--bg2)"><div class="w"><h2 class="rev">Посчитайте <span class="gr">доставку</span></h2><p class="sub rev">Двигайте ползунок — стоимость обновляется сразу. Цена товара считается отдельно.</p>
<div class="calc rev"><div class="cd"><label>Вес посылки: <b id="kg">5</b> кг</label><input type="range" id="w" min="0.5" max="50" step="0.5" value="5"><label>Страна</label><select><option>Беларусь</option><option>Россия</option></select><p style="margin-top:6px">Тариф: $3.9 за килограмм.</p></div>
<div style="text-align:center"><div class="big gr">$<span id="pr">19.5</span></div><p style="color:var(--mu);margin:8px 0 22px">стоимость доставки</p><a class="btn" href="#order">Оформить выкуп</a></div></div></div></section>

<section id="how"><div class="w"><h2 class="rev">Как мы <span class="gr">работаем</span></h2><p class="sub rev">Пять шагов от ссылки до двери.</p>
<div class="steps rev"><div class="cd"><h3>Заявка</h3><p>Отправляете ссылку на товар.</p></div><div class="cd"><h3>Подтверждение</h3><p>Владелец проверяет заказ и подтверждает.</p></div><div class="cd"><h3>Оплата и выкуп</h3><p>Выкупаем товар у продавца.</p></div><div class="cd"><h3>Склад и путь</h3><p>Проверяем и отправляем самолётом/авто.</p></div><div class="cd"><h3>Получение</h3><p>Забираете посылку у себя в стране.</p></div></div></div></section>

<section id="track" style="background:var(--bg2)"><div class="w"><h2 class="rev">Где моя <span class="gr">посылка?</span></h2><p class="sub rev">Введите номер заявки, который вы получили после отправки формы.</p>
<div class="cd rev"><div class="trk"><input id="tc" placeholder="Например, FV-4821"><button class="btn" id="tb">Проверить</button></div><div class="tl" id="tl"></div><p id="tm" style="color:var(--mu);margin-top:8px"></p></div></div></section>

<section><div class="w"><h2 class="rev">Отзывы <span class="gr">клиентов</span></h2><p class="sub rev">Публикуются только после проверки владельцем.</p>
<div class="g3" id="rvs"></div>
<div class="cd rev" style="margin-top:22px;max-width:620px"><h3>Оставить отзыв</h3><div style="height:12px"></div><input id="rn" placeholder="Ваше имя"><textarea id="rt2" rows="3" placeholder="Как всё прошло?"></textarea><button class="btn" id="rb">Отправить на модерацию</button><p id="rm" style="color:var(--b);margin-top:10px"></p></div></div></section>

<section id="pay" style="display:none"><div class="w"><h2 class="rev">Реквизиты для <span class="gr">оплаты</span></h2><p class="sub rev">Оплачивайте после подтверждения заявки и укажите её номер в комментарии к платежу.</p><div class="g3 rev" id="rqs"></div></div></section>
<section id="faq" style="background:var(--bg2)"><div class="w" style="max-width:780px"><h2 class="rev">Частые <span class="gr">вопросы</span></h2><div style="height:24px"></div>
<details class="rev"><summary>Что значит «выкуп»?</summary><p>Вы присылаете ссылку, мы покупаем товар у китайского продавца и привозим вам.</p></details>
<details class="rev"><summary>Сколько стоит доставка?</summary><p>$3.9 за килограмм. Итог зависит от веса посылки — посчитайте в калькуляторе выше.</p></details>
<details class="rev"><summary>Вы возите в Россию?</summary><p>Да, мы доставляем в Беларусь и в Россию.</p></details>
<details class="rev"><summary>Как узнать статус?</summary><p>Владелец подтверждает заявку, и вы смотрите все этапы по номеру на этом сайте.</p></details></div></section>

<section id="order"><div class="w" style="max-width:720px"><h2 class="rev">Оставить <span class="gr">заявку</span></h2><p class="sub rev">Мы свяжемся, подтвердим заказ и сообщим об оплате.</p>
<div class="cd rev"><form id="fm" class="fm"><input id="fn" placeholder="Имя" required><input id="fp" placeholder="Телефон или Telegram" required><select id="fc"><option>Беларусь</option><option>Россия</option></select><input id="fkg" placeholder="Примерный вес, кг"><input class="f" id="fl" placeholder="Ссылка на товар" required><input name="website" id="hp" tabindex="-1" autocomplete="off" style="position:absolute;left:-9999px;opacity:0" aria-hidden="true"><textarea class="f" id="fx" rows="3" placeholder="Размер, цвет, пожелания"></textarea><p class="f" id="fe" style="color:#ff7a8a;margin:0"></p><button class="btn f" id="fb">Отправить заявку</button></form>
<div class="ok" id="ok"><div style="font-size:48px">🚀</div><h3>Заявка принята</h3><div class="code" id="cc"></div><p style="color:var(--mu);margin-bottom:14px">Сохраните номер: по нему вы увидите подтверждение и статусы посылки. Владелец уже получил вашу заявку.</p><div id="rq2" class="g3" style="margin:14px 0;text-align:left"></div><a class="btn o" href="https://t.me/flowavt" target="_blank" rel="noopener">Написать в Telegram</a></div></div></div></section>

<footer><div class="w"><div><div class="logo" style="margin-bottom:8px">FlowaVault</div>Выкуп и доставка из Китая в Беларусь и Россию</div>
<div><a href="tel:+375445980068">+375 44 598 00 68</a><br><a href="https://t.me/flowavt">Telegram: @flowavt</a></div></div></footer>


<script nonce="{{N}}">
const $=s=>document.querySelector(s),ST=["Ожидает подтверждения","Подтверждён","Выкуплен","Склад в Китае","В пути","Прибыл","Выдан"];
const el=(t,c,x)=>{const e=document.createElement(t);if(c)e.className=c;if(x!=null)e.textContent=x;return e};
// фон из точек
{let s="";for(let y=40;y<430;y+=22)for(let x=30;x<540;x+=22)if(Math.hypot(x-280,y-230)<200)s+=`<circle cx="${x}" cy="${y}" r="1.6"/>`;$("#dots").innerHTML=s}
{let t="";for(let i=0;i<40;i++)t+=`<circle class="tw" cx="${Math.random()*560|0}" cy="${Math.random()*460|0}" r="${(Math.random()*1.4+.4).toFixed(1)}" style="animation-delay:-${(Math.random()*3).toFixed(1)}s"/>`;$("#stars").innerHTML=t}
addEventListener("scroll",()=>{$("#pg").style.width=scrollY/(document.body.scrollHeight-innerHeight)*100+"%"},{passive:true});
document.addEventListener("pointermove",e=>{const c=e.target.closest&&e.target.closest(".cd");if(c){const b=c.getBoundingClientRect();c.style.setProperty("--mx",e.clientX-b.left+"px");c.style.setProperty("--my",e.clientY-b.top+"px")}});
{const h=$(".hero"),sc=$(".scene");h.addEventListener("pointermove",e=>{const x=e.clientX/innerWidth-.5,y=e.clientY/innerHeight-.5;sc.style.transform=`perspective(900px) rotateY(${x*10}deg) rotateX(${-y*8}deg)`});h.addEventListener("pointerleave",()=>sc.style.transform="")}
// появление и счётчики
const io=new IntersectionObserver(a=>a.forEach(e=>{if(e.isIntersecting){e.target.classList.add("on");e.target.querySelectorAll("[data-n]").forEach(c=>{const n=+c.dataset.n,d=+c.dataset.d||0,p=c.dataset.p||"",t0=performance.now();(function f(t){const k=Math.min(1,(t-t0)/1400);c.textContent=p+(n*(1-Math.pow(1-k,3))).toFixed(d);if(k<1)requestAnimationFrame(f)})(t0)});io.unobserve(e.target)}}),{threshold:.15});
document.querySelectorAll(".rev").forEach(e=>io.observe(e));
$("#w").oninput=e=>{$("#kg").textContent=e.target.value;$("#pr").textContent=(e.target.value*3.9).toFixed(1)};
const api=async(u,b)=>{const r=await fetch(u,b?{method:"POST",headers:{"Content-Type":"application/json"},body:JSON.stringify(b)}:{});const j=await r.json().catch(()=>({}));if(!r.ok)throw new Error(j.error||"Ошибка, попробуйте ещё раз");return j};
function showTl(code,st){const i=ST.indexOf(st);$("#tl").replaceChildren(...ST.map((s,j)=>el("div",j<=i?"d"+(j==i?" c":""):"",s)));$("#tm").textContent="Заявка "+code+": "+st}
function renderRv(rv){const b=$("#rvs");b.replaceChildren();if(!rv.length){b.append(el("div","cd","Отзывов пока нет — станьте первым."));return}rv.forEach(r=>{const c=el("div","cd");c.append(el("p","",'"'+r.text+'"'),el("h3","",r.name));c.lastChild.style.marginTop="12px";b.append(c)})}
api("/api/reviews").then(renderRv).catch(()=>renderRv([]));
function renderRq(items){["#rqs","#rq2"].forEach(sel=>{const b=$(sel);b.replaceChildren();items.forEach(x=>{const c=el("div","cd");c.style.padding="18px";const v=el("p","",x.value);v.style.cssText="word-break:break-all;margin:6px 0 12px;color:var(--tx)";const k=el("button","btn o","Копировать");k.style.padding="8px 16px";k.onclick=()=>{try{navigator.clipboard.writeText(x.value)}catch(e){}k.textContent="Скопировано ✓";setTimeout(()=>k.textContent="Копировать",1600)};c.append(el("small","",x.title),v,k);b.append(c)})});$("#pay").style.display=items.length?"block":"none"}
api("/api/requisites").then(renderRq).catch(()=>{});
$("#fm").addEventListener("submit",e=>e.preventDefault());
$("#fb").onclick=async()=>{if(!$("#fm").reportValidity())return;const bt=$("#fb");bt.disabled=true;$("#fe").textContent="";
try{const j=await api("/api/order",{name:$("#fn").value,contact:$("#fp").value,country:$("#fc").value,kg:$("#fkg").value,link:$("#fl").value,note:$("#fx").value,website:$("#hp").value});
$("#fm").style.display="none";$("#ok").style.display="block";$("#cc").textContent=j.code;$("#tc").value=j.code}catch(e){$("#fe").textContent=e.message;bt.disabled=false}};
$("#tb").onclick=async()=>{const c=$("#tc").value.trim().toUpperCase();if(!c)return;try{const j=await api("/api/status/"+encodeURIComponent(c));if(!j.status){$("#tl").replaceChildren();$("#tm").textContent="Заявка с таким номером не найдена."}else showTl(c,j.status)}catch(e){$("#tm").textContent=e.message}};
$("#rb").onclick=async()=>{try{await api("/api/review",{name:$("#rn").value,text:$("#rt2").value,website:$("#hp").value});$("#rm").textContent="Спасибо! Отзыв появится после проверки.";$("#rn").value=$("#rt2").value=""}catch(e){$("#rm").textContent=e.message}};
(function(){const i=$("#intro"),n=$("#inm");let seen=0;try{seen=sessionStorage.getItem("fv")}catch(e){}
if(seen){i.remove();return}document.body.classList.add("lk");
"FlowaVault".split("").forEach((c,k)=>{const x=document.createElement("span");x.textContent=c;x.style.animationDelay=(.5+k*.07)+"s";n.append(x)});
const go=()=>{i.classList.add("out");document.body.classList.remove("lk");try{sessionStorage.setItem("fv","1")}catch(e){}setTimeout(()=>i.remove(),1500)};
setTimeout(go,2800);i.addEventListener("click",go)})();
</script></body></html>
'''
OWNER = r'''<!DOCTYPE html><html lang="ru"><head><meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1"><meta name="robots" content="noindex,nofollow"><title>FlowaVault · CRM</title>
<style nonce="{{N}}">
:root{--bg:#07070f;--tx:#f2f1ff;--mu:#9b9ab8;--a:#7c5cff;--b:#19e3c5;--ln:#ffffff1a}*{box-sizing:border-box;margin:0}
body{background:radial-gradient(circle at 20% 0,#1a1240,#07070f 60%) fixed;color:var(--tx);font:15px/1.5 system-ui,Segoe UI,sans-serif;min-height:100vh;padding:20px}
.w{max-width:960px;margin:auto}.cd{background:#ffffff0a;border:1px solid var(--ln);border-radius:20px;padding:20px;margin-bottom:12px}
input,select{width:100%;background:#ffffff0d;border:1px solid var(--ln);color:var(--tx);padding:13px 15px;border-radius:12px;font:inherit;outline:0;margin-bottom:10px}select option{background:#14142a}
input:focus{border-color:var(--b)}.btn{border:0;cursor:pointer;font:700 14px system-ui;padding:12px 22px;border-radius:99px;color:#06060d;background:linear-gradient(100deg,var(--b),var(--a))}
.btn.o{background:none;color:var(--tx);border:1px solid var(--ln)}.btn.r{background:#ff5d73;color:#fff}.mu{color:var(--mu);font-size:13px}
#lg{max-width:380px;margin:18vh auto 0;text-align:center}#lg h1{font-size:26px;margin:10px 0 4px}#er{color:#ff7a8a;min-height:22px;margin:4px 0}
#app{display:none}.hd{display:flex;justify-content:space-between;align-items:center;margin-bottom:16px;gap:10px;flex-wrap:wrap}
.kp{display:grid;grid-template-columns:repeat(4,1fr);gap:10px}.kp b{font-size:28px;display:block}
.tabs{display:flex;gap:8px;margin:14px 0}.tabs button{padding:9px 18px;border-radius:99px;border:1px solid var(--ln);background:none;color:var(--mu);cursor:pointer}.tabs .on{background:var(--a);color:#fff;border-color:var(--a)}
.row{display:grid;grid-template-columns:1fr auto;gap:12px}.row small{display:block;color:var(--mu);word-break:break-word}.row select{width:auto;margin:0 0 8px}
.pill{font-size:12px;padding:2px 10px;border-radius:99px;background:#19e3c522;color:var(--b)}a{color:var(--b)}
@media(max-width:640px){.kp{grid-template-columns:1fr 1fr}.row{grid-template-columns:1fr}}
</style></head><body><div class="w">
<div id="lg" class="cd"><div style="font-size:42px">🔐</div><h1>FlowaVault</h1><p class="mu" style="margin-bottom:18px">Вход для владельца</p><input id="pw" type="password" placeholder="Пароль" autocomplete="current-password"><div id="er"></div><button class="btn" id="go" style="width:100%">Войти</button></div>
<div id="app"><div class="hd"><b style="font-size:20px">FlowaVault · CRM</b><div><button class="btn o" id="np">Сменить пароль</button> <button class="btn o" id="lo">Выйти</button></div></div>
<div class="kp"><div class="cd"><span class="mu">Новые</span><b id="k1">0</b></div><div class="cd"><span class="mu">В работе</span><b id="k2">0</b></div><div class="cd"><span class="mu">Выданы</span><b id="k3">0</b></div><div class="cd"><span class="mu">Отзывы ждут</span><b id="k4">0</b></div></div>
<div class="tabs"><button class="on" data-t="o">Заявки</button><button data-t="r">Отзывы</button><button data-t="q">Реквизиты</button></div><input id="q" placeholder="Поиск по номеру, имени, контакту"><div id="ls"></div></div></div>
<script nonce="{{N}}">
const $=s=>document.querySelector(s),el=(t,c,x)=>{const e=document.createElement(t);if(c)e.className=c;if(x!=null)e.textContent=x;return e};
let R=[],csrf="",tab="o",D={orders:[],reviews:[],statuses:[]};
const api=async(u,b)=>{const r=await fetch(u,{method:b?"POST":"GET",headers:{"Content-Type":"application/json","X-CSRF":csrf},body:b?JSON.stringify(b):undefined,credentials:"same-origin"});const j=await r.json().catch(()=>({}));if(r.status==401&&$("#app").style.display=="block")location.reload();if(!r.ok)throw new Error(j.error||"Ошибка");return j};
async function start(){const m=await api("/api/o/me");if(m.auth){csrf=m.csrf;open_()}}
async function open_(){$("#lg").style.display="none";$("#app").style.display="block";await load();setInterval(()=>{if(tab!="q")load().catch(()=>{})},15000)}
async function load(){D=await api("/api/o/data");draw()}
$("#go").onclick=async()=>{try{const j=await api("/api/o/login",{password:$("#pw").value});csrf=j.csrf;$("#pw").value="";open_()}catch(e){$("#er").textContent=e.message}};
$("#pw").onkeydown=e=>{if(e.key=="Enter")$("#go").click()};
$("#lo").onclick=async()=>{await api("/api/o/logout",{});location.reload()};
$("#np").onclick=async()=>{const p=prompt("Новый пароль (минимум 10 символов):");if(!p)return;try{await api("/api/o/password",{password:p});alert("Пароль изменён")}catch(e){alert(e.message)}};
document.querySelectorAll(".tabs button").forEach(b=>b.onclick=()=>{tab=b.dataset.t;if(tab=="q")R=JSON.parse(JSON.stringify(D.requisites||[]));document.querySelectorAll(".tabs button").forEach(x=>x.classList.toggle("on",x==b));draw()});
$("#q").oninput=draw;
function draw(){const L=$("#ls"),o=D.orders,S=D.statuses;L.replaceChildren();
$("#k1").textContent=o.filter(x=>x.status==S[0]).length;$("#k2").textContent=o.filter(x=>x.status!=S[0]&&x.status!=S[6]).length;$("#k3").textContent=o.filter(x=>x.status==S[6]).length;$("#k4").textContent=D.reviews.filter(r=>!r.ok).length;
const q=$("#q").value.toLowerCase();
if(tab=="o"){$("#q").style.display="block";const f=o.filter(x=>(x.code+x.name+x.contact).toLowerCase().includes(q));if(!f.length)L.append(el("p","mu","Заявок нет."));
f.forEach(x=>{const c=el("div","cd row"),i=el("div");i.append(el("b","",x.code+" · "+x.name));
const ct=el("small","",x.contact+" · "+x.country+(x.kg?" · ~"+x.kg+" кг":"")+" · "+new Date(x.ts*1000).toLocaleString("ru"));i.append(ct);
const ln=el("small");if(/^https?:\/\//.test(x.link)){const a=el("a","",x.link);a.href=x.link;a.target="_blank";a.rel="noopener noreferrer";ln.append(a)}i.append(ln);if(x.note)i.append(el("small","","💬 "+x.note));
const d=el("div"),s=el("select");S.forEach(t=>{const p=el("option","",t);if(t==x.status)p.selected=true;s.append(p)});
s.onchange=async()=>{try{await api("/api/o/status",{code:x.code,status:s.value});await load()}catch(e){alert(e.message)}};
const dl=el("button","btn r","Удалить");dl.onclick=async()=>{if(confirm("Удалить заявку "+x.code+"?")){await api("/api/o/delete",{code:x.code});load()}};
d.append(s,dl);c.append(i,d);L.append(c)})}
else if(tab=="q"){$("#q").style.display="none";L.append(el("p","mu","Эти реквизиты клиенты увидят на сайте для оплаты (карта, IBAN, счёт и т.д.)."));R.forEach((x,i)=>{const c=el("div","cd"),t=el("input"),v=el("input"),d=el("button","btn r","Удалить");t.placeholder="Название (например, Карта Беларусбанк)";v.placeholder="Номер / данные";t.value=x.title;v.value=x.value;t.maxLength=40;v.maxLength=200;t.oninput=()=>x.title=t.value;v.oninput=()=>x.value=v.value;d.onclick=()=>{R.splice(i,1);draw()};c.append(t,v,d);L.append(c)});
const ad=el("button","btn o","+ Добавить реквизит"),sv=el("button","btn","Сохранить");ad.style.marginRight="8px";ad.onclick=()=>{if(R.length<8){R.push({title:"",value:""});draw()}};sv.onclick=async()=>{try{const j=await api("/api/o/req",{items:R});R=j.items;D.requisites=j.items;draw();alert("Реквизиты сохранены и показаны на сайте")}catch(e){alert(e.message)}};L.append(ad,sv)}
else{$("#q").style.display="none";if(!D.reviews.length)L.append(el("p","mu","Отзывов нет."));D.reviews.forEach(r=>{const c=el("div","cd row"),i=el("div");i.append(el("b","",r.name),el("small","",r.text),el("span","pill",r.ok?"опубликован":"на модерации"));const d=el("div");
if(!r.ok){const a=el("button","btn","Опубликовать");a.onclick=async()=>{await api("/api/o/review",{id:r.id});load()};d.append(a,document.createTextNode(" "))}
const x=el("button","btn r","Удалить");x.onclick=async()=>{if(confirm("Удалить отзыв?")){await api("/api/o/delete",{kind:"review",id:r.id});load()}};d.append(x);c.append(i,d);L.append(c)})}}
start().catch(()=>{});
</script></body></html>
'''

if not os.path.exists(KEYF):
    with open(KEYF, "w") as f: f.write(secrets.token_hex(32))
    try: os.chmod(KEYF, 0o600)
    except Exception: pass
app = Flask(__name__)
app.secret_key = open(KEYF).read().strip()
app.config.update(SESSION_COOKIE_HTTPONLY=True, SESSION_COOKIE_SAMESITE="Strict", MAX_CONTENT_LENGTH=20_000,
                  SESSION_COOKIE_SECURE=os.environ.get("HTTPS") == "1", PERMANENT_SESSION_LIFETIME=8 * 3600)

def db():
    c = sqlite3.connect(DB); c.row_factory = sqlite3.Row; return c
def init():
    with db() as c:
        c.executescript("""CREATE TABLE IF NOT EXISTS meta(k TEXT PRIMARY KEY,v TEXT);
        CREATE TABLE IF NOT EXISTS orders(code TEXT PRIMARY KEY,name TEXT,contact TEXT,country TEXT,kg TEXT,link TEXT,note TEXT,status TEXT,ts INTEGER);
        CREATE TABLE IF NOT EXISTS reviews(id INTEGER PRIMARY KEY AUTOINCREMENT,name TEXT,text TEXT,ok INTEGER DEFAULT 0,ts INTEGER);""")
def meta(k, v=None):
    with db() as c:
        if v is None:
            r = c.execute("SELECT v FROM meta WHERE k=?", (k,)).fetchone(); return r[0] if r else None
        c.execute("INSERT OR REPLACE INTO meta VALUES(?,?)", (k, v))

def setup():
    init()
    if not meta("owner_path"): meta("owner_path", "/o-" + secrets.token_urlsafe(9))
    if not meta("pw"):
        pw = os.environ.get("FV_PASSWORD", "")
        while len(pw) < 10:
            pw = input("Придумайте пароль владельца (минимум 10 символов): ").strip()
        meta("pw", generate_password_hash(pw, method="pbkdf2:sha256:600000"))
        print("Пароль сохранён (в виде хэша).")
HITS = {}
def limited(key, n, per):
    now = time.time(); L = [t for t in HITS.get(key, []) if now - t < per]
    if len(L) >= n: HITS[key] = L; return True
    L.append(now); HITS[key] = L; return False
def ip(): return request.remote_addr or "0"
def clean(s, n):
    s = re.sub(r"[\x00-\x08\x0b-\x1f\x7f]", "", str(s or "")).strip(); return s[:n]

@app.before_request
def guard():
    if request.method == "POST":
        o = request.headers.get("Origin")
        if o and o.split("://", 1)[-1] != request.host: abort(403)
        if not request.is_json: abort(400)
    if request.path.startswith("/api/o/") and request.path not in ("/api/o/me", "/api/o/login"):
        if not session.get("own"): return jsonify(error="Нет доступа"), 401
        if request.method == "POST" and not secrets.compare_digest(request.headers.get("X-CSRF", ""), session.get("csrf", "")):
            return jsonify(error="Сессия устарела, обновите страницу"), 403
@app.after_request
def hdr(r):
    n = getattr(request, "nonce", "")
    r.headers["Content-Security-Policy"] = (f"default-src 'none'; script-src 'nonce-{n}'; style-src 'unsafe-inline' https://fonts.googleapis.com; "
        "font-src https://fonts.gstatic.com; connect-src 'self'; img-src 'self' data:; base-uri 'none'; form-action 'none'; frame-ancestors 'none'")
    r.headers.update({"X-Content-Type-Options": "nosniff", "X-Frame-Options": "DENY", "Referrer-Policy": "no-referrer",
                      "Permissions-Policy": "camera=(),microphone=(),geolocation=()", "Cross-Origin-Opener-Policy": "same-origin"})
    if request.path.startswith(("/api/o", meta("owner_path") or "/-")): r.headers["Cache-Control"] = "no-store"; r.headers["X-Robots-Tag"] = "noindex"
    return r
def page(h):
    request.nonce = secrets.token_urlsafe(16)
    return Response(h.replace("{{N}}", request.nonce), mimetype="text/html")

@app.route("/")
def index(): return page(PUBLIC)
@app.route("/robots.txt")
def robots(): return Response("User-agent: *\nAllow: /\n", mimetype="text/plain")
@app.route("/<path:p>")
def owner(p):
    if "/" + p == meta("owner_path"): return page(OWNER)
    abort(404)

@app.post("/api/order")
def order():
    d = request.get_json(silent=True) or {}
    if d.get("website"): return jsonify(code="FV-" + "".join(secrets.choice(ALPHA) for _ in range(6)))  # ловушка для ботов
    if limited("o" + ip(), 5, 3600): return jsonify(error="Слишком много заявок. Попробуйте позже."), 429
    name, contact, link = clean(d.get("name"), 80), clean(d.get("contact"), 80), clean(d.get("link"), 500)
    if len(name) < 2 or len(contact) < 5: return jsonify(error="Укажите имя и контакт"), 400
    if not re.match(r"^https?://[^\s]+$", link): return jsonify(error="Нужна ссылка на товар (http/https)"), 400
    country = "Россия" if d.get("country") == "Россия" else "Беларусь"
    code = "FV-" + "".join(secrets.choice(ALPHA) for _ in range(6))
    with db() as c:
        c.execute("INSERT INTO orders VALUES(?,?,?,?,?,?,?,?,?)", (code, name, contact, country, clean(d.get("kg"), 10), link, clean(d.get("note"), 500), STATUSES[0], int(time.time())))
    return jsonify(code=code)
@app.get("/api/status/<code>")
def status(code):
    if limited("s" + ip(), 40, 60): return jsonify(error="Подождите минуту"), 429
    with db() as c: r = c.execute("SELECT status FROM orders WHERE code=?", (code.strip().upper()[:12],)).fetchone()
    return jsonify(status=r["status"] if r else None)
def get_req():
    try: return json.loads(meta("req") or "[]")
    except Exception: return []
@app.get("/api/requisites")
def requisites(): return jsonify(get_req())
@app.get("/api/reviews")
def reviews():
    with db() as c: rows = c.execute("SELECT name,text FROM reviews WHERE ok=1 ORDER BY id DESC LIMIT 30").fetchall()
    return jsonify([dict(r) for r in rows])
@app.post("/api/review")
def review():
    d = request.get_json(silent=True) or {}
    if d.get("website"): return jsonify(ok=True)
    if limited("r" + ip(), 3, 3600): return jsonify(error="Слишком много отзывов. Попробуйте позже."), 429
    n, t = clean(d.get("name"), 60), clean(d.get("text"), 600)
    if len(n) < 2 or len(t) < 5: return jsonify(error="Заполните имя и текст"), 400
    with db() as c: c.execute("INSERT INTO reviews(name,text,ok,ts) VALUES(?,?,0,?)", (n, t, int(time.time())))
    return jsonify(ok=True)

@app.get("/api/o/me")
def me():
    if session.get("own"): return jsonify(auth=True, csrf=session["csrf"])
    return jsonify(auth=False)
@app.post("/api/o/login")
def login():
    k = "l" + ip()
    if len(HITS.get(k, [])) >= 5 and time.time() - HITS[k][-1] < 900: return jsonify(error="Слишком много попыток. Подождите 15 минут."), 429
    time.sleep(0.6)
    if check_password_hash(meta("pw"), str((request.get_json(silent=True) or {}).get("password", ""))[:200]):
        HITS.pop(k, None); session.clear(); session.permanent = True
        session["own"] = True; session["csrf"] = secrets.token_urlsafe(24)
        return jsonify(auth=True, csrf=session["csrf"])
    HITS.setdefault(k, []).append(time.time()); HITS[k] = HITS[k][-5:]
    return jsonify(error="Неверный пароль"), 401
@app.post("/api/o/logout")
def logout(): session.clear(); return jsonify(ok=True)
@app.get("/api/o/data")
def data():
    with db() as c:
        o = [dict(r) for r in c.execute("SELECT * FROM orders ORDER BY ts DESC LIMIT 500")]
        r = [dict(x) for x in c.execute("SELECT id,name,text,ok FROM reviews ORDER BY id DESC LIMIT 200")]
    return jsonify(orders=o, reviews=r, statuses=STATUSES, requisites=get_req())
@app.post("/api/o/status")
def set_status():
    d = request.get_json(silent=True) or {}
    if d.get("status") not in STATUSES: return jsonify(error="Неверный статус"), 400
    with db() as c: c.execute("UPDATE orders SET status=? WHERE code=?", (d["status"], str(d.get("code"))[:12]))
    return jsonify(ok=True)
@app.post("/api/o/delete")
def delete():
    d = request.get_json(silent=True) or {}
    with db() as c:
        if d.get("kind") == "review": c.execute("DELETE FROM reviews WHERE id=?", (int(d.get("id", 0)),))
        else: c.execute("DELETE FROM orders WHERE code=?", (str(d.get("code"))[:12],))
    return jsonify(ok=True)
@app.post("/api/o/review")
def approve():
    d = request.get_json(silent=True) or {}
    with db() as c: c.execute("UPDATE reviews SET ok=1 WHERE id=?", (int(d.get("id", 0)),))
    return jsonify(ok=True)
@app.post("/api/o/req")
def set_req():
    items = (request.get_json(silent=True) or {}).get("items")
    if not isinstance(items, list) or len(items) > 8: return jsonify(error="Не более 8 реквизитов"), 400
    out = []
    for i in items:
        if not isinstance(i, dict): continue
        a, b = clean(i.get("title"), 40), clean(i.get("value"), 200)
        if a and b: out.append({"title": a, "value": b})
    meta("req", json.dumps(out, ensure_ascii=False)); return jsonify(ok=True, items=out)
@app.post("/api/o/password")
def chpw():
    p = str((request.get_json(silent=True) or {}).get("password", ""))
    if len(p) < 10: return jsonify(error="Минимум 10 символов"), 400
    meta("pw", generate_password_hash(p, method="pbkdf2:sha256:600000")); return jsonify(ok=True)

if __name__ == "__main__":
    setup()
    print("\n=== FlowaVault запущен ===\nСайт для клиентов:  http://127.0.0.1:%d/\nВход для владельца: http://127.0.0.1:%d%s\n(ссылку владельца никому не показывайте)\n" % (PORT, PORT, meta("owner_path")))
    app.run(host="0.0.0.0", port=PORT, debug=False, threaded=True)
