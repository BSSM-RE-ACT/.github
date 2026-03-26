<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BSSM RE:ACT — 부마로그</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans KR', sans-serif;
    background: #0d1117;
    color: #e6edf3;
    max-width: 860px;
    margin: 0 auto;
    padding: 2.5rem 1.5rem;
  }

  /* ── Header ── */
  .header {
    text-align: center;
    margin-bottom: 2rem;
  }
  .header-badge {
    display: inline-block;
    background: linear-gradient(135deg, #667eea, #764ba2, #f093fb);
    color: #fff;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 4px 14px;
    border-radius: 20px;
    margin-bottom: 1rem;
  }
  .title {
    font-size: 52px;
    font-weight: 900;
    letter-spacing: 4px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 50%, #f093fb 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1.1;
    margin-bottom: 0.5rem;
  }
  .subtitle {
    font-size: 15px;
    color: #8b949e;
    margin-bottom: 1.5rem;
  }

  /* ── Banner ── */
  .banner {
    width: 100%;
    border-radius: 14px;
    overflow: hidden;
    margin-bottom: 2rem;
  }
  .banner svg { display: block; width: 100%; }

  /* ── Section ── */
  .section { margin-bottom: 2rem; }
  .section-title {
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: #8b949e;
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid #21262d;
  }

  /* ── Cards ── */
  .card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
  }
  .card p {
    font-size: 14px;
    line-height: 1.8;
    color: #c9d1d9;
  }
  .card p strong { color: #e6edf3; }

  /* ── Project Card ── */
  .project-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 0.6rem;
  }
  .project-name {
    font-size: 18px;
    font-weight: 700;
    color: #58a6ff;
  }
  .project-desc {
    font-size: 14px;
    color: #8b949e;
    line-height: 1.6;
  }
  .project-tags { display: flex; flex-wrap: wrap; gap: 6px; }
  .tag {
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 20px;
    border: 1px solid;
    font-weight: 500;
  }
  .tag-blue  { color: #58a6ff; border-color: #1f6feb; background: rgba(31,111,235,0.12); }
  .tag-green { color: #3fb950; border-color: #238636; background: rgba(35,134,54,0.12); }
  .tag-purple{ color: #bc8cff; border-color: #8957e5; background: rgba(137,87,229,0.12); }
  .tag-pink  { color: #f778ba; border-color: #da3176; background: rgba(218,49,118,0.12); }

  /* ── Tech Stack ── */
  .stack-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
  .stack-item {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 1rem 1.25rem;
  }
  .stack-label {
    font-size: 11px;
    color: #8b949e;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 0.5rem;
  }
  .badge-row { display: flex; flex-wrap: wrap; gap: 6px; }
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 5px;
    background: #0d1117;
    border: 1px solid #30363d;
    border-radius: 6px;
    padding: 4px 10px;
    font-size: 12px;
    color: #c9d1d9;
  }
  .dot { width: 8px; height: 8px; border-radius: 50%; }

  /* ── Team ── */
  .team-grid { display: grid; grid-template-columns: repeat(5, 1fr); gap: 12px; }
  .member {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 1rem 0.5rem;
    text-align: center;
    transition: border-color 0.2s;
  }
  .member:hover { border-color: #8957e5; }
  .member img {
    width: 60px; height: 60px;
    border-radius: 50%;
    border: 2px solid #30363d;
    object-fit: cover;
    margin: 0 auto 8px;
    display: block;
  }
  .member .name { font-size: 13px; font-weight: 700; color: #e6edf3; margin-bottom: 3px; }
  .member .role { font-size: 11px; color: #8b949e; margin-bottom: 5px; }
  .member a { font-size: 11px; color: #58a6ff; text-decoration: none; }

  /* ── Stats ── */
  .stats-img {
    width: 100%;
    border-radius: 10px;
    border: 1px solid #21262d;
  }

  /* ── Contact ── */
  .contact-row {
    display: flex;
    align-items: center;
    gap: 10px;
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 1rem 1.25rem;
    font-size: 14px;
    color: #c9d1d9;
  }
  .contact-row strong { color: #e6edf3; }

  /* ── Footer ── */
  .footer {
    text-align: center;
    margin-top: 2rem;
    font-size: 12px;
    color: #484f58;
  }
  .footer span {
    background: linear-gradient(135deg, #667eea, #f093fb);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-weight: 700;
  }
</style>
</head>
<body>

  <!-- Header -->
  <div class="header">
    <div class="header-badge">BSSM · 2026</div>
    <div class="title">RE:ACT</div>
    <p class="subtitle">부산소프트웨어마이스터고등학교 자유 개발 동아리</p>
  </div>

  <!-- Banner -->
  <div class="banner">
    <svg viewBox="0 0 860 110" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="bg" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0%" stop-color="#0d1117"/>
          <stop offset="100%" stop-color="#0d1117"/>
        </linearGradient>
        <linearGradient id="line1" x1="0" y1="0" x2="1" y2="0">
          <stop offset="0%" stop-color="#667eea"/>
          <stop offset="50%" stop-color="#764ba2"/>
          <stop offset="100%" stop-color="#f093fb"/>
        </linearGradient>
      </defs>
      <rect width="860" height="110" fill="#161b22" rx="14"/>
      <path d="M0,55 Q80,20 160,55 Q240,90 320,55 Q400,20 480,55 Q560,90 640,55 Q720,20 800,55 L860,55" stroke="url(#line1)" stroke-width="2" fill="none" opacity="0.6"/>
      <path d="M0,70 Q90,35 180,70 Q270,105 360,70 Q450,35 540,70 Q630,105 720,70 L860,70" stroke="url(#line1)" stroke-width="1" fill="none" opacity="0.3"/>
      <text x="430" y="66" text-anchor="middle" font-family="-apple-system, sans-serif" font-size="28" font-weight="900" fill="#e6edf3" letter-spacing="6" opacity="0.95">BSSM RE:ACT</text>
    </svg>
  </div>

  <!-- About -->
  <div class="section">
    <div class="section-title">About Us</div>
    <div class="card">
      <p>
        <strong>RE:ACT</strong>는 부산소프트웨어마이스터고등학교의 자유 개발 동아리로,<br>
        오류 기록 문화를 만들고 함께 기술적으로 성장하는 것을 목표로 합니다.<br><br>
        실수를 두려워하지 않고 기록하고 공유함으로써 더 나은 개발자로 성장합니다.
      </p>
    </div>
  </div>

  <!-- Project -->
  <div class="section">
    <div class="section-title">Project</div>
    <div class="project-card">
      <div class="project-name">📝 부마로그 (Bumalogue)</div>
      <div class="project-desc">
        BSSM 학생들을 위한 오류 기록 및 공유 플랫폼.<br>
        개발 중 만나는 다양한 오류와 해결 과정을 기록하고, 팀원들과 지식을 나눕니다.
      </div>
      <div class="project-tags">
        <span class="tag tag-blue">오류 기록</span>
        <span class="tag tag-green">지식 공유</span>
        <span class="tag tag-purple">BSSM 전용</span>
        <span class="tag tag-pink">개발 문화</span>
      </div>
    </div>
  </div>

  <!-- Tech Stack -->
  <div class="section">
    <div class="section-title">Tech Stack</div>
    <div class="stack-grid">
      <div class="stack-item">
        <div class="stack-label">Frontend</div>
        <div class="badge-row">
          <span class="badge"><span class="dot" style="background:#61DAFB"></span>React</span>
          <span class="badge"><span class="dot" style="background:#fff"></span>Next.js</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-label">Backend</div>
        <div class="badge-row">
          <span class="badge"><span class="dot" style="background:#6DB33F"></span>Spring Boot</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-label">Design</div>
        <div class="badge-row">
          <span class="badge"><span class="dot" style="background:#F24E1E"></span>Figma</span>
        </div>
      </div>
      <div class="stack-item">
        <div class="stack-label">DevOps</div>
        <div class="badge-row">
          <span class="badge"><span class="dot" style="background:#2088FF"></span>GitHub Actions</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Team -->
  <div class="section">
    <div class="section-title">Our Team</div>
    <div class="team-grid">
      <div class="member">
        <img src="https://github.com/gunobo.png" alt="임제민">
        <div class="name">임제민</div>
        <div class="role">👑 Lead / Fullstack</div>
        <a href="https://github.com/gunobo">@gunobo</a>
      </div>
      <div class="member">
        <img src="https://github.com/carhope.png" alt="차희망">
        <div class="name">차희망</div>
        <div class="role">🎨 Frontend</div>
        <a href="https://github.com/carhope">@carhope</a>
      </div>
      <div class="member">
        <img src="https://github.com/yanghyomin.png" alt="양효민">
        <div class="name">양효민</div>
        <div class="role">🎨 Frontend</div>
        <a href="https://github.com/yanghyomin">@yanghyomin</a>
      </div>
      <div class="member">
        <img src="https://github.com/leehyunjae100510.png" alt="이현재">
        <div class="name">이현재</div>
        <div class="role">⚙️ Backend</div>
        <a href="https://github.com/leehyunjae100510">@leehyunjae100510</a>
      </div>
      <div class="member">
        <img src="https://github.com/yunji-0504.png" alt="김윤지">
        <div class="name">김윤지</div>
        <div class="role">⚙️ Backend</div>
        <a href="https://github.com/yunji-0504">@yunji-0504</a>
      </div>
    </div>
  </div>

  <!-- Stats -->
  <div class="section">
    <div class="section-title">Our Activities</div>
    <img class="stats-img"
      src="https://github-readme-stats.vercel.app/api?username=BSSM-RE-ACT&show_icons=true&theme=github_dark&hide_border=true&bg_color=161b22"
      alt="GitHub Stats">
  </div>

  <!-- Contact -->
  <div class="section">
    <div class="section-title">Contact</div>
    <div class="contact-row">
      ✉️ &nbsp;<strong>Email</strong>&nbsp;—&nbsp;26_51@bssm.hs.kr
    </div>
  </div>

  <!-- Footer -->
  <div class="footer">
    Made with ♥ by <span>BSSM RE:ACT</span> · 2026
  </div>

</body>
</html>
