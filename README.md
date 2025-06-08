<!DOCTYPE html>
<html lang="uz">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mening Portfolio - Shaxsiy Ma'lumotlar</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Arial', sans-serif;
    }

    body {
      background: linear-gradient(45deg, #0a0a0a, #1a1a2e, #16213e, #0f0f23, #2d1b69);
      background-size: 400% 400%;
      animation: gradientShift 10s ease infinite;
      color: #fff;
      overflow-x: hidden;
      min-height: 100vh;
      line-height: 1.6;
    }

    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .container {
      max-width: 1400px;
      margin: 0 auto;
      padding: 20px;
      position: relative;
    }

    /* Header */
    .header {
      text-align: center;
      padding: 40px 0;
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(20px);
      border-radius: 30px;
      margin-bottom: 40px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      animation: headerGlow 4s ease-in-out infinite alternate;
    }

    @keyframes headerGlow {
      from { box-shadow: 0 10px 40px rgba(138, 43, 226, 0.4); }
      to { box-shadow: 0 10px 40px rgba(0, 191, 255, 0.4); }
    }

    .profile-image {
      width: 200px;
      height: 200px;
      border-radius: 50%;
      margin: 0 auto 30px;
      background: linear-gradient(45deg, #ff6b6b, #4ecdc4, #45b7d1);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 80px;
      animation: profilePulse 3s ease-in-out infinite alternate;
      border: 5px solid rgba(255, 255, 255, 0.3);
      box-shadow: 0 0 30px rgba(255, 255, 255, 0.2);
    }

    @keyframes profilePulse {
      from { transform: scale(1); }
      to { transform: scale(1.05); }
    }

    .main-title {
      font-size: 3.5em;
      background: linear-gradient(45deg, #ff3366, #ff6b6b, #4ecdc4, #45b7d1, #96ceb4, #ffd93d);
      background-size: 600% 600%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: rainbowText 4s ease-in-out infinite;
      margin-bottom: 20px;
    }

    @keyframes rainbowText {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .subtitle {
      font-size: 1.4em;
      color: #ccc;
      margin-bottom: 30px;
    }

    /* Main Grid */
    .main-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
      gap: 30px;
      margin: 40px 0;
    }

    /* Section Cards */
    .section-card {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      border-radius: 25px;
      padding: 30px;
      border: 1px solid rgba(255, 255, 255, 0.2);
      transition: all 0.4s ease;
      position: relative;
    }

    .section-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
    }

    .section-card h2 {
      font-size: 2em;
      margin-bottom: 20px;
      background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      display: flex;
      align-items: center;
      gap: 15px;
    }

    /* Personal Info Styles */
    .info-item {
      display: flex;
      justify-content: space-between;
      padding: 15px 0;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.3s ease;
    }

    .info-item:hover {
      background: rgba(255, 255, 255, 0.05);
      border-radius: 10px;
      padding-left: 10px;
    }

    .info-label {
      font-weight: bold;
      color: #4ecdc4;
    }

    .info-value {
      color: #fff;
      text-align: right;
    }

    /* Countries Grid */
    .countries-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }

    .country-card {
      background: linear-gradient(135deg, rgba(255, 107, 107, 0.2), rgba(78, 205, 196, 0.2));
      padding: 15px;
      border-radius: 15px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      border: 1px solid rgba(255, 255, 255, 0.1);
      position: relative;
    }

    .country-card:hover {
      transform: scale(1.05) rotateY(10deg);
      box-shadow: 0 10px 25px rgba(78, 205, 196, 0.3);
    }

    .country-flag {
      font-size: 30px;
      margin-bottom: 10px;
    }

    .country-name {
      font-size: 14px;
      font-weight: bold;
    }

    /* Jobs Grid */
    .jobs-grid {
      display: flex;
      flex-direction: column;
      gap: 20px;
      margin-top: 20px;
    }

    .job-card {
      background: linear-gradient(135deg, rgba(69, 183, 209, 0.2), rgba(150, 206, 180, 0.2));
      padding: 20px;
      border-radius: 15px;
      border-left: 5px solid #45b7d1;
      transition: all 0.4s ease;
      cursor: pointer;
    }

    .job-card:hover {
      transform: translateX(10px);
      box-shadow: 0 10px 25px rgba(69, 183, 209, 0.3);
    }

    .job-title {
      font-size: 18px;
      font-weight: bold;
      color: #4ecdc4;
      margin-bottom: 10px;
    }

    .job-company {
      color: #ccc;
      margin-bottom: 5px;
    }

    .job-period {
      color: #999;
      font-size: 14px;
    }

    /* People Grid */
    .people-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .person-card {
      background: linear-gradient(135deg, rgba(255, 107, 107, 0.2), rgba(245, 87, 108, 0.2));
      padding: 20px;
      border-radius: 20px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
    }

    .person-card:hover {
      transform: scale(1.08) rotateZ(3deg);
      box-shadow: 0 15px 30px rgba(255, 107, 107, 0.4);
    }

    .person-avatar {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: linear-gradient(45deg, #667eea, #764ba2);
      margin: 0 auto 15px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 35px;
    }

    .person-name {
      font-weight: bold;
      color: #ff6b6b;
      margin-bottom: 10px;
    }

    /* Movies Grid */
    .movies-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .movie-genre {
      background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(118, 75, 162, 0.2));
      padding: 25px;
      border-radius: 20px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .movie-genre:hover {
      transform: translateY(-8px) scale(1.02);
      box-shadow: 0 15px 35px rgba(102, 126, 234, 0.4);
    }

    .genre-icon {
      font-size: 40px;
      margin-bottom: 15px;
    }

    .genre-name {
      font-size: 18px;
      font-weight: bold;
      color: #667eea;
      margin-bottom: 10px;
    }

    .genre-movies {
      font-size: 14px;
      color: #ccc;
    }

    /* Skills Grid */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .skill-card {
      background: linear-gradient(135deg, rgba(255, 193, 7, 0.2), rgba(255, 87, 34, 0.2));
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .skill-card:hover {
      transform: translateY(-5px) scale(1.02);
      box-shadow: 0 10px 25px rgba(255, 193, 7, 0.4);
    }

    .skill-icon {
      font-size: 35px;
      margin-bottom: 15px;
    }

    .skill-name {
      font-size: 16px;
      font-weight: bold;
      color: #ffc107;
      margin-bottom: 5px;
    }

    .skill-level {
      font-size: 14px;
      color: #ccc;
    }

    /* Interests Grid */
    .interests-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }

    .interest-card {
      background: linear-gradient(135deg, rgba(76, 175, 80, 0.2), rgba(139, 195, 74, 0.2));
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .interest-card:hover {
      transform: rotateY(10deg) scale(1.05);
      box-shadow: 0 10px 25px rgba(76, 175, 80, 0.4);
    }

    .interest-icon {
      font-size: 30px;
      margin-bottom: 10px;
    }

    .interest-name {
      font-size: 14px;
      font-weight: bold;
      color: #4caf50;
    }

    /* Languages Grid */
    .languages-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }

    .language-card {
      background: linear-gradient(135deg, rgba(156, 39, 176, 0.2), rgba(233, 30, 99, 0.2));
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .language-card:hover {
      transform: scale(1.08) rotateZ(-3deg);
      box-shadow: 0 10px 25px rgba(156, 39, 176, 0.4);
    }

    .language-flag {
      font-size: 25px;
      margin-bottom: 10px;
    }

    .language-name {
      font-size: 14px;
      font-weight: bold;
      color: #9c27b0;
      margin-bottom: 5px;
    }

    .language-level {
      font-size: 12px;
      color: #ccc;
    }

    /* Contact Grid */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 15px;
      margin-top: 20px;
    }

    .contact-card {
      background: linear-gradient(135deg, rgba(0, 150, 136, 0.2), rgba(0, 188, 212, 0.2));
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      cursor: pointer;
      transition: all 0.4s ease;
      position: relative;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }

    .contact-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(0, 150, 136, 0.4);
    }

    .contact-icon {
      font-size: 30px;
      margin-bottom: 10px;
    }

    .contact-name {
      font-size: 16px;
      font-weight: bold;
      color: #009688;
      margin-bottom: 5px;
    }

    .contact-info {
      font-size: 14px;
      color: #ccc;
    }

    /* Tooltip */
    .tooltip {
      position: absolute;
      background: rgba(0, 0, 0, 0.9);
      color: white;
      padding: 20px;
      border-radius: 15px;
      font-size: 14px;
      z-index: 1000;
      min-width: 300px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
      border: 1px solid rgba(255, 255, 255, 0.2);
      display: none;
      animation: tooltipFadeIn 0.3s ease;
      white-space: pre-line;
    }

    @keyframes tooltipFadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .tooltip h4 {
      color: #4ecdc4;
      margin-bottom: 10px;
      font-size: 16px;
    }

    .tooltip p {
      margin-bottom: 8px;
      line-height: 1.4;
    }

    /* Responsive Design */
    @media (max-width: 1024px) {
      .main-title { font-size: 2.8em; }
      .main-grid { grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); }
      .profile-image { width: 160px; height: 160px; font-size: 60px; }
    }

    @media (max-width: 768px) {
      .main-title { font-size: 2.2em; }
      .main-grid { grid-template-columns: 1fr; gap: 20px; }
      .section-card { padding: 20px; }
      .profile-image { width: 140px; height: 140px; font-size: 50px; }
      .countries-grid { grid-template-columns: repeat(auto-fit, minmax(100px, 1fr)); }
      .people-grid { grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); }
      .movies-grid { grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); }
      .skills-grid { grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); }
      .interests-grid { grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); }
      .languages-grid { grid-template-columns: repeat(auto-fit, minmax(120px, 1fr)); }
      .contact-grid { grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); }
    }

    @media (max-width: 480px) {
      .main-title { font-size: 1.8em; }
      .subtitle { font-size: 1.1em; }
      .container { padding: 15px; }
      .section-card { padding: 15px; }
      .profile-image { width: 120px; height: 120px; font-size: 40px; }
      .tooltip { min-width: 250px; padding: 15px; }
    }

    /* Floating Elements */
    .floating-element {
      position: fixed;
      pointer-events: none;
      z-index: 1;
      opacity: 0.1;
    }

    .floating-shape {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: linear-gradient(45deg, rgba(255, 107, 107, 0.3), rgba(78, 205, 196, 0.3));
      animation: floatAround 25s linear infinite;
    }

    @keyframes floatAround {
      0% { transform: translateX(0px) translateY(0px) rotate(0deg); }
      25% { transform: translateX(150px) translateY(-150px) rotate(90deg); }
      50% { transform: translateX(300px) translateY(0px) rotate(180deg); }
      75% { transform: translateX(150px) translateY(150px) rotate(270deg); }
      100% { transform: translateX(0px) translateY(0px) rotate(360deg); }
    }
  </style>
