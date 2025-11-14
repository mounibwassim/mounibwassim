<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Mounib — GitHub Profile Preview</title>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&family=Unbounded:wght@700;900&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#0b1020;
      --card:#0f1724;
      --accent:#ff6a00;
      --muted:#9aa7bf;
      --glass: rgba(255,255,255,0.04);
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Montserrat,system-ui,Arial;background:linear-gradient(160deg,var(--bg),#061024 60%);color:#e6eef9}
    .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:48px}
    .card{width:980px;max-width:98%;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:20px;padding:28px;box-shadow:0 10px 40px rgba(2,6,23,0.6);backdrop-filter: blur(6px);border:1px solid rgba(255,255,255,0.03)}

    /* header with 3D name */
    .hero{display:grid;grid-template-columns:1fr 360px;gap:24px;align-items:center}
    .name-wrap{position:relative;padding:12px}
    .name-3d{
      font-family: 'Unbounded', cursive; font-size:72px;line-height:0.95;letter-spacing:-2px;
      transform-style:preserve-3d; color:transparent; -webkit-text-stroke:1px rgba(255,255,255,0.08);
      filter:drop-shadow(0 8px 24px rgba(0,0,0,0.6));
      animation: float 4s ease-in-out infinite;
      perspective:800px;
    }
    .name-3d::before, .name-3d::after{
      content:'Mounib'; position:absolute; left:0; top:0; width:100%; height:100%;
      -webkit-text-stroke:0; text-shadow: none; mix-blend-mode:screen;
    }
    .name-3d::before{content:'Mounib'; color:rgba(255,106,0,0.12); transform:translateZ(-30px) rotateX(20deg); filter:blur(6px)}
    .name-3d::after{content:'Mounib'; color:#fff; transform:translateZ(8px) rotateX(-6deg); font-weight:900}

    @keyframes float{0%{transform:translateY(0) rotateX(0)}50%{transform:translateY(-10px) rotateX(2deg)}100%{transform:translateY(0) rotateX(0)}}

    /* dragon container */
    .dragon-stage{display:flex;align-items:center;justify-content:center;height:220px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));border-radius:16px;border:1px solid rgba(255,255,255,0.02);position:relative;overflow:hidden}
    .dragon-svg{width:100%;height:100%;max-height:220px;transition:transform 1s ease}
    .dragon-hidden{position:absolute;inset:0;display:flex;align-items:center;justify-content:center}

    /* info */
    .bio{color:var(--muted);font-size:15px;margin-top:6px}
    .badges{display:flex;gap:10px;margin-top:14px}
    .badge{background:var(--glass);padding:8px 12px;border-radius:999px;font-weight:700;font-size:13px;color:#dff0ff;border:1px solid rgba(255,255,255,0.03)}

    /* skills grid */
    .skills{display:flex;flex-wrap:wrap;gap:12px;margin-top:18px}
    .skill-card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:12px;border-radius:12px;display:flex;align-items:center;gap:10px;width:calc(33% - 8px);min-width:140px;border:1px solid rgba(255,255,255,0.03)}
    .skill-icon{width:44px;height:44px;display:inline-grid;place-items:center;border-radius:8px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));position:relative;overflow:visible}

    .skill-name{font-weight:700}
    .skill-desc{font-size:12px;color:var(--muted)}

    /* flame effect */
    .flame{position:absolute;bottom:4px;left:50%;transform:translateX(-50%);width:18px;height:28px;pointer-events:none;opacity:0}
    .on-fire .flame{animation:burn 1s linear infinite;opacity:1}
    @keyframes burn{0%{transform:translateX(-50%) translateY(8px) scale(0.8)}50%{transform:translateX(-50%) translateY(0) scale(1)}100%{transform:translateX(-50%) translateY(8px) scale(0.8)}}

    /* projects */
    .projects{margin-top:18px;display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
    .project{padding:12px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.00));border:1px solid rgba(255,255,255,0.02)}
    .project h4{margin:0 0 8px 0}
    .links{display:flex;gap:10px;align-items:center;margin-top:12px}
    .icon-link{display:inline-grid;place-items:center;width:44px;height:44px;border-radius:10px;background:transparent;border:1px solid rgba(255,255,255,0.04)}

    /* footer */
    .footer{margin-top:20px;display:flex;justify-content:space-between;align-items:center}
    .degree{font-weight:800;color:#fff;background:linear-gradient(90deg,#2bd2ff,#3a7bff);padding:8px 12px;border-radius:10px}

    /* responsive */
    @media (max-width:880px){.hero{grid-template-columns:1fr;}.name-3d{font-size:48px}.projects{grid-template-columns:1fr}}

  </style>
</head>
<body>
  <div class="wrap">
    <div class="card" role="main">
      <div class="hero">
        <div class="name-wrap">
          <div class="name-3d" id="name3d">Mounib</div>
          <div class="bio">Hi — I'm <strong>Mounib Meftah</strong> — <span style="color:var(--accent);font-weight:800">programmer &amp; AI enthusiast</span>. I build web projects and data tools. I love elegant code, clean UI, and results that make people say <em>"OMG — perfect programmer"</em>.</div>
          <div class="badges">
            <div class="badge">Artificial Intelligence Degree</div>
            <div class="badge">Final Year — 2026</div>
            <div class="badge">Open to collaborations</div>
          </div>

          <div class="skills" style="margin-top:18px">
            <!-- Skill: Python -->
            <div class="skill-card on-fire" data-skill="python">
              <div class="skill-icon" aria-hidden>
                <!-- simple Python-like icon -->
                <svg width="34" height="34" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <rect x="2" y="2" width="20" height="20" rx="4" fill="url(#g1)"/>
                  <defs>
                    <linearGradient id="g1" x1="0" x2="1"><stop offset="0" stop-color="#FFD43B"/><stop offset="1" stop-color="#FFE599"/></linearGradient>
                  </defs>
                </svg>
                <div class="flame" aria-hidden>
                  <!-- flame simple -->
                  <svg viewBox="0 0 24 24" width="18" height="28" xmlns="http://www.w3.org/2000/svg">
                    <path d="M12 2s4 3 4 7c0 3-2 4-2 6-1 3-4 5-4 5s1-3 0-5c-1.3-2-2-2.5-2-5 0-4 4-8 4-8z" fill="#ff8a00" />
                  </svg>
                </div>
              </div>
              <div>
                <div class="skill-name">Python</div>
                <div class="skill-desc">Data, scripts, automation, ML</div>
              </div>
            </div>

            <!-- C++ -->
            <div class="skill-card" data-skill="cpp">
              <div class="skill-icon">
                <svg width="34" height="34" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <rect x="2" y="2" width="20" height="20" rx="4" fill="#3b82f6"/>
                  <text x="50%" y="55%" text-anchor="middle" font-family="monospace" font-size="12" fill="#fff">C++</text>
                </svg>
              </div>
              <div>
                <div class="skill-name">C++</div>
                <div class="skill-desc">Performance &amp; algorithms</div>
              </div>
            </div>

            <!-- SQL -->
            <div class="skill-card" data-skill="sql">
              <div class="skill-icon">
                <svg width="34" height="34" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <rect x="2" y="2" width="20" height="20" rx="4" fill="#10b981"/>
                  <text x="50%" y="55%" text-anchor="middle" font-family="monospace" font-size="12" fill="#fff">SQL</text>
                </svg>
              </div>
              <div>
                <div class="skill-name">SQL</div>
                <div class="skill-desc">Databases, queries, optimization</div>
              </div>
            </div>

            <!-- HTML/CSS -->
            <div class="skill-card" data-skill="web">
              <div class="skill-icon">
                <svg width="34" height="34" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <rect x="2" y="2" width="20" height="20" rx="4" fill="#ef4444"/>
                  <text x="50%" y="48%" text-anchor="middle" font-family="monospace" font-size="10" fill="#fff">HTML</text>
                  <text x="50%" y="68%" text-anchor="middle" font-family="monospace" font-size="8" fill="#fff">CSS</text>
                </svg>
              </div>
              <div>
                <div class="skill-name">HTML &amp; CSS</div>
                <div class="skill-desc">Frontend design &amp; projects</div>
              </div>
            </div>

            <!-- Collab / Colab (Google Colab) -->
            <div class="skill-card" data-skill="colab">
              <div class="skill-icon">
                <svg width="34" height="34" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <rect x="2" y="2" width="20" height="20" rx="4" fill="#8b5cf6"/>
                  <text x="50%" y="55%" text-anchor="middle" font-family="monospace" font-size="10" fill="#fff">Colab</text>
                </svg>
              </div>
              <div>
                <div class="skill-name">Google Colab</div>
                <div class="skill-desc">Notebooks &amp; experiments</div>
              </div>
            </div>

            <!-- Projects: CSS, HTML, Python -->
          </div>

          <div class="projects">
            <div class="project">
              <h4>Portfolio Website</h4>
              <div class="skill-desc">Built with HTML, CSS — responsive UI and animations. (Live demo in repo)</div>
              <div class="links">
                <a class="icon-link" href="#">Repo</a>
                <a class="icon-link" href="#">Demo</a>
              </div>
            </div>
            <div class="project">
              <h4>Data Visualiser (Python)</h4>
              <div class="skill-desc">Python scripts + Colab notebooks to analyze and visualize datasets.</div>
              <div class="links">
                <a class="icon-link" href="#">Notebook</a>
                <a class="icon-link" href="#">Readme</a>
              </div>
            </div>
          </div>

        </div>

        <div class="dragon-stage" aria-hidden="true">
          <!-- decorative dragon SVG that appears after a moment, with a simple fire animation -->
          <div class="dragon-hidden">
            <svg class="dragon-svg" viewBox="0 0 800 220" preserveAspectRatio="xMidYMid meet" xmlns="http://www.w3.org/2000/svg">
              <defs>
                <linearGradient id="gdragon" x1="0" x2="1">
                  <stop offset="0" stop-color="#ff6a00" />
                  <stop offset="1" stop-color="#ff2d2d" />
                </linearGradient>
              </defs>
              <g id="dragon" transform="translate(80,20)">
                <path id="body" d="M10 150 C 60 120, 150 120, 260 150 C 360 180, 420 170, 540 130 C 640 100, 720 60, 760 30" stroke="url(#gdragon)" stroke-width="24" fill="none" stroke-linecap="round"/>
                <circle id="eye" cx="70" cy="70" r="6" fill="#fff" />
                <!-- stylized head -->
                <path id="head" d="M60 60 C 80 50, 100 40, 120 50 C 140 58, 140 78, 120 86 C 100 94, 80 86, 60 80 Z" fill="#ff6a00" opacity="0.95"/>
                <!-- fire breath -->
                <g id="fire" transform="translate(128,60)">
                  <path d="M0 0 C 8 10, 14 20, 10 36 C 6 52, -10 58, -6 34 C -2 18, 6 8, 0 0 Z" fill="#ffb86b" opacity="0.9">
                    <animate attributeName="transform" values="translate(0,0); translate(6,-6); translate(0,0)" dur="0.9s" repeatCount="indefinite" />
                  </path>
                  <path d="M6 4 C 12 14, 18 26, 12 40 C 6 56, -6 56, -2 36 C 2 20, 10 10, 6 4 Z" fill="#ff6a00" opacity="0.95">
                    <animate attributeName="opacity" values="0.8;1;0.8" dur="1s" repeatCount="indefinite" />
                  </path>
                </g>
              </g>
            </svg>
          </div>
        </div>

      </div>

      <div class="footer">
        <div>
          <div style="font-size:14px;color:var(--muted)">Connect with me:</div>
          <div style="display:flex;gap:8px;margin-top:8px">
            <a href="https://instagram.com/your_instagram_here" target="_blank" rel="noopener" class="icon-link">Instagram</a>
            <a href="https://github.com/your_github_here" target="_blank" rel="noopener" class="icon-link">GitHub</a>
            <a href="#" class="icon-link">LinkedIn</a>
          </div>
        </div>
        <div class="degree">Artificial Intelligence Degree</div>
      </div>

    </div>
  </div>

  <script>
    // Simple interactivity: after 2.2s transform the name into dragon (visual swap)
    window.addEventListener('load', ()=>{
      const name = document.getElementById('name3d');
      const dragon = document.querySelector('.dragon-svg');
      setTimeout(()=>{
        // name scales down and dragon scales up (playful effect)
        name.style.transition = 'transform 1s ease, opacity 1s ease';
        name.style.transform = 'scale(0.42) translateY(-20px) rotateX(15deg)';
        name.style.opacity = '0.9';
        dragon.style.transform = 'scale(1) translateY(0)';
        // Make python skill card on fire for effect
        document.querySelectorAll('[data-skill="python"]').forEach(el=>el.classList.add('on-fire'));
      }, 1200);

      // Make the dragon breathe code-fire towards icons: when you hover a skill, briefly animate flame
      document.querySelectorAll('.skill-card').forEach(card=>{
        card.addEventListener('mouseenter', ()=>{
          card.classList.add('on-fire');
        });
        card.addEventListener('mouseleave', ()=>{
          card.classList.remove('on-fire');
        });
      });
    });
  </script>
</body>
</html>
