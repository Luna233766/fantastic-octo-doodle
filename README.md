<!doctype html>
<html lang="zh-CN">
<head>
<meta charset="utf-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1"/>
<title>Luna Mok · 个人名片</title>
<meta name="theme-color" content="#0ea5e9"/>
<style>
  :root{
    --bg:#0b1220;--card:#0f172a;--text:#e5e7eb;--muted:#a3aab7;
    --primary:#0ea5e9;--accent:#22d3ee;--ok:#10b981;--warn:#f59e0b;
    --shadow:0 12px 40px rgba(2,132,199,.35);
  }
  :root[data-theme='light']{
    --bg:#f6f9fc;--card:#ffffff;--text:#0f172a;--muted:#6b7280;
    --primary:#0284c7;--accent:#06b6d4;--shadow:0 10px 30px rgba(2,132,199,.15);
  }
  *{box-sizing:border-box}
  html,body{height:100%}
  body{
    margin:0; font-family: ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial,
    "Noto Sans","PingFang SC","Microsoft YaHei",sans-serif;
    background:
      radial-gradient(1200px 600px at 90% -10%, rgba(34,211,238,.20), transparent 60%),
      radial-gradient(900px 480px at -10% 110%, rgba(14,165,233,.20), transparent 60%),
      var(--bg);
    color:var(--text); line-height:1.6; display:grid; place-items:center; padding:32px 16px;
  }
  .wrap{width:min(980px,96vw)}
  .card{
    position:relative; overflow:clip;
    background:linear-gradient(180deg, color-mix(in oklab,var(--card) 90%, #fff 10%), var(--card));
    border:1px solid color-mix(in oklab,var(--card),#fff 12%);
    border-radius:26px; box-shadow:var(--shadow);
  }
  .glow{position:absolute; inset:-30% auto auto -30%; width:80%; height:80%;
        background:conic-gradient(from 210deg, transparent 0 60deg, color-mix(in oklab,var(--accent), transparent 60%) 60deg 120deg, transparent 120deg 360deg);
        filter:blur(48px) saturate(1.2); opacity:.35; pointer-events:none; animation:float 11s ease-in-out infinite alternate;}
  @keyframes float{to{transform:translate3d(12px,-10px,0) rotate(2deg)}}

  header{display:grid; grid-template-columns:116px 1fr auto; gap:20px; padding:28px; align-items:center;}
  .avatar{width:116px;height:116px;border-radius:24px;display:grid;place-items:center;overflow:hidden;
          background:linear-gradient(135deg,#0ea5e933,#22d3ee33);
          border:1px solid color-mix(in oklab,var(--card),#fff 14%);}
  .avatar img{width:100%;height:100%;object-fit:cover;display:block}
  .avatar .emoji{font-size:62px}

  .title h1{margin:0 0 6px;font-size:clamp(22px,3.4vw,30px)}
  .title p{margin:0;color:var(--muted)}
  .prefs{display:flex;gap:10px;flex-wrap:wrap;margin-top:10px}
  .seg{display:inline-flex;background:color-mix(in oklab,var(--card),#fff 6%);
       border:1px solid color-mix(in oklab,var(--card),#fff 12%); border-radius:12px; overflow:hidden}
  .seg button{padding:8px 12px;border:none;background:transparent;color:var(--text);cursor:pointer}
  .seg button.active{background:color-mix(in oklab,var(--primary),transparent 85%)}

  .actions{display:flex;gap:10px;flex-wrap:wrap;justify-self:end}
  .btn{--_bg:color-mix(in oklab,var(--primary),#000 5%);--_text:#fff;--_bd:transparent;
       display:inline-flex;align-items:center;gap:.5rem;padding:10px 14px;border-radius:12px;
       border:1px solid var(--_bd);background:var(--_bg);color:var(--_text);
       font-weight:600;text-decoration:none;transition:.2s ease transform,.2s ease filter,.2s ease box-shadow;
       box-shadow:0 6px 18px rgba(14,165,233,.25); cursor:pointer; white-space:nowrap}
  .btn.secondary{--_bg:transparent;--_text:var(--text);--_bd:color-mix(in oklab,var(--text),transparent 70%); box-shadow:none}
  .btn.ghost{--_bg:transparent;--_text:var(--text);--_bd:transparent; box-shadow:none; opacity:.9}
  .btn.ok{--_bg:color-mix(in oklab,var(--ok),#000 5%)} .btn.warn{--_bg:color-mix(in oklab,var(--warn),#000 5%)}
  .btn:hover{transform:translateY(-1px);filter:brightness(1.05)}

  main{padding:12px 28px 24px}
  .grid{display:grid;gap:18px;grid-template-columns:1.2fr 1fr}
  section{background:color-mix(in oklab,var(--card),#fff 4%);border:1px solid color-mix(in oklab,var(--card),#fff 10%);
          border-radius:18px;padding:18px}
  section h2{margin:0 0 8px;font-size:18px}
  .tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:8px}
  .tag{padding:6px 10px;border-radius:999px;border:1px solid color-mix(in oklab,var(--text),transparent 80%);font-size:13px}
  .links{display:grid;gap:10px}
  .link{display:grid;grid-template-columns:28px 1fr auto;gap:12px;align-items:center;padding:10px 12px;border-radius:14px;
        background:color-mix(in oklab,var(--card),#fff 6%);border:1px solid color-mix(in oklab,var(--card),#fff 12%)}
  .link a{color:var(--text);text-decoration:none;font-weight:600}
  .link small{color:var(--muted)}

  .audio{display:grid;gap:10px}
  .audio .hint{color:var(--muted);font-size:13px}

  footer{padding:8px 28px 22px;color:var(--muted);font-size:13px;display:flex;justify-content:space-between;align-items:center}
  .toast{position:fixed;inset:auto 16px 16px auto;background:var(--card);color:var(--text);
         border:1px solid color-mix(in oklab,var(--card),#fff 12%);padding:10px 14px;border-radius:12px;box-shadow:var(--shadow);
         opacity:0;transform:translateY(8px);transition:.25s ease;pointer-events:none}
  .toast.show{opacity:1;transform:translateY(0)}

  @media (max-width:760px){
    header{grid-template-columns:88px 1fr;gap:14px}.avatar{width:88px;height:88px;border-radius:18px}
    .actions{grid-column:1/-1;justify-self:start}.grid{grid-template-columns:1fr}
  }
</style>
</head>
<body>
<div class="wrap">
  <div class="card" role="region" aria-label="个人名片卡片">
    <div class="glow" aria-hidden="true"></div>

    <header>
      <div class="avatar" aria-label="头像"><div class="emoji" aria-hidden="true">🌙</div></div>

      <div class="title">
        <h1 data-i18n="hi">👋 你好，我是 <strong>Luna Mok</strong></h1>
        <p data-i18n="subtitle">产品/创意策划 · 设计爱好者 · 永远在路上 ✨</p>
        <div class="prefs">
          <div class="seg" role="group" aria-label="语言 Language">
            <button id="langZh" class="active">中文</button><button id="langEn">English</button>
          </div>
          <div class="seg" role="group" aria-label="主题 Theme">
            <button id="themeDark" class="active">🌙 深色</button><button id="themeLight">☀️ 浅色</button>
          </div>
        </div>
      </div>

      <div class="actions">
        <a class="btn" id="emailBtn" href="#">✉️ 邮件</a>
        <a class="btn secondary" id="phoneBtn" href="#">📞 电话</a>
        <a class="btn secondary" href="weixin://" id="wxBtn">🟩 打开微信</a>
        <a class="btn secondary" id="xBtn" href="https://x.com/LunaMok198149?s=09" target="_blank" rel="noopener">𝕏 X / Twitter</a>
        <a class="btn ok" id="vcard" download="Luna-Mok.vcf" href="#">📇 下载名片</a>
        <button class="btn ghost" id="shareBtn">🔗 分享</button>
      </div>
    </header>

    <main>
      <div class="grid">
        <section aria-label="关于我">
          <h2 data-i18n="about">关于我</h2>
          <p data-i18n="aboutText">
            我热爱把创意变成可落地的体验，关注产品体验与品牌故事的结合。擅长从 0 → 1 的信息架构、内容策略与跨团队协作。
            空闲时喜欢拍照、旅行和逛展～ 
          </p>
          <div class="tags">
            <span class="tag">产品策划</span><span class="tag">用户体验</span><span class="tag">内容运营</span>
            <span class="tag">轻设计</span><span class="tag">摄影/旅行</span>
          </div>
        </section>

        <section aria-label="音频">
          <h2>🎵 音频介绍</h2>
          <div class="audio">
            <audio id="player" controls preload="none" style="width:100%">
              <source src="VID_20250721200017829.mp3" type="audio/mpeg">
            </audio>
            <div>
              <button class="btn secondary" id="playBtn">▶️ 播放/暂停</button>
              <button class="btn secondary" id="muteBtn">🔇 静音</button>
            </div>
            <div class="hint">若无法播放，请确认仓库里已上传 <code>VID_20250721200017829.mp3</code>（与本页面同目录）。</div>
          </div>
        </section>

        <section aria-label="链接">
          <h2 data-i18n="links">联系与链接</h2>
          <div class="links">
            <div class="link">
              <div>🔗</div><div><a id="siteLink" href="#" target="_blank" rel="noopener">个人主页</a><br><small data-i18n="siteDesc">更多作品与文章</small></div><span>↗</span>
            </div>
            <div class="link">
              <div>💼</div><div><a id="inLink" href="#" target="_blank" rel="noopener">LinkedIn</a><br><small data-i18n="inDesc">职业档案</small></div><span>↗</span>
            </div>
            <div class="link">
              <div>📸</div><div><a id="igLink" href="#" target="_blank" rel="noopener">Instagram</a><br><small data-i18n="igDesc">照片日常</small></div><span>↗</span>
            </div>
            <div class="link">
              <div>💻</div><div><a id="ghLink" href="#" target="_blank" rel="noopener">GitHub</a><br><small data-i18n="ghDesc">项目与代码</small></div><span>↗</span>
            </div>
          </div>
        </section>
      </div>
    </main>

    <footer><span>© <span id="year"></span> Luna Mok</span><span>Made with ❤️</span></footer>
  </div>
</div>

<div class="toast" id="toast" role="status" aria-live="polite">已复制到剪贴板 ✅</div>

<script>
const PROFILE = {
  name: "Luna Mok",
  email: "luna@example.com",
  phone: "15578121642",
  site: "https://luna.example.com",
  linkedin: "https://www.linkedin.com/",
  instagram: "https://instagram.com/",
  github: "https://github.com/Luna233766",
  city: "Los Angeles, CA"
};
const $ = s => document.querySelector(s);
$("#year").textContent = new Date().getFullYear();
$("#emailBtn").href = "mailto:" + PROFILE.email;
$("#phoneBtn").href = "tel:" + PROFILE.phone;
$("#siteLink").href = PROFILE.site;
$("#inLink").href = PROFILE.linkedin;
$("#igLink").href = PROFILE.instagram;
$("#ghLink").href = PROFILE.github;

// 音频按钮
const player = $("#player");
$("#playBtn").addEventListener("click", ()=> player.paused ? player.play() : player.pause());
$("#muteBtn").addEventListener("click", ()=> player.muted = !player.muted);
</script>
</body>
</html>
