<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Zeen Market</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Arial, sans-serif;
      background-color: black;
      color: white;
    }
    .navbar {
      background: linear-gradient(90deg, #222 100%, #fff 60%);
      box-shadow: 0 2px 10px #0004;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 14px 0 8px;
      min-height: 58px;
      z-index: 10;
      position: relative;
    }
    .navbar-main {
      display: flex;
      align-items: center;
      gap: 15px;
    }
    .logo-group {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .logo {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .logo img {
      height: 34px;
      border-radius: 7px;
      box-shadow: 0 2px 8px #2f3cbf55;
      background: #222;
    }
    .logo strong {
      font-size: 1.13em;
      letter-spacing: 1.2px;
      color: #f8fbff;
      text-shadow: 1px 1px 2px #0009;
      margin-right: 10px;
    }
    .menu-icon {
      position: absolute;
      top: 14px;
      right: 16px;
      z-index: 20;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      width: 32px;
      height: 32px;
      cursor: pointer;
      transition: background 0.14s;
      border-radius: 7px;
      background: none;
    }
    .menu-icon:hover {
      background: #2531a433;
    }
    .menu-icon .bar {
      width: 22px;
      height: 3.2px;
      background: #f8fbff;
      margin: 2.5px 0;
      border-radius: 2px;
      transition: background 0.14s;
    }
    .navbar-actions {
      display: flex;
      align-items: center;
      gap: 10px;
    }
    .search-bar {
      display: flex;
      align-items: center;
      background: #fff;
      border-radius: 28px;
      padding: 5px 10px;
      margin: 0 10px;
      min-width: 210px;
      width: 260px;
      transition: box-shadow 0.2s;
      box-shadow: 0 0px 3px #fff;
      border: 1.5px solid #000;
      position: relative;
    }
    /* Ubah warna teks input jadi hitam */
    .search-bar input {
      background: transparent;
      border: none;
      outline: none;
      color: #000 !important; /* Ubah warna teks menjadi hitam */
      font-weight: bold;
      font-size: 1em;
      width: 100%;
      padding: 4px 0 4px 5px;
      cursor: pointer;
      /* Tambahkan placeholder warna hitam juga */
    }
    .search-bar input::placeholder {
      color: #000 !important; /* placeholder hitam */
      opacity: 1;
    }
    .search-bar button {
      background: none;
      border: none;
      outline: none;
      cursor: pointer;
      color: #000;
      font-size: 1.3em;
      margin-left: 4px;
      padding: 2px 5px 2px 4px;
      border-radius: 50%;
      transition: background 0.15s;
    }
    .search-bar button:hover {
      background: #fff;
      color: #fff;
    }
    .jual-akun-btn {
      background: #94939f;
      color: #fff;
      font-weight: bold;
      padding: 8px 22px;
      border: none;
      border-radius: 28px;
      font-size: 1.06em;
      border: 1px solid #fff;
      cursor: pointer;
      transition: background 0.15s, transform 0.1s, box-shadow 0.15s;
      letter-spacing: 0.8px;
      display: flex;
      align-items: center;
      gap: 7px;
      position: relative;
      overflow: hidden;
      white-space: nowrap;
    }
    .jual-akun-btn::before {
      content: '';
      display: block;
      position: absolute;
      left: -30%;
      top: -20%;
      width: 70%;
      height: 150%;
      background: linear-gradient(120deg,rgba(255,255,255,0.18) 10%,rgba(255,255,255,0.00) 70%);
      transform: skewX(-18deg);
      transition: left 0.3s;
      z-index: 1;
    }
    .jual-akun-btn:hover::before {
      left: 90%;
      transition: left 0.4s;
    }
    .jual-akun-btn span {
      font-size: 1.25em;
      margin-right: 4px;
      filter: drop-shadow(0 1px 1.5px #fff8);
      z-index: 2;
      position: relative;
    }
    .jual-akun-btn:hover {
      background: linear-gradient(90deg,#2f3cbf 10%, #2531a4 100%);
      transform: scale(1.08) translateY(-2px);
      box-shadow: 0 4px 20px #2f3cbf90, 0 1.5px 12px #fff2 inset;
    }
    @media (max-width: 600px) {
      .navbar { flex-direction: column; align-items: stretch; padding: 6px 5px; }
      .navbar-main { flex-direction: column; gap: 6px; }
      .navbar-actions { justify-content: center; margin-top: 5px; }
      .logo-group { justify-content: center; }
      .search-bar { width: 100%; min-width: 0; margin: 5px 0; }
      .jual-akun-btn {
        width: 350px !important;
        min-width: 0 !important;
        max-width: 280px !important;
        justify-content: center;
        padding-left: 0;
        padding-right: 0;
        margin-left: auto;
        margin-right: auto;
      }
      .menu-icon {
        top: 6px;
        right: 10px;
      }
    }
    .banner {
      height: 165px;
      margin: 10px;
      border-radius: 10px;
      overflow: hidden;
      position: relative;
      background: #222;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .banner video, .banner img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      top: 0; left: 0;
      display: block;
      z-index: 1;
    }
    .section-title {
      margin: 28px 10px 10px 10px;
      font-weight: bold;
      display: flex;
      align-items: center;
      size: 100px;
    }
    /* Tambahkan scroll horizontal untuk flash sale dan top up */
    .flash-scroll-container {
      display: flex;
      flex-wrap: nowrap;
      gap: 10px;
      padding: 10px 0 10px 10px;
      cursor: auto;
      user-select: none;
      scroll-behavior: smooth;
      scroll-snap-type: x mandatory;
      overflow-x: auto;
      overscroll-behavior-x: contain;
      -webkit-overflow-scrolling: touch;
  
    }
    .flash-item {
      flex: 0 0 auto;
      border-radius: 5px;
      overflow: hidden;
      background: #222;
      display: flex;
      justify-content: center;
      align-items: center;
      height: auto;
      margin-right: 0;
      transition: box-shadow 0.22s cubic-bezier(.5,1.5,.5,1), transform 0.33s cubic-bezier(.5,1.5,.5,1);
      padding: 0;
      opacity: 1;
      transform: none;
      animation: none;
      box-shadow: none;
      scroll-snap-align: start;
      scroll-snap-stop: always;
      min-width: 120px;
    }
    .flash-item.active {
      transform: none;
      z-index: auto;
      box-shadow: none;
    }
    .flash-item:last-child {
      margin-right: 0;
    }
    .flash-item a {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      min-width: 80px;
      min-height: 60px;
    }
    .flash-item a img {
      display: block;
      width: auto;
      height: 80px;
      object-fit: contain;
      border-radius: 10px;
      box-shadow: 0 2px 8px #0007;
      background: #222;
      max-width: 180px;
      pointer-events: none;
      user-select: none;
    }
    .scroll-container {
      display: flex;
      flex-wrap: nowrap;
      gap: 10px;
      padding: 10px;
      cursor: auto;
      user-select: none;
      scroll-behavior: smooth;
      scrollbar-width: thin;
      overflow-x: auto;
      -webkit-overflow-scrolling: touch;
      overscroll-behavior-x: contain;
      scroll-snap-type: x mandatory;
    }
    
    .topup-item, .akun-item {
      flex: 0 0 auto;
      width: 100px;
      border-radius: 10px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      background-color: #c3c2cb;
      border-radius: 10px; 
      border: 2px solid #fff;
      position: relative;
      align-items: center;
      justify-content: flex-start;
      box-shadow: 0 2px 9px #000;
      scroll-snap-align: start;
      scroll-snap-stop: always;
    }
    .topup-item .content, .akun-item .content {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 70px;
      width: 30px;
      margin-top: 16px;
    }
    .topup-item .content a, .akun-item .content a {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 74px;
      height: 74px;
    }
    .topup-item .content a img, .akun-item .content a img {
      width: 74px;
      height: 74px;
      object-fit: contain;
      margin-bottom: 16px;
      border-radius: 13px;
      background: #f8fbff;
      box-shadow: 0 2px 9px #000;
      display: block;
      margin: -5px auto 0 auto;
    }
    .label {
      padding: 5px;
      font-size: 11px;
      color: #000;
      text-align: center;
      margin-top: 5px;
    }
    .button {
      background-color: #4f4f50;
      padding: 8px;
      color: white;
      font-weight: bold;
      text-align: center;
      cursor: pointer;
      border-radius: 10px;
      margin: 5px;
    }
    a {
      text-decoration: none;
      color: inherit;
    }
    .jual-modal-backdrop { display: none !important; }
    .notif-maintenance {
      position: fixed;
      top: 22px;
      left: 50%;
      transform: translateX(-50%);
      min-width: 310px;
      background: linear-gradient(105deg,#2531a4f2 20%,#2f3cbfef 85%,#4ff7e7cf 120%);
      color: #fff;
      padding: 22px 36px 20px 54px;
      border-radius: 16px;
      box-shadow: 0 6px 32px #2f3cbf77, 0 2px 12px #fff4 inset;
      font-size: 1.09em;
      font-weight: bold;
      letter-spacing: 0.5px;
      z-index: 9999;
      display: none;
      animation: notif-pop 0.35s cubic-bezier(.17,.88,.45,1.08);
      text-align: left;
      overflow: hidden;
      border: 2.5px solid #44eaffbb;
    }
    .notif-maintenance.active {
      display: flex;
      align-items: center;
      animation: notif-pop 0.33s cubic-bezier(.11,.91,.43,1.11);
    }
    @keyframes notif-pop {
      0% { opacity: 0; transform: translate(-50%, -32px) scale(0.92);}
      70% { opacity: 1; transform: translate(-50%, 4px) scale(1.08);}
      100% { opacity: 1; transform: translate(-50%, 0) scale(1);}
    }
    .notif-maintenance .notif-icon {
      font-size: 2.4em;
      filter: drop-shadow(0 2px 6px #fff9) drop-shadow(0 0 12px #53ffd5cc);
      animation: notif-swing 1.1s infinite alternate;
      pointer-events: none;
      user-select: none;
      margin-right: 18px;
      margin-left: 0;
    }
    .notif-text-group {
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .notif-maintenance .notif-title {
      font-size: 1.14em;
      letter-spacing: 1px;
      color: #fff;
      margin-bottom: 3px;
      font-weight: bold;
      text-shadow: 0 2px 8px #00fff9cc;
    }
    .notif-maintenance .notif-desc {
      font-size: 1em;
      color: #e8fcfa;
      text-shadow: 0 1px 2px #0008;
    }
    .notif-maintenance .notif-progress {
      width: 100%;
      height: 4px;
      border-radius: 2px;
      background: #fff3;
      margin-top: 13px;
      overflow: hidden;
      position: relative;
    }
    .notif-maintenance .notif-progress-bar {
      display: block;
      height: 100%;
      width: 0;
      background: linear-gradient(90deg,#44eaff 0%,#2f3cbf 85%);
      border-radius: 2px;
      transition: width 2.15s linear;
      animation: notif-bar-fill 1.95s linear forwards;
    }
    @keyframes notif-bar-fill {
      0% { width: 0;}
      100% { width: 100%;}
    }
    @media (max-width: 500px) {
      .notif-maintenance { min-width: 0; padding: 18px 16px 16px 12px; }
      .notif-maintenance .notif-icon { font-size: 2em; margin-right: 10px;}
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav class="navbar">
    <div class="navbar-main">
      <div class="logo-group">
        <div class="logo">
          <img src="logo.png" alt="Logo">
          <strong>Zeen Market</strong>
        </div>
      </div>
    </div>
    <div class="navbar-actions">
      <form class="search-bar" id="searchForm" autocomplete="off" onsubmit="return false;">
        <input type="text" id="searchInput" placeholder="CARI GAME ...." aria-label="Cari Game" autocomplete="off" readonly style="cursor:pointer; color:#000 !important;">
        <button type="submit" title="Cari" tabindex="-1"><span>&#128269;</span></button>
      </form>
      <a class="jual-akun-btn" id="jualAkunBtn" href="https://wa.me/6282328581304" target="_blank"><span>🛒</span>JUAL AKUN</a>
    </div>
    <div class="menu-icon" tabindex="0" aria-label="Menu">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
  </nav>

  <!-- Notif Maintenance KEREN -->
  <div id="notifMaintenance" class="notif-maintenance">
    <span class="notif-icon">⚙️</span>
    <div class="notif-text-group">
      <div class="notif-title">Maintenance!</div>
      <div class="notif-progress"><span class="notif-progress-bar" id="notifProgressBar"></span></div>
    </div>
  </div>

  <!-- Banner -->
  <div class="banner" id="banner">
    <video src="erew.mp4" autoplay loop muted playsinline></video>
  </div>

  <div class="section-title">FLASH SALE ⚡</div>
  <div class="flash-scroll-container" id="flashScroll">
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
    <div class="flash-item"><a href="https://wa.me/6282328581304?text=Min take akun" target="_blank"><img src="c.png" alt="Flash 1"></a></div>
  </div>

  <div class="section-title">TOP UP GAME 💎</div>
  <div class="scroll-container" id="topupSection">
    <div class="topup-item">
      <div class="content"><a href="#"><img src="ml.png" alt="Top Up"></a></div>
      <div class="label">MOBILE LEGEND</div>
       <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="ff.png" alt="Top Up"></a></div>
      <div class="label">FREE FIRE</div>
      <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="z.png" alt="Top Up"></a></div>
      <div class="label">ZZZ</div>
      <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="hsr.png " alt="Top Up"></a></div>
      <div class="label">Honkai Star Ra il</div>
      <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="pupg.png " alt="Top Up"></a></div>
      <div class="label">Pubg Mobile</div>
      <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="valo.png " alt="Top Up"></a></div>
      <div class="label">Valorant</div>
    <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="cod.png " alt="Top Up"></a></div>
      <div class="label">COD Mobile</div>
   <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="pb.png " alt="Top Up"></a></div>
      <div class="label">Point Blank</div>
    <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="topup-item">
      <div class="content"><a href="#"><img src="wuwa.png " alt="Top Up"></a></div>
      <div class="label">Wuthering Waves</div>
    <a href="topup-ml.html"><div class="button">TOP UP</div></a>
    </div>
  </div>

  <div class="section-title">AKUN GAME 🎮</div>
  <div class="scroll-container" id="akunGameList">
   
    <div class="akun-item">
      <div class="content"><a href="#"><img src="ml.png" alt="Akun"></a></div>
      <div class="label">MOBILE LEGEND</div>
   <a href="akun.html"><div class="button">TOP UP</div></a>
    </div>
    <div class="akun-item">
      <div class="content"><a href="#"><img src="valo.png" alt="Akun"></a></div>
      <div class="label">VALORANT</div>
      <a href="#"><div class="button">LIHAT</div></a>
    </div>
    <div class="akun-item">
      <div class="content"><a href="#"><img src="pupg.png" alt="Akun"></a></div>
      <div class="label">PUBG MOBILE</div>
      <a href="#"><div class="button">LIHAT</div></a>
    </div>
    <div class="akun-item">
      <div class="content"><a href="#"><img src="gi.png" alt="Akun"></a></div>
      <div class="label">GENSHIN IMPACT</div>
      <a href="#"><div class="button">LIHAT</div></a>
    </div>
    <div class="akun-item">
      <div class="content"><a href="#"><img src="ff.png" alt="Akun"></a></div>
      <div class="label">FREE FIRE</div>
      <a href="#"><div class="button">LIHAT</div></a>
    </div>
    
    
    <!-- ... (item lainnya tetap) ... -->
  </div>

  <script>
    // Hilangkan fitur animasi/scroll/slide untuk flash sale & topup
    // -------- FITUR CARI GAME MAINTENANCE --------
    const searchInput = document.getElementById('searchInput');
    const notifMaintenance = document.getElementById('notifMaintenance');
    const searchForm = document.getElementById('searchForm');
    const notifBar = document.getElementById('notifProgressBar');

    let notifTimeout = null;
    function showNotifMaintenance() {
      notifMaintenance.classList.add('active');
      notifBar.style.width = '0';
      notifBar.style.animation = 'notif-bar-fill 1.95s linear forwards';
      clearTimeout(notifTimeout);
      notifTimeout = setTimeout(() => {
        notifMaintenance.classList.remove('active');
      }, 2100);
    }
    searchInput.addEventListener('click', showNotifMaintenance);
    searchForm.addEventListener('submit', function(e){ e.preventDefault(); showNotifMaintenance(); });
  </script>
</body>
</html>
