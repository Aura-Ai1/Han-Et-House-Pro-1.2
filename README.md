<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>HAN ET HOUSE — Tokat</title>
<meta name="description" content="HAN ET HOUSE — Tokat'ın seçkin et restoranı.">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    background:#080807;
    color:#f5f0e6;
    font-family:'DM Sans',sans-serif;
    overflow-x:hidden;
}

body.lock{
    overflow:hidden;
}

:root{
    --bg:#080807;
    --bg2:#0e0e0c;
    --panel:#131310;
    --gold:#c9a45c;
    --gold2:#ead49b;
    --white:#f5f0e6;
    --muted:#999286;
    --line:rgba(201,164,92,.18);
    --serif:'Cormorant Garamond',serif;
}

/* =========================
   LOADER
========================= */

.loader{
    position:fixed;
    inset:0;
    z-index:99999;
    display:flex;
    justify-content:center;
    align-items:center;
    overflow:hidden;

    background:
        radial-gradient(
            circle at 50% 45%,
            rgba(201,164,92,.14),
            transparent 27%
        ),
        radial-gradient(
            circle at 50% 50%,
            rgba(255,255,255,.025),
            transparent 55%
        ),
        #050504;

    opacity:1;
    visibility:visible;

    transition:
        opacity .75s cubic-bezier(.77,0,.18,1),
        visibility .75s;
}

.loader.hide{
    opacity:0;
    visibility:hidden;
    pointer-events:none;
}

.loader-inner{
    position:relative;
    z-index:3;
    text-align:center;

    animation:
        loaderEnter 1.15s
        cubic-bezier(.16,1,.3,1)
        forwards;
}

.loader-small{
    color:var(--gold);
    font-size:8px;
    letter-spacing:7px;
    margin-bottom:22px;
    opacity:0;
    animation:loaderFade .8s .15s ease forwards;
}

.loader-logo{
    font-family:var(--serif);
    font-size:clamp(43px,9vw,105px);
    font-weight:400;
    letter-spacing:8px;
    color:var(--white);
    white-space:nowrap;

    text-shadow:
        0 0 25px rgba(201,164,92,.08),
        0 0 70px rgba(201,164,92,.04);

    opacity:0;

    animation:
        logoReveal 1.15s
        .25s
        cubic-bezier(.16,1,.3,1)
        forwards;
}

.loader-sub{
    color:#706b61;
    font-size:7px;
    letter-spacing:5px;
    margin-top:16px;

    opacity:0;

    animation:
        loaderFade .8s .55s ease
        forwards;
}

.loader-line{
    width:190px;
    height:1px;
    margin:27px auto 0;

    background:rgba(255,255,255,.08);

    overflow:hidden;

    opacity:0;

    animation:
        loaderFade .5s .6s ease
        forwards;
}

.loader-line span{
    display:block;
    width:0;
    height:100%;

    background:
        linear-gradient(
            90deg,
            transparent,
            var(--gold),
            var(--gold2),
            transparent
        );

    animation:
        loaderProgress 1.55s
        .55s
        cubic-bezier(.65,0,.35,1)
        forwards;
}

.loader-orbit{
    position:absolute;
    left:50%;
    top:50%;

    border-radius:50%;
    border:1px solid rgba(201,164,92,.07);

    transform:translate(-50%,-50%);
}

.orbit-1{
    width:350px;
    height:350px;

    animation:
        orbitRotate 9s linear infinite;
}

.orbit-2{
    width:470px;
    height:470px;

    border-color:rgba(201,164,92,.035);

    animation:
        orbitRotateReverse 14s linear infinite;
}

.orbit-1::after,
.orbit-2::after{

    content:"";

    position:absolute;

    width:5px;
    height:5px;

    border-radius:50%;

    background:var(--gold);

    box-shadow:
        0 0 15px
        rgba(201,164,92,.8);
}

.orbit-1::after{
    top:-3px;
    left:50%;
}

.orbit-2::after{
    bottom:-3px;
    left:50%;
}

@keyframes loaderEnter{

    0%{
        opacity:0;
        transform:
            translateY(25px)
            scale(.96);
        filter:blur(8px);
    }

    100%{
        opacity:1;
        transform:
            translateY(0)
            scale(1);
        filter:blur(0);
    }
}

@keyframes logoReveal{

    0%{
        opacity:0;
        letter-spacing:18px;
        transform:scale(.96);
    }

    100%{
        opacity:1;
        letter-spacing:8px;
        transform:scale(1);
    }
}

@keyframes loaderFade{
    to{
        opacity:1;
    }
}

@keyframes loaderProgress{

    from{
        width:0;
    }

    to{
        width:100%;
    }
}

@keyframes orbitRotate{

    to{
        transform:
            translate(-50%,-50%)
            rotate(360deg);
    }
}

@keyframes orbitRotateReverse{

    to{
        transform:
            translate(-50%,-50%)
            rotate(-360deg);
    }
}

/* =========================
   GRAIN
========================= */

body::before{

    content:"";

    position:fixed;
    inset:0;

    pointer-events:none;
    z-index:9998;

    opacity:.035;

    background-image:
        url("data:image/svg+xml,%3Csvg viewBox='0 0 180 180' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.7'/%3E%3C/svg%3E");
}

/* =========================
   NAVBAR
========================= */

nav{

    position:fixed;

    top:0;
    left:0;
    right:0;

    z-index:1000;

    padding:24px 5%;

    display:flex;

    align-items:center;
    justify-content:space-between;

    transition:.4s;
}