</head>
<body>
  <!-- Floating Background Elements -->
  <div class="floating-element floating-shape" style="top: 5%; left: 5%; animation-delay: 0s;"></div>
  <div class="floating-element floating-shape" style="top: 15%; right: 5%; animation-delay: -8s;"></div>
  <div class="floating-element floating-shape" style="bottom: 15%; left: 15%; animation-delay: -16s;"></div>
  <div class="floating-element floating-shape" style="bottom: 5%; right: 15%; animation-delay: -24s;"></div>

  <div class="container">
    <!-- Header -->
    <div class="header">
      <div class="profile-image">👤</div>
      <h1 class="main-title">Ismoilov Muhammad</h1>
      <p class="subtitle">About by me</p>
    </div>

    <!-- Main Content Grid -->
    <div class="main-grid">
      
      <!-- Personal Information -->
      <div class="section-card">
        <h2>📋 Shaxsiy Ma'lumotlar</h2>
        <div class="info-item">
          <span class="info-label">Ism:</span>
          <span class="info-value">Ismoilov Muhammad</span>
        </div>
        <div class="info-item">
          <span class="info-label">Yosh:</span>
          <span class="info-value">15 yosh</span>
        </div>
        <div class="info-item">
          <span class="info-label">Millat:</span>
          <span class="info-value">O'zbek</span>
        </div>
        <div class="info-item">
          <span class="info-label">Tug'ilgan sana:</span>
          <span class="info-value">21.11.2009</span>
        </div>
        <div class="info-item">
          <span class="info-label">Passport:</span>
          <span class="info-value">I-AN 0037515</span>
        </div>
        <div class="info-item">
          <span class="info-label">Manzil:</span>
          <span class="info-value">Toshkent,30-mavze</span>
        </div>
        <div class="info-item">
          <span class="info-label">Kasb:</span>
          <span class="info-value">Dasturchi</span>
        </div>
        <div class="info-item">
          <span class="info-label">Ta'lim:</span>
          <span class="info-value">Tehnikum litseyi</span>
        </div>
         <div class="info-item">
          <span class="info-label">Bo'y</span>
          <span class="info-value">180</span>
        </div>
         <div class="info-item">
          <span class="info-label">Vazn</span>
          <span class="info-value">60</span>
        </div>
      </div>

      <!-- Visited Countries -->
      <div class="section-card">
        <h2>🌍 Tashrif Buyurgan Davlatlar</h2>
        <div class="countries-grid">
          <div class="country-card" onmouseover="showCountryTooltip(event, 'turkey')" onmouseout="hideTooltip()">
            <div class="country-flag">🇹🇷</div>
            <div class="country-name">Turkiya</div>
          </div>
          <div class="country-card" onmouseover="showCountryTooltip(event, 'uae')" onmouseout="hideTooltip()">
            <div class="country-flag">🇰🇬</div>
            <div class="country-name">Kyrgyzstan</div>
          </div>
          <div class="country-card" onmouseover="showCountryTooltip(event, 'russia')" onmouseout="hideTooltip()">
            <div class="country-flag">🇰🇿</div>
            <div class="country-name">Kazakhstan</div>
          </div>
          <div class="country-card" onmouseover="showCountryTooltip(event, 'kazakhstan')" onmouseout="hideTooltip()">
            <div class="country-flag">🇾🇪</div>
            <div class="country-name">Egypt</div>
          </div>
        </div>
      </div>

      <!-- Work Experience -->
      <div class="section-card">
        <h2>💼 Ishchi Joylar</h2>
        <div class="jobs-grid">
          <div class="job-card" onmouseover="showJobTooltip(event, 'current')" onmouseout="hideTooltip()">
            <div class="job-title">Frontent Dasturchi</div>
            <div class="job-company">Yaprak home</div>
            <div class="job-period">2024</div>
          </div>
          <div class="job-card" onmouseover="showJobTooltip(event, 'prev1')" onmouseout="hideTooltip()">
            <div class="job-title">Sotuvchi</div>
            <div class="job-company">Yaprak home</div>
            <div class="job-period">2024</div>
          </div>
          <div class="job-card" onmouseover="showJobTooltip(event, 'prev2')" onmouseout="hideTooltip()">
            <div class="job-title">Operator</div>
            <div class="job-company">1life</div>
            <div class="job-period">2024</div>
          </div>
          <div class="job-card" onmouseover="showJobTooltip(event, 'intern')" onmouseout="hideTooltip()">
            <div class="job-title">Gaza block</div>
            <div class="job-company">Zhong Cheng</div>
            <div class="job-period">2023</div>
          </div>
        </div>
      </div>

      <!-- Favorite People -->
      <div class="section-card">
        <h2>⭐ Yoqtirgan Odamlar</h2>
        <div class="people-grid">
          <div class="person-card" onmouseover="showPersonTooltip(event, 'elon')" onmouseout="hideTooltip()">
            <div class="person-avatar">❤️</div>
            <div class="person-name">!no</div>
          </div>
          <div class="person-card" onmouseover="showPersonTooltip(event, 'jobs')" onmouseout="hideTooltip()">
            <div class="person-avatar">🥶</div>
            <div class="person-name">Cristiano Ronaldo</div>
          </div>
          <div class="person-card" onmouseover="showPersonTooltip(event, 'gates')" onmouseout="hideTooltip()">
            <div class="person-avatar">💻</div>
            <div class="person-name">x hackers</div>
          </div>
          <div class="person-card" onmouseover="showPersonTooltip(event, 'navoiy')" onmouseout="hideTooltip()">
            <div class="person-avatar">🎭</div>
            <div class="person-name">Kim ji won</div>
          </div>
          <div class="person-card" onmouseover="showPersonTooltip(event, 'mirziyoyev')" onmouseout="hideTooltip()">
            <div class="person-avatar">🕷</div>
            <div class="person-name">Peter</div>
          </div>
          <div class="person-card" onmouseover="showPersonTooltip(event, 'einstein')" onmouseout="hideTooltip()">
            <div class="person-avatar">🧠</div>
            <div class="person-name">Lana del rey <br> Billie Eilish</div>
          </div>
        </div>
      </div>

      <!-- Movie Genres -->
      <div class="section-card">
        <h2>🎬 Yoqtirgan Kino Janrlari</h2>
        <div class="movies-grid">
          <div class="movie-genre" onmouseover="showMovieTooltip(event, 'action')" onmouseout="hideTooltip()">
            <div class="genre-icon">❤️‍🔥</div>
            <div class="genre-name">Kdrama</div>
            <div class="genre-movies">25+ film</div>
          </div>
          <div class="movie-genre" onmouseover="showMovieTooltip(event, 'scifi')" onmouseout="hideTooltip()">
            <div class="genre-icon">🌠</div>
            <div class="genre-name">Marvel</div>
            <div class="genre-movies">10+ film</div>
          </div>
          <div class="movie-genre" onmouseover="showMovieTooltip(event, 'drama')" onmouseout="hideTooltip()">
            <div class="genre-icon">⚔️</div>
            <div class="genre-name">Turk serial</div>
            <div class="genre-movies">15+ film</div>
          </div>
          <div class="movie-genre" onmouseover="showMovieTooltip(event, 'comedy')" onmouseout="hideTooltip()">
            <div class="genre-icon">😂</div>
            <div class="genre-name">Comedy</div>
            <div class="genre-movies">15+ film</div>
          </div>
          <div class="movie-genre" onmouseover="showMovieTooltip(event, 'horror')" onmouseout="hideTooltip()">
            <div class="genre-icon">👻</div>
            <div class="genre-name">Horror</div>
            <div class="genre-movies">12+ film</div>
          </div>
        </div>
      </div>

      <!-- Skills -->
      <div class="section-card">
        <h2>🛠️ Ko'nikmalar</h2>
        <div class="skills-grid">
          <div class="skill-card" onmouseover="showSkillTooltip(event, 'javascript')" onmouseout="hideTooltip()">
            <div class="skill-icon">🟨</div>
            <div class="skill-name">JavaScript</div>
            <div class="skill-level">Expert</div>
          </div>
          <div class="skill-card" onmouseover="showSkillTooltip(event, 'python')" onmouseout="hideTooltip()">
            <div class="skill-icon">🐍</div>
            <div class="skill-name">Python</div>
            <div class="skill-level">Intermediate</div>
          </div>
          <div class="skill-card" onmouseover="showSkillTooltip(event, 'database')" onmouseout="hideTooltip()">
            <div class="skill-icon">🗄️</div>
            <div class="skill-name">Html/css</div>
            <div class="skill-level">Advanced</div>
          </div>
          <div class="skill-card" onmouseover="showSkillTooltip(event, 'design')" onmouseout="hideTooltip()">
            <div class="skill-icon">🎨</div>
            <div class="skill-name">figma/django</div>
            <div class="skill-level">Intermediate</div>
          </div>
        </div>
      </div>

      <!-- Interests -->
      <div class="section-card">
        <h2>🎯 Qiziqishlar</h2>
        <div class="interests-grid">
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'coding')" onmouseout="hideTooltip()">
            <div class="interest-icon">💻</div>
            <div class="interest-name">Dasturlash</div>
          </div>
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'travel')" onmouseout="hideTooltip()">
            <div class="interest-icon">✈️</div>
            <div class="interest-name">Sayohat</div>
          </div>
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'reading')" onmouseout="hideTooltip()">
            <div class="interest-icon">📚</div>
            <div class="interest-name">Kitob o'qish</div>
          </div>
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'music')" onmouseout="hideTooltip()">
            <div class="interest-icon">🎵</div>
            <div class="interest-name">Musiqa</div>
          </div>
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'photography')" onmouseout="hideTooltip()">
            <div class="interest-icon">📸</div>
            <div class="interest-name">Fotografiya</div>
          </div>
          <div class="interest-card" onmouseover="showInterestTooltip(event, 'gaming')" onmouseout="hideTooltip()">
            <div class="interest-icon">🎮</div>
            <div class="interest-name">O'yin</div>
          </div>
        </div>
      </div>

      <!-- Languages -->
      <div class="section-card">
        <h2>🌐 Tillar</h2>
        <div class="languages-grid">
          <div class="language-card" onmouseover="showLanguageTooltip(event, 'uzbek')" onmouseout="hideTooltip()">
            <div class="language-flag">🇺🇿</div>
            <div class="language-name">O'zbek tili</div>
            <div class="language-level">Ona tili</div>
          </div>
          <div class="language-card" onmouseover="showLanguageTooltip(event, 'russian')" onmouseout="hideTooltip()">
            <div class="language-flag">🇷🇺</div>
            <div class="language-name">Rus tili</div>
            <div class="language-level">100/5</div>
          </div>
          <div class="language-card" onmouseover="showLanguageTooltip(event, 'english')" onmouseout="hideTooltip()">
            <div class="language-flag">🇺🇸</div>
            <div class="language-name">Ingliz tili</div>
            <div class="language-level">A2</div>
          </div>
          <div class="language-card" onmouseover="showLanguageTooltip(event, 'turkish')" onmouseout="hideTooltip()">
            <div class="language-flag">🇹🇷</div>
            <div class="language-name">Turk tili</div>
            <div class="language-level">Intermediate</div>
          </div>
          <div class="language-card" onmouseover="showLanguageTooltip(event, 'arabic')" onmouseout="hideTooltip()">
            <div class="language-flag">🕌</div>
            <div class="language-name">Arab tili</div>
            <div class="language-level">once read</div>
          </div>
        </div>
      </div>

      <!-- Contact Info -->
      <div class="section-card">
        <h2>📞 Aloqa Ma'lumotlari</h2>
        <div class="contact-grid">
          <div class="contact-card" onmouseover="showContactTooltip(event, 'phone')" onmouseout="hideTooltip()">
            <div class="contact-icon">📱</div>
            <div class="contact-name">Telefon</div>
            <div class="contact-info">+998 33 009 11 21</div>
          </div>
          <div class="contact-card" onmouseover="showContactTooltip(event, 'email')" onmouseout="hideTooltip()">
            <div class="contact-icon">📧</div>
            <div class="contact-name">Email</div>
            <div class="contact-info">mukhammatismoilovimj@email.com</div>
          </div>
          <div class="contact-card" onmouseover="showContactTooltip(event, 'telegram')" onmouseout="hideTooltip()">
            <div class="contact-icon">✈️</div>
            <div class="contact-name">Telegram</div>
            <div class="contact-info">@lunaxvibe</div>
          </div>
          <div class="contact-card" onmouseover="showContactTooltip(event, 'github')" onmouseout="hideTooltip()">
            <div class="contact-icon">💻</div>
            <div class="contact-name">GitHub</div>
            <div class="contact-info">github.com/ismoilovM</div>
          </div>
          <div class="contact-card" onmouseover="showContactTooltip(event, 'instagram')" onmouseout="hideTooltip()">
            <div class="contact-icon">📷</div>
            <div class="contact-name">Instagram</div>
            <div class="contact-info">@mukhammat_rizz</div>
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- Tooltip -->
  <div id="tooltip" class="tooltip"></div>

  <script>
    const tooltip = document.getElementById('tooltip');

    // Country tooltips
    function showCountryTooltip(event, country) {
      const countryData = {
        turkey: {
          title: 'Turkiya',
          content: `Tashrif buyurgan sana: 2023 yil
Shaharlar: Istanbul, Antalya, Ankara
Davomiylik: 15 kun
Maqsad: Sayohat va madaniy tanishuv
Taassurot: Ajoyib arxitektura va tarix`
        },
        uae: {
          title: 'Birlashgan Arab Amirliklari',
          content: `Tashrif buyurgan sana: 2022 yil
Shaharlar: Dubay, Abu-Dabi
Davomiylik: 7 kun
Maqsad: Biznes safari
Taassurot: Zamonaviy arxitektura va texnologiya`
        },
        russia: {
          title: 'Rossiya',
          content: `Tashrif buyurgan sana: 2021 yil
Shaharlar: Moskva, Sankt-Peterburg
Davomiylik: 10 kun
Maqsad: Ta'lim va madaniyat
Taassurot: Boy tarix va san'at`
        },
        kazakhstan: {
          title: 'Qozog\'iston',
          content: `Tashrif buyurgan sana: 2020 yil
Shaharlar: Almaty, Nur-Sultan
Davomiylik: 5 kun
Maqsad: Qarindoshlarni ziyorat
Taassurot: O'xshash madaniyat va til`
        },
        kyrgyzstan: {
          title: 'Qirg\'iziston',
          content: `Tashrif buyurgan sana: 2019 yil
Shaharlar: Bishkek, Osh
Davomiylik: 3 kun
Maqsad: Tog'li hududlarni ko'rish
Taassurot: Go'zal tabiat va tog'lar`
        },
        tajikistan: {
          title: 'Tojikiston',
          content: `Tashrif buyurgan sana: 2018 yil
Shaharlar: Dushanbe, Khorog
Davomiylik: 4 kun
Maqsad: Tabiiy go'zalliklarni ko'rish
Taassurot: Pamir tog'lari va madaniyat`
        }
      };
      
      const data = countryData[country];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Job tooltips
    function showJobTooltip(event, job) {
      const jobData = {
        current: {
          title: 'Senior Frontend Developer - TechCorp Solutions',
          content: `Vazifalar:
• React va Vue.js loyihalarini yaratish
• Jamoa bilan hamkorlik qilish
• Code review va mentoring
• Performance optimization

Texnologiyalar: React, Vue.js, TypeScript, Node.js
Yutuqlar: 15+ loyiha yakunlandi`
        },
        prev1: {
          title: 'Web Developer - Digital Agency',
          content: `Vazifalar:
• Responsive web saytlar yaratish
• Client bilan aloqa
• SEO optimization
• Database design

Texnologiyalar: HTML, CSS, JavaScript, PHP, MySQL
Yutuqlar: 25+ sayt yaratildi`
        },
        prev2: {
          title: 'Junior Developer - StartUp Inc',
          content: `Vazifalar:
• Bug fixing va testing
• Feature development
• Documentation yozish
• Team meetings

Texnologiyalar: JavaScript, HTML, CSS, Git
Yutuqlar: Programming asoslarini o'rgandim`
        },
        intern: {
          title: 'Intern Developer - IT Academy',
          content: `Vazifalar:
• Dasturlash asoslarini o'rganish
• Kichik loyihalar ustida ishlash
• Mentorlar bilan ishlash
• Portfolio yaratish

Texnologiyalar: HTML, CSS, JavaScript
Yutuqlar: Web development asoslarini egallashim`
        }
      };
      
      const data = jobData[job];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Person tooltips
    function showPersonTooltip(event, person) {
      const personData = {
        elon: {
          title: 'Elon Musk',
          content: `Hayoti: 1971 yilda tug'ilgan, Janubiy Afrika
Ijodi: Tesla, SpaceX, Neuralink kompaniyalarini yaratgan
Sevgisi: Grimes bilan munosabatda bo'lgan, hozir yolg'iz
Yutuqlari: Elektr mashinalar va kosmik texnologiyalar sohasida inqilob
Nima uchun yoqtiraman: Innovatsiya va kelajakka qarash`
        },
        jobs: {
          title: 'Steve Jobs',
          content: `Hayoti: 1955-2011, Amerika
Ijodi: Apple kompaniyasini yaratgan, iPhone ixtirochisi
Sevgisi: Laurene Powell Jobs bilan uylangan
Yutuqlari: Shaxsiy kompyuter va smartfonlar inqilobi
Nima uchun yoqtiraman: Dizayn va foydalanuvchi tajribasiga e'tibor`
        },
        gates: {
          title: 'Bill Gates',
          content: `Hayoti: 1955 yilda tug'ilgan, Amerika
Ijodi: Microsoft kompaniyasini yaratgan
Sevgisi: Melinda bilan ajrashgan, hozir yolg'iz
Yutuqlari: Shaxsiy kompyuterlarni ommalashtirish
Nima uchun yoqtiraman: Xayriya ishlar va ta'limga qo'shgan hissasi`
        },
        navoiy: {
          title: 'Alisher Navoiy',
          content: `Hayoti: 1441-1501, Hirot
Ijodi: "Xamsa", "Mahbub ul-qulub" asarlari
Sevgisi: Adabiyot va she'riyatga bag'ishlagan hayot
Yutuqlari: O'zbek adabiyotining otasi
Nima uchun yoqtiraman: Milliy adabiyotimizning asoschiligiga hurmat`
        },
        mirziyoyev: {
          title: 'Shavkat Mirziyoyev',
          content: `Hayoti: 1957 yilda tug'ilgan, Jizzax
Ijodi: O'zbekiston Respublikasining Prezidenti
Sevgisi: Oila a'zosi, farzandlar otasi
Yutuqlari: Mamlakatni isloh qilish va rivojlantirish
Nima uchun yoqtiraman: Mamlakatni modernizatsiya qilish sa'y-harakatlari`
        },
        einstein: {
          title: 'Albert Einstein',
          content: `Hayoti: 1879-1955, Germaniya/Amerika
Ijodi: Nisbiylik nazariyasi, E=mc² formulasi
Sevgisi: Ikki marta turmushga chiqqan
Yutuqlari: Fizika sohasida inqilobiy kashfiyotlar
Nima uchun yoqtiraman: Ilm-fanga qo'shgan ulkan hissasi`
        }
      };
      
      const data = personData[person];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Movie tooltips
    function showMovieTooltip(event, genre) {
      const movieData = {
        action: {
          title: 'Action Filmlari',
          content: `Sevimli filmlar:
• The Matrix seriyasi
• John Wick seriyasi
• Mission Impossible
• Fast & Furious
• Marvel filmlari

Nima uchun yoqtiraman: Dinamiklik va hayajonli sahnalar`
        },
        scifi: {
          title: 'Sci-Fi Filmlari',
          content: `Sevimli filmlar:
• Interstellar
• Blade Runner 2049
• Inception
• The Martian
• Ex Machina

Nima uchun yoqtiraman: Kelajak va texnologiya haqida o'ylash`
        },
        drama: {
          title: 'Drama Filmlari',
          content: `Sevimli filmlar:
• The Shawshank Redemption
• Forrest Gump
• The Godfather
• Schindler's List
• 12 Years a Slave

Nima uchun yoqtiraman: Chuqur hissiyotlar va hayotiy darslar`
        },
        comedy: {
          title: 'Comedy Filmlari',
          content: `Sevimli filmlar:
• The Hangover seriyasi
• Superbad
• Pineapple Express
• Step Brothers
• Anchorman

Nima uchun yoqtiraman: Stress relieve va kulgi`
        },
        thriller: {
          title: 'Thriller Filmlari',
          content: `Sevimli filmlar:
• Se7en
• The Silence of the Lambs
• Zodiac
• Gone Girl
• Prisoners

Nima uchun yoqtiraman: Suspense va mystery`
        },
        horror: {
          title: 'Horror Filmlari',
          content: `Sevimli filmlar:
• The Conjuring seriyasi
• Hereditary
• A Quiet Place
• Get Out
• It seriyasi

Nima uchun yoqtiraman: Adrenalin va qo'rquv hissi`
        }
      };
      
      const data = movieData[genre];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Skill tooltips
    function showSkillTooltip(event, skill) {
      const skillData = {
        javascript: {
          title: 'JavaScript',
          content: `Daraja: Expert (5+ yil tajriba)
Texnologiyalar:
• ES6+, TypeScript
• DOM manipulation
• Async/Await, Promises
• Modern frameworks

Loyihalar: 50+ JavaScript loyihasi`
        },
        react: {
          title: 'React',
          content: `Daraja: Advanced (3+ yil tajriba)
Texnologiyalar:
• Hooks, Context API
• Redux, MobX
• Next.js, Gatsby
• Testing (Jest, RTL)

Loyihalar: 20+ React ilovasi`
        },
        nodejs: {
          title: 'Node.js',
          content: `Daraja: Advanced (3+ yil tajriba)
Texnologiyalar:
• Express.js, Fastify
• MongoDB, PostgreSQL
• JWT, Authentication
• RESTful APIs

Loyihalar: 15+ backend loyihasi`
        },
        python: {
          title: 'Python',
          content: `Daraja: Intermediate (2+ yil tajriba)
Texnologiyalar:
• Django, Flask
• Data Analysis
• Machine Learning basics
• Automation scripts

Loyihalar: 10+ Python loyihasi`
        },
        database: {
          title: 'Database',
          content: `Daraja: Advanced (4+ yil tajriba)
Texnologiyalar:
• MySQL, PostgreSQL
• MongoDB, Redis
• Database design
• Query optimization

Tajriba: 30+ database loyihasi`
        },
        design: {
          title: 'UI/UX Design',
          content: `Daraja: Intermediate (2+ yil tajriba)
Texnologiyalar:
• Figma, Adobe XD
• Photoshop, Illustrator
• User research
• Prototyping

Loyihalar: 25+ design loyihasi`
        }
      };
      
      const data = skillData[skill];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Interest tooltips
    function showInterestTooltip(event, interest) {
      const interestData = {
        coding: {
          title: 'Dasturlash',
          content: `Sevimli tillari: JavaScript, Python, Java
Kunlik faoliyat: 6-8 soat kod yozish
Open source: GitHub'da 20+ loyiha
O'rganayotgan: Machine Learning, Blockchain`
        },
        travel: {
          title: 'Sayohat',
          content: `Tashrif buyurgan: 6 ta davlat
Rejalar: Yaponiya, Koreya, Evropa
Sevimli faslim: Bahor va kuz
Transport: Samolyot va avtomobil`
        },
        reading: {
          title: 'Kitob o\'qish',
          content: `Sevimli janrlari: Fantastika, texnik kitoblar
Oyiga: 3-4 ta kitob
Sevimli mualliflar: Isaac Asimov, Robert Martin
Hozir o'qiyotgan: "Clean Architecture"`
        },
        music: {
          title: 'Musiqa',
          content: `Sevimli janrlari: Rock, Electronic, Classical
Asboblar: Gitara (boshlang'ich daraja)
Sevimli ijrochilar: Coldplay, Imagine Dragons
Kunlik: 2-3 soat musiqa tinglash`
        },
        sports: {
          title: 'Sport',
          content: `Sevimli sport turlari: Futbol, Tennis
Mashg'ulot: Haftada 3-4 marta
Futbol jamoasi: Barcelona tarafdori
Fitness: Har kuni ertalab 30 daqiqa`
        },
        photography: {
          title: 'Fotografiya',
          content: `Texnika: Canon EOS 2000D
Sevimli mavzular: Tabiat, portret
Instagram: 500+ rasm
Kurslar: Online fotografiya kurslari`
        },
        gaming: {
          title: 'O\'yin',
          content: `Platform: PC, PlayStation 5
Sevimli janrlar: Strategy, RPG, Action
Sevimli o'yinlar: Civilization VI, Witcher 3
Vaqt: Hafta oxirigida 4-5 soat`
        },
        cooking: {
          title: 'Oshpazlik',
          content: `Sevimli taomlar: O'zbek oshi, milliy taomlar
Xalqaro: Italyan, Yapon oshxonasi
Tajriba: 5+ yil uy sharoitida
Ixtisoslashuv: Milliy va Osiyo taomlari`
        }
      };
      
      const data = interestData[interest];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Language tooltips
    function showLanguageTooltip(event, language) {
      const languageData = {
        uzbek: {
          title: 'O\'zbek tili',
          content: `Daraja: Ona tili
Lahjalar: Toshkent lahajasi
Yozuv: Kirill va Lotin
Adabiyot: Klassik va zamonaviy asarlar`
        },
        russian: {
          title: 'Rus tili',
          content: `Daraja: Fluent (C1)
O'rganish: Maktabdan boshlab
Ishlatish: Kundalik muloqot, ishda
Sertifikat: TORFL-2 darajasi`
        },
        english: {
          title: 'Ingliz tili',
          content: `Daraja: Upper-Intermediate (B2)
O'rganish: 8+ yil tajriba
Ishlatish: Texnik hujjatlar, international projects
Sertifikat: IELTS 6.5`
        },
        turkish: {
          title: 'Turk tili',
          content: `Daraja: Intermediate (B1)
O'rganish: Sayohatlar orqali
Ishlatish: Turistik sayohatlar
Qiziqish: Turk seriallari va kinolari`
        },
        arabic: {
          title: 'Arab tili',
          content: `Daraja: Beginner (A1)
O'rganish: Diniy ta'lim orqali
Maqsad: Qur'on o'qish
Reja: Kurs olish va amaliyot`
        }
      };
      
      const data = languageData[language];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    // Contact tooltips
    function showContactTooltip(event, contact) {
      const contactData = {
        phone: {
          title: 'Telefon aloqasi',
          content: `Raqam: +998 90 123 45 67
Vaqt: 9:00 - 18:00 (ish kunlari)
WhatsApp: Mavjud
Telegram: @ahad_dev orqali ham`
        },
        email: {
          title: 'Email aloqasi',
          content: `Email: ahad@email.com
Javob vaqti: 24 soat ichida
Ishchi email: ahad.work@company.com
Portfolio: ahad-portfolio.com`
        },
        telegram: {
          title: 'Telegram',
          content: `Username: @ahad_dev
Faollik: Har kuni online
Bot: Shaxsiy bot mavjud
Guruhlar: IT va dasturlash guruhlari`
        },
        linkedin: {
          title: 'LinkedIn profil',
          content: `Profile: Ahad Abdullayev
Connections: 500+ professional
Experience: To'liq ish tajribasi
Articles: Texnik maqolalar`x
        },
        github: {
          title: 'GitHub profil',
          content: `Username: github.com/ahad
Repositories: 25+ public loyiha
Contributions: Har kuni faol
Stars: 100+ star olgan`
        },
        instagram: {
          title: 'Instagram profil',
          content: `Username: @ahad_abdullayev
Followers: 1000+ followers
Content: Lifestyle va travel
Stories: Kundalik yangiliklar`
        }
      };
      
      const data = contactData[contact];
      tooltip.innerHTML = `<h4>${data.title}</h4><p>${data.content}</p>`;
      showTooltip(event);
    }

    function showTooltip(event) {
      tooltip.style.display = 'block';
      tooltip.style.left = event.pageX + 10 + 'px';
      tooltip.style.top = event.pageY + 10 + 'px';
    }

    function hideTooltip() {
      tooltip.style.display = 'none';
    }

    // Prevent tooltip from going off screen
    document.addEventListener('mousemove', function(e) {
      if (tooltip.style.display === 'block') {
        const tooltipRect = tooltip.getBoundingClientRect();
        const windowWidth = window.innerWidth;
        const windowHeight = window.innerHeight;
        
        let left = e.pageX + 10;
        let top = e.pageY + 10;
        
        if (left + tooltipRect.width > windowWidth) {
          left = e.pageX - tooltipRect.width - 10;
        }
        
        if (top + tooltipRect.height > windowHeight) {
          top = e.pageY - tooltipRect.height - 10;
        }
        
        tooltip.style.left = left + 'px# about-by-me
