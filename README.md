html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#070b14">
<meta name="description" content="Portfolio of Tanishq Gautam, a BCA student at SRM University interested in software development and technology.">
<title>Tanishq Gautam | Developer Portfolio</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.7.2/css/all.min.css">

<style>
:root {
  --bg: #070b14;
  --panel: #0d1422;
  --text: #f2f5ff;
  --muted: #9aa8c0;
  --blue: #6495ff;
  --border: rgba(151, 180, 255, .14);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; scroll-padding-top: 85px; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: "DM Sans", sans-serif;
  line-height: 1.65;
  overflow-x: hidden;
}

body::before {
  content: "";
  position: fixed;
  inset: 0;
  z-index: -1;
  pointer-events: none;
  background:
    radial-gradient(ellipse at 10% 10%, rgba(47, 95, 210, .17), transparent 34%),
    radial-gradient(ellipse at 90% 55%, rgba(42, 87, 173, .09), transparent 32%);
}

a { color: inherit; text-decoration: none; }
button, a { -webkit-tap-highlight-color: transparent; }
button { font: inherit; }
.container { width: min(1120px, 88%); margin: auto; }

header {
  position: fixed;
  inset: 0 0 auto;
  z-index: 100;
  height: 76px;
  background: rgba(7, 11, 20, .85);
  backdrop-filter: blur(18px);
  border-bottom: 1px solid var(--border);
}

.nav {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 25px;
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  font-weight: 700;
  font-family: "Space Grotesk", sans-serif;
}

.brand-mark {
  display: grid;
  place-items: center;
  width: 40px;
  height: 40px;
  border-radius: 12px;
  background: linear-gradient(135deg, #83aaff, #4165ed);
  color: #071020;
  font-size: 15px;
  font-weight: 700;
}

.nav-links { display: flex; align-items: center; gap: 27px; }
.nav-links a { font-size: 13px; color: var(--muted); transition: .2s; }
.nav-links a:hover { color: white; }

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 12px 19px;
  border: 1px solid var(--blue);
  border-radius: 999px;
  font-size: 13px;
  font-weight: 600;
  transition: transform .2s, background .2s;
}