nav.scrolled{

    background:
        rgba(8,8,7,.88);

    backdrop-filter:
        blur(18px);

    padding-top:16px;
    padding-bottom:16px;

    border-bottom:
        1px solid var(--line);
}

.logo{

    font-family:var(--serif);

    font-size:30px;

    letter-spacing:4px;

    color:white;
}

.nav-links{

    display:flex;

    gap:32px;

    list-style:none;
}

.nav-links a{

    color:#ddd7ca;

    text-decoration:none;

    font-size:12px;

    letter-spacing:1.5px;

    text-transform:uppercase;

    transition:.3s;
}

.nav-links a:hover{

    color:var(--gold);
}

.nav-cta{

    text-decoration:none;

    color:#080807;

    background:var(--gold);

    padding:13px 22px;

    font-size:11px;

    letter-spacing:1.5px;

    text-transform:uppercase;

    transition:.3s;
}

.nav-cta:hover{

    background:var(--gold2);

    transform:
        translateY(-2px);
}

/* =========================
   HERO
========================= */

.hero{

    min-height:100vh;

    display:flex;

    align-items:center;

    position:relative;

    background:

        linear-gradient(
            90deg,
            rgba(0,0,0,.82),
            rgba(0,0,0,.3)
        ),

        url("https://images.unsplash.com/photo-1546833999-b9f581a1996d?auto=format&fit=crop&w=2200&q=90")
        center/cover;
}

.hero-content{

    width:min(1100px,90%);

    margin:auto;

    padding-top:80px;
}

.hero-small{

    color:var(--gold);

    letter-spacing:7px;

    font-size:11px;

    margin-bottom:24px;
}

.hero h1{

    font-family:var(--serif);

    font-weight:400;

    font-size:
        clamp(65px,11vw,145px);

    line-height:.78;

    letter-spacing:-3px;
}

.hero h1 span{

    display:block;

    color:var(--gold2);

    font-style:italic;
}

.hero-text{

    max-width:520px;

    margin-top:40px;

    color:#c4bfb3;

    line-height:1.8;

    font-size:15px;
}

.hero-buttons{

    margin-top:38px;

    display:flex;

    gap:15px;
}

.btn{

    display:inline-block;

    padding:16px 28px;

    text-decoration:none;

    font-size:11px;

    letter-spacing:2px;

    text-transform:uppercase;

    transition:.3s;
}

.btn-gold{

    background:var(--gold);

    color:#080807;
}

.btn-gold:hover{

    background:var(--gold2);

    transform:
        translateY(-3px);
}

.btn-outline{

    border:
        1px solid
        rgba(255,255,255,.3);

    color:white;
}

.btn-outline:hover{

    border-color:var(--gold);

    color:var(--gold);
}

/* =========================
   MARQUEE
========================= */

.marquee{

    overflow:hidden;

    border-top:
        1px solid var(--line);

    border-bottom:
        1px solid var(--line);

    padding:22px 0;

    background:#0a0a08;
}

.marquee-track{

    width:max-content;

    display:flex;

    gap:55px;

    animation:
        marquee 25s linear infinite;
}

.marquee span{

    color:#857e70;

    font-size:12px;

    letter-spacing:4px;

    text-transform:uppercase;
}

.marquee .dot{

    color:var(--gold);
}

@keyframes marquee{

    to{
        transform:
            translateX(-50%);
    }
}

/* =========================
   GENERAL
========================= */

section{

    padding:120px 5%;
}

.container{

    max-width:1200px;

    margin:auto;
}

.eyebrow{

    color:var(--gold);

    text-transform:uppercase;

    font-size:10px;

    letter-spacing:5px;

    margin-bottom:20px;
}

.section-title{

    font-family:var(--serif);

    font-size:
        clamp(48px,7vw,90px);

    font-weight:400;

    line-height:.9;
}

.section-title em{

    color:var(--gold2);
}

/* =========================
   STORY
========================= */

.story-grid{

    display:grid;

    grid-template-columns:
        1fr 1fr;

    gap:80px;

    align-items:center;
}

.story-image{

    min-height:650px;

    background:

        url("https://images.unsplash.com/photo-1558030006-450675393462?auto=format&fit=crop&w=1200&q=85")
        center/cover;
}

.story-copy p{

    color:var(--muted);

    line-height:1.9;

    margin-top:30px;

    font-size:15px;
}

.story-sign{

    margin-top:45px;

    font-family:var(--serif);

    color:var(--gold2);

    font-size:28px;
}

/* =========================
   STATS
========================= */

.stats{

    background:#0d0d0b;
}

.stats-grid{

    display:grid;

    grid-template-columns:
        repeat(4,1fr);

    border-top:
        1px solid var(--line);

    border-bottom:
        1px solid var(--line);
}

.stat{

    padding:40px 20px;

    border-right:
        1px solid var(--line);

    text-align:center;
}

.stat:last-child{

    border-right:0;
}

.stat strong{

    display:block;

    font-family:var(--serif);

    font-size:55px;

    color:var(--gold2);

    font-weight:400;
}

.stat span{

    color:#777267;

    font-size:10px;

    letter-spacing:2px;

    text-transform:uppercase;
}

/* =========================
   MENU
========================= */

.menu-head{

    display:flex;

    justify-content:space-between;

    align-items:end;

    gap:30px;

    margin-bottom:55px;
}

.filters{

    display:flex;

    gap:10px;

    flex-wrap:wrap;
}

