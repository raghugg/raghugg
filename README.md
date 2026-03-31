
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  .gh-card {
    background: var(--color-background-primary);
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: var(--border-radius-lg);
    padding: 2rem 2.5rem;
    max-width: 800px;
    margin: 1rem auto;
    font-size: 15px;
    color: var(--color-text-primary);
    line-height: 1.7;
  }
  .label-bar {
    display: flex; align-items: center; gap: 8px;
    font-size: 12px; color: var(--color-text-secondary);
    margin-bottom: 1.5rem; font-family: monospace;
  }
  .dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; }
  .dot-red { background: #E24B4A; } .dot-amber { background: #EF9F27; } .dot-green { background: #639922; }
  .tab-row {
    display: flex; gap: 0; margin-bottom: 1.5rem;
    border-bottom: 0.5px solid var(--color-border-tertiary);
  }
  .tab {
    font-size: 13px; padding: 8px 16px; cursor: pointer;
    color: var(--color-text-secondary);
    border-bottom: 2px solid transparent; margin-bottom: -0.5px;
    background: none; border-top: none; border-left: none; border-right: none;
    font-family: inherit;
  }
  .tab.active { color: var(--color-text-primary); border-bottom: 2px solid #378ADD; font-weight: 500; }
  .panel { display: none; }
  .panel.active { display: block; }
  .badges { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 1.5rem; }
  .badge { font-size: 12px; font-weight: 500; padding: 4px 12px; border-radius: 20px; font-family: monospace; }
  .b-blue { background: #E6F1FB; color: #0C447C; }
  .b-teal { background: #E1F5EE; color: #085041; }
  .b-purple { background: #EEEDFE; color: #3C3489; }
  .b-gray { background: #F1EFE8; color: #444441; }
  .b-amber { background: #FAEEDA; color: #633806; }
  .b-coral { background: #FAECE7; color: #712B13; }
  .section-title {
    font-size: 12px; font-weight: 500; color: var(--color-text-secondary);
    letter-spacing: 0.07em; text-transform: uppercase; margin-bottom: 0.75rem; margin-top: 1.5rem;
  }
  .about-text {
    font-size: 14px; color: var(--color-text-primary); line-height: 1.85;
    padding: 1rem 1.25rem;
    background: var(--color-background-secondary);
    border-radius: var(--border-radius-md);
    border-left: 2px solid #534AB7;
    margin-bottom: 1.5rem;
  }
  .highlight-row { display: flex; flex-direction: column; gap: 10px; margin-bottom: 1.5rem; }
  .highlight-item {
    display: flex; gap: 12px; align-items: flex-start;
    background: var(--color-background-secondary);
    border-radius: var(--border-radius-md);
    padding: 0.75rem 1rem;
    font-size: 13px;
  }
  .hi-icon { font-size: 16px; min-width: 22px; }
  .hi-body { display: flex; flex-direction: column; gap: 2px; }
  .hi-title { font-weight: 500; font-size: 13px; }
  .hi-sub { font-size: 12px; color: var(--color-text-secondary); }
  .currently { display: flex; align-items: center; gap: 8px; font-size: 13px; color: var(--color-text-secondary); margin-bottom: 0.4rem; }
  .pulse { width: 8px; height: 8px; border-radius: 50%; background: #639922; display: inline-block; animation: pulse 1.8s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.3} }
  .links-row { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 1.5rem; }
  .link-btn {
    font-size: 13px; font-weight: 500; padding: 6px 16px;
    border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-secondary);
    background: var(--color-background-primary);
    color: var(--color-text-primary); cursor: pointer; text-decoration: none;
    display: flex; align-items: center; gap: 6px;
  }
  .divider { border: none; border-top: 0.5px solid var(--color-border-tertiary); margin: 1.25rem 0; }
  pre.code-block {
    background: var(--color-background-secondary);
    border-radius: var(--border-radius-md);
    padding: 1.25rem; font-size: 11.5px; font-family: monospace;
    color: var(--color-text-primary); overflow-x: auto;
    line-height: 1.75; white-space: pre;
    border: 0.5px solid var(--color-border-tertiary);
  }
  .comment { color: #888780; }
  .copy-btn {
    display: inline-block; margin-top: 1.25rem; font-size: 13px;
    padding: 8px 18px; border-radius: var(--border-radius-md);
    border: 0.5px solid var(--color-border-secondary);
    background: var(--color-background-primary); color: var(--color-text-primary);
    cursor: pointer; font-family: inherit;
  }
  .copy-btn:hover { background: var(--color-background-secondary); }
  .stat-card { background: var(--color-background-secondary); border-radius: var(--border-radius-md); padding: 0.9rem 1rem; }
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 1.5rem; }
  h1.hero { font-size: 26px; font-weight: 500; margin-bottom: 0.35rem; letter-spacing: -0.5px; }
  .tagline { font-size: 14px; color: var(--color-text-secondary); margin-bottom: 1.5rem; }
</style>

<div class="gh-card">
  <div class="label-bar">
    <span class="dot dot-red"></span><span class="dot dot-amber"></span><span class="dot dot-green"></span>
    <span style="margin-left:4px;">README.md — raghugg/raghugg</span>
  </div>

  <div class="tab-row">
    <button class="tab active" onclick="switchTab('preview',this)">Preview</button>
    <button class="tab" onclick="switchTab('code',this)">README.md code</button>
    <button class="tab" onclick="switchTab('setup',this)">How to set it up</button>
  </div>

  <!-- PREVIEW TAB -->
  <div id="tab-preview" class="panel active">
    <h1 class="hero">Hey, I'm Raghu 👋</h1>
    <p class="tagline">CS grad · HPC & quantum computing researcher · software engineer</p>

    <div class="currently"><span class="pulse"></span> Open to SWE roles — DC/Baltimore area & remote</div>
    <div class="currently" style="color:var(--color-text-secondary)"><span style="width:8px;height:8px;display:inline-block"></span> B.S. Computer Science (magna cum laude) · George Mason University · 3.82 GPA</div>

    <hr class="divider">

    <div class="section-title">Tech stack</div>
    <div class="badges">
      <span class="badge b-blue">C++</span>
      <span class="badge b-blue">Python</span>
      <span class="badge b-blue">Java</span>
      <span class="badge b-blue">JavaScript</span>
      <span class="badge b-teal">React</span>
      <span class="badge b-teal">Node.js</span>
      <span class="badge b-purple">OpenMP</span>
      <span class="badge b-purple">SLURM</span>
      <span class="badge b-purple">Qiskit</span>
      <span class="badge b-gray">Git</span>
      <span class="badge b-gray">Linux</span>
      <span class="badge b-amber">MongoDB</span>
      <span class="badge b-amber">SQL</span>
    </div>

    <div class="section-title">About</div>
    <div class="about-text">
      Recent CS grad (magna cum laude, GMU) with research experience at <strong>Argonne National Laboratory</strong> and GMU's MEGL lab. I build high-performance systems — from quantum circuit simulators achieving sub-10ns precision to parallel algorithms that cut runtimes from 7 minutes to 7 seconds. I also ship full-stack products: most recently a hackathon AI resume tool. Looking for SWE roles where I can write code that actually matters.
    </div>

    <div class="section-title">Highlights</div>
    <div class="highlight-row">
      <div class="highlight-item">
        <span class="hi-icon">⚛️</span>
        <div class="hi-body">
          <span class="hi-title">Research Intern — Argonne National Laboratory (DOE-SULI)</span>
          <span class="hi-sub">Built C++ & Python Pauli-Propagation simulators with OpenMP parallelization · 16+ qubit circuits · &lt;1e-9 error</span>
        </div>
      </div>
      <div class="highlight-item">
        <span class="hi-icon">🚀</span>
        <div class="hi-body">
          <span class="hi-title">HPC Research — Mason Experimental Geometry Lab</span>
          <span class="hi-sub">~60× speedup on HPC cluster with OpenMP + SLURM · Presented at JMM 2025 in Seattle</span>
        </div>
      </div>
      <div class="highlight-item">
        <span class="hi-icon">🏆</span>
        <div class="hi-body">
          <span class="hi-title">Hackathon — Job Hunter AI App (48 hrs)</span>
          <span class="hi-sub">Full-stack React/Vite + Cloudflare Worker · Gemini API · Live at jobhunters.app</span>
        </div>
      </div>
      <div class="highlight-item">
        <span class="hi-icon">🖥️</span>
        <div class="hi-body">
          <span class="hi-title">OS/161 — Operating System from scratch (C)</span>
          <span class="hi-sub">Syscalls, threading, memory management, concurrency · Source available on request</span>
        </div>
      </div>
    </div>

    <div class="section-title">GitHub stats</div>
    <div class="grid-2">
      <div class="stat-card" style="font-size:12px; color:var(--color-text-secondary); display:flex; align-items:center; justify-content:center; min-height:60px; text-align:center">GitHub stats widget renders here<br/>(replace "raghugg" in code)</div>
      <div class="stat-card" style="font-size:12px; color:var(--color-text-secondary); display:flex; align-items:center; justify-content:center; min-height:60px; text-align:center">Streak stats widget renders here</div>
    </div>

    <div class="links-row">
      <span class="link-btn">💼 LinkedIn</span>
      <span class="link-btn">🌐 jobhunters.app</span>
      <span class="link-btn">📬 guggilam.raghu@gmail.com</span>
    </div>
  </div>

  <!-- CODE TAB -->
  <div id="tab-code" class="panel">
    <pre class="code-block" id="readme-code"><span class="comment">&lt;!--
  GitHub Profile README — Raghavendra Guggilam
  Repo: github.com/raghugg/raghugg
--&gt;</span>

# Hey, I'm Raghu 👋

&gt; CS grad · HPC &amp; quantum computing researcher · software engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/raghavendra-guggilam)
[![Portfolio](https://img.shields.io/badge/jobhunters.app-000?style=flat&logo=vercel&logoColor=white)](https://jobhunters.app)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:guggilam.raghu@gmail.com)

---

## 🛠 Tech Stack

**Languages**
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)

**Frameworks &amp; Tools**
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![OpenMP](https://img.shields.io/badge/OpenMP-gray?style=flat)
![Qiskit](https://img.shields.io/badge/Qiskit-6929C4?style=flat&logo=ibm&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

---

## 👤 About Me

- 🎓 **B.S. Computer Science**, George Mason University — *magna cum laude*, GPA 3.82
- ⚛️ Research intern at **Argonne National Laboratory** (DOE-SULI program)
- 🔬 Built quantum circuit simulators and parallel HPC systems with C++, Python, OpenMP, SLURM
- 🚀 Presented research at **Joint Mathematics Meetings 2025** in Seattle
- 🌱 Currently exploring full-stack engineering and distributed systems
- 📫 Reach me at **guggilam.raghu@gmail.com**
- ⚡ Fun fact: Eagle Scout 🦅

---

## 🔬 Research Highlights

| Where | What | Impact |
|-------|------|--------|
| Argonne National Lab (DOE-SULI) | Pauli-Propagation quantum simulator (C++ &amp; Python) | &lt;1e-9 error vs Qiskit reference |
| GMU MEGL Lab | Parallel Tempering for logic circuit synthesis | ~60× speedup on HPC cluster |
| JMM 2025 (Seattle) | Presented stochastic &amp; quantum algorithms research | GMU-funded ($1,200 grant) |

---

## 🚀 Featured Projects

### [Job Hunter](https://jobhunters.app) — AI Resume &amp; Job Search App
`React` `Vite` `Cloudflare Workers` `Gemini API`
&gt; 48-hour hackathon · Full-stack AI resume analyzer · ATS gap detection · automated resume generation

### OS/161 — Operating System from Scratch
`C` `Concurrency` `Systems Programming`
&gt; Syscalls (fork, exec, waitpid), threading, memory management, synchronization primitives — source available on request

### Planetary Exploration — Browser Clicker Game
`HTML` `JavaScript` `CSS`
&gt; Led 4-person team · incremental game with item shop and planet progression

---

## 📊 GitHub Stats

&lt;p align="center"&gt;
  &lt;img src="https://github-readme-stats.vercel.app/api?username=raghugg&show_icons=true&theme=default&hide_border=true&count_private=true" width="48%"/&gt;
  &lt;img src="https://github-readme-streak-stats.herokuapp.com/?user=raghugg&hide_border=true" width="48%"/&gt;
&lt;/p&gt;

&lt;p align="center"&gt;
  &lt;img src="https://github-readme-stats.vercel.app/api/top-langs/?username=raghugg&layout=compact&hide_border=true&langs_count=8" width="42%"/&gt;
&lt;/p&gt;

---

&lt;p align="center"&gt;
  &lt;i&gt;Open to SWE roles — DC/Baltimore area &amp; remote&lt;/i&gt;
&lt;/p&gt;</pre>
    <button class="copy-btn" onclick="copyCode()">Copy README.md</button>
    <span id="copy-confirm" style="font-size:13px; color:#639922; margin-left:12px; display:none;">Copied!</span>
  </div>

  <!-- SETUP TAB -->
  <div id="tab-setup" class="panel">
    <div class="section-title">3 steps to go live</div>
    <div style="display:flex; flex-direction:column; gap:12px;">
      <div class="stat-card" style="display:flex; gap:14px; align-items:flex-start;">
        <span style="font-size:20px; font-weight:500; color:#378ADD; min-width:28px;">1</span>
        <div>
          <div style="font-weight:500; font-size:14px; margin-bottom:4px;">Create a special repo</div>
          <div style="font-size:13px; color:var(--color-text-secondary);">Go to GitHub → New repository. Name it exactly <span style="font-family:monospace; background:var(--color-background-primary); padding:1px 6px; border-radius:4px; border:0.5px solid var(--color-border-tertiary);">raghugg</span> (same as your username). Make it public, check "Add a README".</div>
        </div>
      </div>
      <div class="stat-card" style="display:flex; gap:14px; align-items:flex-start;">
        <span style="font-size:20px; font-weight:500; color:#378ADD; min-width:28px;">2</span>
        <div>
          <div style="font-weight:500; font-size:14px; margin-bottom:4px;">Paste & save the code</div>
          <div style="font-size:13px; color:var(--color-text-secondary);">Copy the README.md code from the tab above. Edit the file in GitHub directly, paste it in, commit. Done.</div>
        </div>
      </div>
      <div class="stat-card" style="display:flex; gap:14px; align-items:flex-start;">
        <span style="font-size:20px; font-weight:500; color:#378ADD; min-width:28px;">3</span>
        <div>
          <div style="font-weight:500; font-size:14px; margin-bottom:4px;">Check your profile</div>
          <div style="font-size:13px; color:var(--color-text-secondary);">Visit github.com/raghugg — the README appears automatically at the top. Stats widgets load live from your real data.</div>
        </div>
      </div>
    </div>
    <div style="margin-top:1.25rem; padding:1rem; background:var(--color-background-secondary); border-radius:var(--border-radius-md); font-size:13px; color:var(--color-text-secondary); line-height:1.8;">
      <strong style="color:var(--color-text-primary);">One thing to verify:</strong> Your GitHub username appears to be <span style="font-family:monospace">raghugg</span> (from your resume). If it's different, do a find-replace on "raghugg" in the code before pasting.
    </div>
  </div>
</div>

<script>
function switchTab(name, el) {
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  el.classList.add('active');
  document.getElementById('tab-' + name).classList.add('active');
}
function copyCode() {
  const code = document.getElementById('readme-code').innerText;
  navigator.clipboard.writeText(code).then(() => {
    const c = document.getElementById('copy-confirm');
    c.style.display = 'inline';
    setTimeout(() => c.style.display = 'none', 2000);
  });
}
</script>
