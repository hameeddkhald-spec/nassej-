<!DOCTYPE html>  
<html lang="ar" dir="rtl">  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
<title>نَسِيج | NASEEJ — AI-Powered Creative Agency</title>  
<link rel="preconnect" href="https://fonts.googleapis.com">  
<link href="https://fonts.googleapis.com/css2?family=Noto+Kufi+Arabic:wght@300;400;500;600;700;800;900&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">  
<style>  
:root{--navy:#0A192F;--navy-dark:#050d1a;--gold:#C9A96E;--gold-light:#E0C896;--sage:#8B9D83;--cream:#F5F0E8;--cream-dark:#E8E2D6;--text-dark:#2D2D2D;--text-light:#F5F0E8;--tr:all .4s cubic-bezier(.4,0,.2,1)}  
*{margin:0;padding:0;box-sizing:border-box}  
html{scroll-behavior:smooth}  
body{font-family:'Noto Kufi Arabic','Inter',sans-serif;background:var(--cream);color:var(--text-dark);overflow-x:hidden;line-height:1.8}  
  
/* LOADER */  
#loader{position:fixed;inset:0;background:var(--navy);z-index:9999;display:flex;align-items:center;justify-content:center;flex-direction:column;transition:opacity .8s,visibility .8s}  
#loader.hidden{opacity:0;visibility:hidden}  
.loader-grid{display:grid;grid-template-columns:repeat(4,16px);grid-template-rows:repeat(4,16px);gap:4px;margin-bottom:24px}  
.loader-cell{width:16px;height:16px;border-radius:3px;opacity:0;transform:scale(0);animation:assemble .6s ease forwards}  
.loader-cell.gold{background:var(--gold)}.loader-cell.sage{background:var(--sage)}.loader-cell.navy{background:#1a3a5c}.loader-cell.empty{background:transparent;border:1px solid var(--gold)}  
@keyframes assemble{to{opacity:1;transform:scale(1)}}  
.loader-text{color:var(--gold);font-size:14px;letter-spacing:4px;animation:pulse 1.5s ease infinite}  
@keyframes pulse{0%,100%{opacity:.5}50%{opacity:1}}  
  
/* NAV */  
nav{position:fixed;top:0;left:0;right:0;z-index:1000;padding:16px 24px;transition:var(--tr);background:transparent}  
nav.scrolled{background:rgba(10,25,47,.95);backdrop-filter:blur(20px);box-shadow:0 4px 30px rgba(0,0,0,.2);padding:12px 24px}  
.nav-container{max-width:1200px;margin:0 auto;display:flex;align-items:center;justify-content:space-between}  
.nav-logo{display:flex;align-items:center;gap:10px;text-decoration:none}  
.nav-logo-icon{width:36px;height:36px;background:var(--navy);border:2px solid var(--gold);border-radius:8px;display:grid;grid-template-columns:repeat(4,1fr);grid-template-rows:repeat(4,1fr);gap:1px;padding:3px}  
.nav-logo-icon span{border-radius:1px}  
.nav-logo-text{color:var(--gold);font-weight:700;font-size:18px;letter-spacing:2px}  
.nav-links{display:flex;gap:32px;list-style:none}  
.nav-links a{color:var(--text-light);text-decoration:none;font-size:14px;font-weight:500;position:relative;padding:4px 0;transition:var(--tr)}  
.nav-links a::after{content:'';position:absolute;bottom:0;right:0;width:0;height:2px;background:var(--gold);transition:var(--tr)}  
.nav-links a:hover{color:var(--gold)}.nav-links a:hover::after{width:100%}  
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;background:none;border:none;padding:4px}  
.hamburger span{display:block;width:24px;height:2px;background:var(--gold);transition:var(--tr);border-radius:2px}  
.mobile-menu{position:fixed;top:0;right:-100%;width:280px;height:100vh;background:var(--navy);z-index:1001;padding:80px 32px 32px;transition:var(--tr);box-shadow:-10px 0 40px rgba(0,0,0,.3)}  
.mobile-menu.open{right:0}  
.mobile-menu .close-btn{position:absolute;top:20px;left:20px;background:none;border:none;color:var(--gold);font-size:28px;cursor:pointer}  
.mobile-menu ul{list-style:none;display:flex;flex-direction:column;gap:24px}  
.mobile-menu a{color:var(--text-light);text-decoration:none;font-size:16px;font-weight:500;display:block;padding:8px 0;border-bottom:1px solid rgba(201,169,110,.2)}  
.mobile-menu a:hover{color:var(--gold)}  
.overlay{position:fixed;inset:0;background:rgba(0,0,0,.5);z-index:1000;opacity:0;visibility:hidden;transition:var(--tr)}  
.overlay.active{opacity:1;visibility:visible}  
  
/* HERO */  
.hero{min-height:100vh;background:var(--cream);position:relative;display:flex;align-items:center;justify-content:center;overflow:hidden;padding:100px 24px 60px}  
.hero-grid{position:absolute;inset:0;overflow:hidden;pointer-events:none}  
.hero-grid-dot{position:absolute;width:4px;height:4px;border-radius:50%;animation:gridFade 4s ease-in-out infinite}  
@keyframes gridFade{0%,100%{opacity:.1;transform:scale(1)}50%{opacity:.6;transform:scale(1.5)}}  
.hero-corner{position:absolute;width:120px;height:120px;pointer-events:none}  
.hero-corner.top-left{top:80px;left:40px;border-top:2px solid var(--gold);border-left:2px solid var(--gold);opacity:.4}  
.hero-corner.bottom-right{bottom:40px;right:40px;border-bottom:2px solid var(--gold);border-right:2px solid var(--gold);opacity:.4}  
.hero-content{position:relative;z-index:2;text-align:center;max-width:800px}  
.hero-icon-wrap{display:inline-flex;align-items:center;justify-content:center;width:100px;height:100px;background:var(--navy);border:2px solid var(--gold);border-radius:20px;margin-bottom:32px;animation:fadeInUp .8s ease forwards;opacity:0}  
.hero-icon{display:grid;grid-template-columns:repeat(4,14px);grid-template-rows:repeat(4,14px);gap:3px}  
.hero-icon span{border-radius:2px}  
.hero-arabic{font-size:clamp(48px,10vw,96px);font-weight:900;color:var(--navy);line-height:1.1;margin-bottom:8px;animation:fadeInUp .8s ease .2s forwards;opacity:0}  
.hero-english{font-size:clamp(18px,4vw,28px);font-weight:300;color:var(--gold);letter-spacing:12px;margin-bottom:16px;animation:fadeInUp .8s ease .4s forwards;opacity:0}  
.hero-tagline{font-size:16px;color:var(--text-dark);opacity:.7;margin-bottom:40px;font-weight:400;animation:fadeInUp .8s ease .5s forwards;opacity:0}  
.hero-buttons{display:flex;gap:16px;justify-content:center;flex-wrap:wrap;animation:fadeInUp .8s ease .6s forwards;opacity:0}  
.btn{display:inline-flex;align-items:center;justify-content:center;padding:14px 36px;border-radius:12px;font-size:15px;font-weight:600;font-family:inherit;cursor:pointer;transition:var(--tr);text-decoration:none;border:none;gap:8px}  
.btn-primary{background:var(--navy);color:var(--gold)}.btn-primary:hover{background:var(--gold);color:var(--navy);transform:translateY(-2px);box-shadow:0 10px 30px rgba(201,169,110,.3)}  
.btn-outline{background:transparent;color:var(--gold);border:2px solid var(--gold)}.btn-outline:hover{background:var(--gold);color:var(--navy);transform:translateY(-2px)}  
@keyframes fadeInUp{from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:translateY(0)}}  
  
