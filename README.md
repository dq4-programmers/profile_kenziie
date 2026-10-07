[absensi futsal.html.html](https://github.com/user-attachments/files/33161393/absensi.futsal.html.html)
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Futsal Manager - Absensi & Tim</title>
<style>
/* FUTSAL PRO ENHANCEMENTS */
.logo3d-wrap{width:120px;height:120px;margin:0 auto 18px;perspective:700px}
.logo3d{width:100%;height:100%;position:relative;transform-style:preserve-3d;animation:logoSpin 6s linear infinite}
.logoFace{position:absolute;inset:8px;border-radius:28px;display:grid;place-items:center;background:linear-gradient(145deg,#39ef7a,#08783a);border:2px solid #9affbd;box-shadow:0 15px 35px #22c55e55,inset 0 0 20px #ffffff22;backface-visibility:hidden}
.logoFace.back{transform:rotateY(180deg);background:linear-gradient(145deg,#087c43,#063b25)}
.logoFace svg{width:75px;filter:drop-shadow(0 5px 5px #063b20)}
@keyframes logoSpin{from{transform:rotateY(0) rotateX(4deg)}to{transform:rotateY(360deg) rotateX(4deg)}}
#appLoading{position:fixed;inset:0;background:#050b14f5;z-index:999;display:none;place-items:center;text-align:center}
.appSpinner{width:62px;height:62px;border:5px solid #263b55;border-top-color:#22c55e;border-radius:50%;animation:appSpin 1s linear infinite;margin:auto auto 16px}
@keyframes appSpin{to{transform:rotate(360deg)}}
.page{animation:menuIn .35s ease}
@keyframes menuIn{from{opacity:0;transform:translateY(9px)}to{opacity:1;transform:none}}

:root{
  --bg:#0b1220; --panel:#111b2e; --panel2:#16233a; --text:#eef4ff;
  --muted:#91a2bd; --accent:#22c55e; --accent2:#16a34a; --danger:#ef4444;
  --warning:#f59e0b; --line:#243451; --white:#fff;
}
*{box-sizing:border-box}
body{margin:0;font-family:Inter,Segoe UI,Arial,sans-serif;background:linear-gradient(135deg,#07101d,#0d1728 55%,#0a1b16);color:var(--text)}
button,input,select,textarea{font:inherit}
.app{min-height:100vh}
.login{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px;background:radial-gradient(circle at 20% 10%,#153d2b 0,transparent 30%),radial-gradient(circle at 80% 90%,#172d55 0,transparent 30%),#07101d}
.login-card{width:min(430px,100%);background:rgba(17,27,46,.94);border:1px solid var(--line);border-radius:24px;padding:32px;box-shadow:0 25px 70px #0008}
.logo{width:82px;height:82px;border-radius:22px;display:grid;place-items:center;background:linear-gradient(145deg,#22c55e,#15803d);margin:0 auto 18px;box-shadow:0 10px 30px #22c55e44}
.logo svg{width:56px;height:56px}
.login h1{text-align:center;margin:0 0 6px;font-size:28px}
.login p{text-align:center;color:var(--muted);margin:0 0 24px}
.form-group{margin-bottom:15px}
label{display:block;color:#cbd5e1;font-size:13px;margin-bottom:7px}
input,select,textarea{width:100%;background:#0b1527;border:1px solid var(--line);color:var(--text);padding:12px 13px;border-radius:11px;outline:none}
input:focus,select:focus,textarea:focus{border-color:var(--accent)}
.btn{border:0;border-radius:11px;padding:11px 15px;cursor:pointer;color:#fff;background:#22304a}
.btn-primary{background:linear-gradient(135deg,var(--accent),var(--accent2));font-weight:700;width:100%}
.btn-danger{background:#7f1d1d}
.btn-warning{background:#854d0e}
.btn-small{padding:7px 10px;font-size:12px}
.error{color:#fca5a5;font-size:13px;margin-top:10px;display:none;text-align:center}
.dashboard{display:none;min-height:100vh}
.sidebar{position:fixed;left:0;top:0;bottom:0;width:250px;background:rgba(11,18,32,.97);border-right:1px solid var(--line);padding:22px 15px;z-index:5}
.brand{display:flex;align-items:center;gap:11px;padding:4px 8px 24px}
.brand .mini-logo{width:42px;height:42px;border-radius:12px;background:linear-gradient(145deg,#22c55e,#15803d);display:grid;place-items:center}
.brand strong{font-size:17px}.brand span{font-size:11px;color:var(--muted);display:block;margin-top:2px}
.nav{display:grid;gap:7px}
.nav button{border:0;background:transparent;color:#aebdd2;text-align:left;padding:12px 13px;border-radius:11px;cursor:pointer;font-size:14px}
.nav button:hover,.nav button.active{background:#17253c;color:#fff}
.nav button.active{box-shadow:inset 3px 0 var(--accent)}
.main{margin-left:250px;padding:22px;max-width:1600px}
.topbar{display:flex;justify-content:space-between;align-items:center;margin-bottom:22px;gap:15px}
.topbar h2{margin:0;font-size:25px}.topbar small{color:var(--muted)}
.userbox{display:flex;align-items:center;gap:10px;color:#cbd5e1}
.avatar{width:38px;height:38px;border-radius:50%;background:#1d4ed8;display:grid;place-items:center;font-weight:700}
.page{display:none}.page.active{display:block}
.cards{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:18px}
.card{background:rgba(17,27,46,.88);border:1px solid var(--line);border-radius:16px;padding:18px}
.stat-label{font-size:12px;color:var(--muted)}.stat-value{font-size:28px;font-weight:800;margin-top:7px}
.grid2{display:grid;grid-template-columns:1.25fr .75fr;gap:16px}
.panel{background:rgba(17,27,46,.88);border:1px solid var(--line);border-radius:16px;padding:18px;margin-bottom:16px}
.panel h3{margin:0 0 14px;font-size:17px}
.toolbar{display:flex;gap:9px;flex-wrap:wrap;margin-bottom:14px}.toolbar input{max-width:280px}
table{width:100%;border-collapse:collapse}th,td{padding:11px 9px;border-bottom:1px solid var(--line);text-align:left;font-size:13px}th{color:#9fb0c8;font-weight:600}td{color:#e5edf9}
.badge{display:inline-block;padding:4px 8px;border-radius:999px;font-size:11px;font-weight:700}.present{background:#064e3b;color:#86efac}.absent{background:#4c0519;color:#fda4af}.permit{background:#78350f;color:#fde68a}.active-b{background:#052e16;color:#86efac}.out{background:#3f3f46;color:#d4d4d8}
.list{display:grid;gap:10px}.news{padding:12px;background:#0d1728;border:1px solid var(--line);border-radius:12px}.news strong{display:block;margin-bottom:4px}.news small{color:var(--muted)}
.quick{display:grid;grid-template-columns:repeat(3,1fr);gap:10px}.quick .btn{padding:13px}
.player-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.player{background:#0d1728;border:1px solid var(--line);border-radius:14px;padding:15px}
.player-head{display:flex;justify-content:space-between;align-items:center}.number{font-size:24px;font-weight:900;color:#4ade80}.player p{margin:5px 0;color:var(--muted);font-size:12px}
.modal{position:fixed;inset:0;background:#0009;display:none;align-items:center;justify-content:center;padding:20px;z-index:20}.modal.open{display:flex}.modal-card{width:min(650px,100%);background:#111b2e;border:1px solid var(--line);border-radius:18px;padding:20px;max-height:90vh;overflow:auto}.modal-actions{display:flex;justify-content:flex-end;gap:9px;margin-top:15px}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}.full{grid-column:1/-1}
.empty{text-align:center;color:var(--muted);padding:25px}
.footer-note{color:#6f819d;font-size:11px;margin-top:20px;text-align:center}
@media(max-width:1000px){.cards{grid-template-columns:repeat(2,1fr)}.grid2{grid-template-columns:1fr}.player-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:720px){.sidebar{position:static;width:auto;border-right:0;border-bottom:1px solid var(--line)}.main{margin-left:0;padding:14px}.nav{grid-template-columns:repeat(3,1fr)}.nav button{font-size:12px}.brand{padding-bottom:15px}.topbar{align-items:flex-start}.cards{grid-template-columns:1fr 1fr}.player-grid{grid-template-columns:1fr}.form-grid{grid-template-columns:1fr}.full{grid-column:auto}}
</style>
</head>
<body>
<div id="loginScreen" class="login">
  <div class="login-card">
    <div class="logo3d-wrap"><div class="logo3d">
<div class="logoFace"><svg viewBox="0 0 100 100" fill="none"><circle cx="50" cy="50" r="42" stroke="white" stroke-width="6"/><path d="M50 24l15 12-6 18H41l-6-18 15-12Z" fill="white"/><path d="M41 54L27 65l5 17M59 54l14 11-5 17M50 54v24" stroke="white" stroke-width="6" stroke-linecap="round"/></svg></div>
<div class="logoFace back"><svg viewBox="0 0 100 100" fill="none"><circle cx="50" cy="50" r="42" stroke="white" stroke-width="6"/><path d="M50 24l15 12-6 18H41l-6-18 15-12Z" fill="white"/></svg></div>
</div></div>
      <svg viewBox="0 0 100 100" fill="none" aria-label="Logo futsal">
        <circle cx="50" cy="50" r="43" stroke="white" stroke-width="6"/>
        <path d="M50 24l15 11-6 18H41l-6-18 15-11Z" fill="white"/>
        <path d="M41 53L27 64l5 17M59 53l14 11-5 17M50 53v23" stroke="white" stroke-width="6" stroke-linecap="round"/>
      </svg>
    </div>
    <h1>FUTSAL MANAGER</h1>
    <p>Sistem Absensi & Manajemen Tim</p>
    <div class="form-group"><label>Username</label><input id="username" placeholder="admin" value="admin"></div>
    <div class="form-group"><label>Password</label><input id="password" type="password" placeholder="Masukkan password"></div>
    <button class="btn btn-primary" onclick="login()">Masuk ke Dashboard</button>
    <div id="loginError" class="error">Username atau password salah.</div>
    <div class="footer-note">Demo HTML lokal • Password: admin123</div>
  </div>
</div>

<div id="appLoading"><div><div class="appSpinner"></div><h3 id="appLoadingTitle">Memuat menu...</h3><p style="color:#91a2bd">Menyiapkan dashboard futsal</p></div></div>\n<div id="dashboard" class="dashboard">
  <aside class="sidebar">
    <div class="brand">
      <div class="mini-logo">
        <svg viewBox="0 0 100 100" width="29" fill="none"><circle cx="50" cy="50" r="43" stroke="white" stroke-width="7"/><path d="M50 25l15 11-6 17H41l-6-17 15-11Z" fill="white"/><path d="M41 53L28 64l5 16M59 53l13 11-5 16M50 53v23" stroke="white" stroke-width="6"/></svg>
      </div>
      <div><strong>Futsal Manager</strong><span>Team Management</span></div>
    </div>
    <div class="nav">
      <button class="active" onclick="showPage('home',this)">🏠 Home</button>
      <button onclick="showPage('jadwal',this)">📅 Jadwal</button>
      <button onclick="showPage('tim',this)">👥 Tim</button>
      <button onclick="showPage('statistik',this)">📊 Statistik</button>
      <button onclick="showPage('berita',this)">📰 Berita</button>
      <button onclick="showPage('izin',this)">📝 Perizinan</button>
      <button onclick="showPage('rekrut',this)">🔎 Rekrutmen</button>
      <button onclick="showPage('out',this)">↗️ Out Pemain</button>
      <button onclick="logout()">🚪 Keluar</button>
    </div>
  </aside>

  <main class="main">
    <div class="topbar">
      <div><h2 id="pageTitle">Home</h2><small id="today"></small></div>
      <div class="userbox"><div class="avatar">A</div><div><b>Admin</b><br><small>Coach / Manager</small></div></div>
    </div>

    <section id="home" class="page active">
      <div class="cards">
        <div class="card"><div class="stat-label">Total Pemain Aktif</div><div class="stat-value" id="totalPlayers">12</div></div>
        <div class="card"><div class="stat-label">Hadir Hari Ini</div><div class="stat-value" id="presentCount">9</div></div>
        <div class="card"><div class="stat-label">Izin</div><div class="stat-value" id="permitCount">2</div></div>
        <div class="card"><div class="stat-label">Tidak Hadir</div><div class="stat-value" id="absentCount">1</div></div>
      </div>
      <div class="grid2">
        <div class="panel">
          <h3>Absensi Latihan Hari Ini</h3>
          <div class="toolbar"><input id="attendanceSearch" placeholder="Cari pemain..." oninput="renderAttendance()"><button class="btn btn-primary" style="width:auto" onclick="openAttendance()">+ Catat Absensi</button></div>
          <div style="overflow:auto"><table><thead><tr><th>Pemain</th><th>No.</th><th>Status</th><th>Waktu</th><th>Aksi</th></tr></thead><tbody id="attendanceBody"></tbody></table></div>
        </div>
        <div>
          <div class="panel"><h3>Pelatih</h3><div class="news"><strong>Coach Andi Pratama</strong><small>Head Coach • Futsal Manager</small></div></div>
          <div class="panel"><h3>Menu Cepat</h3><div class="quick"><button class="btn" onclick="openAttendance()">Absensi</button><button class="btn" onclick="openPermit()">Izin</button><button class="btn" onclick="showPage('rekrut')">Rekrut</button></div></div>
        </div>
      </div>
    </section>

    <section id="jadwal" class="page">
      <div class="panel"><h3>Jadwal Tim</h3><div class="toolbar"><button class="btn btn-primary" style="width:auto" onclick="openSchedule()">+ Tambah Jadwal</button></div>
      <table><thead><tr><th>Tanggal</th><th>Waktu</th><th>Kegiatan</th><th>Lokasi</th><th>Keterangan</th></tr></thead><tbody id="scheduleBody"></tbody></table></div>
    </section>

    <section id="tim" class="page">
      <div class="panel"><h3>Daftar Tim & Pemain</h3><div class="toolbar"><input placeholder="Cari pemain..." oninput="renderPlayers(this.value)"><button class="btn btn-primary" style="width:auto" onclick="openPlayer()">+ Tambah Pemain</button></div><div id="playerGrid" class="player-grid"></div></div>
    </section>

    <section id="statistik" class="page">
      <div class="cards"><div class="card"><div class="stat-label">Kehadiran</div><div class="stat-value">92%</div></div><div class="card"><div class="stat-label">Latihan Bulan Ini</div><div class="stat-value">16</div></div><div class="card"><div class="stat-label">Gol Tim</div><div class="stat-value">38</div></div><div class="card"><div class="stat-label">Pemain Baru</div><div class="stat-value" id="newPlayers">3</div></div></div>
      <div class="panel"><h3>Statistik Kehadiran</h3><div id="statsBars"></div></div>
    </section>

    <section id="berita" class="page">
      <div class="panel"><h3>Berita Tim</h3><div class="toolbar"><button class="btn btn-primary" style="width:auto" onclick="openNews()">+ Tambah Berita</button></div><div id="newsList" class="list"></div></div>
    </section>

    <section id="izin" class="page">
      <div class="panel"><h3>Perizinan Tidak Mengikuti Pelatihan</h3><div class="toolbar"><button class="btn btn-primary" style="width:auto" onclick="openPermit()">+ Ajukan Izin</button></div>
      <table><thead><tr><th>Pemain</th><th>Tanggal</th><th>Jam</th><th>Alasan</th><th>Status</th><th>Aksi</th></tr></thead><tbody id="permitBody"></tbody></table></div>
    </section>

    <section id="rekrut" class="page">
      <div class="panel"><h3>Rekrutmen Pemain</h3><div class="toolbar"><button class="btn btn-primary" style="width:auto" onclick="openRecruit()">+ Kandidat Baru</button></div>
      <table><thead><tr><th>Nama</th><th>Posisi</th><th>Umur</th><th>Negara</th><th>Status</th><th>Aksi</th></tr></thead><tbody id="recruitBody"></tbody></table></div>
    </section>

    <section id="out" class="page">
      <div class="panel"><h3>Out / Riwayat Pemain</h3><p style="color:var(--muted);font-size:13px">Pemain yang keluar dari skuad aktif dapat dicatat di sini.</p>
      <table><thead><tr><th>Nama</th><th>No.</th><th>Posisi</th><th>Tanggal Keluar</th><th>Alasan</th></tr></thead><tbody id="outBody"></tbody></table></div>
    </section>
  </main>
</div>

<div id="modal" class="modal"><div class="modal-card"><h3 id="modalTitle"></h3><div id="modalContent"></div><div class="modal-actions"><button class="btn" onclick="closeModal()">Batal</button><button class="btn btn-primary" style="width:auto" id="modalSave">Simpan</button></div></div></div>

<script>
const players=[
 {id:1,name:"Raka Pratama",num:7,age:16,country:"Indonesia",pos:"Pivot",status:"Aktif"},
 {id:2,name:"Fajar Ramadhan",num:10,age:17,country:"Indonesia",pos:"Flank",status:"Aktif"},
 {id:3,name:"Dimas Saputra",num:1,age:16,country:"Indonesia",pos:"Kiper",status:"Aktif"},
 {id:4,name:"Rizky Maulana",num:8,age:17,country:"Indonesia",pos:"Flank",status:"Aktif"},
 {id:5,name:"Ardiansyah Putra",num:4,age:16,country:"Indonesia",pos:"Anchor",status:"Aktif"},
 {id:6,name:"Bagas Akbar",num:11,age:17,country:"Indonesia",pos:"Pivot",status:"Aktif"},
 {id:7,name:"Naufal Hakim",num:6,age:16,country:"Indonesia",pos:"Anchor",status:"Aktif"},
 {id:8,name:"Ilham Fauzi",num:9,age:18,country:"Indonesia",pos:"Pivot",status:"Aktif"},
 {id:9,name:"Rafi Alamsyah",num:3,age:17,country:"Indonesia",pos:"Flank",status:"Aktif"},
 {id:10,name:"Yoga Firmansyah",num:12,age:16,country:"Indonesia",pos:"Kiper",status:"Aktif"},
 {id:11,name:"Bima Arya",num:5,age:17,country:"Indonesia",pos:"Anchor",status:"Aktif"},
 {id:12,name:"Kevin Prakoso",num:14,age:18,country:"Indonesia",pos:"Flank",status:"Aktif"}
];
let attendance=players.map((p,i)=>({id:p.id,status:i<9?"Hadir":i<11?"Izin":"Tidak Hadir",time:i<9?"18:"+String(2+i).padStart(2,"0"):"-"}));
let permits=[
 {id:1,player:"Bima Arya",date:"2026-10-03",time:"17:00-19:00",reason:"Keperluan keluarga",status:"Disetujui"},
 {id:2,player:"Kevin Prakoso",date:"2026-10-05",time:"18:00-20:00",reason:"Kegiatan sekolah",status:"Menunggu"}
];
let schedules=[
 ["2026-10-03","17:00 - 19:00","Latihan Rutin","GOR Futsal Utama","Fisik & passing"],
 ["2026-10-05","18:00 - 20:00","Latihan Taktik","GOR Futsal Utama","Strategi pertandingan"],
 ["2026-10-08","19:00 - 21:00","Friendly Match","Arena Sport","Uji coba"]
];
let recruits=[
 {name:"Adit Nugraha",pos:"Flank",age:16,country:"Indonesia",status:"Seleksi"},
 {name:"Rendy Wijaya",pos:"Kiper",age:17,country:"Indonesia",status:"Trial"},
 {name:"Fikri Hasan",pos:"Pivot",age:16,country:"Indonesia",status:"Seleksi"}
];
let outs=[]; let news=[
 {title:"Latihan taktik pekan ini",text:"Fokus pada build-up, transisi, dan finishing.",date:"02 Okt 2026"},
 {title:"Seleksi pemain baru dibuka",text:"Pendaftaran trial tersedia melalui menu Rekrutmen.",date:"01 Okt 2026"}
];

function login(){
const u=document.getElementById("username")?.value.trim();
const p=document.getElementById("password")?.value;
if(u==="admin"&&p==="admin123"){
document.getElementById("loginError").style.display="none";
const l=document.getElementById("loading");
if(l){l.style.display="grid";const t=document.getElementById("loadTitle");const x=document.getElementById("loadText");
if(t)t.textContent="Memverifikasi login...";if(x)x.textContent="Menyiapkan Futsal Manager";
setTimeout(()=>{if(t)t.textContent="Memuat dashboard...";if(x)x.textContent="Mengambil data tim dan jadwal"},650);
setTimeout(()=>{l.style.display="none";document.getElementById("loginScreen").style.display="none";document.getElementById("dashboard").style.display="block";if(typeof init==="function")init()},1300);
} else {document.getElementById("loginScreen").style.display="none";document.getElementById("dashboard").style.display="block";if(typeof init==="function")init();}
}else{document.getElementById("loginError").style.display="block";}
}
document.getElementById("password").addEventListener("keydown",e=>{if(e.key==="Enter")login()});
function logout(){document.getElementById("dashboard").style.display="none";document.getElementById("loginScreen").style.display="flex";document.getElementById("password").value=""}
function init(){document.getElementById("today").textContent=new Date().toLocaleDateString("id-ID",{weekday:"long",year:"numeric",month:"long",day:"numeric"});renderAll()}
function showPage(id,btn){
const ov=document.getElementById("appLoading");
if(ov){ov.style.display="grid";const tt=document.getElementById("appLoadingTitle");if(tt)tt.textContent="Membuka "+(id.charAt(0).toUpperCase()+id.slice(1))+"...";}
setTimeout(()=>{
document.querySelectorAll(".page").forEach(x=>x.classList.remove("active"));
document.getElementById(id).classList.add("active");
document.querySelectorAll(".nav button").forEach(x=>x.classList.remove("active"));
if(btn)btn.classList.add("active");
const titleMap={home:"Home",jadwal:"Jadwal",tim:"Tim",statistik:"Statistik",berita:"Berita",izin:"Perizinan",rekrut:"Rekrutmen",out:"Out Pemain"};
const pt=document.getElementById("pageTitle");if(pt)pt.textContent=titleMap[id]||id;
if(ov)ov.style.display="none";
},380);
}
function renderAll(){renderAttendance();renderPlayers();renderSchedule();renderPermits();renderRecruit();renderOut();renderNews();renderStats();updateCards()}
function updateCards(){document.getElementById("totalPlayers").textContent=players.filter(p=>p.status==="Aktif").length;document.getElementById("presentCount").textContent=attendance.filter(a=>a.status==="Hadir").length;document.getElementById("permitCount").textContent=attendance.filter(a=>a.status==="Izin").length;document.getElementById("absentCount").textContent=attendance.filter(a=>a.status==="Tidak Hadir").length}
function renderAttendance(){let q=(document.getElementById("attendanceSearch")?.value||"").toLowerCase();let rows=attendance.map(a=>{let p=players.find(x=>x.id===a.id);return p&&p.name.toLowerCase().includes(q)?`<tr><td>${p.name}</td><td>#${p.num}</td><td><span class="badge ${a.status==="Hadir"?"present":a.status==="Izin"?"permit":"absent"}">${a.status}</span></td><td>${a.time}</td><td><button class="btn btn-small" onclick="cycleAttendance(${p.id})">Ubah</button></td></tr>`:""}).join("");document.getElementById("attendanceBody").innerHTML=rows||`<tr><td colspan="5" class="empty">Tidak ada data.</td></tr>`}
function cycleAttendance(id){let a=attendance.find(x=>x.id===id);a.status=a.status==="Hadir"?"Izin":a.status==="Izin"?"Tidak Hadir":"Hadir";a.time=a.status==="Hadir"?new Date().toLocaleTimeString("id-ID",{hour:"2-digit",minute:"2-digit"}):"-";renderAttendance();updateCards()}
function renderPlayers(q=""){q=q.toLowerCase();document.getElementById("playerGrid").innerHTML=players.filter(p=>p.name.toLowerCase().includes(q)).map(p=>`<div class="player"><div class="player-head"><strong>${p.name}</strong><span class="number">#${p.num}</span></div><p>⚽ ${p.pos}</p><p>🎂 ${p.age} tahun</p><p>🌍 ${p.country}</p><span class="badge active-b">${p.status}</span></div>`).join("")}
function renderSchedule(){document.getElementById("scheduleBody").innerHTML=schedules.map(s=>`<tr><td>${s[0]}</td><td>${s[1]}</td><td>${s[2]}</td><td>${s[3]}</td><td>${s[4]}</td></tr>`).join("")}
function renderPermits(){document.getElementById("permitBody").innerHTML=permits.map(p=>`<tr><td>${p.player}</td><td>${p.date}</td><td>${p.time}</td><td>${p.reason}</td><td><span class="badge ${p.status==="Disetujui"?"present":"permit"}">${p.status}</span></td><td><button class="btn btn-small" onclick="approvePermit(${p.id})">Setujui</button></td></tr>`).join("")}
function approvePermit(id){let p=permits.find(x=>x.id===id);p.status="Disetujui";renderPermits()}
function renderRecruit(){document.getElementById("recruitBody").innerHTML=recruits.map((r,i)=>`<tr><td>${r.name}</td><td>${r.pos}</td><td>${r.age}</td><td>${r.country}</td><td><span class="badge permit">${r.status}</span></td><td><button class="btn btn-small" onclick="acceptRecruit(${i})">Terima</button></td></tr>`).join("")}
function acceptRecruit(i){let r=recruits[i];players.push({id:Date.now(),name:r.name,num:players.length+1,age:r.age,country:r.country,pos:r.pos,status:"Aktif"});recruits.splice(i,1);renderAll();alert("Pemain berhasil ditambahkan ke tim aktif.")}
function renderOut(){document.getElementById("outBody").innerHTML=outs.length?outs.map(x=>`<tr><td>${x.name}</td><td>#${x.num}</td><td>${x.pos}</td><td>${x.date}</td><td>${x.reason}</td></tr>`).join(""):`<tr><td colspan="5" class="empty">Belum ada pemain yang keluar.</td></tr>`}
function renderNews(){document.getElementById("newsList").innerHTML=news.map(n=>`<div class="news"><strong>${n.title}</strong><div>${n.text}</div><small>${n.date}</small></div>`).join("")}
function renderStats(){let data=[["Hadir",92],["Izin",5],["Tidak Hadir",3]];document.getElementById("statsBars").innerHTML=data.map(d=>`<div style="margin:14px 0"><div style="display:flex;justify-content:space-between;font-size:13px;margin-bottom:6px"><span>${d[0]}</span><b>${d[1]}%</b></div><div style="height:10px;background:#22304a;border-radius:99px;overflow:hidden"><div style="width:${d[1]}%;height:100%;background:linear-gradient(90deg,#22c55e,#16a34a);border-radius:99px"></div></div></div>`).join("")}
function openModal(title,content,save){document.getElementById("modalTitle").textContent=title;document.getElementById("modalContent").innerHTML=content;document.getElementById("modalSave").onclick=save;document.getElementById("modal").classList.add("open")}
function closeModal(){document.getElementById("modal").classList.remove("open")}
function openAttendance(){openModal("Catat Absensi",`<div class="form-grid"><div><label>Pemain</label><select id="fPlayer">${players.filter(p=>p.status==="Aktif").map(p=>`<option value="${p.id}">${p.name} (#${p.num})</option>`).join("")}</select></div><div><label>Status</label><select id="fStatus"><option>Hadir</option><option>Izin</option><option>Tidak Hadir</option></select></div></div>`,()=>{let id=+document.getElementById("fPlayer").value,s= document.getElementById("fStatus").value,a=attendance.find(x=>x.id===id);if(a){a.status=s;a.time=s==="Hadir"?new Date().toLocaleTimeString("id-ID",{hour:"2-digit",minute:"2-digit"}):"-"}else attendance.push({id,status:s,time:"-"});renderAll();closeModal()})}
function openPermit(){openModal("Ajukan Perizinan",`<div class="form-grid"><div><label>Pemain</label><select id="pPlayer">${players.map(p=>`<option>${p.name}</option>`).join("")}</select></div><div><label>Tanggal</label><input id="pDate" type="date"></div><div><label>Waktu</label><input id="pTime" placeholder="17:00-19:00"></div><div><label>Status</label><select id="pStatus"><option>Menunggu</option><option>Disetujui</option></select></div><div class="full"><label>Alasan</label><textarea id="pReason" rows="3" placeholder="Alasan tidak mengikuti latihan"></textarea></div></div>`,()=>{permits.push({id:Date.now(),player:document.getElementById("pPlayer").value,date:document.getElementById("pDate").value,time:document.getElementById("pTime").value,reason:document.getElementById("pReason").value,status:document.getElementById("pStatus").value});renderPermits();closeModal()})}
function openSchedule(){openModal("Tambah Jadwal",`<div class="form-grid"><div><label>Tanggal</label><input id="sDate" type="date"></div><div><label>Waktu</label><input id="sTime" placeholder="18:00 - 20:00"></div><div><label>Kegiatan</label><input id="sAct" placeholder="Latihan"></div><div><label>Lokasi</label><input id="sLoc" placeholder="GOR"></div><div class="full"><label>Keterangan</label><input id="sNote"></div></div>`,()=>{schedules.push([sDate.value,sTime.value,sAct.value,sLoc.value,sNote.value]);renderSchedule();closeModal()})}
function openPlayer(){openModal("Tambah Pemain",`<div class="form-grid"><div><label>Nama</label><input id="nName"></div><div><label>No. Punggung</label><input id="nNum" type="number"></div><div><label>Umur</label><input id="nAge" type="number"></div><div><label>Negara</label><input id="nCountry" value="Indonesia"></div><div class="full"><label>Posisi</label><select id="nPos"><option>Kiper</option><option>Anchor</option><option>Flank</option><option>Pivot</option></select></div></div>`,()=>{players.push({id:Date.now(),name:nName.value,num:+nNum.value,age:+nAge.value,country:nCountry.value,pos:nPos.value,status:"Aktif"});attendance.push({id:players.at(-1).id,status:"Tidak Hadir",time:"-"});renderAll();closeModal()})}
function openRecruit(){openModal("Kandidat Rekrutmen",`<div class="form-grid"><div><label>Nama</label><input id="rName"></div><div><label>Posisi</label><select id="rPos"><option>Kiper</option><option>Anchor</option><option>Flank</option><option>Pivot</option></select></div><div><label>Umur</label><input id="rAge" type="number"></div><div><label>Negara</label><input id="rCountry" value="Indonesia"></div></div>`,()=>{recruits.push({name:rName.value,pos:rPos.value,age:+rAge.value,country:rCountry.value,status:"Seleksi"});renderRecruit();closeModal()})}
function openNews(){openModal("Tambah Berita",`<div class="form-grid"><div class="full"><label>Judul</label><input id="bTitle"></div><div class="full"><label>Isi Berita</label><textarea id="bText" rows="4"></textarea></div></div>`,()=>{news.unshift({title:bTitle.value,text:bText.value,date:new Date().toLocaleDateString("id-ID")});renderNews();closeModal()})}
</script>
</body>
</html>
