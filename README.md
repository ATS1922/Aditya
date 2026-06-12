<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
  <title>Biodata 3D · Aditya</title>
  <!-- Font Awesome untuk ikon -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    /* Reset & Font */
    body {
      margin: 0;
      overflow-x: hidden;
      font-family: 'Poppins', 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #0b0f1c 0%, #1a1f2f 100%);
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      perspective: 1200px;
    }

    /* Container 3D utama */
    .scene {
      width: 100%;
      max-width: 700px;
      margin: 40px 20px;
      transform-style: preserve-3d;
      transition: transform 0.1s ease-out;
    }

    /* Kartu biodata 3D */
    .card-3d {
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      border-radius: 48px;
      padding: 35px 30px 40px;
      box-shadow: 0 40px 70px rgba(0, 0, 0, 0.7), 0 0 0 1px rgba(255, 255, 255, 0.15), inset 0 0 30px rgba(255, 255, 255, 0.05);
      transform-style: preserve-3d;
      transform: rotateX(5deg) rotateY(5deg);
      transition: transform 0.4s cubic-bezier(0.23, 1, 0.32, 1), box-shadow 0.4s ease;
      color: #f0f4ff;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.2);
      letter-spacing: 0.3px;
    }

    /* Efek 3D saat hover kartu */
    .card-3d:hover {
      box-shadow: 0 50px 90px rgba(0, 180, 255, 0.25), 0 0 0 1px rgba(255, 255, 255, 0.3), inset 0 0 40px rgba(255, 255, 255, 0.1);
      transform: rotateX(2deg) rotateY(3deg) translateZ(15px);
    }

    /* Header dengan nama */
    .name-title {
      font-size: 3.8rem;
      font-weight: 800;
      text-align: center;
      margin-bottom: 5px;
      background: linear-gradient(135deg, #ffd966, #ffb347);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      text-shadow: 0 10px 20px rgba(0,0,0,0.5);
      transform: translateZ(40px);
      letter-spacing: 2px;
    }

    .sub-role {
      text-align: center;
      font-size: 1.2rem;
      font-weight: 400;
      color: #b4c8f0;
      margin-top: -10px;
      margin-bottom: 25px;
      transform: translateZ(25px);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }

    .sub-role i {
      color: #ffb347;
    }

    /* Grid informasi */
    .info-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px 20px;
      margin: 25px 0 20px;
      transform: translateZ(30px);
    }

    .info-item {
      background: rgba(10, 15, 27, 0.55);
      backdrop-filter: blur(12px);
      border-radius: 24px;
      padding: 15px 16px;
      display: flex;
      align-items: center;
      gap: 14px;
      box-shadow: 0 10px 20px rgba(0,0,0,0.5), inset 0 1px 1px rgba(255,255,255,0.2);
      border: 1px solid rgba(255,255,255,0.15);
      transition: all 0.3s ease;
      transform: translateZ(15px);
    }

    .info-item:hover {
      background: rgba(20, 30, 45, 0.7);
      border-color: rgba(255, 200, 100, 0.5);
      transform: translateZ(30px) scale(1.02);
      box-shadow: 0 15px 30px rgba(0,0,0,0.6);
    }

    .info-icon {
      font-size: 2rem;
      width: 45px;
      text-align: center;
      color: #ffb347;
      filter: drop-shadow(0 0 8px #ff9900);
    }

    .info-text {
      display: flex;
      flex-direction: column;
    }

    .info-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 2px;
      font-weight: 600;
      color: #9aa9c9;
    }

    .info-value {
      font-weight: 700;
      font-size: 1.15rem;
      color: #fff;
      text-shadow: 0 2px 5px black;
    }

    /* Deskripsi / tentang */
    .description-box {
      background: rgba(255,255,255,0.05);
      backdrop-filter: blur(10px);
      border-radius: 28px;
      padding: 18px 20px;
      margin: 20px 0 18px;
      border-left: 5px solid #ffb347;
      transform: translateZ(25px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.4);
      line-height: 1.6;
      font-style: italic;
      color: #d9e2ff;
    }

    .description-box i {
      color: #ffb347;
      margin-right: 8px;
    }

    /* Tombol Menu */
    .menu-button {
      display: flex;
      justify-content: center;
      margin: 15px 0 10px;
      transform: translateZ(35px);
    }

    .btn-menu {
      background: rgba(255, 255, 255, 0.08);
      backdrop-filter: blur(15px);
      border: 1px solid rgba(255, 255, 255, 0.3);
      color: white;
      font-weight: 600;
      padding: 12px 30px;
      border-radius: 50px;
      font-size: 1.2rem;
      letter-spacing: 2px;
      cursor: pointer;
      transition: 0.3s;
      display: flex;
      align-items: center;
      gap: 10px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.5);
      background: linear-gradient(135deg, rgba(255,180,70,0.2), rgba(255,140,0,0.1));
    }

    .btn-menu i {
      font-size: 1.2rem;
      color: #ffb347;
    }

    .btn-menu:hover {
      background: rgba(255, 200, 100, 0.2);
      border-color: #ffb347;
      box-shadow: 0 0 30px #ff9900aa;
      transform: scale(1.05) translateZ(10px);
    }

    /* Tombol project game */
    .project-link-wrapper {
      display: flex;
      justify-content: center;
      margin-top: 25px;
      transform: translateZ(40px);
    }

    .project-btn {
      background: linear-gradient(145deg, #232a3e, #0f1322);
      border: 1px solid rgba(255, 215, 0, 0.45);
      color: #ffd966;
      font-weight: 700;
      font-size: 1.2rem;
      padding: 14px 32px;
      border-radius: 40px;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 12px;
      backdrop-filter: blur(10px);
      box-shadow: 0 15px 30px rgba(0,0,0,0.7), 0 0 25px rgba(255,200,0,0.3);
      transition: all 0.4s ease;
      letter-spacing: 1px;
      text-shadow: 0 2px 5px black;
    }

    .project-btn i {
      font-size: 1.5rem;
      color: #ffb347;
      filter: drop-shadow(0 0 6px orange);
    }

    .project-btn:hover {
      background: #1e2338;
      border-color: #ffb347;
      box-shadow: 0 0 40px #ffaa00, 0 20px 35px black;
      transform: translateZ(20px) scale(1.04);
      color: #fff;
    }

    /* Responsif */
    @media (max-width: 550px) {
      .info-grid {
        grid-template-columns: 1fr;
      }
      .name-title {
        font-size: 2.8rem;
      }
    }

    /* Animasi ambient */
    @keyframes float {
      0% { transform: translateZ(30px); }
      50% { transform: translateZ(42px); }
      100% { transform: translateZ(30px); }
    }
    .card-3d {
      animation: float 6s infinite ease-in-out;
    }
  </style>
</head>
<body>
  <div class="scene" id="scene">
    <div class="card-3d" id="card3d">
      
      <!-- Nama -->
      <h1 class="name-title">ADITYA</h1>
      <div class="sub-role">
        <i class="fas fa-stethoscope"></i> Calon Dokter • 2000
      </div>

      <!-- Grid biodata -->
      <div class="info-grid">
        <div class="info-item">
          <div class="info-icon"><i class="fas fa-calendar-alt"></i></div>
          <div class="info-text">
            <span class="info-label">Tanggal Lahir</span>
            <span class="info-value">01 Oktober 2000</span>
          </div>
        </div>
        <div class="info-item">
          <div class="info-icon"><i class="fas fa-futbol"></i></div>
          <div class="info-text">
            <span class="info-label">Hobi</span>
            <span class="info-value">Main Bola</span>
          </div>
        </div>
        <div class="info-item">
          <div class="info-icon"><i class="fas fa-school"></i></div>
          <div class="info-text">
            <span class="info-label">Sekolah</span>
            <span class="info-value">SMA AL Muslim</span>
          </div>
        </div>
        <div class="info-item">
          <div class="info-icon"><i class="fas fa-user-md"></i></div>
          <div class="info-text">
            <span class="info-label">Cita-Cita</span>
            <span class="info-value">Dokter</span>
          </div>
        </div>
      </div>

      <!-- Deskripsi singkat -->
      <div class="description-box">
        <i class="fas fa-quote-left"></i> 
        Seorang pemuda bersemangat dari SMA AL Muslim, kelahiran Oktober 2000. 
        Menggabungkan disiplin lapangan hijau dengan mimpi mulia menjadi dokter. 
        Selalu bertekad memberikan dampak positif lewat kesehatan dan sportivitas.
        <i class="fas fa-quote-right"></i>
      </div>

      <!-- Tombol Menu (interaktif, bisa ditambahkan fungsi) -->
      <div class="menu-button">
        <button class="btn-menu" id="menuButton">
          <i class="fas fa-bars"></i> MENU
        </button>
      </div>

      <!-- Tombol Project Game dengan link -->
      <div class="project-link-wrapper">
        <a href="https://ats1922.github.io/Jajan/" target="_blank" rel="noopener noreferrer" class="project-btn">
          <i class="fas fa-gamepad"></i> PROJECT GAME
        </a>
      </div>
      
      <!-- Elemen dekoratif 3D kecil -->
      <div style="position: absolute; bottom: 15px; right: 25px; font-size: 0.8rem; color: rgba(255,255,255,0.4); transform: translateZ(15px);">
        <i class="fas fa-cube"></i> 3D Bio
      </div>
    </div>
  </div>

  <script>
    (function() {
      // Efek 3D interaktif mengikuti posisi mouse (parallax halus)
      const scene = document.getElementById('scene');
      const card = document.getElementById('card3d');
      
      // Fungsi untuk update rotasi 3D berdasarkan mouse
      function handleMouseMove(e) {
        if (!scene || !card) return;
        
        // Dapatkan area scene
        const rect = scene.getBoundingClientRect();
        const centerX = rect.left + rect.width / 2;
        const centerY = rect.top + rect.height / 2;
        
        // Posisi mouse relatif terhadap pusat
        let mouseX = e.clientX - centerX;
        let mouseY = e.clientY - centerY;
        
        // Faktor rotasi (semakin jauh dari tengah, semakin besar rotasi)
        const maxRotate = 12; // derajat maksimum
        const rotateY = (mouseX / (rect.width / 2)) * maxRotate;
        const rotateX = - (mouseY / (rect.height / 2)) * maxRotate;
        
        // Batasi rotasi agar tidak ekstrem
        const limitedY = Math.min(Math.max(rotateY, -maxRotate), maxRotate);
        const limitedX = Math.min(Math.max(rotateX, -maxRotate), maxRotate);
        
        // Terapkan transformasi dengan transisi halus sudah di CSS, tapi kita set manual
        card.style.transform = `rotateX(${limitedX}deg) rotateY(${limitedY}deg) translateZ(5px)`;
      }
      
      // Reset ke posisi awal saat mouse keluar dari jendela (opsional)
      function handleMouseLeave() {
        if (card) {
          card.style.transform = 'rotateX(5deg) rotateY(5deg) translateZ(0px)';
        }
      }
      
      // Event listener untuk pergerakan mouse di seluruh dokumen agar lebih responsif
      document.addEventListener('mousemove', handleMouseMove);
      
      // Ketika mouse meninggalkan halaman, kembali ke posisi default
      document.addEventListener('mouseleave', handleMouseLeave);
      
      // Untuk perangkat sentuh (mobile) kita bisa tambahkan orientasi device, 
      // tapi untuk sederhana kita gunakan sentuhan layar.
      function handleTouchMove(e) {
        e.preventDefault();
        if (!scene || !card || e.touches.length === 0) return;
        
        const touch = e.touches[0];
        const rect = scene.getBoundingClientRect();
        const centerX = rect.left + rect.width / 2;
        const centerY = rect.top + rect.height / 2;
        
        let touchX = touch.clientX - centerX;
        let touchY = touch.clientY - centerY;
        
        const maxRotate = 10;
        const rotateY = (touchX / (rect.width / 2)) * maxRotate;
        const rotateX = - (touchY / (rect.height / 2)) * maxRotate;
        
        card.style.transform = `rotateX(${Math.min(Math.max(rotateX, -maxRotate), maxRotate)}deg) rotateY(${Math.min(Math.max(rotateY, -maxRotate), maxRotate)}deg) translateZ(5px)`;
      }
      
      function handleTouchEnd() {
        if (card) {
          card.style.transform = 'rotateX(5deg) rotateY(5deg) translateZ(0px)';
        }
      }
      
      scene.addEventListener('touchmove', handleTouchMove, { passive: false });
      scene.addEventListener('touchend', handleTouchEnd);
      scene.addEventListener('touchcancel', handleTouchEnd);
      
      // Tombol Menu interaktif (menampilkan notifikasi atau aksi)
      const menuBtn = document.getElementById('menuButton');
      menuBtn.addEventListener('click', function(e) {
        e.stopPropagation();
        // Efek visual klik
        menuBtn.style.transform = 'scale(0.96)';
        setTimeout(() => {
          menuBtn.style.transform = '';
        }, 150);
        
        // Tampilkan pesan menu (bisa dikembangkan)
        alert('✨ Menu Biodata Aditya:\n\n• Data Diri\n• Pendidikan\n• Hobi & Cita-cita\n• Project Game\n\n"Terus bergerak maju!"');
      });
      
      // Sedikit perbaikan untuk memastikan kartu tetap terlihat 3D saat tidak ada mouse (default)
      // Sudah diatur di CSS. Juga tambahkan animasi subtle.
      console.log('🌐 Biodata 3D Aditya siap! Gerakkan mouse untuk efek 3D.');
    })();
  </script>
</body>
</html>
