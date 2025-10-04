<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>696 PARTY</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #0d0d2b, #1a1a40);
      color: #f5f5f5;
      margin: 0;
      padding: 0;
    }

    /* Canvas bintang */
    #stars {
      position: fixed;
      top: 0; left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      background: transparent;
    }

    /* Animasi neon glow header */
    header h1 {
      animation: neon 2s infinite alternate;
    }
    @keyframes neon {
      from { text-shadow: 0 0 5px #00f7ff, 0 0 15px #7209b7; }
      to { text-shadow: 0 0 20px #ff00ff, 0 0 30px #00f7ff; }
    }

    /* Hero card animasi masuk */
    .hero-card {
      animation: fadeInUp 1s ease forwards;
      opacity: 0;
    }
    @keyframes fadeInUp {
      from { transform: translateY(30px); opacity: 0; }
      to { transform: translateY(0); opacity: 1; }
    }

    header {
      background: linear-gradient(90deg, #7209b7, #3a0ca3, #4361ee);
      padding: 20px;
      text-align: center;
      color: #fff;
      box-shadow: 0 0 20px rgba(114, 9, 183, 0.8);
    }
    header h1 {
      margin: 0;
      font-size: 26px;
      text-shadow: 0 0 8px #fff, 0 0 15px #00d4ff;
    }

    .party-container {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      padding: 20px;
    }
    .hero-card {
      background: linear-gradient(180deg, #1e1e2f, #2a2a4a);
      border-radius: 15px;
      border: 2px solid transparent;
      box-shadow: 0 0 12px rgba(0, 212, 255, 0.3);
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s, border 0.3s;
    }
    .hero-card:hover {
      transform: scale(1.08);
      border: 2px solid #00d4ff;
      box-shadow: 0 0 20px #00d4ff, 0 0 40px #7209b7;
    }
    .hero-card img {
      width: 100%;
      height: 140px;
      object-fit: cover;
      border-bottom: 2px solid rgba(0, 212, 255, 0.5);
    }
    .hero-info {
      padding: 10px;
      text-align: center;
    }
    .hero-info h3 {
      margin: 5px 0;
      font-size: 16px;
      color: #00d4ff;
      text-shadow: 0 0 6px #00d4ff;
    }
    .hero-info p {
      margin: 0;
      font-size: 13px;
      color: #ffd369;
      font-weight: bold;
    }

    /* Modal */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.8);
      justify-content: center;
      align-items: center;
    }
    .modal-content {
      background: #1e1e2f;
      padding: 20px;
      border-radius: 12px;
      text-align: center;
      box-shadow: 0 0 20px #00d4ff;
      max-width: 300px;
    }
    .modal-content h2 {
      color: #00d4ff;
    }
    .modal-content button {
      margin-top: 10px;
      padding: 8px 16px;
      background: #00d4ff;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }

    /* Intro */
    #intro {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #3a0ca3, #7209b7, #4361ee);
      color: #fff;
      text-align: center;
    }
    #intro h1 {
      font-size: 40px;
      text-shadow: 0 0 15px #00f7ff;
    }
    #intro button {
      margin-top: 20px;
      padding: 12px 24px;
      background: #00d4ff;
      border: none;
      border-radius: 8px;
      font-size: 16px;
      cursor: pointer;
      color: #000;
    }

    /* Halaman 2 */
    #page2 {
      padding: 20px;
      text-align: center;
    }
    .about-text {
      margin: 20px auto;
      max-width: 600px;
      line-height: 1.6;
    }
    .sticker {
      margin: 20px auto;
    }
    nav {
      text-align: center;
      margin: 10px 0;
    }
    nav button {
      margin: 5px;
      padding: 10px 18px;
      background: #00d4ff;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <!-- Canvas bintang -->
  <canvas id="stars"></canvas>

  <!-- Intro -->
  <section id="intro">
    <h1>Welcome to 696 PARTY</h1>
    <button onclick="startParty()">MULAI</button>
  </section>

  <!-- Halaman 1 -->
  <section id="page1" style="display:none;">
    <header>
      <h1>696 PARTY</h1>
      <p>Anggota Party</p>
    </header>

    <nav>
      <button onclick="showPage(1)">Halaman 1</button>
      <button onclick="showPage(2)">Halaman 2</button>
    </nav>

    <div class="party-container">
      <div class="hero-card" onclick="openModal('ZYAT', 'XP LANE', 'Hero Favorit: cici')">
        <img src="https://i.supaimg.com/e4ac05a6-0058-4ddb-a569-2dbeb6f0a9c6.jpg" alt="cici">
        <div class="hero-info"><h3>ZYAT</h3><p>XP LANE</p></div>
      </div>
      <div class="hero-card" onclick="openModal('CALVINE', 'JUNGLER', 'Hero Favorit: julian')">
        <img src="https://i.supaimg.com/360bdef9-24bf-4a3f-ac77-d6a8aaa11afc.jpg" alt="julian">
        <div class="hero-info"><h3>CALVINE</h3><p>JUNGLER</p></div>
      </div>
      <div class="hero-card" onclick="openModal('KENZYSKY', 'GOLD LANE', 'Hero Favorit: granger')">
        <img src="https://i.supaimg.com/5041dd79-6986-401b-8bff-417ba1c4ee67.jpg" alt="granger">
        <div class="hero-info"><h3>KENZYSKY</h3><p>GOLD LANE</p></div>
      </div>
      <div class="hero-card" onclick="openModal('FRICILLA', 'MAGE', 'Hero Favorit: kagura')">
        <img src="https://i.supaimg.com/72db14c4-3634-4e61-8737-bf9af4ad5604.jpg" alt="kagura">
        <div class="hero-info"><h3>FRICILLA</h3><p>MAGE</p></div>
      </div>
      <div class="hero-card" onclick="openModal('SUPER DREAM', 'XP LANE', 'Hero Favorit: lapu lapu')">
        <img src="https://i.supaimg.com/797ce193-0ed3-4e18-856b-923231f5cca8.jpg" alt="lapu lapu">
        <div class="hero-info"><h3>SUPER DREAM</h3><p>XP LANE</p></div>
      </div>
      <div class="hero-card" onclick="openModal('masgliez', 'XP LANE', 'Hero Favorit: yuzhong')">
        <img src="https://i.supaimg.com/458a2a91-d780-44d3-9f1e-3ac8b352b20a.jpg" alt="yuzhong">
        <div class="hero-info"><h3>masgliez</h3><p>XP LANE</p></div>
      </div>
      <div class="hero-card" onclick="openModal('AINZZ', 'ROAM', 'Hero Favorit: jonshon')">
        <img src="https://i.supaimg.com/7c42dcee-43d1-4e77-adce-a81bdad0dd91.jpg" alt="jonshon">
        <div class="hero-info"><h3>AINZZ</h3><p>ROAM</p></div>
      </div>
      <div class="hero-card" onclick="openModal('cheys', 'JUNGLER', 'Hero Favorit: lancelot')">
        <img src="https://i.supaimg.com/2d81db97-8749-43f9-89ce-e4563cd6cc7f.jpg" alt="lancelot">
        <div class="hero-info"><h3>cheys</h3><p>JUNGLER</p></div>
      </div>
    </div>
  </section>

  <!-- Halaman 2 -->
  <section id="page2" style="display:none;">
    <header>
      <h1>Tentang 696 Party</h1>
    </header>

    <nav>
      <button onclick="showPage(1)">Halaman 1</button>
      <button onclick="showPage(2)">Halaman 2</button>
    </nav>

    <div class="about-text">
      <p>696 PARTY adalah sebuah tim Mobile Legends yang berisi 8 anggota. 
      Setiap anggota memiliki peran penting dalam pertandingan dan selalu berusaha kompak.</p>
    </div>

    <div class="sticker">
      <img src="https://i.supaimg.com/e391ad44-8ad2-4623-8016-719a2ef80f12.png" alt="Stiker 1" style="max-width:250px;border-radius:12px;">
    </div>

    <div class="about-text">
      <p>Selain itu, tim ini juga sudah banyak mengikuti turnamen kecil maupun besar. 
      Kerja sama dan semangat adalah kunci kemenangan mereka.</p>
    </div>

    <div class="sticker">
      <img src="https://i.supaimg.com/7f38c05e-06a7-416e-a6cb-11f18e2daf26.jpg" alt="Stiker 2" style="max-width:250px;border-radius:12px;">
    </div>
  </section>

  <!-- Modal Hero -->
  <div class="modal" id="heroModal">
    <div class="modal-content">
      <h2 id="heroName"></h2>
      <p id="heroRole"></p>
      <p id="heroFav"></p>
      <button onclick="closeModal()">Tutup</button>
    </div>
  </div>

  <script>
    // Stars animation
    const canvas = document.getElementById('stars');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    let stars = [];
    for (let i=0; i<100; i++){
      stars.push({
        x: Math.random()*canvas.width,
        y: Math.random()*canvas.height,
        r: Math.random()*2+1,
        d: Math.random()*0.5
      });
    }

    function drawStars(){
      ctx.clearRect(0,0,canvas.width,canvas.height);
      ctx.fillStyle = "white";
      ctx.beginPath();
      for(let i=0;i<stars.length;i++){
        const s = stars[i];
        ctx.moveTo(s.x, s.y);
        ctx.arc(s.x, s.y, s.r, 0, Math.PI*2, true);
      }
      ctx.fill();
      updateStars();
    }

    function updateStars(){
      for(let i=0;i<stars.length;i++){
        const s = stars[i];
        s.y += s.d;
        if(s.y > canvas.height){
          s.y = 0;
          s.x = Math.random()*canvas.width;
        }
      }
    }

    setInterval(drawStars, 50);

    // Page navigation & modal
    function startParty(){
      document.getElementById("intro").style.display="none";
      document.getElementById("page1").style.display="block";
    }
    function showPage(num){
      document.getElementById("page1").style.display = (num===1) ? "block" : "none";
      document.getElementById("page2").style.display = (num===2) ? "block" : "none";
    }
    function openModal(name, role, fav){
      document.getElementById("heroName").innerText = name;
      document.getElementById("heroRole").innerText = "Role: " + role;
      document.getElementById("heroFav").innerText = fav;
      document.getElementById("heroModal").style.display = "flex";
    }
    function closeModal(){
      document.getElementById("heroModal").style.display = "none";
    }
  </script>
</body>
</html>