.filter{

    border:
        1px solid var(--line);

    background:transparent;

    color:#aaa397;

    padding:12px 18px;

    cursor:pointer;

    font-family:inherit;

    font-size:10px;

    letter-spacing:1.5px;

    text-transform:uppercase;

    transition:.3s;
}

.filter.active,
.filter:hover{

    background:var(--gold);

    color:#080807;
}

.menu-grid{

    display:grid;

    grid-template-columns:
        repeat(2,1fr);

    gap:1px;

    background:var(--line);
}

.menu-item{

    background:#0b0b09;

    padding:35px;

    display:flex;

    justify-content:space-between;

    gap:30px;

    transition:.3s;
}

.menu-item:hover{

    background:#12120f;
}

.menu-info h3{

    font-family:var(--serif);

    font-size:29px;

    font-weight:500;
}

.menu-info p{

    margin-top:10px;

    color:#777267;

    font-size:12px;

    line-height:1.6;
}

.price{

    color:var(--gold);

    white-space:nowrap;

    font-family:var(--serif);

    font-size:25px;
}

/* =========================
   SIGNATURE
========================= */

.signature{

    background:#0c0c0a;
}

.signature-grid{

    display:grid;

    grid-template-columns:
        1fr 1fr;

    min-height:650px;
}

.signature-image{

    background:

        url("https://images.unsplash.com/photo-1529692236671-f1f6cf9683ba?auto=format&fit=crop&w=1400&q=90")
        center/cover;
}

.signature-copy{

    padding:80px;

    display:flex;

    justify-content:center;

    flex-direction:column;
}

.signature-copy h2{

    font-family:var(--serif);

    font-size:
        clamp(50px,6vw,80px);

    font-weight:400;
}

.signature-copy p{

    color:var(--muted);

    line-height:1.9;

    margin-top:25px;

    max-width:500px;
}

.signature-price{

    margin-top:30px;

    color:var(--gold);

    font-family:var(--serif);

    font-size:32px;
}

/* =========================
   EXPERIENCE
========================= */

.experience-grid{

    display:grid;

    grid-template-columns:
        repeat(3,1fr);

    gap:18px;

    margin-top:55px;
}

.experience-card{

    min-height:340px;

    border:
        1px solid var(--line);

    padding:35px;

    display:flex;

    flex-direction:column;

    justify-content:end;

    background:

        linear-gradient(
            180deg,
            transparent,
            rgba(0,0,0,.8)
        ),

        #11110f;

    transition:.5s;
}

.experience-card:hover{

    transform:
        translateY(-8px);

    border-color:
        rgba(201,164,92,.55);
}

.experience-number{

    color:var(--gold);

    font-size:11px;

    letter-spacing:3px;

    margin-bottom:auto;
}

.experience-card h3{

    font-family:var(--serif);

    font-size:38px;

    font-weight:400;
}

.experience-card p{

    color:#8f897d;

    font-size:13px;

    line-height:1.7;

    margin-top:10px;
}

/* =========================
   GALLERY
========================= */

.gallery-grid{

    display:grid;

    grid-template-columns:
        repeat(3,1fr);

    gap:8px;

    margin-top:55px;
}

.gallery-item{

    height:340px;

    overflow:hidden;

    cursor:pointer;
}

.gallery-item.large{

    height:500px;
}

.gallery-item img{

    width:100%;
    height:100%;

    object-fit:cover;

    transition:
        transform .8s
        cubic-bezier(.16,1,.3,1);
}

.gallery-item:hover img{

    transform:scale(1.07);
}

/* =========================
   TESTIMONIAL
========================= */

.testimonial{

    text-align:center;

    background:#0d0d0b;
}

.quote{

    max-width:900px;

    margin:30px auto;

    font-family:var(--serif);

    font-size:
        clamp(35px,5vw,65px);

    line-height:1.05;
}

.quote-author{

    color:var(--gold);

    letter-spacing:3px;

    font-size:10px;

    text-transform:uppercase;
}

/* =========================
   RESERVATION
========================= */

.reservation{

    background:

        linear-gradient(
            rgba(8,8,7,.88),
            rgba(8,8,7,.96)
        ),

        url("https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=2000&q=85")
        center/cover;
}

.reservation-box{

    max-width:850px;

    margin:auto;

    text-align:center;
}

.reservation h2{

    font-family:var(--serif);

    font-size:
        clamp(55px,8vw,100px);

    font-weight:400;
}

.reservation-intro{

    max-width:600px;

    margin:25px auto 45px;

    color:#a49e91;

    line-height:1.8;
}

.reservation-form{

    text-align:left;

    padding:40px;

    background:
        rgba(12,12,10,.88);

    border:
        1px solid var(--line);

    backdrop-filter:blur(15px);
}

.form-row{

    display:grid;

    grid-template-columns:
        1fr 1fr;

    gap:18px;
}

.form-group{

    margin-bottom:20px;
}

.form-group label{

    display:block;

    color:var(--gold);

    font-size:9px;

    letter-spacing:3px;

    margin-bottom:9px;
}

.form-group input,
.form-group select,
.form-group textarea{

    width:100%;

    background:#10100e;

    border:
        1px solid
        rgba(201,164,92,.18);

    color:#eee8dc;

    padding:16px;

    font-family:inherit;

    font-size:13px;

    outline:none;

    transition:.3s;
}