.button:hover { transform: translateY(-3px); }
.button.primary { background: linear-gradient(135deg, #7ba5ff, #5379f4); color: #071020; border-color: transparent; }
.button.secondary { color: var(--text); }
.button.secondary:hover { background: rgba(100,149,255,.1); }

.menu-toggle {
  display: none;
  background: transparent;
  color: white;
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 9px 12px;
  cursor: pointer;
}

.hero {
  min-height: 720px;
  padding: 145px 0 85px;
  display: flex;
  align-items: center;
  position: relative;
}

.hero-grid {
  display: grid;
  grid-template-columns: 1.15fr .85fr;
  align-items: center;
  gap: 50px;
}

.eyebrow, .section-label {
  color: var(--blue);
  font-family: "Space Grotesk", sans-serif;
  font-size: 11px;
  letter-spacing: 2.5px;
  font-weight: 700;
  text-transform: uppercase;
}

.eyebrow { margin-bottom: 20px; }

.hero h1 {
  font-family: "Space Grotesk", sans-serif;
  font-size: clamp(55px, 7.3vw, 88px);
  line-height: .99;
  letter-spacing: -5px;
  margin-bottom: 23px;
}

.gradient-text {
  background: linear-gradient(100deg, #8db4ff, #5e77ff 65%, #b3a2ff);
  color: transparent;
  -webkit-background-clip: text;
  background-clip: text;
}

.hero h2 { font-size: 18px; font-weight: 500; margin-bottom: 14px; }

.hero-copy { max-width: 520px; color: var(--muted); font-size: 15px; }

.hero-actions { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 28px; }

.social-links { display: flex; gap: 12px; margin-top: 27px; }

.social-links a {
  display: grid;
  place-items: center;
  width: 40px;
  height: 40px;
  border: 1px solid var(--border);
  border-radius: 12px;
  color: #d8e3ff;
  transition: .2s;
}

.social-links a:hover { color: var(--blue); border-color: var(--blue); transform: translateY(-3px); }

.hero-art {
  min-height: 390px;
  display: grid;
  place-items: center;
  position: relative;
}

.art-glow {
  width: min(340px, 80%);
  aspect-ratio: 1;
  position: absolute;
  border-radius: 35%;
  background: linear-gradient(145deg, rgba(45,93,210,.28), rgba(28,42,88,.08));
  border: 1px solid rgba(100,149,255,.2);
  transform: rotate(-9deg);
  box-shadow: 0 0 100px rgba(37, 92, 230, .12);
}

.profile-card {
  width: min(310px, 78%);
  min-height: 325px;
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
  border: 1px solid var(--border);
  background: linear-gradient(145deg, rgba(19,31,53,.96), rgba(8,13,24,.96));
  border-radius: 25px;
  box-shadow: 0 25px 90px rgba(0,0,0,.25);
}

.avatar {
  width: 105px;
  height: 105px;
  border-radius: 30px;
  display: grid;
  place-items: center;
  margin-bottom: 22px;
  font-family: "Space Grotesk", sans-serif;
  font-size: 36px;
  font-weight: 700;
  color: #dce7ff;
  background: linear-gradient(135deg, #253f7b, #172440);
  border: 1px solid rgba(135,171,255,.4);
}

.profile-card h3 { font-size: 22px; font-family: "Space Grotesk", sans-serif; }
.profile-card p { color: var(--muted); font-size: 13px; margin-top: 5px; }

.floating-note {
  position: absolute;
  z-index: 2;
  padding: 11px 15px;
  border: 1px solid var(--border);
  border-radius: 14px;
  background: #101a2b;
  color: #c5d6ff;
  font-size: 12px;
  box-shadow: 0 12px 40px rgba(0,0,0,.2);
}

.note-one { top: 25px; right: 0; }
.note-two { bottom: 30px; left: 0; }

section { padding: 85px 0; border-top: 1px solid var(--border); }

.section-heading { margin-bottom: 35px; }
.section-heading h2 {
  font: 600 clamp(30px, 4vw, 42px)/1.2 "Space Grotesk", sans-serif;
  letter-spacing: -1.5px;
  margin-top: 9px;
}
.section-heading p { color: var(--muted); font-size: 14px; max-width: 560px; margin-top: 12px; }

.about-grid { display: grid; grid-template-columns: .9fr 1.1fr; gap: 55px; align-items: start; }
.about-copy { color: var(--muted); font-size: 15px; }
.about-copy p + p { margin-top: 15px; }

.info-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 12px; }
.info-card {
  min-width: 0;
  display: flex;
  gap: 13px;
  align-items: center;
  padding: 19px;
  border: 1px solid var(--border);
  border-radius: 15px;
  background: rgba(14,22,37,.78);
}
.info-icon {
  flex: 0 0 40px;
  height: 40px;
  display: grid;
  place-items: center;
  border-radius: 13px;
  background: rgba(72,117,229,.16);
  color: #8fb0ff;
}
.info-card small { display: block; color: var(--muted); font-size: 11px; }
.info-card strong { display: block; font-size: 13px; font-weight: 600; overflow-wrap: anywhere; }

.skills-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 14px; }
.skill-card {
  min-height: 130px;
  padding: 20px;
  border: 1px solid var(--border);
  border-radius: 17px;
  background: rgba(14,22,37,.72);
  transition: .25s;
}
.skill-card:hover { transform: translateY(-5px); border-color: rgba(100,149,255,.5); }
.skill-card i { color: var(--blue); font-size: 24px; margin-bottom: 18px; }
.skill-card h3 { font-size: 14px; }
.skill-card p { font-size: 11px; color: var(--muted); margin-top: 4px; }

.projects-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 17px; }
.project-card {
  display: flex;
  flex-direction: column;
  min-height: 270px;
  padding: 25px;
  border: 1px solid var(--border);
  border-radius: 18px;
  background: linear-gradient(145deg, rgba(16,25,43,.95), rgba(8,13,23,.95));
  transition: .25s;
}
.project-card:hover { transform: translateY(-5px); border-color: rgba(100,149,255,.5); }
.project-top { display: flex; justify-content: space-between; align-items: center; }
.project-icon {
  display: grid;
  place-items: center;
  width: 47px;
  height: 47px;
  border-radius: 14px;
  background: rgba(72,117,229,.17);
  color: #8fb0ff;
  font-size: 20px;
}
.project-top .project-status { font-size: 10px; color: #9aafd7; border: 1px solid var(--border); padding: 4px 8px; border-radius: 99px; }
.project-card h3 { font: 600 21px "Space Grotesk", sans-serif; margin-top: 22px; }
.project-card p { color: var(--muted); font-size: 13px; margin-top: 8px; }
.tags { display: flex; flex-wrap: wrap; gap: 7px; margin-top: auto; padding-top: 20px; }
.tags span { font-size: 10px; color: #c8d5ee; background: #17243a; padding: 5px 9px; border-radius: 99px; }

.education-card {
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  gap: 25px;
  padding: 27px;
  border: 1px solid var(--border);
  border-radius: 18px;
  background: rgba(14,22,37,.78);
}
.education-icon {
  width: 60px; height: 60px;
  display: grid; place-items: center;
  color: #a5beff; font-size: 24px;
  background: rgba(72,117,229,.17);
  border-radius: 17px;
}
.education-card h3 { font: 600 20px "Space Grotesk", sans-serif; }
.education-card p, .education-card small { color: var(--muted); font-size: 13px; }
.education-date { text-align: right; font-size: 12px; color: #a9c0ff; }

.contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 50px; align-items: center; }
.contact-copy { color: var(--muted); font-size: 14px; max-width: 440px; }
.contact-links { display: grid; gap: 13px; }
.contact-link {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 16px;
  border: 1px solid var(--border);
  border-radius: 15px;
  background: rgba(14,22,37,.72);
}
.contact-link i { width: 42px; height: 42px; display: grid; place-items: center; border-radius: 13px; background: rgba(72,117,229,.17); color: #a5beff; }
.contact-link small { display: block; color: var(--muted); font-size: 11px; }
.contact-link strong { display: block; font-size: 13px; overflow-wrap: anywhere; }

footer { padding: 25px 0; border-top: 1px solid var(--border); }
.footer-inner { display: flex; justify-content: space-between; align-items: center; gap: 20px; }
footer p { font-size: 12px; color: var(--muted); }
.back-top { color: var(--blue); border: 1px solid var(--border); width: 38px; height: 38px; display: grid; place-items: center; border-radius: 50%; }

.reveal { opacity: 0; transform: translateY(18px); transition: opacity .6s ease, transform .6s ease; }
.reveal.visible { opacity: 1; transform: translateY(0); }

@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { scroll-behavior: auto !important; transition-duration: .01ms !important; animation-duration: .01ms !important; }
  .reveal { opacity: 1; transform: none; }
}

@media (max-width: 850px) {
  .nav-links { gap: 15px; }
  .nav-links a { font-size: 12px; }
  .nav-cta { display: none; }
  .hero-grid { gap: 20px; }
  .hero h1 { font-size: clamp(54px, 8vw, 75px); }
  .about-grid { gap: 30px; }
  .skills-grid { grid-template-columns: repeat(3, 1fr); }
  .projects-grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 620px) {
  header { height: 68px; }
  .container { width: 90%; }
  .brand { font-size: 13px; gap: 8px; }
  .brand-mark { width: 35px; height: 35px; }
  .menu-toggle { display: block; }
  .nav { position: relative; }
  .nav-links {
    display: none;
    position: absolute;
    top: 59px;
    left: 0;
    right: 0;
    padding: 16px;
    flex-direction: column;
    align-items: stretch;
    gap: 0;
    background: #0d1422;
    border: 1px solid var(--border);
    border-radius: 15px;
  }
  .nav-links.open { display: flex; }
  .nav-links a { padding: 11px 8px; font-size: 14px; }
  .hero { padding: 120px 0 65px; min-height: auto; }
  .hero-grid { grid-template-columns: 1fr; }
  .hero h1 { font-size: clamp(55px, 13vw, 75px); letter-spacing: -3px; }
  .hero-copy { font-size: 14px; }
  .hero-art { min-height: 300px; margin-top: 15px; }
  .profile-card { min-height: 265px; }
  .art-glow { width: 260px; }
  .note-one { right: 0; top: 5px; }
  .note-two { bottom: 4px; left: 0; }
  section { padding: 65px 0; }
  .about-grid, .contact-grid { grid-template-columns: 1fr; gap: 28px; }
  .info-grid { grid-template-columns: 1fr; }
  .skills-grid { grid-template-columns: repeat(2, 1fr); gap: 10px; }
  .skill-card { min-height: 115px; padding: 16px; }
  .projects-grid { grid-template-columns: 1fr; }
  .project-card { min-height: 245px; }
  .education-card { grid-template-columns: auto 1fr; gap: 15px; padding: 19px; }
  .education-date { grid-column: 2; text-align: left; }
  .footer-inner { flex-wrap: wrap; }
}

@media (max-width: 360px) {
  .hero-actions { align-items: stretch; flex-direction: column; }
  .hero-actions .button { width: 100%; }
}
</style>
</head>

<body>
<header>
  <div class="container nav">
    <a class="brand" href="#home" aria-label="Tanishq Gautam home">
      <span class="brand-mark">TG</span>
      <span>Tanishq Gautam</span>
    </a>

    <nav class="nav-links" id="navLinks" aria-label="Main navigation">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#skills">Skills</a>
      <a href="#projects">Projects</a>
      <a href="#education">Education</a>
      <a href="#contact">Contact</a>
    </nav>

    <a class="button secondary nav-cta" href="mailto:cintex20@gmail.com">
      Let's Connect <i class="fa-regular fa-paper-plane"></i>
    </a>

    <button class="menu-toggle" id="menuToggle" aria-label="Toggle navigation" aria-expanded="false">
      <i class="fa-solid fa-bars"></i>
    </button>
  </div>
</header>

<main>
  <section class="hero" id="home">
    <div class="container hero-grid">
      <div class="reveal">
        <p class="eyebrow">BCA STUDENT · TECHNOLOGY ENTHUSIAST</p>
        <h1>Hello, I'm<br><span class="gradient-text">Tanishq Gautam.</span></h1>
        <h2>Student. Learner. Future Developer.</h2>
        <p class="hero-copy">
          I'm pursuing BCA at SRM University and exploring the world of
          technology, programming, and digital product development.
          I'm here to learn, build useful things, and grow with every project.
        </p>

        <div class="hero-actions">
          <a href="#projects" class="button primary">Explore My Work <i class="fa-solid fa-arrow-right"></i></a>
          <a href="#contact" class="button secondary">Contact Me <i class="fa-regular fa-envelope"></i></a>
        </div>

        <div class="social-links">
          <a href="https://www.linkedin.com/feed/" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">
            <i class="fa-brands fa-linkedin-in"></i>
          </a>
          <a href="https://github.com/" target="_blank" rel="noopener noreferrer" aria-label="GitHub">
            <i class="fa-brands fa-github"></i>
          </a>
          <a href="mailto:cintex20@gmail.com" aria-label="Email">
            <i class="fa-regular fa-envelope"></i>
          </a>
        </div>
      </div>

      <div class="hero-art reveal" aria-label="Personal introduction card">
        <div class="art-glow"></div>
        <div class="floating-note note-one"><i class="fa-solid fa-code"></i> Always learning</div>
        <div class="profile-card">
          <div class="avatar">TG</div>
          <h3>Tanishq Gautam</h3>
          <p>BCA Student · SRM University</p>
          <p style="margin-top:18px;color:#91adff">Build · Learn · Improve</p>
        </div>
        <div class="floating-note note-two"><i class="fa-solid fa-lightbulb"></i> Ideas into projects</div>
      </div>
    </div>
  </section>

  <section id="about">
    <div class="container about-grid">
      <div class="reveal">
        <div class="section-heading">
          <p class="section-label">01 / ABOUT ME</p>
          <h2>Turning curiosity<br>into capability.</h2>
        </div>
        <div class="about-copy">
          <p>
            I'm Tanishq Gautam, a Bachelor of Computer Applications student
            at SRM University with an interest in software development,
            web technologies, and problem solving.
          </p>
          <p>
            I'm working towards strengthening my fundamentals, building
            practical projects, and learning how technology can solve
            real problems. This portfolio will grow alongside my journey.
          </p>
        </div>
      </div>

      <div class="info-grid reveal">
        <div class="info-card">
          <div class="info-icon"><i class="fa-regular fa-user"></i></div>
          <div><small>Full Name</small><strong>Tanishq Gautam</strong></div>
        </div>
        <div class="info-card">
          <div class="info-icon"><i class="fa-solid fa-graduation-cap"></i></div>
          <div><small>Program</small><strong>BCA</strong></div>
        </div>
        <div class="info-card">
          <div class="info-icon"><i class="fa-solid fa-building-columns"></i></div>
          <div><small>University</small><strong>SRM University</strong></div>
        </div>
        <div class="info-card">
          <div class="info-icon"><i class="fa-regular fa-envelope"></i></div>
          <div><small>Email</small><strong>cintex20@gmail.com</strong></div>
        </div>
      </div>
    </div>
  </section>

  <section id="skills">
    <div class="container">
      <div class="section-heading reveal">
        <p class="section-label">02 / MY TOOLKIT</p>
        <h2>Technologies & tools.</h2>
        <p>A snapshot of the technologies I use or am learning. I'll update this section as my skills develop.</p>
      </div>

      <div class="skills-grid">
        <article class="skill-card reveal">
          <i class="fa-brands fa-html5"></i><h3>HTML5</h3><p>Web structure</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-brands fa-css3-alt"></i><h3>CSS3</h3><p>Styling & layouts</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-brands fa-js"></i><h3>JavaScript</h3><p>Web interactions</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-solid fa-code"></i><h3>C Programming</h3><p>Programming fundamentals</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-brands fa-git-alt"></i><h3>Git</h3><p>Version control</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-brands fa-github"></i><h3>GitHub</h3><p>Code repositories</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-brands fa-react"></i><h3>React</h3><p>Learning next</p>
        </article>
        <article class="skill-card reveal">
          <i class="fa-solid fa-terminal"></i><h3>Problem Solving</h3><p>Practice in progress</p>
        </article>
      </div>
    </div>
  </section>

  <section id="projects">
    <div class="container">
      <div class="section-heading reveal">
        <p class="section-label">03 / SELECTED WORK</p>
        <h2>Projects & experiments.</h2>
        <p>Use this space to showcase completed projects. The cards below are starter concepts from the portfolio design; replace them with real work before presenting the site professionally.</p>
      </div>

      <div class="projects-grid">
        <article class="project-card reveal">
          <div class="project-top">
            <div class="project-icon"><i class="fa-solid fa-book-open"></i></div>
            <span class="project-status">Concept</span>
          </div>
          <h3>StudyFlow</h3>
          <p>A student productivity app concept for organizing study sessions, tracking tasks, and building consistent study habits.</p>
          <div class="tags"><span>HTML</span><span>CSS</span><span>JavaScript</span></div>
        </article>

        <article class="project-card reveal">
          <div class="project-top">
            <div class="project-icon"><i class="fa-solid fa-chart-line"></i></div>
            <span class="project-status">Concept</span>
          </div>
          <h3>Insight</h3>
          <p>An interactive dashboard concept that presents information through a simple, clear, and easy-to-understand interface.</p>
          <div class="tags"><span>JavaScript</span><span>UI</span><span>APIs</span></div>
        </article>

        <article class="project-card reveal">
          <div class="project-top">
            <div class="project-icon"><i class="fa-solid fa-laptop-code"></i></div>
            <span class="project-status">In progress</span>
          </div>
          <h3>Portfolio Website</h3>
          <p>This personal website is a starting point for documenting my learning journey and presenting future projects.</p>
          <div class="tags"><span>HTML</span><span>CSS</span><span>JavaScript</span></div>
        </article>
      </div>
    </div>
  </section>

  <section id="education">
    <div class="container">
      <div class="section-heading reveal">
        <p class="section-label">04 / EDUCATION</p>
        <h2>My academic journey.</h2>
      </div>

      <div class="education-card reveal">
        <div class="education-icon"><i class="fa-solid fa-graduation-cap"></i></div>
        <div>
          <h3>Bachelor of Computer Applications (BCA)</h3>
          <p>SRM University</p>
          <small>Computer applications, programming, and technology</small>
        </div>
        <div class="education-date">Currently studying</div>
      </div>
    </div>
  </section>

  <section id="contact">
    <div class="container contact-grid">
      <div class="reveal">
        <div class="section-heading">
          <p class="section-label">05 / GET IN TOUCH</p>
          <h2>Let's connect<br>and create.</h2>
        </div>
        <p class="contact-copy">
          Have an idea, want to collaborate, or simply want to talk about
          technology and learning? Feel free to reach out.
        </p>
        <div class="hero-actions">
          <a class="button primary" href="mailto:cintex20@gmail.com">
            Send Me an Email <i class="fa-regular fa-paper-plane"></i>
          </a>
        </div>
      </div>

      <div class="contact-links reveal">
        <a class="contact-link" href="mailto:cintex20@gmail.com">
          <i class="fa-regular fa-envelope"></i>
          <span><small>Email</small><strong>cintex20@gmail.com</strong></span>
        </a>
        <a class="contact-link" href="https://www.linkedin.com/feed/" target="_blank" rel="noopener noreferrer">
          <i class="fa-brands fa-linkedin-in"></i>
          <span><small>LinkedIn</small><strong>Visit LinkedIn</strong></span>
        </a>
        <a class="contact-link" href="https://github.com/" target="_blank" rel="noopener noreferrer">
          <i class="fa-brands fa-github"></i>
          <span><small>GitHub</small><strong>Explore repositories</strong></span>
        </a>
      </div>
    </div>
  </section>
</main>

<footer>
  <div class="container footer-inner">
    <a class="brand" href="#home">
      <span class="brand-mark">TG</span><span>Tanishq Gautam</span>
    </a>
    <p>Designed with care · <span id="year"></span> Tanishq Gautam</p>
    <a class="back-top" href="#home" aria-label="Back to top"><i class="fa-solid fa-arrow-up"></i></a>
  </div>
</footer>

<script>
const menuToggle = document.getElementById("menuToggle");
const navLinks = document.getElementById("navLinks");

menuToggle.addEventListener("click", () => {
  const isOpen = navLinks.classList.toggle("open");
  menuToggle.setAttribute("aria-expanded", String(isOpen));
  menuToggle.innerHTML = isOpen
    ? '<i class="fa-solid fa-xmark"></i>'
    : '<i class="fa-solid fa-bars"></i>';
});

navLinks.querySelectorAll("a").forEach(link => {
  link.addEventListener("click", () => {
    navLinks.classList.remove("open");
    menuToggle.setAttribute("aria-expanded", "false");
    menuToggle.innerHTML = '<i class="fa-solid fa-bars"></i>';
  });
});

document.getElementById("year").textContent = new Date().getFullYear();

if ("IntersectionObserver" in window &&
    !window.matchMedia("(prefers-reduced-motion: reduce)").matches) {
  const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add("visible");
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12 });

  document.querySelectorAll(".reveal").forEach(element => observer.observe(element));
} else {
  document.querySelectorAll(".reveal").forEach(element => element.classList.add("visible"));
}
</script>
</body>
</html>
