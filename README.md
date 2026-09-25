# Industry-Ready-Full-Stack-Enterprise-Platform
Industry-ready full-stack enterprise platform built with modern technologies, featuring scalable architecture, secure authentication, real-time data management, responsive UI, REST APIs, cloud integration, role-based access, and optimized performance for seamless business operations.

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>EnterprisePro — Enterprise Management Platform</title>

<style>
:root{
  --bg:#f4f7fb;
  --card:#ffffff;
  --card2:#f8fafc;
  --text:#172033;
  --muted:#687386;
  --primary:#5b5cf0;
  --primary2:#7c3aed;
  --success:#16a34a;
  --warning:#f59e0b;
  --danger:#ef4444;
  --info:#0284c7;
  --border:#e5e9f2;
  --shadow:0 12px 35px rgba(20,30,60,.08);
  --sidebar:260px;
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

html{
  scroll-behavior:smooth;
}

body{
  font-family:Inter,Segoe UI,Arial,sans-serif;
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
}

button,input,select,textarea{
  font:inherit;
}

button{
  cursor:pointer;
}

.hidden{
  display:none!important;
}

/* =========================
   AUTH PAGE
========================= */

.auth-screen{
  min-height:100vh;
  position:relative;
  overflow:hidden;
  display:flex;
  align-items:center;
  justify-content:center;
  padding:30px;
  background:
    radial-gradient(circle at 10% 20%,rgba(124,58,237,.25),transparent 30%),
    radial-gradient(circle at 90% 80%,rgba(37,99,235,.22),transparent 30%),
    linear-gradient(135deg,#070b1c,#10183a 50%,#080d20);
}

.auth-grid{
  position:absolute;
  inset:0;
  opacity:.18;
  background-image:
    linear-gradient(rgba(255,255,255,.08) 1px,transparent 1px),
    linear-gradient(90deg,rgba(255,255,255,.08) 1px,transparent 1px);
  background-size:45px 45px;
  animation:gridMove 20s linear infinite;
}

@keyframes gridMove{
  from{transform:translate(0,0)}
  to{transform:translate(45px,45px)}
}

.orb{
  position:absolute;
  border-radius:50%;
  filter:blur(5px);
  opacity:.5;
  animation:float 8s ease-in-out infinite;
}

.orb.one{
  width:280px;
  height:280px;
  background:#7c3aed;
  left:-100px;
  top:-80px;
}

.orb.two{
  width:230px;
  height:230px;
  background:#2563eb;
  right:-70px;
  bottom:-60px;
  animation-delay:2s;
}

.orb.three{
  width:120px;
  height:120px;
  background:#06b6d4;
  right:25%;
  top:10%;
  animation-delay:4s;
}

@keyframes float{
  0%,100%{transform:translateY(0) scale(1)}
  50%{transform:translateY(-30px) scale(1.08)}
}

.auth-container{
  width:min(1180px,100%);
  min-height:650px;
  display:grid;
  grid-template-columns:1.1fr .9fr;
  position:relative;
  z-index:2;
  border:1px solid rgba(255,255,255,.14);
  border-radius:30px;
  overflow:hidden;
  background:rgba(255,255,255,.07);
  backdrop-filter:blur(25px);
  box-shadow:0 35px 100px rgba(0,0,0,.4);
  animation:authIn .9s ease;
}

@keyframes authIn{
  from{
    opacity:0;
    transform:translateY(30px) scale(.97);
  }
  to{
    opacity:1;
    transform:none;
  }
}

.auth-hero{
  padding:65px;
  color:white;
  display:flex;
  flex-direction:column;
  justify-content:center;
  background:linear-gradient(145deg,rgba(91,92,240,.35),rgba(124,58,237,.12));
}

.brand{
  display:flex;
  align-items:center;
  gap:12px;
  font-weight:800;
  font-size:25px;
  margin-bottom:40px;
}

.brand-icon{
  width:46px;
  height:46px;
  display:grid;
  place-items:center;
  border-radius:14px;
  background:linear-gradient(135deg,#6366f1,#a855f7);
  box-shadow:0 10px 30px rgba(99,102,241,.4);
}

.auth-hero h1{
  font-size:clamp(38px,5vw,64px);
  line-height:1.03;
  margin-bottom:22px;
  letter-spacing:-2px;
}

.gradient-text{
  background:linear-gradient(90deg,#93c5fd,#c4b5fd,#f0abfc);
  -webkit-background-clip:text;
  background-clip:text;
  color:transparent;
}

.auth-hero p{
  color:#cbd5e1;
  font-size:17px;
  line-height:1.7;
  max-width:570px;
}

.feature-list{
  margin-top:35px;
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:15px;
}

.feature{
  display:flex;
  align-items:center;
  gap:10px;
  color:#e2e8f0;
  font-size:14px;
}

.feature span{
  width:25px;
  height:25px;
  display:grid;
  place-items:center;
  border-radius:50%;
  background:rgba(255,255,255,.1);
}

.auth-stats{
  display:flex;
  gap:35px;
  margin-top:45px;
}

.auth-stat strong{
  display:block;
  font-size:25px;
}

.auth-stat small{
  color:#94a3b8;
}

.auth-box{
  background:rgba(255,255,255,.96);
  padding:55px;
  display:flex;
  flex-direction:column;
  justify-content:center;
}

.auth-box h2{
  font-size:30px;
  margin-bottom:8px;
}

.auth-box .subtitle{
  color:#718096;
  margin-bottom:25px;
}

.auth-tabs{
  display:flex;
  background:#eef1f7;
  padding:4px;
  border-radius:12px;
  margin-bottom:25px;
}

.auth-tab{
  flex:1;
  border:0;
  padding:11px;
  border-radius:9px;
  background:transparent;
  color:#687386;
  font-weight:600;
}

.auth-tab.active{
  background:white;
  color:#4f46e5;
  box-shadow:0 3px 10px rgba(0,0,0,.08);
}

.form-group{
  margin-bottom:16px;
}

.form-group label{
  display:block;
  font-size:13px;
  font-weight:700;
  margin-bottom:7px;
  color:#374151;
}

.form-group input,
.form-group select,
.form-group textarea{
  width:100%;
  border:1px solid #dbe1eb;
  background:white;
  border-radius:10px;
  padding:12px 13px;
  outline:none;
  transition:.2s;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus{
  border-color:#6366f1;
  box-shadow:0 0 0 3px rgba(99,102,241,.12);
}

.password-row{
  position:relative;
}

.password-toggle{
  position:absolute;
  right:10px;
  top:37px;
  border:0;
  background:transparent;
  color:#6b7280;
}

.primary-btn{
  width:100%;
  border:0;
  color:white;
  padding:13px 16px;
  border-radius:11px;
  font-weight:700;
  background:linear-gradient(135deg,#5b5cf0,#7c3aed);
  box-shadow:0 8px 20px rgba(91,92,240,.25);
  transition:.2s;
}

.primary-btn:hover{
  transform:translateY(-2px);
  box-shadow:0 12px 28px rgba(91,92,240,.35);
}

.text-btn{
  border:0;
  background:none;
  color:#5b5cf0;
  font-weight:700;
}

.auth-footer{
  margin-top:18px;
  font-size:13px;
  color:#6b7280;
  text-align:center;
}

.demo-box{
  margin-top:18px;
  padding:12px;
  border-radius:10px;
  background:#f1f5f9;
  font-size:12px;
  color:#475569;
}

/* =========================
   APP
========================= */

.app{
  min-height:100vh;
  display:flex;
}

.sidebar{
  width:var(--sidebar);
  background:#101426;
  color:#cbd5e1;
  position:fixed;
  inset:0 auto 0 0;
  z-index:50;
  display:flex;
  flex-direction:column;
  transition:.3s;
}

.sidebar-brand{
  padding:22px 20px;
  color:white;
  display:flex;
  align-items:center;
  gap:10px;
  font-weight:800;
  font-size:20px;
  border-bottom:1px solid rgba(255,255,255,.07);
}

.sidebar-brand .brand-icon{
  width:38px;
  height:38px;
  font-size:16px;
}

.sidebar-nav{
  padding:15px 10px;
  overflow:auto;
  flex:1;
}

.nav-section{
  margin:18px 10px 8px;
  font-size:10px;
  text-transform:uppercase;
  letter-spacing:1.4px;
  color:#64748b;
  font-weight:800;
}

.nav-item{
  width:100%;
  border:0;
  background:none;
  color:#94a3b8;
  padding:11px 12px;
  display:flex;
  align-items:center;
  gap:12px;
  border-radius:10px;
  text-align:left;
  margin-bottom:3px;
  transition:.2s;
}

.nav-item:hover{
  color:white;
  background:rgba(255,255,255,.06);
}

.nav-item.active{
  color:white;
  background:linear-gradient(90deg,rgba(99,102,241,.28),rgba(124,58,237,.14));
}

.nav-icon{
  width:23px;
  text-align:center;
}

.sidebar-footer{
  padding:15px;
  border-top:1px solid rgba(255,255,255,.07);
}

.user-mini{
  display:flex;
  align-items:center;
  gap:10px;
}

.avatar{
  width:36px;
  height:36px;
  border-radius:50%;
  display:grid;
  place-items:center;
  background:linear-gradient(135deg,#6366f1,#a855f7);
  color:white;
  font-weight:800;
}

.user-mini div:last-child{
  overflow:hidden;
}

.user-mini strong{
  display:block;
  color:white;
  font-size:13px;
  white-space:nowrap;
  overflow:hidden;
  text-overflow:ellipsis;
}

.user-mini small{
  color:#64748b;
}

.main{
  margin-left:var(--sidebar);
  width:calc(100% - var(--sidebar));
  min-width:0;
}

.topbar{
  height:70px;
  position:sticky;
  top:0;
  z-index:40;
  background:rgba(255,255,255,.88);
  backdrop-filter:blur(15px);
  border-bottom:1px solid var(--border);
  display:flex;
  align-items:center;
  justify-content:space-between;
  padding:0 25px;
}

.top-left{
  display:flex;
  align-items:center;
  gap:15px;
}

.mobile-menu{
  display:none;
  border:0;
  background:none;
  font-size:23px;
}

.global-search{
  width:min(350px,35vw);
  position:relative;
}

.global-search input{
  width:100%;
  border:1px solid var(--border);
  background:var(--card2);
  padding:10px 15px 10px 38px;
  border-radius:10px;
  outline:none;
}

.global-search span{
  position:absolute;
  left:13px;
  top:9px;
  color:#94a3b8;
}

.top-actions{
  display:flex;
  align-items:center;
  gap:9px;
}

.icon-btn{
  width:38px;
  height:38px;
  border:1px solid var(--border);
  background:var(--card);
  border-radius:10px;
  color:var(--muted);
  position:relative;
}

.notification-dot{
  position:absolute;
  width:7px;
  height:7px;
  border-radius:50%;
  background:#ef4444;
  right:7px;
  top:6px;
}

.content{
  padding:25px;
}

.page{
  display:none;
  animation:pageIn .35s ease;
}

.page.active{
  display:block;
}

@keyframes pageIn{
  from{
    opacity:0;
    transform:translateY(10px);
  }
  to{
    opacity:1;
    transform:none;
  }
}

.page-header{
  display:flex;
  justify-content:space-between;
  align-items:flex-start;
  gap:15px;
  margin-bottom:22px;
}

.page-header h1{
  font-size:27px;
  letter-spacing:-.5px;
}

.page-header p{
  color:var(--muted);
  margin-top:5px;
  font-size:14px;
}

.header-actions{
  display:flex;
  gap:8px;
}

.btn{
  border:1px solid var(--border);
  background:var(--card);
  color:var(--text);
  border-radius:9px;
  padding:9px 13px;
  font-weight:650;
}

.btn.primary{
  background:var(--primary);
  color:white;
  border-color:var(--primary);
}

.btn.success{
  background:var(--success);
  color:white;
  border-color:var(--success);
}

.btn.danger{
  background:var(--danger);
  color:white;
  border-color:var(--danger);
}

/* =========================
   CARDS
========================= */

.grid{
  display:grid;
  gap:15px;
}

.kpi-grid{
  grid-template-columns:repeat(6,1fr);
}

.kpi{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:15px;
  padding:18px;
  box-shadow:var(--shadow);
  position:relative;
  overflow:hidden;
}

.kpi:after{
  content:"";
  position:absolute;
  width:70px;
  height:70px;
  border-radius:50%;
  right:-30px;
  bottom:-30px;
  background:rgba(99,102,241,.06);
}

.kpi-top{
  display:flex;
  justify-content:space-between;
  align-items:center;
  margin-bottom:13px;
}

.kpi-icon{
  width:37px;
  height:37px;
  border-radius:10px;
  display:grid;
  place-items:center;
  background:#eef2ff;
  color:#4f46e5;
}

.kpi small{
  color:var(--muted);
}

.kpi h2{
  font-size:25px;
  margin:5px 0;
}

.trend{
  font-size:12px;
  font-weight:700;
}

.up{color:var(--success)}
.down{color:var(--danger)}

.dashboard-grid{
  display:grid;
  grid-template-columns:2fr 1fr;
  gap:15px;
  margin-top:15px;
}

.card{
  background:var(--card);
  border:1px solid var(--border);
  border-radius:15px;
  padding:18px;
  box-shadow:var(--shadow);
}

.card-title{
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:15px;
}

.card-title h3{
  font-size:15px;
}

.card-title span{
  color:var(--muted);
  font-size:12px;
}

.chart{
  width:100%;
  height:270px;
}

canvas{
  width:100%;
  height:100%;
}

.two-col{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:15px;
  margin-top:15px;
}

.three-col{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
  margin-top:15px;
}

/* =========================
   METRIC PANELS
========================= */

.metric-list{
  display:grid;
  gap:13px;
}

.metric-row{
  display:flex;
  justify-content:space-between;
  align-items:center;
  font-size:13px;
  margin-bottom:6px;
}

.progress{
  height:7px;
  background:#e9edf5;
  border-radius:20px;
  overflow:hidden;
}

.progress span{
  display:block;
  height:100%;
  border-radius:20px;
  background:linear-gradient(90deg,#6366f1,#8b5cf6);
}

.status{
  display:inline-flex;
  align-items:center;
  gap:6px;
  padding:5px 8px;
  border-radius:20px;
  font-size:11px;
  font-weight:700;
}

.status:before{
  content:"";
  width:6px;
  height:6px;
  border-radius:50%;
  background:currentColor;
}

.status.success{
  color:#15803d;
  background:#dcfce7;
}

.status.warning{
  color:#b45309;
  background:#fef3c7;
}

.status.danger{
  color:#b91c1c;
  background:#fee2e2;
}

.status.info{
  color:#0369a1;
  background:#e0f2fe;
}

/* =========================
   ACTIVITY
========================= */

.activity{
  display:grid;
  gap:0;
}

.activity-item{
  display:flex;
  gap:11px;
  padding:12px 0;
  border-bottom:1px solid var(--border);
}

.activity-item:last-child{
  border-bottom:0;
}

.activity-dot{
  width:31px;
  height:31px;
  border-radius:9px;
  display:grid;
  place-items:center;
  background:#eef2ff;
  color:#4f46e5;
  flex-shrink:0;
}

.activity-item strong{
  font-size:13px;
}

.activity-item p{
  font-size:12px;
  color:var(--muted);
  margin-top:3px;
}

.activity-item time{
  display:block;
  font-size:10px;
  color:#94a3b8;
  margin-top:4px;
}

/* =========================
   ACTION CENTER
========================= */

.action-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:10px;
}

.action-card{
  border:1px solid var(--border);
  background:var(--card2);
  border-radius:11px;
  padding:13px;
  transition:.2s;
  cursor:pointer;
}

.action-card:hover{
  transform:translateY(-3px);
  box-shadow:var(--shadow);
}

.action-card strong{
  display:block;
  font-size:13px;
  margin-top:7px;
}

.action-card small{
  color:var(--muted);
}

/* =========================
   TABLES
========================= */

.table-wrap{
  overflow:auto;
}

table{
  width:100%;
  border-collapse:collapse;
  min-width:650px;
}

th,td{
  padding:12px;
  text-align:left;
  border-bottom:1px solid var(--border);
  font-size:13px;
}

th{
  color:var(--muted);
  font-size:11px;
  text-transform:uppercase;
  letter-spacing:.5px;
}

td{
  color:var(--text);
}

.toolbar{
  display:flex;
  gap:10px;
  margin-bottom:15px;
  flex-wrap:wrap;
}

.toolbar input,
.toolbar select{
  border:1px solid var(--border);
  background:var(--card);
  color:var(--text);
  border-radius:9px;
  padding:9px 12px;
  outline:none;
}

/* =========================
   SPECIAL PANELS
========================= */

.health-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:10px;
}

.health-item{
  padding:15px;
  border-radius:11px;
  background:var(--card2);
  border:1px solid var(--border);
}

.health-item strong{
  font-size:19px;
  display:block;
  margin-top:7px;
}

.health-item small{
  color:var(--muted);
}

.health-circle{
  width:85px;
  height:85px;
  border-radius:50%;
  display:grid;
  place-items:center;
  margin:auto;
  background:
    radial-gradient(circle at center,var(--card) 58%,transparent 59%),
    conic-gradient(#22c55e 0 92%,#e5e7eb 92%);
  font-size:19px;
  font-weight:800;
}

.score-card{
  text-align:center;
}

.score-card p{
  color:var(--muted);
  font-size:12px;
  margin-top:8px;
}

.insight{
  padding:12px;
  border-left:3px solid #6366f1;
  background:var(--card2);
  margin-bottom:9px;
  border-radius:0 9px 9px 0;
}

.insight strong{
  font-size:12px;
}

.insight p{
  color:var(--muted);
  font-size:11px;
  margin-top:4px;
}

.calendar{
  display:grid;
  gap:8px;
}

.event{
  display:flex;
  gap:10px;
  padding:9px;
  border-radius:9px;
  background:var(--card2);
}

.event-date{
  min-width:42px;
  text-align:center;
  border-radius:7px;
  padding:5px;
  background:#eef2ff;
  color:#4f46e5;
  font-weight:800;
  font-size:11px;
}

.event strong{
  font-size:12px;
}

.event small{
  display:block;
  color:var(--muted);
  margin-top:3px;
}

/* =========================
   DARK MODE
========================= */

body.dark{
  --bg:#0b1020;
  --card:#111827;
  --card2:#151d2d;
  --text:#e5e7eb;
  --muted:#94a3b8;
  --border:#263247;
  --shadow:0 12px 35px rgba(0,0,0,.22);
}

body.dark .topbar{
  background:rgba(15,23,42,.88);
}

body.dark .global-search input,
body.dark .toolbar input,
body.dark .toolbar select,
body.dark .form-group input,
body.dark .form-group select,
body.dark .form-group textarea{
  background:#111827;
  color:#e5e7eb;
  border-color:#334155;
}

body.dark .icon-btn,
body.dark .btn{
  background:#111827;
  color:#e5e7eb;
  border-color:#334155;
}

body.dark .auth-box{
  background:#111827;
  color:#e5e7eb;
}

body.dark .auth-tabs,
body.dark .demo-box{
  background:#1e293b;
}

body.dark .auth-tab.active{
  background:#111827;
}

body.dark .form-group label{
  color:#cbd5e1;
}

body.dark .progress{
  background:#273449;
}

body.dark .kpi-icon{
  background:#1e1b4b;
}

/* =========================
   TOAST
========================= */

.toast-container{
  position:fixed;
  right:20px;
  bottom:20px;
  z-index:9999;
  display:grid;
  gap:10px;
}

.toast{
  min-width:280px;
  max-width:380px;
  padding:14px 16px;
  border-radius:11px;
  background:#111827;
  color:white;
  box-shadow:0 15px 40px rgba(0,0,0,.2);
  animation:toastIn .3s ease;
  font-size:13px;
}

.toast.success{border-left:4px solid #22c55e}
.toast.error{border-left:4px solid #ef4444}
.toast.info{border-left:4px solid #38bdf8}

@keyframes toastIn{
  from{
    opacity:0;
    transform:translateX(30px);
  }
  to{
    opacity:1;
    transform:none;
  }
}

/* =========================
   MODAL
========================= */

.modal-overlay{
  position:fixed;
  inset:0;
  background:rgba(2,6,23,.65);
  z-index:1000;
  display:grid;
  place-items:center;
  padding:20px;
}

.modal{
  width:min(600px,100%);
  background:var(--card);
  color:var(--text);
  border-radius:18px;
  padding:22px;
  box-shadow:0 30px 80px rgba(0,0,0,.3);
  animation:modalIn .25s ease;
}

@keyframes modalIn{
  from{opacity:0;transform:scale(.95)}
  to{opacity:1;transform:none}
}

.modal-header{
  display:flex;
  justify-content:space-between;
  margin-bottom:18px;
}

.close{
  border:0;
  background:none;
  color:var(--muted);
  font-size:22px;
}

/* =========================
   MOBILE
========================= */

@media(max-width:1200px){
  .kpi-grid{
    grid-template-columns:repeat(3,1fr);
  }

  .health-grid{
    grid-template-columns:repeat(2,1fr);
  }
}

@media(max-width:900px){
  .auth-container{
    grid-template-columns:1fr;
  }

  .auth-hero{
    display:none;
  }

  .sidebar{
    transform:translateX(-100%);
  }

  .sidebar.open{
    transform:none;
  }

  .main{
    margin-left:0;
    width:100%;
  }

  .mobile-menu{
    display:block;
  }

  .dashboard-grid,
  .two-col{
    grid-template-columns:1fr;
  }

  .three-col{
    grid-template-columns:1fr 1fr;
  }

  .global-search{
    width:200px;
  }
}

@media(max-width:650px){
  .content{
    padding:15px;
  }

  .topbar{
    padding:0 12px;
  }

  .global-search{
    display:none;
  }

  .kpi-grid{
    grid-template-columns:1fr 1fr;
  }

  .three-col{
    grid-template-columns:1fr;
  }

  .action-grid{
    grid-template-columns:1fr 1fr;
  }

  .page-header{
    flex-direction:column;
  }

  .auth-box{
    padding:30px 22px;
  }

  .health-grid{
    grid-template-columns:1fr 1fr;
  }
}
</style>
</head>

<body>

<!-- =========================
     AUTH SCREEN
========================= -->

<section id="authScreen" class="auth-screen">

  <div class="auth-grid"></div>
  <div class="orb one"></div>
  <div class="orb two"></div>
  <div class="orb three"></div>

  <div class="auth-container">

    <div class="auth-hero">

      <div class="brand">
        <div class="brand-icon">EP</div>
        EnterprisePro
      </div>

      <h1>
        Enterprise
        <span class="gradient-text">Command Center</span>
      </h1>

      <p>
        A unified enterprise management platform for HR, Finance,
        Inventory, CRM, Security, DevOps, Analytics and Operations.
      </p>

      <div class="feature-list">
        <div class="feature"><span>✓</span> Enterprise Analytics</div>
        <div class="feature"><span>✓</span> HR Management</div>
        <div class="feature"><span>✓</span> Finance Control</div>
        <div class="feature"><span>✓</span> Inventory Management</div>
        <div class="feature"><span>✓</span> CRM & Sales</div>
        <div class="feature"><span>✓</span> DevOps Monitoring</div>
        <div class="feature"><span>✓</span> Security Operations</div>
        <div class="feature"><span>✓</span> Executive Reports</div>
      </div>

      <div class="auth-stats">
        <div class="auth-stat">
          <strong>99.9%</strong>
          <small>Platform Uptime</small>
        </div>
        <div class="auth-stat">
          <strong>24/7</strong>
          <small>Monitoring</small>
        </div>
        <div class="auth-stat">
          <strong>360°</strong>
          <small>Visibility</small>
        </div>
      </div>

    </div>

    <div class="auth-box">

      <div id="loginView">

        <h2>Welcome back</h2>
        <p class="subtitle">Sign in to your enterprise workspace.</p>

        <div class="auth-tabs">
          <button class="auth-tab active" onclick="showAuthView('login')">
            Login
          </button>
          <button class="auth-tab" onclick="showAuthView('register')">
            Create Account
          </button>
        </div>

        <form id="loginForm">

          <div class="form-group">
            <label>Email</label>
            <input id="loginEmail" type="email"
              placeholder="admin@enterprisepro.com" required>
          </div>

          <div class="form-group password-row">
            <label>Password</label>
            <input id="loginPassword" type="password"
              placeholder="Enter password" required>
            <button type="button" class="password-toggle"
              onclick="togglePassword('loginPassword',this)">👁</button>
          </div>

          <div style="text-align:right;margin-bottom:18px">
            <button type="button" class="text-btn"
              onclick="showAuthView('forgot')">
              Forgot password?
            </button>
          </div>

          <button class="primary-btn" type="submit">
            Sign In →
          </button>

        </form>

        <div class="demo-box">
          <strong>Demo Login</strong><br>
          Email: admin@enterprisepro.com<br>
          Password: admin123
        </div>

      </div>

      <div id="registerView" class="hidden">

        <h2>Create account</h2>
        <p class="subtitle">Create your enterprise workspace account.</p>

        <form id="registerForm">

          <div class="form-group">
            <label>Full Name</label>
            <input id="registerName" placeholder="Your name" required>
          </div>

          <div class="form-group">
            <label>Email</label>
            <input id="registerEmail" type="email"
              placeholder="you@company.com" required>
          </div>

          <div class="form-group">
            <label>Password</label>
            <input id="registerPassword" type="password"
              placeholder="Minimum 6 characters" required>
          </div>

          <div class="form-group">
            <label>Confirm Password</label>
            <input id="registerConfirm" type="password"
              placeholder="Repeat password" required>
          </div>

          <button class="primary-btn" type="submit">
            Create Account
          </button>

        </form>

        <p class="auth-footer">
          Already have an account?
          <button class="text-btn" onclick="showAuthView('login')">
            Login
          </button>
        </p>

      </div>

      <div id="forgotView" class="hidden">

        <h2>Reset password</h2>

        <p class="subtitle">
          Enter your account email and we'll simulate sending a
          password reset link.
        </p>

        <form id="forgotForm">

          <div class="form-group">
            <label>Email Address</label>
            <input id="forgotEmail"
              type="email"
              placeholder="you@company.com"
              required>
          </div>

          <button class="primary-btn" type="submit">
            Send Reset Link
          </button>

        </form>

        <p class="auth-footer">
          <button class="text-btn" onclick="showAuthView('login')">
            ← Back to Login
          </button>
        </p>

      </div>

    </div>

  </div>
</section>

<!-- =========================
     MAIN APPLICATION
========================= -->

<div id="app" class="app hidden">

  <aside id="sidebar" class="sidebar">

    <div class="sidebar-brand">
      <div class="brand-icon">EP</div>
      EnterprisePro
    </div>

    <nav class="sidebar-nav">

      <div class="nav-section">Overview</div>

      <button class="nav-item active" data-page="dashboard">
        <span class="nav-icon">📊</span> Dashboard
      </button>

      <button class="nav-item" data-page="analytics">
        <span class="nav-icon">📈</span> Analytics
      </button>

      <div class="nav-section">Business</div>

      <button class="nav-item" data-page="hr">
        <span class="nav-icon">👥</span> HR Management
      </button>

      <button class="nav-item" data-page="inventory">
        <span class="nav-icon">📦</span> Inventory
      </button>

      <button class="nav-item" data-page="crm">
        <span class="nav-icon">🛒</span> CRM & Sales
      </button>

      <button class="nav-item" data-page="finance">
        <span class="nav-icon">💰</span> Finance
      </button>

      <div class="nav-section">Technology</div>

      <button class="nav-item" data-page="devops">
        <span class="nav-icon">🚀</span> DevOps & CI/CD
      </button>

      <button class="nav-item" data-page="monitoring">
        <span class="nav-icon">🖥️</span> Monitoring
      </button>

      <button class="nav-item" data-page="security">
        <span class="nav-icon">🔐</span> Security
      </button>

      <button class="nav-item" data-page="incidents">
        <span class="nav-icon">🚨</span> Incidents
      </button>

      <div class="nav-section">Operations</div>

      <button class="nav-item" data-page="backup">
        <span class="nav-icon">💾</span> Backup & DR
      </button>

      <button class="nav-item" data-page="reports">
        <span class="nav-icon">📑</span> Reports
      </button>

      <button class="nav-item" data-page="users">
        <span class="nav-icon">🧑‍💼</span> Users & RBAC
      </button>

      <button class="nav-item" data-page="settings">
        <span class="nav-icon">⚙️</span> Settings
      </button>

    </nav>

    <div class="sidebar-footer">
      <div class="user-mini">
        <div class="avatar" id="sidebarAvatar">A</div>
        <div>
          <strong id="sidebarName">Administrator</strong>
          <small>Enterprise Admin</small>
        </div>
      </div>
    </div>

  </aside>

  <main class="main">

    <header class="topbar">

      <div class="top-left">

        <button class="mobile-menu" onclick="toggleSidebar()">☰</button>

        <div class="global-search">
          <span>⌕</span>
          <input id="globalSearch"
            placeholder="Search enterprise data...">
        </div>

      </div>

      <div class="top-actions">

        <button class="icon-btn" onclick="showToast('All systems operational','success')">
          <span>✓</span>
        </button>

        <button class="icon-btn" onclick="showNotifications()">
          🔔
          <span class="notification-dot"></span>
        </button>

        <button class="icon-btn" onclick="toggleTheme()" id="themeButton">
          🌙
        </button>

        <button class="icon-btn" onclick="logout()">
          ↪
        </button>

      </div>

    </header>

    <section class="content">

      <!-- ================= DASHBOARD ================= -->

      <section id="page-dashboard" class="page active">

        <div class="page-header">

          <div>
            <h1>Enterprise Dashboard</h1>
            <p id="dashboardGreeting">
              Real-time overview of your organization.
            </p>
          </div>

          <div class="header-actions">
            <button class="btn" onclick="refreshDashboard()">↻ Refresh</button>
            <button class="btn primary" onclick="generateReport()">Generate Report</button>
          </div>

        </div>

        <!-- KPI -->
        <div class="grid kpi-grid">

          <div class="kpi">
            <div class="kpi-top">
              <small>Revenue</small>
              <div class="kpi-icon">₹</div>
            </div>
            <h2 id="revenueKpi">₹24.8M</h2>
            <span class="trend up">▲ 14.8% this month</span>
          </div>

          <div class="kpi">
            <div class="kpi-top">
              <small>Net Profit</small>
              <div class="kpi-icon">↗</div>
            </div>
            <h2>₹6.4M</h2>
            <span class="trend up">▲ 9.7%</span>
          </div>

          <div class="kpi">
            <div class="kpi-top">
              <small>Customers</small>
              <div class="kpi-icon">👥</div>
            </div>
            <h2>12,482</h2>
            <span class="trend up">▲ 8.2%</span>
          </div>

          <div class="kpi">
            <div class="kpi-top">
              <small>Orders</small>
              <div class="kpi-icon">🛒</div>
            </div>
            <h2>8,921</h2>
            <span class="trend up">▲ 11.4%</span>
          </div>

          <div class="kpi">
            <div class="kpi-top">
              <small>Employees</small>
              <div class="kpi-icon">🧑</div>
            </div>
            <h2 id="employeeKpi">1,284</h2>
            <span class="trend up">▲ 3.1%</span>
          </div>

          <div class="kpi">
            <div class="kpi-top">
              <small>Uptime</small>
              <div class="kpi-icon">⚡</div>
            </div>
            <h2>99.96%</h2>
            <span class="trend up">Healthy</span>
          </div>

        </div>

        <!-- Revenue / Executive -->
        <div class="dashboard-grid">

          <div class="card">

            <div class="card-title">
              <h3>Revenue & Profit Performance</h3>
              <span>Last 12 months</span>
            </div>

            <div class="chart">
              <canvas id="revenueChart"></canvas>
            </div>

          </div>

          <div class="card score-card">

            <div class="card-title">
              <h3>Enterprise Health</h3>
              <span>Live</span>
            </div>

            <div class="health-circle">92%</div>

            <p>
              Overall platform and business health
            </p>

            <div style="margin-top:20px;text-align:left">

              <div class="metric-row">
                <span>Business</span>
                <strong>95%</strong>
              </div>
              <div class="progress"><span style="width:95%"></span></div>

              <div class="metric-row" style="margin-top:12px">
                <span>Technology</span>
                <strong>91%</strong>
              </div>
              <div class="progress"><span style="width:91%"></span></div>

              <div class="metric-row" style="margin-top:12px">
                <span>Security</span>
                <strong>89%</strong>
              </div>
              <div class="progress"><span style="width:89%"></span></div>

              <div class="metric-row" style="margin-top:12px">
                <span>Operations</span>
                <strong>94%</strong>
              </div>
              <div class="progress"><span style="width:94%"></span></div>

            </div>

          </div>

        </div>

        <!-- Action Center -->
        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Management Action Center</h3>
            <span>Requires attention</span>
          </div>

          <div class="action-grid">

            <div class="action-card" onclick="showPage('hr')">
              👥
              <strong>12 Leave Requests</strong>
              <small>Awaiting approval</small>
            </div>

            <div class="action-card" onclick="showPage('inventory')">
              📦
              <strong>7 Low Stock</strong>
              <small>Inventory alerts</small>
            </div>

            <div class="action-card" onclick="showPage('finance')">
              💰
              <strong>4 Overdue Invoices</strong>
              <small>₹284K pending</small>
            </div>

            <div class="action-card" onclick="showPage('security')">
              🔐
              <strong>3 Security Alerts</strong>
              <small>Review required</small>
            </div>

            <div class="action-card" onclick="showPage('incidents')">
              🚨
              <strong>1 Critical Incident</strong>
              <small>Engineering team</small>
            </div>

            <div class="action-card" onclick="showPage('devops')">
              🚀
              <strong>2 Deployments</strong>
              <small>Pending approval</small>
            </div>

            <div class="action-card" onclick="showPage('backup')">
              💾
              <strong>Backup Healthy</strong>
              <small>Last backup 12 min ago</small>
            </div>

            <div class="action-card" onclick="showPage('reports')">
              📑
              <strong>8 Reports</strong>
              <small>Available for download</small>
            </div>

          </div>

        </div>

        <!-- Business overview -->
        <div class="three-col">

          <div class="card">

            <div class="card-title">
              <h3>HR Overview</h3>
              <span>Today</span>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>Attendance</span>
                  <strong>94.8%</strong>
                </div>
                <div class="progress"><span style="width:94.8%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Employee Retention</span>
                  <strong>91%</strong>
                </div>
                <div class="progress"><span style="width:91%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Recruitment</span>
                  <strong>72%</strong>
                </div>
                <div class="progress"><span style="width:72%"></span></div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Inventory Health</h3>
              <span>All warehouses</span>
            </div>

            <div class="metric-list">

              <div class="metric-row">
                <span>Total Products</span>
                <strong>18,492</strong>
              </div>

              <div class="metric-row">
                <span>Inventory Value</span>
                <strong>₹8.7M</strong>
              </div>

              <div class="metric-row">
                <span>Low Stock</span>
                <span class="status warning">7 Items</span>
              </div>

              <div class="metric-row">
                <span>Out of Stock</span>
                <span class="status danger">2 Items</span>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Finance Snapshot</h3>
              <span>This month</span>
            </div>

            <div class="metric-list">

              <div class="metric-row">
                <span>Receivables</span>
                <strong>₹3.2M</strong>
              </div>

              <div class="metric-row">
                <span>Payables</span>
                <strong>₹1.8M</strong>
              </div>

              <div class="metric-row">
                <span>Cash Flow</span>
                <span class="trend up">+₹1.4M</span>
              </div>

              <div class="metric-row">
                <span>Budget Usage</span>
                <strong>68%</strong>
              </div>

            </div>

          </div>

        </div>

        <!-- Technology -->
        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Technology & Infrastructure</h3>
            <span>Live monitoring</span>
          </div>

          <div class="health-grid">

            <div class="health-item">
              <small>CPU Utilization</small>
              <strong>42%</strong>
              <span class="status success">Healthy</span>
            </div>

            <div class="health-item">
              <small>Memory</small>
              <strong>61%</strong>
              <span class="status success">Healthy</span>
            </div>

            <div class="health-item">
              <small>API Latency</small>
              <strong>128ms</strong>
              <span class="status success">Normal</span>
            </div>

            <div class="health-item">
              <small>Database</small>
              <strong>99.98%</strong>
              <span class="status success">Operational</span>
            </div>

            <div class="health-item">
              <small>Containers</small>
              <strong>184</strong>
              <span class="status success">Running</span>
            </div>

            <div class="health-item">
              <small>Deployments</small>
              <strong>24</strong>
              <span class="status info">This week</span>
            </div>

            <div class="health-item">
              <small>Build Success</small>
              <strong>97.8%</strong>
              <span class="status success">Excellent</span>
            </div>

            <div class="health-item">
              <small>Cloud Storage</small>
              <strong>68%</strong>
              <span class="status warning">Monitor</span>
            </div>

          </div>

        </div>

        <!-- Bottom -->
        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>Recent Enterprise Activity</h3>
              <span>Live feed</span>
            </div>

            <div class="activity">

              <div class="activity-item">
                <div class="activity-dot">🚀</div>
                <div>
                  <strong>Production deployment completed</strong>
                  <p>Release v4.8.2 deployed successfully.</p>
                  <time>2 minutes ago</time>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">💰</div>
                <div>
                  <strong>Invoice INV-1042 paid</strong>
                  <p>Payment received: ₹184,500.</p>
                  <time>8 minutes ago</time>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">👥</div>
                <div>
                  <strong>New employee onboarded</strong>
                  <p>Engineering department.</p>
                  <time>21 minutes ago</time>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">🔐</div>
                <div>
                  <strong>Security scan completed</strong>
                  <p>No critical vulnerabilities detected.</p>
                  <time>32 minutes ago</time>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">💾</div>
                <div>
                  <strong>Database backup completed</strong>
                  <p>Backup verified successfully.</p>
                  <time>48 minutes ago</time>
                </div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>AI Enterprise Insights</h3>
              <span>Analysis</span>
            </div>

            <div class="insight">
              <strong>📦 Inventory Forecast</strong>
              <p>Product A may reach critical stock level within 5 days.</p>
            </div>

            <div class="insight">
              <strong>📈 Sales Performance</strong>
              <p>Current sales are 12% above the monthly target.</p>
            </div>

            <div class="insight">
              <strong>💰 Finance</strong>
              <p>4 invoices require payment follow-up.</p>
            </div>

            <div class="insight">
              <strong>🚀 DevOps</strong>
              <p>API latency increased slightly after the latest deployment.</p>
            </div>

            <div class="insight">
              <strong>🔐 Security</strong>
              <p>3 security events require administrator review.</p>
            </div>

          </div>

        </div>

        <!-- Calendar -->
        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Upcoming Enterprise Events</h3>
            <span>This week</span>
          </div>

          <div class="calendar">

            <div class="event">
              <div class="event-date">25<br>SEP</div>
              <div>
                <strong>Monthly Management Review</strong>
                <small>10:00 AM · Conference Room A</small>
              </div>
            </div>

            <div class="event">
              <div class="event-date">26<br>SEP</div>
              <div>
                <strong>Production Maintenance</strong>
                <small>01:00 AM · Infrastructure Team</small>
              </div>
            </div>

            <div class="event">
              <div class="event-date">27<br>SEP</div>
              <div>
                <strong>Payroll Processing</strong>
                <small>09:00 AM · HR & Finance</small>
              </div>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= ANALYTICS ================= -->

      <section id="page-analytics" class="page">

        <div class="page-header">
          <div>
            <h1>Advanced Analytics</h1>
            <p>Business intelligence and enterprise performance.</p>
          </div>
          <button class="btn primary" onclick="showToast('Analytics report generated','success')">
            Export Analytics
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Growth Rate</small>
            <h2>18.6%</h2>
            <span class="trend up">▲ 4.2%</span>
          </div>

          <div class="kpi">
            <small>Conversion Rate</small>
            <h2>7.8%</h2>
            <span class="trend up">▲ 1.1%</span>
          </div>

          <div class="kpi">
            <small>Retention</small>
            <h2>91.2%</h2>
            <span class="trend up">▲ 2.4%</span>
          </div>

          <div class="kpi">
            <small>Churn</small>
            <h2>2.1%</h2>
            <span class="trend down">▼ 0.4%</span>
          </div>

          <div class="kpi">
            <small>AOV</small>
            <h2>₹8,420</h2>
            <span class="trend up">▲ 6.8%</span>
          </div>

          <div class="kpi">
            <small>Customer LTV</small>
            <h2>₹74K</h2>
            <span class="trend up">▲ 9.3%</span>
          </div>

        </div>

        <div class="dashboard-grid">

          <div class="card">
            <div class="card-title">
              <h3>Sales Trend</h3>
              <span>12 months</span>
            </div>
            <div class="chart">
              <canvas id="salesChart"></canvas>
            </div>
          </div>

          <div class="card">
            <div class="card-title">
              <h3>Department Performance</h3>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>Sales</span><strong>94%</strong>
                </div>
                <div class="progress"><span style="width:94%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Engineering</span><strong>91%</strong>
                </div>
                <div class="progress"><span style="width:91%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Finance</span><strong>87%</strong>
                </div>
                <div class="progress"><span style="width:87%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>HR</span><strong>90%</strong>
                </div>
                <div class="progress"><span style="width:90%"></span></div>
              </div>

            </div>
          </div>

        </div>

      </section>

      <!-- ================= HR ================= -->

      <section id="page-hr" class="page">

        <div class="page-header">

          <div>
            <h1>HR Management</h1>
            <p>Employees, attendance, payroll and workforce analytics.</p>
          </div>

          <button class="btn primary" onclick="addEmployee()">
            + Add Employee
          </button>

        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Total Employees</small>
            <h2 id="hrEmployeeCount">1,284</h2>
            <span class="trend up">▲ 3.1%</span>
          </div>

          <div class="kpi">
            <small>Attendance</small>
            <h2>94.8%</h2>
            <span class="trend up">Healthy</span>
          </div>

          <div class="kpi">
            <small>On Leave</small>
            <h2>42</h2>
            <span class="trend">Today</span>
          </div>

          <div class="kpi">
            <small>Open Positions</small>
            <h2>28</h2>
            <span class="trend up">Hiring</span>
          </div>

          <div class="kpi">
            <small>Payroll</small>
            <h2>₹12.4M</h2>
            <span class="trend">Monthly</span>
          </div>

          <div class="kpi">
            <small>Retention</small>
            <h2>91%</h2>
            <span class="trend up">▲ 2.1%</span>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="toolbar">
            <input id="employeeSearch" placeholder="Search employees...">
            <select>
              <option>All Departments</option>
              <option>Engineering</option>
              <option>Sales</option>
              <option>Finance</option>
              <option>HR</option>
            </select>
          </div>

          <div class="table-wrap">

            <table>

              <thead>
                <tr>
                  <th>Employee</th>
                  <th>Department</th>
                  <th>Role</th>
                  <th>Status</th>
                  <th>Performance</th>
                </tr>
              </thead>

              <tbody id="employeeTable"></tbody>

            </table>

          </div>

        </div>

      </section>

      <!-- ================= INVENTORY ================= -->

      <section id="page-inventory" class="page">

        <div class="page-header">
          <div>
            <h1>Inventory Management</h1>
            <p>Products, warehouses, suppliers and stock monitoring.</p>
          </div>
          <button class="btn primary" onclick="showToast('Product creation form opened','info')">
            + Add Product
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Total Products</small>
            <h2>18,492</h2>
          </div>

          <div class="kpi">
            <small>Inventory Value</small>
            <h2>₹8.7M</h2>
          </div>

          <div class="kpi">
            <small>Low Stock</small>
            <h2>7</h2>
            <span class="trend down">Attention</span>
          </div>

          <div class="kpi">
            <small>Out of Stock</small>
            <h2>2</h2>
            <span class="trend down">Critical</span>
          </div>

          <div class="kpi">
            <small>Warehouses</small>
            <h2>12</h2>
          </div>

          <div class="kpi">
            <small>Suppliers</small>
            <h2>284</h2>
          </div>

        </div>

        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>Stock Distribution</h3>
              <span>By warehouse</span>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>Hyderabad Warehouse</span>
                  <strong>82%</strong>
                </div>
                <div class="progress"><span style="width:82%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Visakhapatnam Warehouse</span>
                  <strong>67%</strong>
                </div>
                <div class="progress"><span style="width:67%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Bangalore Warehouse</span>
                  <strong>73%</strong>
                </div>
                <div class="progress"><span style="width:73%"></span></div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Inventory Alerts</h3>
            </div>

            <div class="activity">

              <div class="activity-item">
                <div class="activity-dot">⚠</div>
                <div>
                  <strong>Product SKU-104 below threshold</strong>
                  <p>Current stock: 18 units.</p>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">🚨</div>
                <div>
                  <strong>SKU-208 out of stock</strong>
                  <p>Purchase order recommended.</p>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">📦</div>
                <div>
                  <strong>Shipment arriving</strong>
                  <p>Expected tomorrow.</p>
                </div>
              </div>

            </div>

          </div>

        </div>

      </section>

      <!-- ================= CRM ================= -->

      <section id="page-crm" class="page">

        <div class="page-header">
          <div>
            <h1>CRM & Sales</h1>
            <p>Customers, leads, quotations and sales pipeline.</p>
          </div>
          <button class="btn primary" onclick="showToast('New customer form opened','info')">
            + Add Customer
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Customers</small>
            <h2>12,482</h2>
          </div>

          <div class="kpi">
            <small>Active Leads</small>
            <h2>1,842</h2>
          </div>

          <div class="kpi">
            <small>Conversion</small>
            <h2>7.8%</h2>
          </div>

          <div class="kpi">
            <small>Pipeline</small>
            <h2>₹14.8M</h2>
          </div>

          <div class="kpi">
            <small>Orders</small>
            <h2>8,921</h2>
          </div>

          <div class="kpi">
            <small>Average Order</small>
            <h2>₹8,420</h2>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Sales Funnel</h3>
          </div>

          <div class="metric-list">

            <div>
              <div class="metric-row">
                <span>Leads</span><strong>1,842</strong>
              </div>
              <div class="progress"><span style="width:100%"></span></div>
            </div>

            <div>
              <div class="metric-row">
                <span>Qualified</span><strong>1,020</strong>
              </div>
              <div class="progress"><span style="width:70%"></span></div>
            </div>

            <div>
              <div class="metric-row">
                <span>Proposals</span><strong>584</strong>
              </div>
              <div class="progress"><span style="width:50%"></span></div>
            </div>

            <div>
              <div class="metric-row">
                <span>Won</span><strong>312</strong>
              </div>
              <div class="progress"><span style="width:34%"></span></div>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= FINANCE ================= -->

      <section id="page-finance" class="page">

        <div class="page-header">
          <div>
            <h1>Finance & Accounting</h1>
            <p>Financial control, invoices, payments and cash flow.</p>
          </div>

          <button class="btn primary" onclick="showToast('Invoice form opened','info')">
            + Create Invoice
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Revenue</small>
            <h2>₹24.8M</h2>
          </div>

          <div class="kpi">
            <small>Profit</small>
            <h2>₹6.4M</h2>
          </div>

          <div class="kpi">
            <small>Receivables</small>
            <h2>₹3.2M</h2>
          </div>

          <div class="kpi">
            <small>Payables</small>
            <h2>₹1.8M</h2>
          </div>

          <div class="kpi">
            <small>Expenses</small>
            <h2>₹18.4M</h2>
          </div>

          <div class="kpi">
            <small>Cash Flow</small>
            <h2>₹1.4M</h2>
          </div>

        </div>

        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>Financial Health</h3>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>Budget Utilization</span>
                  <strong>68%</strong>
                </div>
                <div class="progress"><span style="width:68%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Receivables Collection</span>
                  <strong>84%</strong>
                </div>
                <div class="progress"><span style="width:84%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Expense Control</span>
                  <strong>91%</strong>
                </div>
                <div class="progress"><span style="width:91%"></span></div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Invoice Status</h3>
            </div>

            <div class="metric-row">
              <span>Paid</span>
              <span class="status success">1,284</span>
            </div>

            <div class="metric-row">
              <span>Pending</span>
              <span class="status warning">84</span>
            </div>

            <div class="metric-row">
              <span>Overdue</span>
              <span class="status danger">4</span>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= DEVOPS ================= -->

      <section id="page-devops" class="page">

        <div class="page-header">
          <div>
            <h1>DevOps & CI/CD</h1>
            <p>Deployment pipelines, builds and infrastructure delivery.</p>
          </div>

          <button class="btn primary" onclick="runDeployment()">
            🚀 Run Deployment
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Deployments</small>
            <h2>24</h2>
            <span class="trend up">This week</span>
          </div>

          <div class="kpi">
            <small>Build Success</small>
            <h2>97.8%</h2>
          </div>

          <div class="kpi">
            <small>Failed Builds</small>
            <h2>3</h2>
          </div>

          <div class="kpi">
            <small>Deployment Frequency</small>
            <h2>4.2/day</h2>
          </div>

          <div class="kpi">
            <small>MTTR</small>
            <h2>18m</h2>
          </div>

          <div class="kpi">
            <small>Pipeline Status</small>
            <h2>Healthy</h2>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>CI/CD Pipelines</h3>
          </div>

          <div class="table-wrap">

            <table>

              <thead>
                <tr>
                  <th>Pipeline</th>
                  <th>Branch</th>
                  <th>Build</th>
                  <th>Deployment</th>
                  <th>Status</th>
                </tr>
              </thead>

              <tbody>

                <tr>
                  <td>Enterprise API</td>
                  <td>main</td>
                  <td>#4821</td>
                  <td>Production</td>
                  <td><span class="status success">Success</span></td>
                </tr>

                <tr>
                  <td>Web Portal</td>
                  <td>release</td>
                  <td>#2718</td>
                  <td>Staging</td>
                  <td><span class="status info">Running</span></td>
                </tr>

                <tr>
                  <td>Analytics Engine</td>
                  <td>develop</td>
                  <td>#982</td>
                  <td>Testing</td>
                  <td><span class="status warning">Testing</span></td>
                </tr>

              </tbody>

            </table>

          </div>

        </div>

      </section>

      <!-- ================= MONITORING ================= -->

      <section id="page-monitoring" class="page">

        <div class="page-header">
          <div>
            <h1>Monitoring & Observability</h1>
            <p>Infrastructure, APIs, databases and services.</p>
          </div>
          <span class="status success">All Systems Operational</span>
        </div>

        <div class="health-grid">

          <div class="health-item">
            <small>API Gateway</small>
            <strong>99.99%</strong>
            <span class="status success">Healthy</span>
          </div>

          <div class="health-item">
            <small>Database</small>
            <strong>99.98%</strong>
            <span class="status success">Healthy</span>
          </div>

          <div class="health-item">
            <small>Redis Cache</small>
            <strong>99.97%</strong>
            <span class="status success">Healthy</span>
          </div>

          <div class="health-item">
            <small>Message Queue</small>
            <strong>99.94%</strong>
            <span class="status success">Healthy</span>
          </div>

        </div>

        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>System Resources</h3>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>CPU</span><strong>42%</strong>
                </div>
                <div class="progress"><span style="width:42%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Memory</span><strong>61%</strong>
                </div>
                <div class="progress"><span style="width:61%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Storage</span><strong>68%</strong>
                </div>
                <div class="progress"><span style="width:68%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Network</span><strong>34%</strong>
                </div>
                <div class="progress"><span style="width:34%"></span></div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>API Performance</h3>
            </div>

            <div class="metric-row">
              <span>Requests/min</span>
              <strong>18,482</strong>
            </div>

            <div class="metric-row">
              <span>Average Latency</span>
              <strong>128ms</strong>
            </div>

            <div class="metric-row">
              <span>Error Rate</span>
              <strong>0.08%</strong>
            </div>

            <div class="metric-row">
              <span>5xx Errors</span>
              <strong>12</strong>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= SECURITY ================= -->

      <section id="page-security" class="page">

        <div class="page-header">
          <div>
            <h1>Security Operations</h1>
            <p>Security posture, vulnerabilities, access and compliance.</p>
          </div>

          <span class="status success">Security Monitoring Active</span>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Security Score</small>
            <h2>89/100</h2>
          </div>

          <div class="kpi">
            <small>Critical Vulnerabilities</small>
            <h2>0</h2>
            <span class="trend up">Excellent</span>
          </div>

          <div class="kpi">
            <small>High Risk</small>
            <h2>3</h2>
            <span class="trend down">Review</span>
          </div>

          <div class="kpi">
            <small>Failed Logins</small>
            <h2>28</h2>
          </div>

          <div class="kpi">
            <small>MFA Adoption</small>
            <h2>94%</h2>
          </div>

          <div class="kpi">
            <small>Audit Events</small>
            <h2>18,492</h2>
          </div>

        </div>

        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>Compliance</h3>
            </div>

            <div class="metric-list">

              <div>
                <div class="metric-row">
                  <span>ISO Controls</span>
                  <strong>96%</strong>
                </div>
                <div class="progress"><span style="width:96%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Access Reviews</span>
                  <strong>91%</strong>
                </div>
                <div class="progress"><span style="width:91%"></span></div>
              </div>

              <div>
                <div class="metric-row">
                  <span>Security Training</span>
                  <strong>88%</strong>
                </div>
                <div class="progress"><span style="width:88%"></span></div>
              </div>

            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Security Events</h3>
            </div>

            <div class="activity">

              <div class="activity-item">
                <div class="activity-dot">🔐</div>
                <div>
                  <strong>Multiple failed login attempts</strong>
                  <p>Account security review recommended.</p>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">🛡️</div>
                <div>
                  <strong>Vulnerability scan completed</strong>
                  <p>No critical issues detected.</p>
                </div>
              </div>

              <div class="activity-item">
                <div class="activity-dot">👤</div>
                <div>
                  <strong>New administrator session</strong>
                  <p>Authenticated using MFA.</p>
                </div>
              </div>

            </div>

          </div>

        </div>

      </section>

      <!-- ================= INCIDENTS ================= -->

      <section id="page-incidents" class="page">

        <div class="page-header">
          <div>
            <h1>Incident Management</h1>
            <p>Monitor, assign and resolve operational incidents.</p>
          </div>

          <button class="btn danger" onclick="createIncident()">
            + Create Incident
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Critical</small>
            <h2>1</h2>
          </div>

          <div class="kpi">
            <small>High</small>
            <h2>3</h2>
          </div>

          <div class="kpi">
            <small>Open</small>
            <h2>7</h2>
          </div>

          <div class="kpi">
            <small>Resolved</small>
            <h2>184</h2>
          </div>

          <div class="kpi">
            <small>MTTA</small>
            <h2>6m</h2>
          </div>

          <div class="kpi">
            <small>MTTR</small>
            <h2>18m</h2>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="table-wrap">

            <table>

              <thead>
                <tr>
                  <th>Incident</th>
                  <th>Severity</th>
                  <th>Owner</th>
                  <th>Status</th>
                  <th>Created</th>
                </tr>
              </thead>

              <tbody>

                <tr>
                  <td>API latency spike</td>
                  <td><span class="status danger">Critical</span></td>
                  <td>Engineering</td>
                  <td><span class="status warning">Investigating</span></td>
                  <td>12 min ago</td>
                </tr>

                <tr>
                  <td>Payment timeout</td>
                  <td><span class="status warning">High</span></td>
                  <td>Platform</td>
                  <td><span class="status info">Monitoring</span></td>
                  <td>42 min ago</td>
                </tr>

                <tr>
                  <td>Report generation delay</td>
                  <td><span class="status info">Medium</span></td>
                  <td>Analytics</td>
                  <td><span class="status success">Resolved</span></td>
                  <td>2 hr ago</td>
                </tr>

              </tbody>

            </table>

          </div>

        </div>

      </section>

      <!-- ================= BACKUP ================= -->

      <section id="page-backup" class="page">

        <div class="page-header">
          <div>
            <h1>Backup & Disaster Recovery</h1>
            <p>Data protection, backup verification and recovery readiness.</p>
          </div>

          <button class="btn primary" onclick="showToast('Backup started','success')">
            Start Backup
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Backup Success</small>
            <h2>99.8%</h2>
          </div>

          <div class="kpi">
            <small>Last Backup</small>
            <h2>12m</h2>
          </div>

          <div class="kpi">
            <small>Backup Size</small>
            <h2>842 GB</h2>
          </div>

          <div class="kpi">
            <small>RPO</small>
            <h2>15 min</h2>
          </div>

          <div class="kpi">
            <small>RTO</small>
            <h2>45 min</h2>
          </div>

          <div class="kpi">
            <small>DR Readiness</small>
            <h2>94%</h2>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Backup Services</h3>
          </div>

          <div class="health-grid">

            <div class="health-item">
              <small>Production DB</small>
              <strong>Healthy</strong>
              <span class="status success">Verified</span>
            </div>

            <div class="health-item">
              <small>Object Storage</small>
              <strong>Healthy</strong>
              <span class="status success">Verified</span>
            </div>

            <div class="health-item">
              <small>Application Data</small>
              <strong>Healthy</strong>
              <span class="status success">Verified</span>
            </div>

            <div class="health-item">
              <small>DR Region</small>
              <strong>Ready</strong>
              <span class="status success">Standby</span>
            </div>

          </div>

        </div>

      </section>

      <!-- ================= REPORTS ================= -->

      <section id="page-reports" class="page">

        <div class="page-header">
          <div>
            <h1>Reports Center</h1>
            <p>Enterprise reports and data exports.</p>
          </div>
        </div>

        <div class="action-grid">

          <div class="action-card" onclick="exportData('employees')">
            👥
            <strong>HR Report</strong>
            <small>Employee data CSV</small>
          </div>

          <div class="action-card" onclick="exportData('finance')">
            💰
            <strong>Finance Report</strong>
            <small>Financial summary</small>
          </div>

          <div class="action-card" onclick="exportData('inventory')">
            📦
            <strong>Inventory Report</strong>
            <small>Stock summary</small>
          </div>

          <div class="action-card" onclick="exportData('dashboard')">
            📊
            <strong>Executive Report</strong>
            <small>Dashboard summary</small>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="card-title">
            <h3>Available Reports</h3>
          </div>

          <div class="table-wrap">

            <table>

              <thead>
                <tr>
                  <th>Report</th>
                  <th>Category</th>
                  <th>Generated</th>
                  <th>Format</th>
                  <th>Action</th>
                </tr>
              </thead>

              <tbody>

                <tr>
                  <td>Monthly Executive Summary</td>
                  <td>Management</td>
                  <td>Today</td>
                  <td>PDF</td>
                  <td><button class="btn" onclick="generateReport()">Generate</button></td>
                </tr>

                <tr>
                  <td>Employee Performance</td>
                  <td>HR</td>
                  <td>Yesterday</td>
                  <td>CSV</td>
                  <td><button class="btn" onclick="exportData('employees')">Download</button></td>
                </tr>

                <tr>
                  <td>Inventory Valuation</td>
                  <td>Inventory</td>
                  <td>Yesterday</td>
                  <td>CSV</td>
                  <td><button class="btn" onclick="exportData('inventory')">Download</button></td>
                </tr>

              </tbody>

            </table>

          </div>

        </div>

      </section>

      <!-- ================= USERS ================= -->

      <section id="page-users" class="page">

        <div class="page-header">
          <div>
            <h1>Users & RBAC</h1>
            <p>Enterprise users, roles and access management.</p>
          </div>

          <button class="btn primary"
            onclick="showToast('User invitation created','success')">
            + Invite User
          </button>
        </div>

        <div class="grid kpi-grid">

          <div class="kpi">
            <small>Total Users</small>
            <h2>1,842</h2>
          </div>

          <div class="kpi">
            <small>Administrators</small>
            <h2>18</h2>
          </div>

          <div class="kpi">
            <small>Managers</small>
            <h2>84</h2>
          </div>

          <div class="kpi">
            <small>Active Sessions</small>
            <h2>642</h2>
          </div>

          <div class="kpi">
            <small>MFA Enabled</small>
            <h2>94%</h2>
          </div>

          <div class="kpi">
            <small>Pending Invites</small>
            <h2>12</h2>
          </div>

        </div>

        <div class="card" style="margin-top:15px">

          <div class="table-wrap">

            <table>

              <thead>
                <tr>
                  <th>User</th>
                  <th>Email</th>
                  <th>Role</th>
                  <th>MFA</th>
                  <th>Status</th>
                </tr>
              </thead>

              <tbody>

                <tr>
                  <td>Administrator</td>
                  <td>admin@enterprisepro.com</td>
                  <td>Super Admin</td>
                  <td>Enabled</td>
                  <td><span class="status success">Active</span></td>
                </tr>

                <tr>
                  <td>Priya Sharma</td>
                  <td>priya@company.com</td>
                  <td>Finance Manager</td>
                  <td>Enabled</td>
                  <td><span class="status success">Active</span></td>
                </tr>

                <tr>
                  <td>Rahul Kumar</td>
                  <td>rahul@company.com</td>
                  <td>Engineering</td>
                  <td>Enabled</td>
                  <td><span class="status success">Active</span></td>
                </tr>

              </tbody>

            </table>

          </div>

        </div>

      </section>

      <!-- ================= SETTINGS ================= -->

      <section id="page-settings" class="page">

        <div class="page-header">
          <div>
            <h1>Settings</h1>
            <p>Configure your EnterprisePro workspace.</p>
          </div>
        </div>

        <div class="two-col">

          <div class="card">

            <div class="card-title">
              <h3>Appearance</h3>
            </div>

            <div class="metric-row">
              <span>Dark Mode</span>
              <button class="btn" onclick="toggleTheme()">Toggle Theme</button>
            </div>

            <div class="metric-row">
              <span>Auto Refresh</span>
              <span class="status success">Enabled</span>
            </div>

            <div class="metric-row">
              <span>Animations</span>
              <span class="status success">Enabled</span>
            </div>

          </div>

          <div class="card">

            <div class="card-title">
              <h3>Data Management</h3>
            </div>

            <button class="btn danger" onclick="resetDemoData()">
              Reset Demo Data
            </button>

            <p style="color:var(--muted);font-size:12px;margin-top:12px">
              This will reset locally stored demo information.
            </p>

          </div>

        </div>

      </section>

    </section>

  </main>

</div>

<div id="toastContainer" class="toast-container"></div>

<div id="modalRoot"></div>

<script>
/* ==========================================================
   ENTERPRISEPRO APPLICATION
========================================================== */

const defaultEmployees = [
  {
    name:"Arjun Rao",
    department:"Engineering",
    role:"Senior Software Engineer",
    status:"Active",
    performance:"94%"
  },
  {
    name:"Priya Sharma",
    department:"Finance",
    role:"Finance Manager",
    status:"Active",
    performance:"91%"
  },
  {
    name:"Rahul Kumar",
    department:"Engineering",
    role:"DevOps Engineer",
    status:"Active",
    performance:"96%"
  },
  {
    name:"Ananya Reddy",
    department:"HR",
    role:"HR Business Partner",
    status:"Active",
    performance:"89%"
  },
  {
    name:"Vikram Singh",
    department:"Sales",
    role:"Sales Manager",
    status:"Active",
    performance:"97%"
  }
];

let employees =
  JSON.parse(localStorage.getItem("ep_employees")) ||
  defaultEmployees;

let users =
  JSON.parse(localStorage.getItem("ep_users")) ||
  [
    {
      name:"Administrator",
      email:"admin@enterprisepro.com",
      password:"admin123",
      role:"Super Admin"
    }
  ];

let currentUser =
  JSON.parse(localStorage.getItem("ep_current_user")) || null;

/* ==========================================================
   INIT
========================================================== */

document.addEventListener("DOMContentLoaded",()=>{

  initTheme();

  document.querySelectorAll(".nav-item").forEach(btn=>{
    btn.addEventListener("click",()=>{
      showPage(btn.dataset.page);
    });
  });

  document
    .getElementById("loginForm")
    .addEventListener("submit",handleLogin);

  document
    .getElementById("registerForm")
    .addEventListener("submit",handleRegister);

  document
    .getElementById("forgotForm")
    .addEventListener("submit",handleForgot);

  document
    .getElementById("employeeSearch")
    ?.addEventListener("input",renderEmployees);

  document
    .getElementById("globalSearch")
    ?.addEventListener("input",globalSearch);

  if(currentUser){
    openApp();
  }

  renderEmployees();

  setTimeout(drawCharts,300);

  window.addEventListener("resize",()=>{
    drawCharts();
  });

});

/* ==========================================================
   AUTH
========================================================== */

function showAuthView(view){

  document.getElementById("loginView").classList.add("hidden");
  document.getElementById("registerView").classList.add("hidden");
  document.getElementById("forgotView").classList.add("hidden");

  document.getElementById(view+"View").classList.remove("hidden");
}

function handleLogin(e){

  e.preventDefault();

  const email =
    document.getElementById("loginEmail").value.trim().toLowerCase();

  const password =
    document.getElementById("loginPassword").value;

  const user = users.find(
    u => u.email.toLowerCase() === email &&
         u.password === password
  );

  if(!user){
    showToast("Invalid email or password","error");
    return;
  }

  currentUser = user;

  localStorage.setItem(
    "ep_current_user",
    JSON.stringify(user)
  );

  openApp();

  showToast(
    "Welcome back, "+user.name+"!",
    "success"
  );
}

function handleRegister(e){

  e.preventDefault();

  const name =
    document.getElementById("registerName").value.trim();

  const email =
    document.getElementById("registerEmail").value.trim().toLowerCase();

  const password =
    document.getElementById("registerPassword").value;

  const confirm =
    document.getElementById("registerConfirm").value;

  if(password.length < 6){
    showToast("Password must contain at least 6 characters","error");
    return;
  }

  if(password !== confirm){
    showToast("Passwords do not match","error");
    return;
  }

  if(users.some(u=>u.email.toLowerCase()===email)){
    showToast("An account with this email already exists","error");
    return;
  }

  const user = {
    name,
    email,
    password,
    role:"Enterprise User"
  };

  users.push(user);

  localStorage.setItem(
    "ep_users",
    JSON.stringify(users)
  );

  showToast(
    "Account created successfully. You can now login.",
    "success"
  );

  document.getElementById("registerForm").reset();

  showAuthView("login");

  document.getElementById("loginEmail").value=email;
}

function handleForgot(e){

  e.preventDefault();

  const email =
    document.getElementById("forgotEmail")
      .value
      .trim()
      .toLowerCase();

  const exists =
    users.some(u=>u.email.toLowerCase()===email);

  /*
    SECURITY NOTE:
    A production system should not reveal whether
    an email exists. This demo always displays a
    generic response.
  */

  const token =
    Math.random().toString(36).substring(2,12);

  showModal(
    "Password Reset",
    `
      <p style="color:var(--muted);line-height:1.6">
        If an account exists for
        <strong>${escapeHTML(email)}</strong>,
        a password reset email would be sent.
      </p>

      <div style="
        margin-top:15px;
        padding:14px;
        border-radius:10px;
        background:var(--card2);
        font-size:12px;
      ">
        <strong>Demo reset token</strong><br><br>
        ${token}
      </div>

      <p style="
        margin-top:12px;
        color:var(--muted);
        font-size:12px;
      ">
        Production applications should generate the token
        on the backend and send it through a secure email
        service.
      </p>
    `
  );

  document.getElementById("forgotForm").reset();
}

function togglePassword(id,button){

  const input=document.getElementById(id);

  if(input.type==="password"){
    input.type="text";
    button.textContent="🙈";
  }else{
    input.type="password";
    button.textContent="👁";
  }
}

/* ==========================================================
   APP
========================================================== */

function openApp(){

  document
    .getElementById("authScreen")
    .classList.add("hidden");

  document
    .getElementById("app")
    .classList.remove("hidden");

  const name =
    currentUser?.name || "Administrator";

  document.getElementById("sidebarName").textContent=name;

  document.getElementById("sidebarAvatar").textContent =
    name.charAt(0).toUpperCase();

  document.getElementById("dashboardGreeting").textContent =
    "Welcome "+name+" — here's your enterprise overview.";

  renderEmployees();

  setTimeout(drawCharts,200);
}

function logout(){

  currentUser=null;

  localStorage.removeItem("ep_current_user");

  document
    .getElementById("app")
    .classList.add("hidden");

  document
    .getElementById("authScreen")
    .classList.remove("hidden");

  showAuthView("login");

  showToast("You have been logged out","info");
}

/* ==========================================================
   NAVIGATION
========================================================== */

function showPage(page){

  document.querySelectorAll(".page")
    .forEach(p=>p.classList.remove("active"));

  const target =
    document.getElementById("page-"+page);

  if(target){
    target.classList.add("active");
  }

  document.querySelectorAll(".nav-item")
    .forEach(item=>{
      item.classList.toggle(
        "active",
        item.dataset.page===page
      );
    });

  document
    .getElementById("sidebar")
    .classList.remove("open");

  setTimeout(drawCharts,100);
}

function toggleSidebar(){

  document
    .getElementById("sidebar")
    .classList.toggle("open");
}

/* ==========================================================
   THEME
========================================================== */

function initTheme(){

  const theme =
    localStorage.getItem("ep_theme") || "light";

  if(theme==="dark"){
    document.body.classList.add("dark");
    document.getElementById("themeButton").textContent="☀";
  }
}

function toggleTheme(){

  document.body.classList.toggle("dark");

  const dark =
    document.body.classList.contains("dark");

  localStorage.setItem(
    "ep_theme",
    dark ? "dark" : "light"
  );

  document.getElementById("themeButton").textContent =
    dark ? "☀" : "🌙";

  drawCharts();
}

/* ==========================================================
   EMPLOYEES
========================================================== */

function renderEmployees(){

  const table =
    document.getElementById("employeeTable");

  if(!table)return;

  const search =
    document.getElementById("employeeSearch")
      ?.value
      .toLowerCase() || "";

  const filtered =
    employees.filter(e =>
      Object.values(e)
        .join(" ")
        .toLowerCase()
        .includes(search)
    );

  table.innerHTML =
    filtered.map(e=>`
      <tr>
        <td><strong>${escapeHTML(e.name)}</strong></td>
        <td>${escapeHTML(e.department)}</td>
        <td>${escapeHTML(e.role)}</td>
        <td>
          <span class="status success">
            ${escapeHTML(e.status)}
          </span>
        </td>
        <td>${escapeHTML(e.performance)}</td>
      </tr>
    `).join("");

  document.getElementById("employeeKpi").textContent =
    (1284 + employees.length - defaultEmployees.length).toLocaleString();

  document.getElementById("hrEmployeeCount").textContent =
    (1284 + employees.length - defaultEmployees.length).toLocaleString();
}

function addEmployee(){

  showModal(
    "Add Employee",
    `
      <div class="form-group">
        <label>Name</label>
        <input id="newEmployeeName" placeholder="Employee name">
      </div>

      <div class="form-group">
        <label>Department</label>
        <select id="newEmployeeDepartment">
          <option>Engineering</option>
          <option>Sales</option>
          <option>Finance</option>
          <option>HR</option>
          <option>Operations</option>
        </select>
      </div>

      <div class="form-group">
        <label>Role</label>
        <input id="newEmployeeRole" placeholder="Job role">
      </div>

      <button class="btn primary"
        onclick="saveEmployee()">
        Save Employee
      </button>
    `
  );
}

function saveEmployee(){

  const name =
    document.getElementById("newEmployeeName").value.trim();

  const department =
    document.getElementById("newEmployeeDepartment").value;

  const role =
    document.getElementById("newEmployeeRole").value.trim();

  if(!name || !role){
    showToast("Please complete all fields","error");
    return;
  }

  employees.push({
    name,
    department,
    role,
    status:"Active",
    performance:"New"
  });

  localStorage.setItem(
    "ep_employees",
    JSON.stringify(employees)
  );

  closeModal();

  renderEmployees();

  showToast(
    "Employee added successfully",
    "success"
  );
}

/* ==========================================================
   GLOBAL SEARCH
========================================================== */

function globalSearch(e){

  const q =
    e.target.value.trim().toLowerCase();

  if(!q)return;

  const mappings = {
    hr:"hr",
    employee:"hr",
    inventory:"inventory",
    stock:"inventory",
    finance:"finance",
    invoice:"finance",
    sales:"crm",
    customer:"crm",
    crm:"crm",
    security:"security",
    devops:"devops",
    deployment:"devops",
    monitoring:"monitoring",
    incident:"incidents",
    backup:"backup",
    report:"reports",
    user:"users"
  };

  for(const key in mappings){

    if(key.includes(q) || q.includes(key)){

      showPage(mappings[key]);

      showToast(
        "Opened "+mappings[key]+" module",
        "info"
      );

      return;
    }
  }
}

/* ==========================================================
   CHARTS
========================================================== */

function setupCanvas(canvas){

  if(!canvas)return null;

  const rect =
    canvas.getBoundingClientRect();

  const dpr =
    window.devicePixelRatio || 1;

  canvas.width =
    rect.width*dpr;

  canvas.height =
    rect.height*dpr;

  const ctx =
    canvas.getContext("2d");

  ctx.scale(dpr,dpr);

  return {
    ctx,
    width:rect.width,
    height:rect.height
  };
}

function drawLineChart(id,data1,data2){

  const canvas=document.getElementById(id);

  if(!canvas)return;

  const setup=setupCanvas(canvas);

  if(!setup)return;

  const {
    ctx,
    width,
    height
  }=setup;

  const dark =
    document.body.classList.contains("dark");

  const text =
    dark ? "#94a3b8" : "#64748b";

  const grid =
    dark ? "#263247" : "#e5e7eb";

  ctx.clearRect(0,0,width,height);

  const pad=35;

  for(let i=0;i<5;i++){

    const y =
      pad + i*((height-pad*2)/4);

    ctx.beginPath();
    ctx.moveTo(pad,y);
    ctx.lineTo(width-pad,y);

    ctx.strokeStyle=grid;
    ctx.lineWidth=1;
    ctx.stroke();

    ctx.fillStyle=text;
    ctx.font="10px Arial";

    ctx.fillText(
      String(100-i*25),
      5,
      y+3
    );
  }

  function plot(data,offset){

    const max=Math.max(...data);
    const min=Math.min(...data);

    ctx.beginPath();

    data.forEach((value,i)=>{

      const x =
        pad +
        i*((width-pad*2)/(data.length-1));

      const y =
        height-pad -
        ((value-min)/(max-min || 1))*
        (height-pad*2);

      if(i===0)
        ctx.moveTo(x,y);
      else
        ctx.lineTo(x,y);
    });

    ctx.strokeStyle =
      offset ? "#8b5cf6" : "#6366f1";

    ctx.lineWidth=3;
    ctx.stroke();

    data.forEach((value,i)=>{

      const x =
        pad +
        i*((width-pad*2)/(data.length-1));

      const y =
        height-pad -
        ((value-min)/(max-min || 1))*
        (height-pad*2);

      ctx.beginPath();
      ctx.arc(x,y,3,0,Math.PI*2);

      ctx.fillStyle =
        offset ? "#8b5cf6" : "#6366f1";

      ctx.fill();
    });
  }

  plot(data1,0);
  plot(data2,1);

  ctx.fillStyle=text;
  ctx.font="11px Arial";

  [
    "O","N","D","J","F","M",
    "A","M","J","J","A","S"
  ].forEach((m,i)=>{

    const x =
      pad +
      i*((width-pad*2)/11);

    ctx.fillText(
      m,
      x-3,
      height-10
    );
  });

}

function drawCharts(){

  drawLineChart(
    "revenueChart",
    [48,54,50,63,67,72,76,81,79,88,94,100],
    [35,42,39,47,50,57,61,63,66,71,78,84]
  );

  drawLineChart(
    "salesChart",
    [45,49,55,51,60,67,64,72,76,81,87,92],
    [30,35,40,42,47,51,54,60,63,68,73,79]
  );
}

/* ==========================================================
   ACTIONS
========================================================== */

function refreshDashboard(){

  const kpi =
    document.getElementById("revenueKpi");

  const values=[
    "₹24.8M",
    "₹25.1M",
    "₹25.4M",
    "₹25.7M"
  ];

  let i=0;

  const interval=setInterval(()=>{

    kpi.textContent=values[i++];

    if(i>=values.length){
      clearInterval(interval);
    }

  },180);

  showToast(
    "Dashboard data refreshed",
    "success"
  );
}

function runDeployment(){

  showModal(
    "Production Deployment",
    `
      <p style="color:var(--muted)">
        Deployment pipeline simulation.
      </p>

      <div style="
        margin:18px 0;
        padding:15px;
        border-radius:10px;
        background:var(--card2);
      ">
        <div class="metric-row">
          <span>Build</span>
          <span class="status success">Passed</span>
        </div>

        <div class="metric-row">
          <span>Security Scan</span>
          <span class="status success">Passed</span>
        </div>

        <div class="metric-row">
          <span>Tests</span>
          <span class="status success">Passed</span>
        </div>

        <div class="metric-row">
          <span>Deployment</span>
          <span class="status warning">Pending</span>
        </div>
      </div>

      <button class="btn primary"
        onclick="completeDeployment()">
        Approve Deployment
      </button>
    `
  );
}

function completeDeployment(){

  closeModal();

  showToast(
    "Deployment completed successfully",
    "success"
  );
}

function createIncident(){

  showModal(
    "Create Incident",
    `
      <div class="form-group">
        <label>Incident Title</label>
        <input id="incidentTitle"
          placeholder="Enter incident">
      </div>

      <div class="form-group">
        <label>Severity</label>
        <select id="incidentSeverity">
          <option>Critical</option>
          <option>High</option>
          <option>Medium</option>
          <option>Low</option>
        </select>
      </div>

      <button class="btn danger"
        onclick="saveIncident()">
        Create Incident
      </button>
    `
  );
}

function saveIncident(){

  const title =
    document.getElementById("incidentTitle").value.trim();

  const severity =
    document.getElementById("incidentSeverity").value;

  if(!title){
    showToast("Enter incident title","error");
    return;
  }

  closeModal();

  showToast(
    severity+" incident created: "+title,
    "success"
  );
}

/* ==========================================================
   REPORTS / EXPORT
========================================================== */

function generateReport(){

  const content = `
EnterprisePro Executive Report
==============================

Revenue: ₹24.8M
Net Profit: ₹6.4M
Customers: 12,482
Orders: 8,921
Employees: 1,284
Platform Uptime: 99.96%
Security Score: 89/100
Enterprise Health: 92%

Generated: ${new Date().toLocaleString()}
`;

  downloadFile(
    "enterprise-executive-report.txt",
    content,
    "text/plain"
  );

  showToast(
    "Executive report downloaded",
    "success"
  );
}

function exportData(type){

  let rows=[];

  if(type==="employees"){

    rows=[
      ["Name","Department","Role","Status","Performance"],
      ...employees.map(e=>[
        e.name,
        e.department,
        e.role,
        e.status,
        e.performance
      ])
    ];

  }else{

    rows=[
      ["Metric","Value"],
      ["Revenue","₹24.8M"],
      ["Profit","₹6.4M"],
      ["Customers","12,482"],
      ["Orders","8,921"],
      ["Employees","1,284"],
      ["Inventory Value","₹8.7M"],
      ["Security Score","89/100"],
      ["Uptime","99.96%"]
    ];

  }

  const csv =
    rows.map(row =>
      row.map(value =>
        `"${String(value).replace(/"/g,'""')}"`
      ).join(",")
    ).join("\n");

  downloadFile(
    "enterprise-"+type+"-report.csv",
    csv,
    "text/csv"
  );

  showToast(
    "Report downloaded",
    "success"
  );
}

function downloadFile(filename,content,type){

  const blob =
    new Blob([content],{type});

  const url =
    URL.createObjectURL(blob);

  const a =
    document.createElement("a");

  a.href=url;
  a.download=filename;

  document.body.appendChild(a);

  a.click();

  a.remove();

  URL.revokeObjectURL(url);
}

/* ==========================================================
   NOTIFICATIONS
========================================================== */

function showNotifications(){

  showModal(
    "Notifications",
    `
      <div class="activity">

        <div class="activity-item">
          <div class="activity-dot">🚨</div>
          <div>
            <strong>Critical incident</strong>
            <p>API latency requires investigation.</p>
          </div>
        </div>

        <div class="activity-item">
          <div class="activity-dot">📦</div>
          <div>
            <strong>Low inventory</strong>
            <p>7 products below threshold.</p>
          </div>
        </div>

        <div class="activity-item">
          <div class="activity-dot">💰</div>
          <div>
            <strong>Invoice overdue</strong>
            <p>4 invoices require follow-up.</p>
          </div>
        </div>

        <div class="activity-item">
          <div class="activity-dot">🚀</div>
          <div>
            <strong>Deployment completed</strong>
            <p>Production deployment successful.</p>
          </div>
        </div>

      </div>
    `
  );
}

/* ==========================================================
   MODAL
========================================================== */

function showModal(title,content){

  const root =
    document.getElementById("modalRoot");

  root.innerHTML=`
    <div class="modal-overlay"
      onclick="if(event.target===this)closeModal()">

      <div class="modal">

        <div class="modal-header">
          <h2>${escapeHTML(title)}</h2>

          <button class="close"
            onclick="closeModal()">×</button>
        </div>

        ${content}

      </div>

    </div>
  `;
}

function closeModal(){

  document.getElementById("modalRoot").innerHTML="";
}

/* ==========================================================
   TOAST
========================================================== */

function showToast(message,type="info"){

  const container =
    document.getElementById("toastContainer");

  const toast =
    document.createElement("div");

  toast.className="toast "+type;

  toast.textContent=message;

  container.appendChild(toast);

  setTimeout(()=>{

    toast.style.opacity="0";
    toast.style.transform="translateX(30px)";

    setTimeout(
      ()=>toast.remove(),
      300
    );

  },3500);
}

/* ==========================================================
   RESET
========================================================== */

function resetDemoData(){

  if(!confirm(
    "Reset all demo employee data?"
  ))return;

  employees =
    [...defaultEmployees];

  localStorage.setItem(
    "ep_employees",
    JSON.stringify(employees)
  );

  renderEmployees();

  showToast(
    "Demo data reset",
    "success"
  );
}

/* ==========================================================
   SECURITY / UTILITY
========================================================== */

function escapeHTML(value){

  return String(value)
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;")
    .replace(/'/g,"&#039;");
}

/* ==========================================================
   AUTO REFRESH SIMULATION
========================================================== */

setInterval(()=>{

  if(
    !document
      .getElementById("app")
      ?.classList
      .contains("hidden")
  ){

    const indicator =
      document.querySelector(
        ".top-actions .icon-btn"
      );

    if(indicator){

      indicator.style.transform="scale(1.08)";

      setTimeout(()=>{
        indicator.style.transform="";
      },200);

    }

  }

},15000);

/* ==========================================================
   KEYBOARD SHORTCUTS
========================================================== */

document.addEventListener("keydown",e=>{

  if(e.key==="Escape"){
    closeModal();
  }

  if(e.ctrlKey && e.key.toLowerCase()==="k"){

    e.preventDefault();

    document
      .getElementById("globalSearch")
      ?.focus();
  }

});
</script>

</body>
</html>
