# Kevotish-
Jesus 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Portfolio</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg: #0e0e0e;
      --surface: #161616;
      --accent: #c8f04a;
      --accent2: #f0a84a;
      --text: #f0ede6;
      --muted: #888;
      --border: #2a2a2a;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 100;
      display: flex; justify-content: space-between; align-items: center;
      padding: 1.2rem 2.5rem;
      background: rgba(14,14,14,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
    }
    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem;
      color: var(--accent);
      letter-spacing: 0.02em;
    }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--accent); }

    /* ── HERO ── */
    #hero {
      min-height: 100vh;
      display: flex; align-items: center;
      padding: 8rem 2.5rem 4rem;
      position: relative;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background: radial-gradient(ellipse 80% 60% at 70% 50%, rgba(200,240,74,0.07) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-grid {
      position: absolute; inset: 0;
      background-image: linear-gradient(var(--border) 1px, transparent 1px),
                        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      opacity: 0.3;
      pointer-events: none;
    }
    .hero-content { position: relative; max-width: 900px; }
    .hero-tag {
      display: inline-block;
      background: rgba(200,240,74,0.12);
      color: var(--accent);
      border: 1px solid rgba(200,240,74,0.3);
      border-radius: 100px;
      padding: 0.3rem 1rem;
      font-size: 0.8rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.6s ease both;
    }
    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3rem, 8vw, 6.5rem);
      line-height: 1.05;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.6s 0.1s ease both;
    }
    .hero-title span { color: var(--accent); font-style: italic; }
    .hero-desc {
      font-size: 1.1rem;
      color: var(--muted);
      max-width: 520px;
      margin-bottom: 2.5rem;
      font-weight: 300;
      animation: fadeUp 0.6s 0.2s ease both;
    }
    .hero-cta {
      display: flex; gap: 1rem; flex-wrap: wrap;
      animation: fadeUp 0.6s 0.3s ease both;
    }
    .btn {
      padding: 0.85rem 2rem;
      border-radius: 6px;
      font-size: 0.95rem;
      font-weight: 500;
      cursor: pointer;
      text-decoration: none;
      transition: all 0.2s;
      display: inline-block;
    }
    .btn-primary {
      background: var(--accent);
      color: #0e0e0e;
      border: none;
    }
    .btn-primary:hover { background: #d9ff55; transform: translateY(-2px); }
    .btn-outline {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }
    .btn-outline:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

    /* ── ABOUT ── */
    #about {
      padding: 6rem 2.5rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 5rem;
      align-items: center;
      max-width: 1100px;
      margin: 0 auto;
    }
    .about-image-wrap {
      position: relative;
    }
    .about-image {
      width: 100%;
      aspect-ratio: 4/5;
      border-radius: 12px;
      background: var(--surface);
      border: 1px solid var(--border);
      display: flex; align-items: center; justify-content: center;
      font-size: 6rem;
      position: relative;
      overflow: hidden;
    }
    .about-image::before {
      content: '';
      position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(200,240,74,0.05), transparent);
    }
    .about-image-accent {
      position: absolute;
      bottom: -10px; right: -10px;
      width: 80px; height: 80px;
      background: var(--accent);
      border-radius: 8px;
      z-index: -1;
    }
    .section-label {
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1rem;
      font-weight: 500;
    }
    .section-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 4vw, 2.8rem);
      line-height: 1.2;
      margin-bottom: 1.2rem;
    }
    .about-text { color: var(--muted); font-weight: 300; margin-bottom: 1rem; }
    .stats {
      display: grid; grid-template-columns: 1fr 1fr;
      gap: 1rem; margin-top: 2rem;
    }
    .stat {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1rem 1.2rem;
    }
    .stat-num {
      font-family: 'Playfair Display', serif;
      font-size: 2rem;
      color: var(--accent);
    }
    .stat-label { font-size: 0.8rem; color: var(--muted); }

    /* ── SKILLS ── */
    #skills {
      padding: 6rem 2.5rem;
      background: var(--surface);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }
    .skills-inner { max-width: 1100px; margin: 0 auto; }
    .skills-header { text-align: center; margin-bottom: 3rem; }
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1rem;
    }
    .skill-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 1.5rem;
      transition: border-color 0.2s, transform 0.2s;
    }
    .skill-card:hover { border-color: var(--accent); transform: translateY(-4px); }
    .skill-icon { font-size: 2rem; margin-bottom: 0.75rem; }
    .skill-name { font-weight: 500; margin-bottom: 0.5rem; }
    .skill-bar { height: 4px; background: var(--border); border-radius: 4px; overflow: hidden; }
    .skill-fill { height: 100%; background: var(--accent); border-radius: 4px; transition: width 1s ease; }

    /* ── PROJECTS ── */
    #projects { padding: 6rem 2.5rem; }
    .projects-inner { max-width: 1100px; margin: 0 auto; }
    .projects-header { margin-bottom: 3rem; }
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 1.5rem;
    }
    .project-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.2s, border-color 0.2s;
    }
    .project-card:hover { transform: translateY(-6px); border-color: var(--accent); }
    .project-thumb {
      height: 180px;
      display: flex; align-items: center; justify-content: center;
      font-size: 4rem;
      position: relative;
    }
    .project-thumb-1 { background: linear-gradient(135deg, #1a2a0a, #2a3a1a); }
    .project-thumb-2 { background: linear-gradient(135deg, #0a1a2a, #1a2a3a); }
    .project-thumb-3 { background: linear-gradient(135deg, #2a0a1a, #3a1a2a); }
    .project-body { padding: 1.5rem; }
    .project-tags { display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 0.75rem; }
    .tag {
      font-size: 0.72rem;
      padding: 0.2rem 0.6rem;
      border-radius: 4px;
      background: rgba(200,240,74,0.1);
      color: var(--accent);
      border: 1px solid rgba(200,240,74,0.2);
      letter-spacing: 0.05em;
    }
    .project-title { font-weight: 600; font-size: 1.1rem; margin-bottom: 0.5rem; }
    .project-desc { color: var(--muted); font-size: 0.9rem; font-weight: 300; margin-bottom: 1.2rem; }
    .project-link {
      color: var(--accent);
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 500;
      letter-spacing: 0.05em;
      display: inline-flex; align-items: center; gap: 0.4rem;
    }
    .project-link:hover { gap: 0.7rem; }

    /* ── CONTACT ── */
    #contact {
      padding: 6rem 2.5rem;
      background: var(--surface);
      border-top: 1px solid var(--border);
    }
    .contact-inner {
      max-width: 600px; margin: 0 auto; text-align: center;
    }
    .contact-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 3.5rem);
      margin-bottom: 1rem;
    }
    .contact-title span { color: var(--accent); font-style: italic; }
    .contact-sub { color: var(--muted); margin-bottom: 2.5rem; font-weight: 300; }
    .contact-form { display: flex; flex-direction: column; gap: 1rem; text-align: left; }
    .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
    label { font-size: 0.8rem; letter-spacing: 0.08em; text-transform: uppercase; color: var(--muted); }
    input, textarea {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 0.85rem 1rem;
      color: var(--text);
      font-family: 'DM Sans', sans-serif;
      font-size: 0.95rem;
      transition: border-color 0.2s;
      outline: none;
      resize: vertical;
    }
    input:focus, textarea:focus { border-color: var(--accent); }
    textarea { min-height: 130px; }
    .form-submit { margin-top: 0.5rem; }

    /* ── FOOTER ── */
    footer {
      text-align: center;
      padding: 2rem;
      border-top: 1px solid var(--border);
      color: var(--muted);
      font-size: 0.85rem;
    }
    footer span { color: var(--accent); }

    /* ── ANIMATIONS ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ── RESPONSIVE ── */
    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { gap: 1.2rem; }
      #hero { padding: 7rem 1.5rem 3rem; }
      #about { grid-template-columns: 1fr; gap: 2.5rem; padding: 4rem 1.5rem; }
      .about-image-wrap { display: none; }
      #skills, #projects, #contact { padding: 4rem 1.5rem; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="logo">YourName.</div>
    <ul class="nav-links">
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <section id="hero">
    <div class="hero-bg"></div>
    <div class="hero-grid"></div>
    <div class="hero-content">
      <div class="hero-tag">👋 Available for work</div>
      <h1 class="hero-title">
        Hi, I'm <span>Your Name</span><br>
        I build things<br>for the web.
      </h1>
      <p class="hero-desc">
        A passionate developer who loves creating beautiful, functional websites and applications that make a difference.
      </p>
      <div class="hero-cta">
        <a href="#projects" class="btn btn-primary">View My Work</a>
        <a href="#contact" class="btn btn-outline">Get In Touch</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="about-image-wrap">
      <div class="about-image">🧑‍💻</div>
      <div class="about-image-accent"></div>
    </div>
    <div class="about-text-content">
      <div class="section-label">About Me</div>
      <h2 class="section-title">Turning ideas into reality, one line at a time.</h2>
      <p class="about-text">I'm a developer with a passion for crafting clean, intuitive digital experiences. I love solving problems and learning new technologies.</p>
      <p class="about-text">When I'm not coding, you'll find me exploring design trends, contributing to open-source, or enjoying a good cup of coffee ☕</p>
      <div class="stats">
        <div class="stat">
          <div class="stat-num">10+</div>
          <div class="stat-label">Projects Completed</div>
        </div>
        <div class="stat">
          <div class="stat-num">2+</div>
          <div class="stat-label">Years Experience</div>
        </div>
        <div class="stat">
          <div class="stat-num">5+</div>
          <div class="stat-label">Happy Clients</div>
        </div>
        <div class="stat">
          <div class="stat-num">∞</div>
          <div class="stat-label">Cups of Coffee</div>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="skills-inner">
      <div class="skills-header">
        <div class="section-label">What I know</div>
        <h2 class="section-title">My Skills</h2>
      </div>
      <div class="skills-grid">
        <div class="skill-card">
          <div class="skill-icon">🌐</div>
          <div class="skill-name">HTML</div>
          <div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🎨</div>
          <div class="skill-name">CSS</div>
          <div class="skill-bar"><div class="skill-fill" style="width:80%"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">⚡</div>
          <div class="skill-name">JavaScript</div>
          <div class="skill-bar"><div class="skill-fill" style="width:70%"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🐙</div>
          <div class="skill-name">Git & GitHub</div>
          <div class="skill-bar"><div class="skill-fill" style="width:75%"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">📱</div>
          <div class="skill-name">Responsive Design</div>
          <div class="skill-bar"><div class="skill-fill" style="width:85%"></div></div>
        </div>
        <div class="skill-card">
          <div class="skill-icon">🔧</div>
          <div class="skill-name">VS Code</div>
          <div class="skill-bar"><div class="skill-fill" style="width:90%"></div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="projects-inner">
      <div class="projects-header">
        <div class="section-label">My Work</div>
        <h2 class="section-title">Featured Projects</h2>
      </div>
      <div class="projects-grid">
        <div class="project-card">
          <div class="project-thumb project-thumb-1">🌿</div>
          <div class="project-body">
            <div class="project-tags"><span class="tag">HTML</span><span class="tag">CSS</span></div>
            <div class="project-title">Project One</div>
            <p class="project-desc">A short description of what this project does and the problem it solves.</p>
            <a href="#" class="project-link">View Project →</a>
          </div>
        </div>
        <div class="project-card">
          <div class="project-thumb project-thumb-2">🌊</div>
          <div class="project-body">
            <div class="project-tags"><span class="tag">JavaScript</span><span class="tag">CSS</span></div>
            <div class="project-title">Project Two</div>
            <p class="project-desc">A short description of what this project does and the problem it solves.</p>
            <a href="#" class="project-link">View Project →</a>
          </div>
        </div>
        <div class="project-card">
          <div class="project-thumb project-thumb-3">🌸</div>
          <div class="project-body">
            <div class="project-tags"><span class="tag">HTML</span><span class="tag">JS</span></div>
            <div class="project-title">Project Three</div>
            <p class="project-desc">A short description of what this project does and the problem it solves.</p>
            <a href="#" class="project-link">View Project →</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact">
    <div class="contact-inner">
      <div class="section-label">Get In Touch</div>
      <h2 class="contact-title">Let's Work <span>Together</span></h2>
      <p class="contact-sub">Have a project in mind or just want to say hello? I'd love to hear from you!</p>
      <div class="contact-form">
        <div class="form-group">
          <label for="name">Your Name</label>
          <input type="text" id="name" placeholder="Jane Smith" />
        </div>
        <div class="form-group">
          <label for="email">Email Address</label>
          <input type="email" id="email" placeholder="jane@example.com" />
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea id="message" placeholder="Tell me about your project..."></textarea>
        </div>
        <div class="form-submit">
          <button class="btn btn-primary" style="width:100%;font-size:1rem;" onclick="alert('Thanks for reaching out! (Connect this to a real service like Formspree)')">Send Message</button>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <p>Built with <span>♥</span> and hosted on GitHub Pages · © 2026 YourName</p>
  </footer>

</body>
</html>