/* SECTIONS COMMON */  
section{padding:100px 24px;position:relative}  
.container{max-width:1200px;margin:0 auto}  
.section-title{font-size:clamp(28px,5vw,42px);font-weight:800;text-align:center;margin-bottom:16px}  
.section-subtitle{text-align:center;font-size:16px;opacity:.7;margin-bottom:60px}  
  
/* PROBLEMS */  
.problems{background:var(--navy)}.problems .section-title{color:var(--gold)}  
.problems-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:24px}  
.problem-card{background:rgba(10,25,47,.8);border:1px solid var(--gold);border-radius:16px;padding:32px;transition:var(--tr);opacity:0;transform:translateY(30px)}  
.problem-card.visible{opacity:1;transform:translateY(0)}  
.problem-card:hover{transform:translateY(-8px);box-shadow:0 20px 40px rgba(201,169,110,.15)}  
.problem-icon{width:56px;height:56px;background:rgba(201,169,110,.1);border-radius:14px;display:flex;align-items:center;justify-content:center;margin-bottom:20px;font-size:28px}  
.problem-card h3{color:var(--gold);font-size:18px;font-weight:700;margin-bottom:12px}  
.problem-card p{color:var(--text-light);opacity:.8;font-size:14px;line-height:1.8}  
  
/* SOLUTIONS */  
.solutions{background:var(--cream)}.solutions .section-title{color:var(--navy)}  
.solutions-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px}  
.solution-card{background:#fff;border-radius:20px;padding:40px 32px;text-align:center;box-shadow:0 4px 20px rgba(0,0,0,.05);transition:var(--tr);border:2px solid transparent;opacity:0;transform:translateY(30px)}  
.solution-card.visible{opacity:1;transform:translateY(0)}  
.solution-card:hover{border-color:var(--gold);transform:translateY(-6px);box-shadow:0 20px 40px rgba(0,0,0,.08)}  
.solution-icon{width:72px;height:72px;background:linear-gradient(135deg,rgba(201,169,110,.1),rgba(139,157,131,.1));border-radius:20px;display:flex;align-items:center;justify-content:center;margin:0 auto 24px;font-size:32px}  
.solution-card h3{color:var(--navy);font-size:18px;font-weight:700;margin-bottom:12px}  
.solution-card p{color:var(--text-dark);opacity:.7;font-size:14px;line-height:1.8}  
  
/* PRICING */  
.pricing{background:var(--navy)}.pricing .section-title{color:var(--gold)}.pricing .section-subtitle{color:var(--text-light);opacity:.6}  
.currency-toggle{display:flex;justify-content:center;gap:8px;margin-bottom:48px;flex-wrap:wrap}  
.currency-btn{padding:10px 24px;border-radius:8px;border:1px solid rgba(201,169,110,.3);background:transparent;color:var(--text-light);font-family:inherit;font-size:14px;cursor:pointer;transition:var(--tr)}  
.currency-btn.active{background:var(--gold);color:var(--navy);border-color:var(--gold);font-weight:600}  
.currency-btn:hover:not(.active){border-color:var(--gold);color:var(--gold)}  
.pricing-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;align-items:start}  
.pricing-card{background:rgba(255,255,255,.03);border:1px solid rgba(201,169,110,.3);border-radius:24px;padding:40px 28px;text-align:center;transition:var(--tr);position:relative;opacity:0;transform:translateY(30px)}  
.pricing-card.visible{opacity:1;transform:translateY(0)}  
.pricing-card:hover{transform:translateY(-6px);border-color:var(--gold)}  
.pricing-card.highlighted{border:2px solid var(--gold);background:linear-gradient(180deg,rgba(201,169,110,.08),transparent);transform:scale(1.05);box-shadow:0 0 60px rgba(201,169,110,.1)}  
.pricing-card.highlighted:hover{transform:scale(1.05) translateY(-6px)}  
.badge{position:absolute;top:-12px;left:50%;transform:translateX(-50%);background:var(--gold);color:var(--navy);padding:6px 20px;border-radius:20px;font-size:12px;font-weight:700}  
.pricing-card h3{color:var(--gold);font-size:20px;font-weight:700;margin-bottom:16px}  
.price{font-size:36px;font-weight:800;color:var(--text-light);margin-bottom:4px}  
.price-secondary{font-size:14px;color:var(--sage);margin-bottom:24px}  
.pricing-features{list-style:none;text-align:right;margin-bottom:32px}  
.pricing-features li{color:var(--text-light);opacity:.8;font-size:14px;padding:8px 0;border-bottom:1px solid rgba(255,255,255,.05);display:flex;align-items:center;gap:8px}  
.pricing-features li::before{content:'✓';color:var(--gold);font-weight:700;flex-shrink:0}  
.pricing-card .btn{width:100%}  
  
