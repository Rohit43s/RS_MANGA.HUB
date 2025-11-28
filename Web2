<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>RS MANGA HUB — Final</title>

<!-- Fonts & icons -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<style>
  :root{
    --bg:#0f1113; --card:#141619; --muted:#9aa0a6; --accent:#ff6b6b; --accent-2:#24b7ff; --glass:rgba(255,255,255,0.04);
    --radius:12px; --text:#e9eef2; --maxw:1200px;
  }
  :root.light{
    --bg:#f6f7f9; --card:#ffffff; --muted:#48535a; --accent:#e04f63; --accent-2:#2b9cff; --glass:rgba(0,0,0,0.04); --text:#121212;
  }

  *{box-sizing:border-box;margin:0;padding:0}
  html,body{height:100%}
  body{
    font-family:"Poppins",system-ui,-apple-system,"Segoe UI",Roboto,Arial;
    background:linear-gradient(180deg,var(--bg),#070809);
    color:var(--text);
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    min-height:100vh;
    line-height:1.45;
  }
  a{ color:var(--accent); text-decoration:none }
  .wrap{ max-width:var(--maxw); margin:18px auto; padding:12px; }

  /* header */
  header.site-header{
    display:flex;align-items:center;gap:14px;padding:12px;border-radius:12px;
    background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
    border:1px solid rgba(255,255,255,0.03);
    position: sticky; top:12px; z-index:90;
  }
  .logo{ font-weight:700; font-size:18px; background:linear-gradient(90deg,var(--accent),var(--accent-2)); -webkit-background-clip:text; color:transparent }
  nav.main-nav{ display:flex; gap:10px; margin-left:8px; flex:1; }
  nav.main-nav button{ background:transparent; border:0; color:var(--muted); padding:8px 10px; border-radius:8px; cursor:pointer; font-weight:600 }
  nav.main-nav button.active{ color:var(--text); background: rgba(255,255,255,0.02) }

  .header-actions{ display:flex; gap:8px; align-items:center }
  .icon-btn{ background:transparent; border:0; color:var(--muted); cursor:pointer; padding:8px; border-radius:8px; font-size:16px }
  .btn{ background: linear-gradient(90deg,var(--accent),var(--accent-2)); border:0; padding:8px 12px; border-radius:10px; color:#fff; cursor:pointer; }
  .btn.ghost{ background:transparent; border:1px solid rgba(255,255,255,0.04); color:var(--muted) }
  .btn.small{ padding:6px 8px; font-size:13px }

  /* pages */
  .page{ display:none; padding:18px 0 }
  .page.active{ display:block }

  /* hero */
  .hero{ display:flex; gap:18px; align-items:center; margin:18px 0; padding:18px; border-radius:12px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); border:1px solid rgba(255,255,255,0.03) }
  .hero .left{ flex:1 }
  .hero .right img{ width:320px; height:220px; object-fit:cover; border-radius:10px }

  /* grid */
  .cards-grid{ display:grid; grid-template-columns: repeat(4, 1fr); gap:14px; margin-top:10px }
  .card{ background:var(--card); border-radius:10px; overflow:hidden; cursor:pointer; border:1px solid rgba(255,255,255,0.03); transition: transform .18s ease, box-shadow .18s ease; padding-bottom:6px }
  .card:hover{ transform:translateY(-6px); box-shadow: 0 12px 32px rgba(0,0,0,0.5) }
  .card img{ width:100%; height:200px; object-fit:cover; display:block }
  .card .meta{ padding:10px }
  .muted{ color:var(--muted); font-size:13px }

  /* manga detail */
  .manga-detail{ display:flex; gap:18px; align-items:flex-start; margin-top:12px }
  .manga-cover img{ width:280px; border-radius:10px }
  .chapters{ list-style:none; padding-left:0; margin-top:10px }
  .chapters li{ margin-bottom:8px }

  /* reader */
  #readerOverlay{ display:none; position:fixed; inset:0; background:rgba(0,0,0,0.95); z-index:9999; overflow:auto; padding:24px }
  .reader-wrap{ max-width:1100px; margin:0 auto; color:var(--text) }
  .reader-controls{ display:flex; justify-content:space-between; align-items:center; margin-bottom:12px }
  .reader-area{ padding:12px; border-radius:8px; background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01)); min-height:60vh }
  .reader-area.vertical img{ width:100%; margin-bottom:12px }
  .reader-area.page img{ width:100%; display:block; margin:0 auto; max-height:80vh }

  /* upload / admin */
  .upload-form{ display:grid; gap:10px; max-width:760px }
  .upload-form input, .upload-form textarea{ width:100%; padding:10px; border-radius:8px; background:transparent; border:1px solid rgba(255,255,255,0.04); color:var(--text) }

  .card-admin{ padding:12px; margin:12px 0; background:var(--card); border-radius:8px; border:1px solid rgba(255,255,255,0.03) }

  /* footer */
  footer.site-footer{ margin-top:30px; padding:20px; text-align:center; color:var(--muted) }

  /* responsive */
  @media (max-width:1100px){ .cards-grid{ grid-template-columns: repeat(3, 1fr); } .hero .right img{ width:260px; height:180px } .manga-cover img{ width:200px } }
  @media (max-width:820px){ nav.main-nav{ display:none } .cards-grid{ grid-template-columns: repeat(2, 1fr) } .manga-detail{ flex-direction:column } }
  @media (max-width:480px){ .cards-grid{ grid-template-columns: 1fr } .hero .right img{ width:100%; height:220px } .manga-cover img{ width:100% } }

  /* small helpers */
  .hidden{ display:none !important; }
  .top-right-badge { position:fixed; right:18px; top:18px; z-index:90; }
  textarea { min-height:100px; resize:vertical; }
  .chip{ padding:6px 8px; border-radius:8px; background:var(--card); cursor:pointer; border:1px solid rgba(255,255,255,0.03); margin-right:6px; margin-bottom:6px; display:inline-block; color:var(--muted) }
  .fav { color: #ff9ab0; font-weight:700 }
</style>
</head>
<body>
  <div class="wrap">

    <header class="site-header" role="banner">
      <div class="logo">RS MANGA HUB</div>

      <nav class="main-nav" role="navigation" id="navLinks">
        <button data-page="home" class="nav-btn active">Home</button>
        <button data-page="library" class="nav-btn">Library</button>
        <button data-page="upload" class="nav-btn">Upload</button>
        <button data-page="dashboard" class="nav-btn">Approvals</button>
        <button data-page="help" class="nav-btn">Help</button>
        <button data-page="contact" class="nav-btn">Contact</button>
      </nav>

      <div class="header-actions">
        <div class="search" title="Search" style="display:flex;align-items:center;gap:6px;background:var(--glass);padding:6px;border-radius:8px">
          <input id="searchInput" placeholder="Search manga, author, tags..." aria-label="Search" style="background:transparent;border:0;color:var(--text);outline:none;">
          <button id="searchBtn" class="icon-btn" title="Search"><i class="fa fa-search"></i></button>
        </div>

        <button id="themeToggle" class="icon-btn" title="Toggle theme"><i class="fa fa-moon"></i></button>

        <div id="authArea"></div>

      </div>
    </header>

    <div id="notifWrap" class="top-right-badge"></div>

    <!-- PAGES -->
    <!-- HOME -->
    <main id="home" class="page active">
      <div class="hero">
        <div class="left">
          <span class="badge" style="display:inline-block;background:var(--accent);color:#fff;padding:6px 10px;border-radius:999px;font-weight:700;margin-bottom:8px;font-size:13px">Featured</span>
          <h1 id="heroTitle">Blade of Ryota</h1>
          <p class="muted" id="heroMeta">By Ayumi Natori • Ongoing • 34.3K views</p>
          <div style="margin-top:12px">
            <button id="ctaRead" class="btn">Read Now</button>
            <button id="ctaLibrary" class="btn ghost" style="margin-left:8px">Library</button>
          </div>
        </div>
        <div class="right"><img id="heroImg" src="https://i.ibb.co/xtyCMc6Q" alt="featured"></div>
      </div>

      <section class="section">
        <div style="display:flex;justify-content:space-between;align-items:end">
          <div><h2>Top Ranked</h2><p class="muted">Ranked by rating and recency</p></div>
          <div><button id="btnMyFavs" class="btn small">My Favorites</button></div>
        </div>

        <div id="topGrid" class="cards-grid" aria-live="polite"></div>
      </section>

      <section class="section">
        <h3>Featured Picks</h3>
        <div id="featuredRow" class="cards-grid"></div>
      </section>
    </main>

    <!-- LIBRARY -->
    <main id="library" class="page">
      <h2>Manga Library</h2>
      <div id="libraryGrid" class="cards-grid"></div>
    </main>

    <!-- MANGA DETAIL -->
    <main id="mangaDetail" class="page">
      <button id="backToLib" class="btn ghost" style="margin-bottom:12px">← Back to Library</button>
      <div class="manga-detail">
        <div class="manga-cover"><img id="mangaCover" src="" alt="cover"></div>
        <div class="manga-meta">
          <h1 id="mangaTitle">Title</h1>
          <p class="muted" id="mangaAuthor">By Author</p>
          <p class="muted" id="mangaInfo">Release • Language • Rating</p>
          <p id="mangaDesc">Description</p>

          <div style="margin-top:12px">
            <button id="favBtn" class="btn small">♡ Favorite</button>
            <button id="likeBtn" class="btn small">Like</button>
            <button id="openReaderBtn" class="btn small">Open Reader</button>
          </div>

          <h3 style="margin-top:16px">Chapters</h3>
          <ul id="chaptersList" class="chapters"></ul>

          <h3 style="margin-top:12px">Comments</h3>
          <div id="commentsWrap">
            <div id="commentsList"></div>
            <div style="margin-top:8px">
              <textarea id="commentInput" placeholder="Add a comment..."></textarea>
              <button id="postComment" class="btn small" style="margin-top:6px">Post</button>
            </div>
          </div>
        </div>
      </div>
    </main>

    <!-- READER OVERLAY -->
    <div id="readerOverlay">
      <div class="reader-wrap">
        <div class="reader-controls">
          <div>
            <label style="color:var(--muted)"><input id="readerModeToggle" type="checkbox"> Vertical</label>
            <button id="prevPage" class="btn small">Prev</button>
            <button id="nextPage" class="btn small">Next</button>
            <button id="zoomOut" class="btn small">−</button>
            <button id="zoomIn" class="btn small">+</button>
          </div>
          <div><button id="closeReader" class="btn ghost">Close</button></div>
        </div>
        <section id="readerArea" class="reader-area vertical"></section>
      </div>
    </div>

    <!-- UPLOAD -->
    <main id="upload" class="page">
      <h2>Upload Manga / Chapter</h2>
      <form id="uploadForm" class="upload-form">
        <label>Title<input name="title" required></label>
        <label>Author<input name="author"></label>
        <label>Summary<textarea name="summary"></textarea></label>
        <label>Tags (comma separated)<input name="tags"></label>
        <label>Cover Image<input type="file" id="coverFile" accept="image/*" required></label>
        <label>Chapter images (multiple)<input type="file" id="chapterFiles" accept="image/*" multiple required></label>
        <div class="form-actions">
          <button class="btn" type="submit">Submit for Approval</button>
        </div>
      </form>
      <p class="muted">Uploads are stored locally for this demo. Connect Firebase later for persistent storage.</p>
    </main>

    <!-- DASHBOARD -->
    <main id="dashboard" class="page">
      <h2>Pending Uploads (Admin)</h2>
      <div id="adminLock" class="card-admin">
        <p class="muted">Protected Admin Dashboard (demo). Enter admin password:</p>
        <input id="adminPass" placeholder="Admin password" style="padding:8px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);width:240px">
        <button id="adminUnlock" class="btn small" style="margin-left:8px">Unlock</button>
        <div class="muted" style="margin-top:8px">Demo admin password: <code>rs-admin-2025</code></div>
      </div>
      <div id="pendingList"></div>
    </main>

    <!-- HELP -->
    <main id="help" class="page">
      <h2>Help & FAQ</h2>
      <p class="muted">How to upload: Use the Upload page to submit a cover + chapter images. Admin will approve the upload before publishing.</p>
      <p class="muted">Contact support at: itsamritanshofficial@gmail.com</p>
    </main>

    <!-- CONTACT -->
    <main id="contact" class="page">
      <h2>Contact</h2>
      <p>Email: <b>itsamritanshofficial@gmail.com</b></p>
      <form id="contactForm" style="max-width:640px;margin-top:12px">
        <input name="name" placeholder="Your name">
        <input name="email" placeholder="Your email">
        <textarea name="message" placeholder="Message"></textarea>
        <button class="btn" type="submit">Send Message</button>
      </form>
    </main>

    <footer class="site-footer">© <span id="year"></span> RS MANGA HUB — All rights reserved.</footer>
  </div>

<script>
/* =========================
   RS MANGA HUB — FINAL SINGLE FILE
   All functionality: local demo (localStorage)
   ========================= */

/* STORAGE KEYS */
const KEYS = {
  users: 'rsh_users_v3',
  session: 'rsh_session_v3',
  published: 'rsh_published_v3',
  uploads: 'rsh_uploads_v3',
  commentsPrefix: 'rsh_comments_v3_',
  notifs: 'rsh_notifs_v3',
  theme: 'rsh_theme_v3'
};

/* UTIL */
const $ = s => document.querySelector(s);
const $$ = s => Array.from(document.querySelectorAll(s));
const uid = p => (p||'id') + Date.now().toString(36) + Math.random().toString(36).slice(2,8);
const now = () => Date.now();
function lsGet(k,d=null){ try{ const v = localStorage.getItem(k); return v ? JSON.parse(v) : d; } catch { return d } }
function lsSet(k,v){ localStorage.setItem(k, JSON.stringify(v)) }
function lsRm(k){ localStorage.removeItem(k) }

/* THEME */
(function initTheme(){
  const saved = lsGet(KEYS.theme);
  if(saved === 'light') document.documentElement.classList.add('light');
  else if(saved === 'dark') document.documentElement.classList.remove('light');
  else {
    // prefer system
    const prefersDark = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
    if(!prefersDark) document.documentElement.classList.add('light');
  }
})();
$('#themeToggle')?.addEventListener('click', ()=>{
  const isLight = document.documentElement.classList.toggle('light');
  lsSet(KEYS.theme, isLight ? 'light' : 'dark');
});

/* SEED DATA (5 images from your links) */
(function seed(){
  if(!lsGet(KEYS.published)){
    const data = [
      { id:'m1', title:'Tokyo Ghoul', author:'Sui Ishida', artist:'Sui Ishida', release:'2011-09-01', language:'JP', genres:['Dark','Thriller'], status:'Ongoing', rating:4.6, cover:'https://i.ibb.co/xtyCMc6Q', pages:['https://i.ibb.co/xtyCMc6Q','https://i.ibb.co/xtyCMc6Q'], views:12500, likes:1200, createdAt:now() },
      { id:'m2', title:'Naruto', author:'Masashi Kishimoto', artist:'Masashi Kishimoto', release:'1999-09-21', language:'JP', genres:['Action','Adventure'], status:'Completed', rating:4.5, cover:'https://i.ibb.co/nqpc1VhX', pages:['https://i.ibb.co/nqpc1VhX','https://i.ibb.co/nqpc1VhX'], views:43200, likes:5300, createdAt:now()-86400000 },
      { id:'m3', title:'One Piece', author:'Eiichiro Oda', artist:'Eiichiro Oda', release:'1997-07-22', language:'JP', genres:['Adventure','Fantasy'], status:'Ongoing', rating:4.7, cover:'https://i.ibb.co/Hf565yP4', pages:['https://i.ibb.co/Hf565yP4','https://i.ibb.co/Hf565yP4'], views:88000, likes:10200, createdAt:now()-172800000 },
      { id:'m4', title:'Jujutsu Kaisen', author:'Gege Akutami', artist:'Gege Akutami', release:'2018-03-05', language:'JP', genres:['Action','Horror'], status:'Ongoing', rating:4.4, cover:'https://i.ibb.co/NnGqLfD5', pages:['https://i.ibb.co/NnGqLfD5','https://i.ibb.co/NnGqLfD5'], views:66200, likes:7300, createdAt:now()-259200000 },
      { id:'m5', title:'Demon Slayer', author:'Koyoharu Gotouge', artist:'Koyoharu Gotouge', release:'2016-02-15', language:'JP', genres:['Action','Drama'], status:'Completed', rating:4.8, cover:'https://i.ibb.co/9mg7T6hy', pages:['https://i.ibb.co/9mg7T6hy','https://i.ibb.co/9mg7T6hy'], views:99000, likes:14000, createdAt:now()-345600000 }
    ];
    lsSet(KEYS.published, data);
  }
  if(!lsGet(KEYS.users)){
    lsSet(KEYS.users, [{ id:'u_admin', email:'admin@rsmanga.demo', pass:'admin', name:'Admin', isAdmin:true, favorites:[] }]);
  }
  if(!lsGet(KEYS.uploads)) lsSet(KEYS.uploads, []);
  if(!lsGet(KEYS.notifs)) lsSet(KEYS.notifs, []);
})();

/* AUTH (local demo) */
function currentSession(){ return lsGet(KEYS.session, null) }
function setSession(sess){ lsSet(KEYS.session, sess) }
function logout(){ lsRm(KEYS.session); renderAuthUI(); location.reload(); }

/* register/login (local) */
function registerLocal(email, pass, name=''){
  const users = lsGet(KEYS.users, []);
  if(users.find(u=>u.email===email)) throw new Error('Email already registered');
  const u = { id: uid('u_'), email, pass, name, isAdmin:false, favorites:[], likes:[] };
  users.push(u); lsSet(KEYS.users, users);
  setSession({ id: u.id, email: u.email, name: u.name, isAdmin:false });
  return u;
}
function loginLocal(email, pass){
  const users = lsGet(KEYS.users, []);
  const u = users.find(it => it.email===email && it.pass===pass);
  if(!u) throw new Error('Invalid credentials');
  setSession({ id: u.id, email: u.email, name: u.name, isAdmin: !!u.isAdmin });
  return u;
}

/* AUTH UI */
function renderAuthUI(){
  const authArea = $('#authArea');
  const sess = currentSession();
  if(!authArea) return;
  if(sess){
    authArea.innerHTML = `<div style="display:flex;gap:8px;align-items:center">
      <div style="font-size:13px;color:var(--muted)">Hi, ${sess.name || sess.email}</div>
      <button id="btnProfile" class="btn small">Profile</button>
      <button id="btnLogout" class="btn small">Logout</button>
    </div>`;
    $('#btnLogout')?.addEventListener('click', logout);
    $('#btnProfile')?.addEventListener('click', ()=> alert('Profile (demo) — ' + (sess.name||sess.email)));
  } else {
    authArea.innerHTML = `<div style="display:flex;gap:8px"><button id="btnLogin" class="btn small ghost">Login</button><button id="btnSignup" class="btn small">Sign Up</button></div>`;
    $('#btnLogin')?.addEventListener('click', openLoginModal);
    $('#btnSignup')?.addEventListener('click', openSignupModal);
  }
}
renderAuthUI();

/* Simple modals using prompt (quick) */
function openSignupModal(){
  const email = prompt('Email:'); if(!email) return;
  const pass = prompt('Password:'); if(!pass) return;
  const name = prompt('Display name (optional):') || email.split('@')[0];
  try{
    registerLocal(email, pass, name);
    alert('Account created & logged in');
    renderAuthUI();
  }catch(e){ alert(e.message) }
}
function openLoginModal(){
  const email = prompt('Email:'); if(!email) return;
  const pass = prompt('Password:'); if(!pass) return;
  try{
    loginLocal(email, pass);
    alert('Logged in');
    renderAuthUI();
  }catch(e){ alert(e.message) }
}

/* NAVIGATION */
const pages = ['home','library','mangaDetail','upload','dashboard','help','contact'];
function showPage(page){
  pages.forEach(p => {
    const el = document.getElementById(p);
    if(!el) return;
    if(p === page) el.classList.add('active'), el.classList.remove('hidden');
    else el.classList.remove('active');
  });
  // active nav button
  $$('.nav-btn').forEach(b => { b.classList.toggle('active', b.dataset.page === page); });
  // special: index
  if(page === 'home') renderHome();
  if(page === 'library') renderLibrary();
  if(page === 'dashboard') renderPending();
}
$$('.nav-btn').forEach(b => b.addEventListener('click', ()=> showPage(b.dataset.page)));

/* SEARCH */
$('#searchBtn')?.addEventListener('click', ()=>{
  const q = ($('#searchInput')?.value || '').trim().toLowerCase();
  if(!q) return alert('Enter search');
  cons