.form-group textarea{

    resize:vertical;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus{

    border-color:var(--gold);

    box-shadow:
        0 0 0 1px
        rgba(201,164,92,.12);
}

.form-group input::placeholder,
.form-group textarea::placeholder{

    color:#625e55;
}

.form-group select option{

    background:#10100e;

    color:white;
}

.reservation-submit{

    width:100%;

    border:0;

    background:var(--gold);

    color:#080807;

    padding:19px;

    cursor:pointer;

    font-family:inherit;

    font-size:10px;

    letter-spacing:2px;

    font-weight:600;

    transition:.3s;
}

.reservation-submit span{

    margin-left:15px;

    font-size:16px;
}

.reservation-submit:hover{

    background:var(--gold2);

    transform:translateY(-2px);
}

.reservation-success{

    display:none;

    margin-top:25px;

    padding:40px;

    background:#10100e;

    border:
        1px solid var(--line);
}

.reservation-success.show{

    display:block;
}

.success-icon{

    width:55px;
    height:55px;

    margin:0 auto 20px;

    display:flex;

    align-items:center;
    justify-content:center;

    border:
        1px solid var(--gold);

    border-radius:50%;

    color:var(--gold);

    font-size:25px;
}

.reservation-success h3{

    font-family:var(--serif);

    font-size:38px;

    font-weight:400;
}

.reservation-success p{

    color:var(--muted);

    margin-top:10px;
}

.reservation-summary{

    margin-top:25px;

    color:#d5cec1;

    line-height:2;

    font-size:13px;
}

/* =========================
   CONTACT
========================= */

.contact-grid{

    display:grid;

    grid-template-columns:
        1fr 1fr;

    gap:80px;
}

.contact-list{

    margin-top:40px;
}

.contact-row{

    padding:22px 0;

    border-bottom:
        1px solid var(--line);
}

.contact-label{

    color:var(--gold);

    text-transform:uppercase;

    font-size:9px;

    letter-spacing:3px;

    margin-bottom:7px;
}

.contact-value{

    color:#d4cec1;

    font-size:15px;
}

.map{

    min-height:450px;

    background:

        linear-gradient(
            rgba(8,8,7,.3),
            rgba(8,8,7,.3)
        ),

        url("https://images.unsplash.com/photo-1477959858617-67f85cf4f1df?auto=format&fit=crop&w=1200&q=80")
        center/cover;

    display:flex;

    align-items:center;

    justify-content:center;
}

.map a{

    background:#080807;

    color:var(--gold2);

    padding:18px 25px;

    text-decoration:none;

    font-size:10px;

    letter-spacing:2px;

    text-transform:uppercase;
}

/* =========================
   FOOTER
========================= */

footer{

    padding:60px 5% 35px;

    background:#060605;

    border-top:
        1px solid var(--line);
}

.footer-top{

    display:flex;

    justify-content:space-between;

    align-items:center;

    gap:30px;
}

.footer-logo{

    font-family:var(--serif);

    font-size:45px;

    letter-spacing:4px;
}

.footer-social{

    display:flex;

    gap:25px;
}

.footer-social a{

    color:#898378;

    text-decoration:none;

    font-size:11px;

    letter-spacing:2px;
}

.footer-social a:hover{

    color:var(--gold);
}

.footer-bottom{

    border-top:
        1px solid var(--line);

    margin-top:45px;

    padding-top:25px;

    display:flex;

    justify-content:space-between;

    color:#57534b;

    font-size:10px;
}

/* =========================
   REVEAL
========================= */

.reveal{

    opacity:0;

    transform:
        translateY(35px);

    transition:
        opacity .9s ease,
        transform .9s ease;
}

.reveal.show{

    opacity:1;

    transform:none;
}

/* =========================
   MOBILE
========================= */

@media(max-width:800px){

    nav{

        padding:18px 5%;
    }

    .nav-links{

        display:none;
    }

    .logo{

        font-size:24px;
    }

    .nav-cta{

        padding:10px 13px;

        font-size:9px;
    }

    .hero-content{

        padding-top:100px;
    }

    .hero h1{

        font-size:65px;

        letter-spacing:-1px;
    }

    .hero-text{

        font-size:14px;
    }

    .hero-buttons{

        flex-direction:column;

        align-items:flex-start;
    }

    section{

        padding:80px 5%;
    }

    .story-grid,
    .signature-grid,
    .contact-grid{

        grid-template-columns:1fr;

        gap:35px;
    }

    .story-image{

        min-height:430px;

        order:2;
    }

    .story-copy{

        order:1;
    }

    .stats-grid{

        grid-template-columns:
            repeat(2,1fr);
    }

    .stat{

        border-bottom:
            1px solid var(--line);
    }

    .menu-head{

        flex-direction:column;

        align-items:flex-start;
    }

    .menu-grid{

        grid-template-columns:1fr;
    }

    .signature-copy{

        padding:50px 30px;
    }

    .experience-grid{

        grid-template-columns:1fr;
    }

    .gallery-grid{

        grid-template-columns:
            1fr 1fr;
    }

    .gallery-item,
    .gallery-item.large{

        height:260px;
    }

    .footer-top{

        flex-direction:column;

        align-items:flex-start;
    }

    .footer-bottom{

        flex-direction:column;

        gap:10px;
    }

    .loader-logo{

        font-size:48px;

        letter-spacing:4px;
    }

    .orbit-1{

        width:270px;
        height:270px;
    }

    .orbit-2{

        width:360px;
        height:360px;
    }

    .reservation-form{

        padding:25px 18px;
    }

    .form-row{

        grid-template-columns:1fr;

        gap:0;
    }

}

@media(max-width:420px){

    .hero h1{

        font-size:54px;
    }

    .gallery-grid{

        grid-template-columns:1fr;
    }

    .gallery-item,
    .gallery-item.large{

        height:330px;
    }

    .loader-logo{

        font-size:40px;
    }

}

</style>
</head>

<body class="lock">

<!-- =========================
     LOADER
========================= -->

<div class="loader" id="loader">

    <div class="loader-orbit orbit-1"></div>
    <div class="loader-orbit orbit-2"></div>

    <div class="loader-inner">

        <div class="loader-small">
            TOKAT • ESTABLISHED
        </div>

        <div class="loader-logo">
            HAN ET HOUSE
        </div>

        <div class="loader-sub">
            PREMIUM STEAK EXPERIENCE
        </div>

        <div class="loader-line">
            <span></span>
        </div>

    </div>

</div>


<!-- =========================
     NAV
========================= -->

<nav id="nav">

    <div class="logo">
        HAN ET HOUSE
    </div>

    <ul class="nav-links">

        <li>
            <a href="#story">
                Hikâyemiz
            </a>
        </li>

        <li>
            <a href="#menu">
                Menü
            </a>
        </li>

        <li>
            <a href="#experience">
                Deneyim
            </a>
        </li>

        <li>
            <a href="#gallery">
                Galeri
            </a>
        </li>

        <li>
            <a href="#reservation">
                Rezervasyon
            </a>
        </li>

        <li>
            <a href="#contact">
                İletişim
            </a>
        </li>

    </ul>

    <a
        class="nav-cta"
        href="#reservation"
    >
        Rezervasyon
    </a>

</nav>


<!-- =========================
     HERO
========================= -->

<header class="hero">

    <div class="hero-content reveal">

        <div class="hero-small">
            TOKAT • STEAKHOUSE
        </div>

        <h1>
            Etin
            <span>Sanatı.</span>
        </h1>

        <p class="hero-text">

            Özenle seçilen etler,
            ustalıkla hazırlanan
            lezzetler ve Tokat'ın
            kalbinde unutulmaz
            bir gastronomi deneyimi.

        </p>

        <div class="hero-buttons">

            <a
                href="#menu"
                class="btn btn-gold"
            >
                Menüyü Keşfet
            </a>

            <a
                href="#reservation"
                class="btn btn-outline"
            >
                Masa Ayır
            </a>

        </div>

    </div>

</header>


<!-- =========================
     MARQUEE
========================= -->

<div class="marquee">

    <div class="marquee-track">

        <span>Premium Et</span>
        <span class="dot">✦</span>

        <span>Ustalık</span>
        <span class="dot">✦</span>

        <span>Tokat</span>
        <span class="dot">✦</span>

        <span>Lezzet</span>
        <span class="dot">✦</span>

        <span>HAN ET HOUSE</span>
        <span class="dot">✦</span>

        <span>Premium Et</span>
        <span class="dot">✦</span>

        <span>Ustalık</span>
        <span class="dot">✦</span>

        <span>Tokat</span>
        <span class="dot">✦</span>

        <span>Lezzet</span>
        <span class="dot">✦</span>

        <span>HAN ET HOUSE</span>

    </div>

</div>


<!-- =========================
     STORY
========================= -->

<section id="story">

    <div class="container">

        <div class="story-grid">

            <div class="story-image reveal"></div>

            <div class="story-copy reveal">

                <div class="eyebrow">
                    Hikâyemiz
                </div>

                <h2 class="section-title">

                    Et sadece<br>

                    <em>bir yemek</em><br>

                    değildir.

                </h2>

                <p>

                    HAN ET HOUSE'ta iyi etin
                    yalnızca pişirilmediğine,
                    deneyimlenmesi gerektiğine
                    inanıyoruz.

                </p>

                <p>

                    En kaliteli ürünleri seçiyor,
                    doğru tekniklerle hazırlıyor
                    ve her tabağı kendine özgü
                    bir karakterle sunuyoruz.

                </p>

                <div class="story-sign">
                    HAN ET HOUSE
                </div>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     STATS
========================= -->

<section class="stats">

    <div class="container">

        <div class="stats-grid reveal">

            <div class="stat">

                <strong>4.6</strong>

                <span>
                    Misafir Puanı
                </span>

            </div>

            <div class="stat">

                <strong>287+</strong>

                <span>
                    Değerlendirme
                </span>

            </div>

            <div class="stat">

                <strong>100%</strong>

                <span>
                    Lezzet Tutkusu
                </span>

            </div>

            <div class="stat">

                <strong>∞</strong>

                <span>
                    Memnuniyet
                </span>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     MENU
========================= -->

<section id="menu">

    <div class="container">

        <div class="menu-head reveal">

            <div>

                <div class="eyebrow">
                    Menü
                </div>

                <h2 class="section-title">

                    Seçkin<br>

                    <em>Lezzetler.</em>

                </h2>

            </div>

            <div class="filters">

                <button
                    class="filter active"
                    data-filter="all"
                >
                    Tümü
                </button>

                <button
                    class="filter"
                    data-filter="et"
                >
                    Etler
                </button>

                <button
                    class="filter"
                    data-filter="izgara"
                >
                    Izgara
                </button>

                <button
                    class="filter"
                    data-filter="tatli"
                >
                    Tatlı
                </button>

            </div>

        </div>


        <div class="menu-grid">

            <div
                class="menu-item reveal"
                data-category="et"
            >

                <div class="menu-info">

                    <h3>
                        Dana Antrikot
                    </h3>

                    <p>
                        Özenle seçilmiş premium dana eti.
                    </p>

                </div>

                <div class="price">
                    ₺1.100
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="et"
            >

                <div class="menu-info">

                    <h3>
                        Dana Bonfile
                    </h3>

                    <p>
                        Yumuşak dokusu ve yoğun aromasıyla.
                    </p>

                </div>

                <div class="price">
                    ₺1.100
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="et"
            >

                <div class="menu-info">

                    <h3>
                        Kuzu Pirzola
                    </h3>

                    <p>
                        Izgarada ustalıkla hazırlanır.
                    </p>

                </div>

                <div class="price">
                    ₺1.000
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="et"
            >

                <div class="menu-info">

                    <h3>
                        Kuzu Lokum
                    </h3>

                    <p>
                        Özel seçilmiş kuzu eti.
                    </p>

                </div>

                <div class="price">
                    ₺1.150
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="et"
            >

                <div class="menu-info">

                    <h3>
                        Küşleme
                    </h3>

                    <p>
                        Et severlerin özel tercihi.
                    </p>

                </div>

                <div class="price">
                    ₺1.100
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="izgara"
            >

                <div class="menu-info">

                    <h3>
                        Izgara Köfte
                    </h3>

                    <p>
                        Geleneksel lezzetin HAN dokunuşu.
                    </p>

                </div>

                <div class="price">
                    ₺550
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="izgara"
            >

                <div class="menu-info">

                    <h3>
                        Adana Kebap
                    </h3>

                    <p>
                        Izgarada hazırlanan özel Adana.
                    </p>

                </div>

                <div class="price">
                    ₺600
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="izgara"
            >

                <div class="menu-info">

                    <h3>
                        Adana Dürüm
                    </h3>

                    <p>
                        Klasik Adana lezzetinin dürüm hali.
                    </p>

                </div>

                <div class="price">
                    ₺300
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="tatli"
            >

                <div class="menu-info">

                    <h3>
                        Ekmek Kadayıfı
                    </h3>

                    <p>
                        Geleneksel Türk tatlısı.
                    </p>

                </div>

                <div class="price">
                    ₺170
                </div>

            </div>


            <div
                class="menu-item reveal"
                data-category="tatli"
            >

                <div class="menu-info">

                    <h3>
                        Fırın Sütlaç
                    </h3>

                    <p>
                        Fırında hazırlanmış klasik tat.
                    </p>

                </div>

                <div class="price">
                    ₺200
                </div>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     SIGNATURE
========================= -->

<section class="signature">

    <div class="container">

        <div class="signature-grid reveal">

            <div class="signature-image"></div>

            <div class="signature-copy">

                <div class="eyebrow">
                    HAN Selection
                </div>

                <h2>

                    Kuzu<br>

                    <em>Lokum</em>

                </h2>

                <p>

                    Özel olarak seçilen kuzu etinin
                    doğru ısı ve ustalıkla
                    hazırlanmasıyla ortaya çıkan
                    eşsiz bir HAN ET HOUSE
                    deneyimi.

                </p>

                <div class="signature-price">
                    ₺1.150
                </div>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     EXPERIENCE
========================= -->

<section id="experience">

    <div class="container">

        <div class="eyebrow reveal">
            Deneyim
        </div>

        <h2 class="section-title reveal">

            Masadan<br>

            <em>daha fazlası.</em>

        </h2>


        <div class="experience-grid">

            <div class="experience-card reveal">

                <div class="experience-number">
                    01 / SELECTION
                </div>

                <h3>
                    Seçim
                </h3>

                <p>
                    Kaliteli bir deneyim için
                    doğru ürünü seçmekle başlıyoruz.
                </p>

            </div>


            <div class="experience-card reveal">

                <div class="experience-number">
                    02 / FIRE
                </div>

                <h3>
                    Ateş
                </h3>

                <p>
                    Izgaranın gücü ve ustalığın
                    dengesiyle ideal pişirme.
                </p>

            </div>


            <div class="experience-card reveal">

                <div class="experience-number">
                    03 / MOMENT
                </div>

                <h3>
                    An
                </h3>

                <p>
                    Lezzetin yanında iyi sohbetler
                    ve unutulmaz anlar.
                </p>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     GALLERY
========================= -->

<section id="gallery">

    <div class="container">

        <div class="eyebrow reveal">
            Galeri
        </div>

        <h2 class="section-title reveal">

            HAN'ın<br>

            <em>atmosferi.</em>

        </h2>


        <div class="gallery-grid">

            <div class="gallery-item large reveal">

                <img
                    src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=85"
                    alt="HAN ET HOUSE yemek"
                >

            </div>

            <div class="gallery-item reveal">

                <img
                    src="https://images.unsplash.com/photo-1558030006-450675393462?auto=format&fit=crop&w=900&q=85"
                    alt="Izgara et"
                >

            </div>

            <div class="gallery-item large reveal">

                <img
                    src="https://images.unsplash.com/photo-1529692236671-f1f6cf9683ba?auto=format&fit=crop&w=1200&q=85"
                    alt="Steak"
                >

            </div>

            <div class="gallery-item reveal">

                <img
                    src="https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=900&q=85"
                    alt="Restoran yemeği"
                >

            </div>

            <div class="gallery-item reveal">

                <img
                    src="https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=900&q=85"
                    alt="Lezzet"
                >

            </div>

            <div class="gallery-item reveal">

                <img
                    src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=900&q=85"
                    alt="Et tabağı"
                >

            </div>

        </div>

    </div>

</section>


<!-- =========================
     TESTIMONIAL
========================= -->

<section class="testimonial">

    <div class="container reveal">

        <div class="eyebrow">
            Misafirlerimiz
        </div>

        <div class="quote">

            “İyi etin, iyi bir atmosfer ve
            güzel bir akşamla buluştuğu yer.”

        </div>

        <div class="quote-author">
            HAN ET HOUSE • TOKAT
        </div>

    </div>

</section>


<!-- =========================
     RESERVATION
========================= -->

<section
    class="reservation"
    id="reservation"
>

    <div class="reservation-box reveal">

        <div class="eyebrow">
            MASANIZI AYIRIN
        </div>

        <h2>

            Akşamınızı<br>

            <em>özel kılın.</em>

        </h2>

        <p class="reservation-intro">

            Tarih, saat ve kişi sayınızı seçerek
            rezervasyon talebinizi oluşturun.

        </p>


        <form
            class="reservation-form"
            id="reservationForm"
        >

            <div class="form-row">

                <div class="form-group">

                    <label>
                        TARİH
                    </label>

                    <input
                        type="date"
                        id="reservationDate"
                        required
                    >

                </div>


                <div class="form-group">

                    <label>
                        SAAT
                    </label>

                    <select
                        id="reservationTime"
                        required
                    >

                        <option value="">
                            Saat seçin
                        </option>

                        <option>18:00</option>
                        <option>18:30</option>
                        <option>19:00</option>
                        <option>19:30</option>
                        <option>20:00</option>
                        <option>20:30</option>
                        <option>21:00</option>
                        <option>21:30</option>
                        <option>22:00</option>
                        <option>22:30</option>
                        <option>23:00</option>

                    </select>

                </div>

            </div>


            <div class="form-row">

                <div class="form-group">

                    <label>
                        KİŞİ SAYISI
                    </label>

                    <select
                        id="guestCount"
                        required
                    >

                        <option value="">
                            Kişi sayısı
                        </option>

                        <option>1</option>
                        <option>2</option>
                        <option>3</option>
                        <option>4</option>
                        <option>5</option>
                        <option>6</option>
                        <option>7</option>
                        <option>8</option>
                        <option>9</option>
                        <option>10</option>
                        <option>11</option>
                        <option>12</option>

                    </select>

                </div>


                <div class="form-group">

                    <label>
                        AD SOYAD
                    </label>

                    <input
                        type="text"
                        id="guestName"
                        placeholder="Adınız Soyadınız"
                        required
                    >

                </div>

            </div>


            <div class="form-group">

                <label>
                    TELEFON
                </label>

                <input
                    type="tel"
                    id="guestPhone"
                    placeholder="05XX XXX XX XX"
                    required
                >

            </div>


            <div class="form-group">

                <label>
                    NOT
                </label>

                <textarea
                    id="guestNote"
                    rows="4"
                    placeholder="Özel bir isteğiniz varsa yazabilirsiniz."
                ></textarea>

            </div>


            <button
                type="submit"
                class="reservation-submit"
            >

                REZERVASYON TALEBİ GÖNDER

                <span>→</span>

            </button>

        </form>


        <div
            class="reservation-success"
            id="reservationSuccess"
        >

            <div class="success-icon">
                ✓
            </div>

            <h3>
                Talebiniz Alındı
            </h3>

            <p>
                Rezervasyon bilgileriniz
                başarıyla oluşturuldu.
            </p>

            <div
                class="reservation-summary"
                id="reservationSummary"
            ></div>

        </div>

    </div>

</section>


<!-- =========================
     CONTACT
========================= -->

<section id="contact">

    <div class="container">

        <div class="contact-grid">

            <div class="reveal">

                <div class="eyebrow">
                    İletişim
                </div>

                <h2 class="section-title">

                    Bizi<br>

                    <em>bulun.</em>

                </h2>


                <div class="contact-list">

                    <div class="contact-row">

                        <div class="contact-label">
                            Adres
                        </div>

                        <div class="contact-value">

                            Yeşilırmak,
                            Sıtkı Ulaşoğlu 2. Sk.,
                            60030 Tokat Merkez / Tokat

                        </div>

                    </div>


                    <div class="contact-row">

                        <div class="contact-label">
                            Telefon
                        </div>

                        <div class="contact-value">

                            +90 356 212 48 88

                        </div>

                    </div>


                    <div class="contact-row">

                        <div class="contact-label">
                            Instagram
                        </div>

                        <div class="contact-value">

                            @han_et_house

                        </div>

                    </div>

                </div>

            </div>


            <div class="map reveal">

                <a
                    href="https://www.google.com/maps/search/?api=1&query=HAN+ET+HOUSE+Tokat"
                    target="_blank"
                >
                    Google Maps'te Aç
                </a>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     FOOTER
========================= -->

<footer>

    <div class="footer-top">

        <div class="footer-logo">
            HAN ET HOUSE
        </div>

        <div class="footer-social">

            <a
                href="https://www.instagram.com/han_et_house/"
                target="_blank"
            >
                INSTAGRAM
            </a>

            <a
                href="#reservation"
            >
                REZERVASYON
            </a>

        </div>

    </div>


    <div class="footer-bottom">

        <span>
            © 2026 HAN ET HOUSE
        </span>

        <span>
            TOKAT • TÜRKİYE
        </span>

    </div>

</footer>


<script>

/* =========================
   EXACT 2 SECOND LOADER
========================= */

const loader =
    document.getElementById("loader");

const loaderStart =
    performance.now();

function closeLoader(){

    const elapsed =
        performance.now() - loaderStart;

    const remaining =
        Math.max(
            0,
            2000 - elapsed
        );

    setTimeout(() => {

        loader.classList.add("hide");

        document.body.classList.remove(
            "lock"
        );

    }, remaining);

}

if(
    document.readyState ===
    "complete"
){

    closeLoader();

}else{

    window.addEventListener(
        "load",
        closeLoader,
        {once:true}
    );

}


/* =========================
   NAV SCROLL
========================= */

const nav =
    document.getElementById("nav");

window.addEventListener(
    "scroll",
    () => {

        if(
            window.scrollY > 40
        ){

            nav.classList.add(
                "scrolled"
            );

        }else{

            nav.classList.remove(
                "scrolled"
            );

        }

    }
);


/* =========================
   SCROLL REVEAL
========================= */

const revealElements =
    document.querySelectorAll(
        ".reveal"
    );

const observer =
    new IntersectionObserver(
        entries => {

            entries.forEach(
                entry => {

                    if(
                        entry.isIntersecting
                    ){

                        entry.target.classList.add(
                            "show"
                        );

                        observer.unobserve(
                            entry.target
                        );

                    }

                }
            );

        },
        {
            threshold:.12
        }
    );


revealElements.forEach(
    element => {

        observer.observe(
            element
        );

    }
);


/* =========================
   MENU FILTER
========================= */

const filters =
    document.querySelectorAll(
        ".filter"
    );

const menuItems =
    document.querySelectorAll(
        ".menu-item"
    );

filters.forEach(
    filter => {

        filter.addEventListener(
            "click",
            () => {

                filters.forEach(
                    button => {

                        button.classList.remove(
                            "active"
                        );

                    }
                );

                filter.classList.add(
                    "active"
                );

                const category =
                    filter.dataset.filter;

                menuItems.forEach(
                    item => {

                        if(
                            category === "all" ||
                            item.dataset.category ===
                            category
                        ){

                            item.style.display =
                                "flex";

                        }else{

                            item.style.display =
                                "none";

                        }

                    }
                );

            }
        );

    }
);


/* =========================
   GALLERY
========================= */

document
.querySelectorAll(
    ".gallery-item img"
)
.forEach(
    img => {

        img.addEventListener(
            "click",
            () => {

                const overlay =
                    document.createElement(
                        "div"
                    );

                overlay.style.position =
                    "fixed";

                overlay.style.inset =
                    "0";

                overlay.style.zIndex =
                    "999999";

                overlay.style.background =
                    "rgba(0,0,0,.94)";

                overlay.style.display =
                    "flex";

                overlay.style.alignItems =
                    "center";

                overlay.style.justifyContent =
                    "center";

                overlay.style.padding =
                    "30px";

                overlay.style.cursor =
                    "zoom-out";


                const image =
                    document.createElement(
                        "img"
                    );

                image.src =
                    img.src;

                image.style.maxWidth =
                    "95%";

                image.style.maxHeight =
                    "90%";

                image.style.objectFit =
                    "contain";


                overlay.appendChild(
                    image
                );

                document.body.appendChild(
                    overlay
                );


                overlay.addEventListener(
                    "click",
                    () => {

                        overlay.remove();

                    }
                );

            }
        );

    }
);


/* =========================
   RESERVATION
========================= */

const reservationForm =
    document.getElementById(
        "reservationForm"
    );

const reservationDate =
    document.getElementById(
        "reservationDate"
    );

const reservationTime =
    document.getElementById(
        "reservationTime"
    );

const guestCount =
    document.getElementById(
        "guestCount"
    );

const guestName =
    document.getElementById(
        "guestName"
    );

const guestPhone =
    document.getElementById(
        "guestPhone"
    );

const guestNote =
    document.getElementById(
        "guestNote"
    );

const reservationSuccess =
    document.getElementById(
        "reservationSuccess"
    );

const reservationSummary =
    document.getElementById(
        "reservationSummary"
    );


/* Bugünden önceki tarih seçilemez */

const now =
    new Date();

const year =
    now.getFullYear();

const month =
    String(
        now.getMonth()+1
    ).padStart(2,"0");

const day =
    String(
        now.getDate()
    ).padStart(2,"0");

reservationDate.min =
    `${year}-${month}-${day}`;


/* Form */

reservationForm.addEventListener(
    "submit",
    function(e){

        e.preventDefault();


        const date =
            reservationDate.value;

        const time =
            reservationTime.value;

        const guests =
            guestCount.value;

        const name =
            guestName.value.trim();

        const phone =
            guestPhone.value.trim();

        const note =
            guestNote.value.trim();


        reservationSummary.innerHTML = `

            <strong>
                ${name}
            </strong>

            <br>

            📅 ${date}

            <br>

            🕐 ${time}

            <br>

            👥 ${guests} kişi

            <br>

            📱 ${phone}

            ${
                note
                ?
                `<br>📝 ${note}`
                :
                ""
            }

        `;


        reservationForm.style.display =
            "none";

        reservationSuccess.classList.add(
            "show"
        );

    }
);


/* =========================
   SMOOTH ANCHOR
========================= */

document
.querySelectorAll(
    'a[href^="#"]'
)
.forEach(
    link => {

        link.addEventListener(
            "click",
            function(e){

                const target =
                    document.querySelector(
                        this.getAttribute(
                            "href"
                        )
                    );

                if(target){

                    e.preventDefault();

                    target.scrollIntoView({
                        behavior:"smooth"
                    });

                }

            }
        );

    }
);

</script>

</body>
</html>