/* AUDIENCE */  
.audience{background:var(--cream)}.audience .section-title{color:var(--navy)}  
.audience-grid{display:flex;flex-direction:column;gap:20px}  
.audience-card{display:flex;align-items:center;gap:24px;background:#fff;border-radius:16px;padding:28px 32px;box-shadow:0 4px 20px rgba(0,0,0,.04);transition:var(--tr);border-right:4px solid var(--sage);opacity:0;transform:translateX(-30px)}  
.audience-card.visible{opacity:1;transform:translateX(0)}  
.audience-card:hover{transform:translateX(-6px);box-shadow:0 10px 30px rgba(0,0,0,.08)}  
.audience-icon{width:64px;height:64px;background:linear-gradient(135deg,rgba(139,157,131,.15),rgba(139,157,131,.05));border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:28px;flex-shrink:0}  
.audience-card h3{color:var(--navy);font-size:17px;font-weight:700;margin-bottom:6px}  
.audience-card p{color:var(--text-dark);opacity:.65;font-size:14px}  
  
/* PORTFOLIO */  
.portfolio{background:var(--navy)}.portfolio .section-title{color:var(--gold)}  
.portfolio-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:20px}  
.portfolio-item{position:relative;border-radius:16px;overflow:hidden;aspect-ratio:4/3;cursor:pointer;opacity:0;transform:scale(.95);transition:var(--tr)}  
.portfolio-item.visible{opacity:1;transform:scale(1)}  
.portfolio-item:hover{transform:scale(1.03)}  
.portfolio-item:hover .portfolio-overlay{opacity:1}  
.portfolio-placeholder{width:100%;height:100%;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:8px}  
.portfolio-placeholder span{font-size:40px}.portfolio-placeholder p{color:#fff;font-weight:600;font-size:14px}  
.portfolio-overlay{position:absolute;inset:0;background:rgba(10,25,47,.8);display:flex;align-items:center;justify-content:center;opacity:0;transition:var(--tr)}  
.portfolio-overlay span{color:var(--gold);font-weight:600;font-size:14px;border:1px solid var(--gold);padding:10px 24px;border-radius:8px}  
  
/* TESTIMONIALS */  
.testimonials{background:var(--cream)}.testimonials .section-title{color:var(--navy)}  
.testimonials-slider{position:relative;overflow:hidden}  
.testimonials-track{display:flex;transition:transform .5s ease;gap:24px}  
.testimonial-card{min-width:100%;background:#fff;border-radius:16px;padding:40px;border-right:4px solid var(--gold);box-shadow:0 4px 20px rgba(0,0,0,.04);position:relative}  
.testimonial-quote{font-size:48px;color:var(--sage);line-height:1;margin-bottom:8px;opacity:.5}  
.testimonial-text{font-size:17px;color:var(--text-dark);line-height:1.9;margin-bottom:24px;font-weight:500}  
.testimonial-author{color:var(--navy);font-weight:700;font-size:15px}  
.testimonial-location{color:var(--sage);font-size:13px}  
.testimonials-nav{display:flex;justify-content:center;gap:12px;margin-top:32px}  
.testimonials-nav button{width:12px;height:12px;border-radius:50%;border:2px solid var(--gold);background:transparent;cursor:pointer;transition:var(--tr)}  
.testimonials-nav button.active{background:var(--gold)}  
  
/* TECH */  
.tech{background:var(--navy)}.tech .section-title{color:var(--gold)}  
.tools-row{display:flex;justify-content:center;gap:32px;flex-wrap:wrap;margin-bottom:80px}  
.tool-item{display:flex;flex-direction:column;align-items:center;gap:12px;opacity:0;transform:translateY(20px)}  
.tool-item.visible{opacity:1;transform:translateY(0);transition:var(--tr)}  
.tool-icon{width:64px;height:64px;background:rgba(255,255,255,.05);border:1px solid rgba(201,169,110,.2);border-radius:16px;display:flex;align-items:center;justify-content:center;font-size:24px;transition:var(--tr)}  
.tool-item:hover .tool-icon{border-color:var(--gold);transform:translateY(-4px)}  
.tool-name{color:var(--text-light);font-size:13px;font-weight:500}  
.process-timeline{display:flex;justify-content:space-between;align-items:flex-start;position:relative;max-width:900px;margin:0 auto}  
.process-timeline::before{content:'';position:absolute;top:28px;right:12%;left:12%;height:2px;background:linear-gradient(90deg,var(--gold),var(--sage))}  
.process-step{display:flex;flex-direction:column;align-items:center;text-align:center;position:relative;z-index:1;flex:1;opacity:0;transform:translateY(20px)}  
.process-step.visible{opacity:1;transform:translateY(0);transition:var(--tr)}  
.process-number{width:56px;height:56px;background:var(--navy);border:2px solid var(--gold);border-radius:50%;display:flex;align-items:center;justify-content:center;color:var(--gold);font-weight:700;font-size:18px;margin-bottom:16px;transition:var(--tr)}  
.process-step:hover .process-number{background:var(--gold);color:var(--navy)}  
.process-step h4{color:var(--text-light);font-size:14px;font-weight:600;max-width:140px}  
  
/* FAQ */  
.faq{background:var(--cream)}.faq .section-title{color:var(--navy)}  
.faq-list{max-width:800px;margin:0 auto;display:flex;flex-direction:column;gap:12px}  
.faq-item{background:#fff;border-radius:12px;overflow:hidden;box-shadow:0 2px 10px rgba(0,0,0,.04);opacity:0;transform:translateY(20px)}  
.faq-item.visible{opacity:1;transform:translateY(0);transition:var(--tr)}  
.faq-question{width:100%;padding:20px 24px;background:none;border:none;font-family:inherit;font-size:15px;font-weight:600;color:var(--navy);text-align:right;cursor:pointer;display:flex;align-items:center;justify-content:space-between;gap:16px}  
.faq-arrow{width:24px;height:24px;border:2px solid var(--gold);border-radius:50%;display:flex;align-items:center;justify-content:center;color:var(--gold);font-size:12px;transition:var(--tr);flex-shrink:0}  
.faq-item.open .faq-arrow{transform:rotate(180deg);background:var(--gold);color:var(--navy)}  
.faq-answer{max-height:0;overflow:hidden;transition:max-height .4s ease,padding .4s ease;padding:0 24px}  
.faq-item.open .faq-answer{max-height:300px;padding:0 24px 20px}  
.faq-answer p{color:var(--text-dark);opacity:.7;font-size:14px;line-height:1.8}  
  
/* CONTACT */  
.contact{background:linear-gradient(180deg,var(--navy),var(--navy-dark));padding:100px 24px}  
.contact .section-title{color:var(--gold)}.contact .section-subtitle{color:var(--text-light);opacity:.6}  
.contact-grid{display:grid;grid-template-columns:1fr 1fr;gap:48px;max-width:1000px;margin:0 auto;align-items:start}  
.contact-form{display:flex;flex-direction:column;gap:16px}  
.form-group{display:flex;flex-direction:column;gap:6px}  
.form-group label{color:var(--text-light);font-size:13px;font-weight:500;opacity:.8}  
.form-group input,.form-group select,.form-group textarea{padding:14px 16px;border-radius:10px;border:1px solid rgba(201,169,110,.3);background:rgba(255,255,255,.05);color:var(--text-light);font-family:inherit;font-size:14px;transition:var(--tr)}  
.form-group input:focus,.form-group select:focus,.form-group textarea:focus{outline:none;border-color:var(--gold);background:rgba(255,255,255,.08)}  
.form-group input::placeholder,.form-group textarea::placeholder{color:rgba(245,240,232,.3)}  
.form-group textarea{min-height:120px;resize:vertical}  
.btn-gold{background:var(--gold);color:var(--navy);padding:16px;font-size:16px;font-weight:700;border:none;border-radius:12px;cursor:pointer;font-family:inherit;transition:var(--tr);margin-top:8px}  
.btn-gold:hover{background:var(--gold-light);transform:translateY(-2px);box-shadow:0 10px 30px rgba(201,169,110,.3)}  
.whatsapp-btn{display:inline-flex;align-items:center;justify-content:center;gap:10px;background:#25D366;color:#fff;padding:14px 28px;border-radius:12px;text-decoration:none;font-weight:600;font-size:15px;transition:var(--tr);margin-top:16px}  
.whatsapp-btn:hover{background:#128C7E;transform:translateY(-2px)}  
.contact-info{display:flex;flex-direction:column;gap:32px}  
.contact-info-block h4{color:var(--gold);font-size:16px;margin-bottom:12px}  
.contact-info-block p{color:var(--text-light);opacity:.7;font-size:14px;line-height:1.8}  
  
/* FOOTER */  
footer{background:var(--navy-dark);padding:60px 24px 0}  
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:40px;max-width:1200px;margin:0 auto;padding-bottom:40px}  
.footer-brand{display:flex;align-items:center;gap:12px;margin-bottom:16px}  
.footer-brand-icon{width:40px;height:40px;background:var(--navy);border:2px solid var(--gold);border-radius:10px;display:grid;grid-template-columns:repeat(4,1fr);grid-template-rows:repeat(4,1fr);gap:1px;padding:4px}  
.footer-brand-icon span{border-radius:1px}  
.footer-brand-text{color:var(--gold);font-weight:700;font-size:20px}  
.footer-desc{color:var(--text-light);opacity:.5;font-size:13px;line-height:1.8}  
.footer-col h4{color:var(--gold);font-size:14px;font-weight:700;margin-bottom:20px}  
.footer-col ul{list-style:none;display:flex;flex-direction:column;gap:12px}  
.footer-col a{color:var(--text-light);opacity:.6;text-decoration:none;font-size:14px;transition:var(--tr)}  
.footer-col a:hover{opacity:1;color:var(--gold)}  
.footer-social{display:flex;gap:12px;margin-top:16px}  
.footer-social a{width:36px;height:36px;border:1px solid rgba(201,169,110,.3);border-radius:8px;display:flex;align-items:center;justify-content:center;color:var(--gold);text-decoration:none;font-size:16px;transition:var(--tr)}  
.footer-social a:hover{background:var(--gold);color:var(--navy);border-color:var(--gold)}  
.footer-countries{display:flex;gap:8px;flex-wrap:wrap}  
.country-tag{background:rgba(201,169,110,.1);border:1px solid rgba(201,169,110,.2);border-radius:8px;padding:6px 12px;color:var(--text-light);font-size:13px;display:flex;align-items:center;gap:6px}  
.footer-bottom{border-top:1px solid rgba(255,255,255,.05);padding:20px 24px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px;max-width:1200px;margin:0 auto}  
.footer-bottom p,.footer-bottom a{color:var(--text-light);opacity:.4;font-size:12px}.footer-bottom a{text-decoration:underline}  
  
/* RESPONSIVE */  
@media(max-width:1024px){  
.problems-grid,.solutions-grid,.pricing-grid,.portfolio-grid{grid-template-columns:repeat(2,1fr)}  
.contact-grid{grid-template-columns:1fr}.footer-grid{grid-template-columns:repeat(2,1fr)}  
.process-timeline::before{display:none}.process-timeline{flex-wrap:wrap;gap:32px}.process-step{flex:1 1 45%}  
}  
@media(max-width:768px){  
.nav-links{display:none}.hamburger{display:flex}  
.hero-buttons{flex-direction:column;width:100%}.hero-buttons .btn{width:100%}  
.problems-grid,.solutions-grid,.pricing-grid,.portfolio-grid{grid-template-columns:1fr}  
.pricing-card.highlighted{transform:none}.pricing-card.highlighted:hover{transform:translateY(-6px)}  
.audience-card{flex-direction:column;text-align:center}.testimonial-card{padding:28px}  
.process-timeline{flex-direction:column;align-items:center}.process-step{flex:none;width:100%}  
.footer-grid{grid-template-columns:1fr;gap:32px}.footer-bottom{flex-direction:column;text-align:center}  
section{padding:60px 20px}.hero-corner{width:60px;height:60px}  
}  
</style>  
<base target="_blank">  
</head>  
<body>  
  
<!-- LOADER -->  
<div id="loader">  
    <div class="loader-grid" id="loaderGrid"></div>  
    <div class="loader-text">NASEEJ</div>  
</div>  
  
<!-- OVERLAY -->  
<div class="overlay" id="overlay"></div>  
  
<!-- MOBILE MENU -->  
<div class="mobile-menu" id="mobileMenu">  
    <button class="close-btn" id="closeMenu">&times;</button>  
    <ul>  
        <li><a href="#hero" class="mobile-link">الرئيسية</a></li>  
        <li><a href="#pricing" class="mobile-link">الباقات</a></li>  
        <li><a href="#portfolio" class="mobile-link">الأعمال</a></li>  
        <li><a href="#solutions" class="mobile-link">من نحن</a></li>  
        <li><a href="#contact" class="mobile-link">تواصل معنا</a></li>  
    </ul>  
</div>  
  
<!-- NAVIGATION -->  
<nav id="navbar">  
    <div class="nav-container">  
        <a href="#hero" class="nav-logo">  
            <div class="nav-logo-icon">  
                <span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span>  
                <span style="background:var(--sage)"></span><span style="background:var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span>  
                <span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:var(--sage)"></span>  
                <span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span>  
            </div>  
            <span class="nav-logo-text">NASEEJ</span>  
        </a>  
        <ul class="nav-links">  
            <li><a href="#hero">الرئيسية</a></li>  
            <li><a href="#pricing">الباقات</a></li>  
            <li><a href="#portfolio">الأعمال</a></li>  
            <li><a href="#solutions">من نحن</a></li>  
            <li><a href="#contact">تواصل معنا</a></li>  
        </ul>  
        <button class="hamburger" id="hamburger">  
            <span></span><span></span><span></span>  
        </button>  
    </div>  
</nav>  
  
<!-- HERO SECTION -->  
<section class="hero" id="hero">  
    <div class="hero-grid" id="heroGrid"></div>  
    <div class="hero-corner top-left"></div>  
    <div class="hero-corner bottom-right"></div>  
    <div class="hero-content">  
        <div class="hero-icon-wrap">  
            <div class="hero-icon">  
                <span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span>  
                <span style="background:var(--sage)"></span><span style="background:var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span>  
                <span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:var(--sage)"></span>  
                <span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span>  
            </div>  
        </div>  
        <h1 class="hero-arabic">نَسِيج</h1>  
        <p class="hero-english">NASEEJ</p>  
        <p class="hero-tagline">AI-Powered Creative Agency</p>  
        <div class="hero-buttons">  
            <a href="#contact" class="btn btn-primary">اطلب عرض سعر</a>  
            <a href="#portfolio" class="btn btn-outline">شاهد أعمالنا</a>  
        </div>  
    </div>  
</section>  
  
<!-- PROBLEMS SECTION -->  
<section class="problems" id="problems">  
    <div class="container">  
        <h2 class="section-title">مشاكل تواجه متجرك الإلكتروني؟</h2>  
        <div class="problems-grid">  
            <div class="problem-card scroll-reveal">  
                <div class="problem-icon">😩</div>  
                <h3>إرهاق الإعلانات (Ad Fatigue)</h3>  
                <p>80% من الشركات تُعيد نفس الإعلان 3-4 أشهر → انخفاض CTR 60%</p>  
            </div>  
            <div class="problem-card scroll-reveal">  
                <div class="problem-icon">💸</div>  
                <h3>تكلفة الإنتاج الباهظة</h3>  
                <p>فيديو تقليدي = $5,000-$30,000. نحن نُنتج بنفس الجودة بـ 1/10 التكلفة</p>  
            </div>  
            <div class="problem-card scroll-reveal">  
                <div class="problem-icon">⏱️</div>  
                <h3>بطء الإنتاج</h3>  
                <p>وكالة تقليدية = 2-3 أسابيع لفيديو واحد. نحن = 48 ساعة لـ 25 محتوى</p>  
            </div>  
            <div class="problem-card scroll-reveal">  
                <div class="problem-icon">🌍</div>  
                <h3>محتوى لا يناسب الثقافة المحلية</h3>  
                <p>أدوات AI عالمية = محتوى غربي. نحن = فريق عربي يفهم السوق الخليجي والعراقي</p>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- SOLUTIONS SECTION -->  
<section class="solutions" id="solutions">  
    <div class="container">  
        <h2 class="section-title">كيف نحلها؟</h2>  
        <div class="solutions-grid">  
            <div class="solution-card scroll-reveal">  
                <div class="solution-icon">⚡</div>  
                <h3>سرعة فائقة</h3>  
                <p>25 محتوى مرئي في 48 ساعة باستخدام أحدث أدوات AI</p>  
            </div>  
            <div class="solution-card scroll-reveal">  
                <div class="solution-icon">🎨</div>  
                <h3>جودة بشرية + سرعة آلة</h3>  
                <p>AI ينتج + فريق عربي يراجع ويُحسّن للسوق المحلي</p>  
            </div>  
            <div class="solution-card scroll-reveal">  
                <div class="solution-icon">🔄</div>  
                <h3>تجديد دائم للإعلانات</h3>  
                <p>50+ variant إبداعي شهرياً لمنع Ad Fatigue</p>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- PRICING SECTION -->  
<section class="pricing" id="pricing">  
    <div class="container">  
        <h2 class="section-title">باقاتنا</h2>  
        <p class="section-subtitle">أسعار واقعية مُحسّنة للسوق الخليجي والعراقي</p>  
        <div class="currency-toggle">  
            <button class="currency-btn active" data-currency="sar">ريال سعودي</button>  
            <button class="currency-btn" data-currency="aed">درهم إماراتي</button>  
            <button class="currency-btn" data-currency="iqd">دينار عراقي</button>  
        </div>  
        <div class="pricing-grid">  
            <div class="pricing-card scroll-reveal">  
                <h3>الباقة الأساسية</h3>  
                <div class="price" data-sar="2,999 ر.س" data-aed="2,999 د.إ" data-iqd="1,100,000 د.ع">2,999 ر.س</div>  
                <div class="price-secondary" data-sar="" data-aed="" data-iqd="">1,100,000 د.ع</div>  
                <ul class="pricing-features">  
                    <li>12 محتوى مرئي</li>  
                    <li>4 بوستات تصميم</li>  
                    <li>تسليم خلال 72 ساعة</li>  
                    <li>تعديل واحد مجاني</li>  
                </ul>  
                <button class="btn btn-outline">ابدأ الآن</button>  
            </div>  
            <div class="pricing-card highlighted scroll-reveal">  
                <div class="badge">الأكثر طلباً</div>  
                <h3>الباقة المتوسطة</h3>  
                <div class="price" data-sar="5,999 ر.س" data-aed="5,999 د.إ" data-iqd="2,200,000 د.ع">5,999 ر.س</div>  
                <div class="price-secondary" data-sar="" data-aed="" data-iqd="">2,200,000 د.ع</div>  
                <ul class="pricing-features">  
                    <li>25 محتوى مرئي</li>  
                    <li>استراتيجية محتوى شهرية</li>  
                    <li>A/B Testing لـ 5 إعلانات</li>  
                    <li>تعديلان مجانيان</li>  
                    <li>دعم واتساب مباشر</li>  
                </ul>  
                <button class="btn btn-primary">ابدأ الآن</button>  
            </div>  
            <div class="pricing-card scroll-reveal">  
                <h3>الباقة المتقدمة</h3>  
                <div class="price" data-sar="9,999 ر.س" data-aed="9,999 د.إ" data-iqd="3,700,000 د.ع">9,999 ر.س</div>  
                <div class="price-secondary" data-sar="" data-aed="" data-iqd="">3,700,000 د.ع</div>  
                <ul class="pricing-features">  
                    <li>50+ محتوى مرئي</li>  
                    <li>UGC AI بأصوات واقعية</li>  
                    <li>إدارة كاملة للحساب</li>  
                    <li>تقارير أداء أسبوعية</li>  
                    <li>تعديلات غير محدودة</li>  
                </ul>  
                <button class="btn btn-outline">تواصل معنا</button>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- AUDIENCE SECTION -->  
<section class="audience" id="audience">  
    <div class="container">  
        <h2 class="section-title">لمن هذه الخدمة؟</h2>  
        <div class="audience-grid">  
            <div class="audience-card scroll-reveal">  
                <div class="audience-icon">📦</div>  
                <div>  
                    <h3>أصحاب متاجر الدروبشيبينغ</h3>  
                    <p>تحتاج 50+ صورة منتج/شهر بدون ميزانية مصوّر</p>  
                </div>  
            </div>  
            <div class="audience-card scroll-reveal">  
                <div class="audience-icon">🛍️</div>  
                <div>  
                    <h3>متاجر المنتجات المحلية</h3>  
                    <p>عطور، أزياء، مكياج — تحتاج Reels يومية للبقاء في الخوارزمية</p>  
                </div>  
            </div>  
            <div class="audience-card scroll-reveal">  
                <div class="audience-icon">🏷️</div>  
                <div>  
                    <h3>وكالات التسويق الصغيرة</h3>  
                    <p>بيع الاستراتيجية ونحن نُنفذ الإنتاج باسمك (White Label)</p>  
                </div>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- PORTFOLIO SECTION -->  
<section class="portfolio" id="portfolio">  
    <div class="container">  
        <h2 class="section-title">أعمالنا</h2>  
        <div class="portfolio-grid">  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#1a0a2e,#4a1a4e)">  
                    <span>🌸</span>  
                    <p>Instagram Reel — عطور</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#0a1a2e,#1a3a5e)">  
                    <span>👗</span>  
                    <p>Product Grid — أزياء</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#2e0a1a,#5e1a3a)">  
                    <span>💄</span>  
                    <p>TikTok Thumbnail — مكياج</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#0a2e1a,#1a5e3a)">  
                    <span>📱</span>  
                    <p>Facebook Ad — إلكترونيات</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#2e2a0a,#5e5a1a)">  
                    <span>🍔</span>  
                    <p>Story Template — توصيل طعام</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
            <div class="portfolio-item scroll-reveal">  
                <div class="portfolio-placeholder" style="background:linear-gradient(135deg,#1a1a2e,#3a3a5e)">  
                    <span>🏠</span>  
                    <p>Carousel Post — ديكور</p>  
                </div>  
                <div class="portfolio-overlay"><span>شاهد التفاصيل</span></div>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- TESTIMONIALS SECTION -->  
<section class="testimonials" id="testimonials">  
    <div class="container">  
        <h2 class="section-title">ماذا يقول عملاؤنا؟</h2>  
        <div class="testimonials-slider">  
            <div class="testimonials-track" id="testimonialsTrack">  
                <div class="testimonial-card">  
                    <div class="testimonial-quote">"</div>  
                    <p class="testimonial-text">وفّرت 70% من ميزانية التصوير ومحتواي صار يتجدد أسبوعياً</p>  
                    <p class="testimonial-author">أحمد</p>  
                    <p class="testimonial-location">متجر عطور، الرياض 🇸🇦</p>  
                </div>  
                <div class="testimonial-card">  
                    <div class="testimonial-quote">"</div>  
                    <p class="testimonial-text">Naseej أنتجولي 30 Reels في أقل من أسبوع، مبيعاتي زادت 40%</p>  
                    <p class="testimonial-author">فاطمة</p>  
                    <p class="testimonial-location">متجر مكياج، دبي 🇦🇪</p>  
                </div>  
                <div class="testimonial-card">  
                    <div class="testimonial-quote">"</div>  
                    <p class="testimonial-text">أخيراً وكالة تفهم السوق العراقي وتُنتج محتوى يناسب جمهورنا</p>  
                    <p class="testimonial-author">علي</p>  
                    <p class="testimonial-location">متجر إلكتروني، بغداد 🇮🇶</p>  
                </div>  
            </div>  
            <div class="testimonials-nav">  
                <button class="active" data-slide="0"></button>  
                <button data-slide="1"></button>  
                <button data-slide="2"></button>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- TECH STACK SECTION -->  
<section class="tech" id="tech">  
    <div class="container">  
        <h2 class="section-title">أدواتنا</h2>  
        <div class="tools-row">  
            <div class="tool-item scroll-reveal"><div class="tool-icon">🎨</div><span class="tool-name">Recraft v4.1</span></div>  
            <div class="tool-item scroll-reveal"><div class="tool-icon">🖼️</div><span class="tool-name">Midjourney</span></div>  
            <div class="tool-item scroll-reveal"><div class="tool-icon">🎬</div><span class="tool-name">Runway</span></div>  
            <div class="tool-item scroll-reveal"><div class="tool-icon">✏️</div><span class="tool-name">Canva Pro</span></div>  
            <div class="tool-item scroll-reveal"><div class="tool-icon">🤖</div><span class="tool-name">ChatGPT</span></div>  
            <div class="tool-item scroll-reveal"><div class="tool-icon">🎙️</div><span class="tool-name">HeyGen</span></div>  
        </div>  
        <div class="process-timeline">  
            <div class="process-step scroll-reveal"><div class="process-number">1</div><h4>تحليل المتجر</h4></div>  
            <div class="process-step scroll-reveal"><div class="process-number">2</div><h4>استراتيجية المحتوى</h4></div>  
            <div class="process-step scroll-reveal"><div class="process-number">3</div><h4>إنتاج AI + مراجعة بشرية</h4></div>  
            <div class="process-step scroll-reveal"><div class="process-number">4</div><h4>التسليم والنشر</h4></div>  
        </div>  
    </div>  
</section>  
  
<!-- FAQ SECTION -->  
<section class="faq" id="faq">  
    <div class="container">  
        <h2 class="section-title">الأسئلة الشائعة</h2>  
        <div class="faq-list">  
            <div class="faq-item scroll-reveal">  
                <button class="faq-question">هل المحتوى جاهز للاستخدام التجاري؟<span class="faq-arrow">▼</span></button>  
                <div class="faq-answer"><p>نعم، جميع المحتويات التي نُنتجها تأتي بحقوق استخدام تجاري كاملة. لا توجد قيود على الاستخدام في الإعلانات المدفوعة أو المنشورات العضوية.</p></div>  
            </div>  
            <div class="faq-item scroll-reveal">  
                <button class="faq-question">كم يستغرق إنتاج المحتوى؟<span class="faq-arrow">▼</span></button>  
                <div class="faq-answer"><p>الباقة الأساسية: 72 ساعة. الباقة المتوسطة: 48 ساعة. الباقة المتقدمة: 24-48 ساعة حسب الحجم. نحن نستخدم أحدث أدوات AI لتسريع الإنتاج دون المساس بالجودة.</p></div>  
            </div>  
            <div class="faq-item scroll-reveal">  
                <button class="faq-question">هل تدعمون اللهجة العراقية/الخليجية؟<span class="faq-arrow">▼</span></button>  
                <div class="faq-answer"><p>بالتأكيد! فريقنا عربي بالكامل ويفهم الفروقات الثقافية واللغوية بين السوق السعودي، الإماراتي، والعراقي. نُنتج محتوى مُحسّن لكل سوق على حدة.</p></div>  
            </div>  
            <div class="faq-item scroll-reveal">  
                <button class="faq-question">هل يمكن تعديل المحتوى بعد التسليم؟<span class="faq-arrow">▼</span></button>  
                <div class="faq-answer"><p>نعم، كل باقة تتضمن عدداً من التعديلات المجانية. الباقة الأساسية: تعديل واحد. المتوسطة: تعديلان. المتقدمة: تعديلات غير محدودة خلال فترة الاشتراك.</p></div>  
            </div>  
            <div class="faq-item scroll-reveal">  
                <button class="faq-question">ما الفرق بينكم وبين Canva؟<span class="faq-arrow">▼</span></button>  
                <div class="faq-answer"><p>Canva أداة تصميم عامة. نحن وكالة متخصصة: نُنتج محتوى مُخصص لعلامتك التجارية، بأسلوب عربي أصيل، مع استراتيجية محتوى مدروسة ودعم فني مباشر.</p></div>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- CONTACT SECTION -->  
<section class="contact" id="contact">  
    <div class="container">  
        <h2 class="section-title">ابدأ رحلتك مع نَسِيج</h2>  
        <p class="section-subtitle">احصل على استشارة مجانية وعرض سعر مخصص لمتجرك</p>  
        <div class="contact-grid">  
            <form class="contact-form" onsubmit="event.preventDefault();alert('تم إرسال طلبك بنجاح! سنتواصل معك خلال 24 ساعة.');">  
                <div class="form-group">  
                    <label>الاسم</label>  
                    <input type="text" placeholder="اسمك الكامل" required>  
                </div>  
                <div class="form-group">  
                    <label>البريد الإلكتروني</label>  
                    <input type="email" placeholder="your@email.com" required>  
                </div>  
                <div class="form-group">  
                    <label>رقم الواتساب</label>  
                    <input type="tel" placeholder="+966 5X XXX XXXX" required>  
                </div>  
                <div class="form-group">  
                    <label>نوع المتجر</label>  
                    <select required>  
                        <option value="">اختر نوع المتجر</option>  
                        <option>دروبشيبينغ</option>  
                        <option>منتجات محلية</option>  
                        <option>وكالة تسويق</option>  
                        <option>أخرى</option>  
                    </select>  
                </div>  
                <div class="form-group">  
                    <label>رسالتك</label>  
                    <textarea placeholder="اخبرنا أكثر عن متجرك واحتياجاتك..."></textarea>  
                </div>  
                <button type="submit" class="btn-gold">أرسل الطلب</button>  
                <a href="https://wa.me/966500000000" class="whatsapp-btn" target="_blank">  
                    <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>  
                    تواصل عبر واتساب  
                </a>  
            </form>  
            <div class="contact-info">  
                <div class="contact-info-block">  
                    <h4>⚡ سرعة الاستجابة</h4>  
                    <p>نرد على جميع الاستفسارات خلال 24 ساعة. للطوارئ: واتساب مباشر.</p>  
                </div>  
                <div class="contact-info-block">  
                    <h4>🎯 استشارة مجانية</h4>  
                    <p>جلسة استشارية مجانية لمدة 30 دقيقة لتحليل متجرك واقتراح أفضل استراتيجية محتوى.</p>  
                </div>  
                <div class="contact-info-block">  
                    <h4>🔒 ضمان الرضا</h4>  
                    <p>إذا لم تكن راضياً عن أول دفعة، نعيد الإنتاج مجاناً أو نسترد المبلغ كاملاً.</p>  
                </div>  
            </div>  
        </div>  
    </div>  
</section>  
  
<!-- FOOTER -->  
<footer>  
    <div class="footer-grid">  
        <div class="footer-col">  
            <div class="footer-brand">  
                <div class="footer-brand-icon">  
                    <span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span>  
                    <span style="background:var(--sage)"></span><span style="background:var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span>  
                    <span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span><span style="background:var(--sage)"></span>  
                    <span style="background:var(--gold)"></span><span style="background:transparent;border:1px solid var(--gold)"></span><span style="background:var(--gold)"></span><span style="background:var(--sage)"></span>  
                </div>  
                <span class="footer-brand-text">نَسِيج</span>  
            </div>  
            <p class="footer-desc">وكالة إبداعية مدعومة بالذكاء الاصطناعي، متخصصة في إنتاج المحتوى المرئي لمتاجر التجارة الإلكترونية في السعودية، الإمارات، والعراق.</p>  
            <div class="footer-social">  
                <a href="#" aria-label="Instagram">📷</a>  
                <a href="#" aria-label="TikTok">🎵</a>  
                <a href="#" aria-label="X">𝕏</a>  
                <a href="#" aria-label="LinkedIn">💼</a>  
            </div>  
        </div>  
        <div class="footer-col">  
            <h4>روابط سريعة</h4>  
            <ul>  
                <li><a href="#hero">الرئيسية</a></li>  
                <li><a href="#pricing">الباقات</a></li>  
                <li><a href="#portfolio">الأعمال</a></li>  
                <li><a href="#contact">تواصل معنا</a></li>  
            </ul>  
        </div>  
        <div class="footer-col">  
            <h4>تواصل معنا</h4>  
            <ul>  
                <li><a href="https://wa.me/966500000000">واتساب</a></li>  
                <li><a href="#">إنستغرام</a></li>  
                <li><a href="#">تيك توك</a></li>  
                <li><a href="mailto:hello@naseej.agency">إيميل</a></li>  
            </ul>  
        </div>  
        <div class="footer-col">  
            <h4>نخدم</h4>  
            <div class="footer-countries">  
                <div class="country-tag">🇸🇦 السعودية</div>  
                <div class="country-tag">🇦🇪 الإمارات</div>  
                <div class="country-tag">🇮🇶 العراق</div>  
            </div>  
        </div>  
    </div>  
    <div class="footer-bottom">  
        <p>© 2026 Naseej. جميع الحقوق محفوظة.</p>  
        <a href="#">Earnings Disclaimer</a>  
    </div>  
</footer>  
  
<script>  
  
// LOADER  
const loaderGrid = document.getElementById('loaderGrid');  
const pattern = ['gold','sage','empty','gold','sage','gold','gold','empty','empty','gold','sage','sage','gold','empty','gold','sage'];  
pattern.forEach((type, i) => {  
    const cell = document.createElement('div');  
    cell.className = 'loader-cell ' + type;  
    cell.style.animationDelay = (i * 0.05) + 's';  
    loaderGrid.appendChild(cell);  
});  
  
window.addEventListener('load', () => {  
    setTimeout(() => {  
        document.getElementById('loader').classList.add('hidden');  
    }, 1800);  
});  
  
// HERO GRID DOTS  
const heroGrid = document.getElementById('heroGrid');  
for (let i = 0; i < 60; i++) {  
    const dot = document.createElement('div');  
    dot.className = 'hero-grid-dot';  
    dot.style.left = Math.random() * 100 + '%';  
    dot.style.top = Math.random() * 100 + '%';  
    dot.style.background = Math.random() > 0.5 ? 'var(--gold)' : 'var(--sage)';  
    dot.style.animationDelay = Math.random() * 4 + 's';  
    dot.style.animationDuration = (3 + Math.random() * 3) + 's';  
    heroGrid.appendChild(dot);  
}  
  
// NAV SCROLL  
const navbar = document.getElementById('navbar');  
window.addEventListener('scroll', () => {  
    navbar.classList.toggle('scrolled', window.scrollY > 50);  
});  
  
// MOBILE MENU  
const hamburger = document.getElementById('hamburger');  
const mobileMenu = document.getElementById('mobileMenu');  
const overlay = document.getElementById('overlay');  
const closeMenu = document.getElementById('closeMenu');  
  
function openMenu() {  
    mobileMenu.classList.add('open');  
    overlay.classList.add('active');  
    document.body.style.overflow = 'hidden';  
}  
function closeMenuFn() {  
    mobileMenu.classList.remove('open');  
    overlay.classList.remove('active');  
    document.body.style.overflow = '';  
}  
  
hamburger.addEventListener('click', openMenu);  
closeMenu.addEventListener('click', closeMenuFn);  
overlay.addEventListener('click', closeMenuFn);  
document.querySelectorAll('.mobile-link').forEach(link => {  
    link.addEventListener('click', closeMenuFn);  
});  
  
// SCROLL REVEAL  
const revealEls = document.querySelectorAll('.scroll-reveal');  
const revealObserver = new IntersectionObserver((entries) => {  
    entries.forEach((entry, i) => {  
        if (entry.isIntersecting) {  
            setTimeout(() => {  
                entry.target.classList.add('visible');  
            }, i % 4 * 100);  
            revealObserver.unobserve(entry.target);  
        }  
    });  
}, { threshold: 0.1 });  
revealEls.forEach(el => revealObserver.observe(el));  
  
// CURRENCY TOGGLE  
const currencyBtns = document.querySelectorAll('.currency-btn');  
const prices = document.querySelectorAll('.price');  
const priceSecondaries = document.querySelectorAll('.price-secondary');  
  
currencyBtns.forEach(btn => {  
    btn.addEventListener('click', () => {  
        currencyBtns.forEach(b => b.classList.remove('active'));  
        btn.classList.add('active');  
        const curr = btn.dataset.currency;  
        prices.forEach(p => { p.textContent = p.dataset[curr]; });  
        priceSecondaries.forEach(p => {  
            const val = p.dataset[curr];  
            if (val) p.textContent = val;  
            else p.style.display = curr === 'sar' ? 'none' : 'block';  
        });  
    });  
});  
  
// TESTIMONIALS SLIDER  
const track = document.getElementById('testimonialsTrack');  
const dots = document.querySelectorAll('.testimonials-nav button');  
let currentSlide = 0;  
  
function goToSlide(n) {  
    currentSlide = n;  
    track.style.transform = 'translateX(' + (n * -100) + '%)';  
    dots.forEach((d, i) => d.classList.toggle('active', i === n));  
}  
  
dots.forEach((dot, i) => {  
    dot.addEventListener('click', () => goToSlide(i));  
});  
  
setInterval(() => {  
    goToSlide((currentSlide + 1) % 3);  
}, 5000);  
  
// FAQ ACCORDION  
document.querySelectorAll('.faq-question').forEach(q => {  
    q.addEventListener('click', () => {  
        const item = q.parentElement;  
        const isOpen = item.classList.contains('open');  
        document.querySelectorAll('.faq-item').forEach(f => f.classList.remove('open'));  
        if (!isOpen) item.classList.add('open');  
    });  
});  
  
// SMOOTH SCROLL FOR ANCHOR LINKS  
document.querySelectorAll('a[href^="#"]').forEach(anchor => {  
    anchor.addEventListener('click', function(e) {  
        e.preventDefault();  
        const target = document.querySelector(this.getAttribute('href'));  
        if (target) {  
            target.scrollIntoView({ behavior: 'smooth', block: 'start' });  
        }  
    });  
});  
</script>  
</body>  
</html>  
