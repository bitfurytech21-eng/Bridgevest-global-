<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>BridgeVest Global — Building Wealth, Securing Futures</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
:root{
  --blue-900:#032b5b;
  --blue-700:#0b4a8a;
  --blue-500:#1f73b7;
  --accent:#ffd166;
  --muted:#6b7280;
  --glass: rgba(255,255,255,0.06);
  --card: #ffffff;
  --radius:14px;
  font-family: "Inter", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
}
*{box-sizing:border-box}
body{
  margin:0;
  color:#083042;
  background: linear-gradient(180deg,#eaf4ff 0%, #ffffff 100%);
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
  line-height:1.45;
}
.topbar{
  display:flex;
  justify-content:space-between;
  gap:10px;
  padding:10px 20px;
  background:linear-gradient(90deg, rgba(255,255,255,0.25), rgba(255,255,255,0.12));
  align-items:center;
  border-bottom:1px solid rgba(10,20,30,0.04);
  position:sticky;
  top:0;
  z-index:40;
  backdrop-filter: blur(6px);
}
.lang-select{
  display:flex;
  gap:8px;
  align-items:center;
  font-size:14px;
  color:var(--blue-900);
}
.auth-actions{display:flex; gap:8px; align-items:center;}
.btn{
  background:var(--blue-700);
  color:white;
  padding:8px 14px;
  border-radius:10px;
  border:0;
  cursor:pointer;
  font-weight:600;
  box-shadow: 0 6px 18px rgba(15,60,120,0.12);
}
.btn.ghost{background:transparent;color:var(--blue-700);border:1px solid rgba(15,60,120,0.08);box-shadow:none}
.brand{display:flex;align-items:center;gap:12px;font-weight:700;color:var(--blue-900)}
.brand .logo{
  width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--blue-700),var(--blue-500));
  display:flex;align-items:center;justify-content:center;color:white;font-weight:800;
}
.hero{
  display:grid;
  grid-template-columns: 1fr 420px;
  gap:32px;
  align-items:center;
  padding:48px 6vw;
  min-height:68vh;
  background:
    linear-gradient(180deg, rgba(2,48,77,0.03), rgba(255,255,255,0.0));
}
.hero-left{max-width:820px;}
.hero h1{font-size:34px;margin:0 0 12px 0;color:var(--blue-900);line-height:1.06;}
.hero p{color:var(--muted);margin:0 0 18px 0; font-size:16px;}
.hero .cta{display:flex;gap:12px}
.hero-card{
  border-radius:18px;
  overflow:hidden;
  position:relative;
  box-shadow:0 24px 60px rgba(10,30,60,0.08);
  background:linear-gradient(180deg,rgba(255,255,255,0.6),rgba(255,255,255,0.4));
  padding:18px;
}
.hero-visual{
  border-radius:16px;
  height:100%;
  min-height:280px;
  background-image: url("https://images.unsplash.com/photo-1509395176047-4a66953fd231?q=80&w=1400&auto=format&fit=crop&ixlib=rb-4.0.3&s=7f1f3c9c9cde785e2b2d0b7f3f5b5a0a");
  background-size:cover;
  background-position:center;
  position:relative;
  display:flex;
  flex-direction:column;
  justify-content:flex-end;
  color:white;
}
.hero-visual .overlay{
  padding:18px;
  background:linear-gradient(180deg, transparent, rgba(3,43,91,0.6));
}
section{padding:36px 6vw}
.container{max-width:1100px;margin:0 auto}
.grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.card{
  background:white;
  border-radius:12px;
  padding:18px;
  box-shadow:0 12px 30px rgba(10,30,60,0.04);
}
.muted{color:var(--muted)}
.charts {display:flex; gap:18px; align-items:stretch;}
.chart-card{flex:1;padding:14px;border-radius:12px;background:linear-gradient(180deg,#ffffff,#f8fbff);}
.programs{display:flex;gap:12px;flex-wrap:wrap}
.program{flex:1;min-width:220px;padding:16px;border-radius:12px;background:linear-gradient(180deg,#fff,#f9fdff);}
footer{
  padding:28px 6vw;
  background:linear-gradient(180deg, rgba(3,43,91,0.02), rgba(3,43,91,0.01));
  color:var(--muted);
}
.footer-grid{display:flex;gap:18px;flex-wrap:wrap;align-items:flex-start}
.modal-backdrop{position:fixed;inset:0;background:rgba(3,12,25,0.45);display:none;align-items:center;justify-content:center;z-index:80}
.modal{background:white;border-radius:12px;padding:18px;min-width:320px;max-width:520px;box-shadow:0 30px 80px rgba(3,20,40,0.3)}
.form-row{display:flex;flex-direction:column;gap:8px;margin-bottom:12px}
input,select{padding:10px;border-radius:8px;border:1px solid rgba(10,20,30,0.06)}
.small{font-size:13px;color:var(--muted)}
@media (max-width:980px){
  .hero{grid-template-columns:1fr; padding:28px 4vw; gap:20px}
  .grid-3{grid-template-columns:1fr}
  .hero h1{font-size:28px}
  .topbar{padding:8px 12px}
  .hero-visual{min-height:220px}
}
</style>
</head>
<body>

<!-- TOP BAR -->
<div class="topbar">
  <div style="display:flex;align-items:center;gap:14px;">
    <div class="brand" aria-hidden="true">
      <div class="logo">BV</div>
      <div>
        <div style="font-size:14px">BridgeVest Global</div>
        <div class="small muted">Building Wealth, Securing Futures</div>
      </div>
    </div>
    <div class="lang-select">
      🌐
      <select aria-label="Select language" id="langSelect">
        <option>English</option>
        <option>French</option>
        <option>Spanish</option>
        <option>Chinese</option>
        <option>Arabic</option>
      </select>
    </div>
  </div>
  <div class="auth-actions">
    <button class="btn ghost" id="btnLogin">Login</button>
    <button class="btn" id="btnRegister">Create Account</button>
  </div>
</div>

<!-- HERO -->
<header class="hero" role="banner">
  <div class="hero-left">
    <div style="display:flex;gap:10px;align-items:center;margin-bottom:8px">
      <div style="background:var(--accent);padding:6px 10px;border-radius:999px;font-weight:700;color:#07324a">New</div>
      <div class="small muted">Now open: Agriculture & Real Estate investments</div>
    </div>
    <h1>Your Bridge to Smarter Investments through Agriculture, Real Estate, and Beyond.</h1>
    <p>Where technology meets opportunity. Invest in verified agricultural and real estate ventures powered by transparency and innovation.</p>
    <div class="cta" style="margin-top:18px">
      <button class="btn" id="ctaLogin">Login</button>
      <button class="btn ghost" id="ctaCreate">Create Account</button>
    </div>
    <div style="margin-top:26px" class="hero-card">
      <strong>How it works</strong>
      <div style="display:flex;gap:10px;margin-top:12px;">
        <div style="flex:1">
          <div class="small muted">Step 1</div>
          <div>Register an account</div>
        </div>
        <div style="flex:1">
          <div class="small muted">Step 2</div>
          <div>Fund your account</div>
        </div>
        <div style="flex:1">
          <div class="small muted">Step 3</div>
          <div>Choose a plan & invest</div>
        </div>
      </div>
    </div>
  </div>
  <div class="hero-visual" aria-hidden="true">
    <div class="overlay">
      <div style="display:flex;justify-content:space-between;align-items:center;">
        <div>
          <div style="font-weight:700">BridgeVest Live</div>
          <div class="small">Agri & Property indices • Updated in real-time </div>
        </div>
        <div style="background:rgba(255,255,255,0.12);padding:8px;border-radius:10px;font-weight:600">Invest</div>
      </div>
    </div>
  </div>
</header>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div style="display:flex;justify-content:space-between;align-items:flex-start;gap:18px;flex-wrap:wrap">
      <div style="flex:1;min-width:300px">
        <h2>About BridgeVest Global</h2>
        <p class="muted">BridgeVest Global is a diversified asset management company transforming agriculture and real estate into transparent, high-yielding opportunities through a professional and technology-driven ecosystem. Our integrated model merges human expertise, AI forecasting, and blockchain transparency.</p>
        <p class="small muted">
          <strong>Vision:</strong> To make agriculture and real estate the world’s most accessible, trusted, and profitable investment classes. To democratize access to opportunities that drive food security, housing, and sustainable wealth globally. <br>
          <strong>Mission:</strong> To bridge people from capital to opportunity, turning ordinary savings into growth through innovation, integrity, and expert management, connecting sustainable assets with smart financial technology. <br>
          <strong>Motto:</strong> “Building Wealth, Securing Futures.”
        </p>
      </div>
      <div style="width:420px">
        <div class="card">
          <strong>Why choose BridgeVest</strong>
          <ul style="margin:10px 0 0 18px;color:var(--muted)">
            <li>Licensed & Certified — investor protection</li>
            <li>Blockchain-backed transparency</li>
            <li>Flexible Strategies across asset classes</li>
            <li>24/7 Live support</li>
          </ul>
          <div style="margin-top:12px;display:flex;gap:8px">
            <button class="btn" onclick="backendCall('ExplorePlans')">Explore Our Plans</button>
            <button class="btn ghost" onclick="backendCall('ContactSupport')">Contact</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- BOARDS OF DIRECTORS -->
<section id="boards">
  <div class="container">
    <h2>Board of Directors</h2>
    <div class="grid-3" style="margin-top:12px">
      <div class="card">
        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Director 1" style="width:100%;border-radius:12px;object-fit:cover"/>
        <h4>John Doe</h4>
        <div class="small muted">CEO</div>
      </div>
      <div class="card">
        <img src="https://randomuser.me/api/portraits/women/44.jpg" alt="Director 2" style="width:100%;border-radius:12px;object-fit:cover"/>
        <h4>Jane Smith</h4>
        <div class="small muted">CFO</div>
      </div>
      <div class="card">
        <img src="https://randomuser.me/api/portraits/men/55.jpg" alt="Director 3" style="width:100%;border-radius:12px;object-fit:cover"/>
        <h4>Michael Lee</h4>
        <div class="small muted">COO</div>
      </div>
    </div>
  </div>
</section>

<!-- INVESTMENTS -->
<section id="investments" style="background:linear-gradient(180deg,rgba(15,70,130,0.02),transparent)">
  <div class="container">
    <h3>Our Best Investments</h3>
    <div class="grid-3" style="margin-top:14px">
      <div class="card">
        <h4>Agriculture Investment</h4>
        <p class="muted">Connect with real agricultural assets. Invest across value chains from plantations to processing. Your investment serves as the seed managed by our professionals to yield measurable growth.</p>
        <div style="display:flex;gap:8px;margin-top:10px">
          <button class="btn" onclick="backendCall('AgriViewPlans')">View Plans</button>
          <button class="btn ghost" onclick="backendCall('AgriRentLand')">Rent a Land</button>
        </div>
      </div>
      <div class="card">
        <h4>Real Estate Investment</h4>
        <p class="muted">Property leasing, construction projects and estate development without hands-on management.</p>
        <div style="display:flex;gap:8px;margin-top:10px">
          <button class="btn" onclick="backendCall('RealEstatePlans')">View Plans</button>
          <button class="btn ghost" onclick="backendCall('RentBuild')">Rent & Build</button>
        </div>
      </div>
      <div class="card">
        <h4>Commodity & Property Indices</h4>
        <canvas id="commodityChart" height="150"></canvas>
        <canvas id="propertyChart" height="150" style="margin-top:12px;"></canvas>
      </div>
    </div>
  </div>
</section>

<!-- PROGRAMS -->
<section id="programs">
  <div class="container">
    <h3>Programs & Initiatives</h3>
    <div class="programs" style="margin-top:12px">
      <div class="program">
        <strong>Investor Referral</strong>
        <div class="small muted">Earn commission for every successful referral.</div>
      </div>
      <div class="program">
        <strong>BridgeVest Partner</strong>
        <div class="small muted">Collaborate on verified projects worldwide.</div>
      </div>
      <div class="program">
        <strong>Learn & Earn</strong>
        <div class="small muted">Grow your investment knowledge while earning rewards.</div>
      </div>
    </div>
  </div>
</section>

<!-- NEWSLETTER -->
<section id="newsletter" style="background:linear-gradient(180deg,#f7fbff,#ffffff)">
  <div class="container" style="display:flex;gap:18px;align-items:center;justify-content:space-between;flex-wrap:wrap">
    <div style="flex:1;min-width:260px">
      <h3>Stay Ahead with BridgeVest Updates</h3>
      <p class="muted">Subscribe to receive project insights, forecasts and investor opportunities.</p>
    </div>
    <div style="min-width:320px;display:flex;gap:8px">
      <input id="newsletterEmail" placeholder="Enter Email Address" type="email" style="flex:1" />
      <button class="btn" onclick="backendCall('SubscribeNewsletter', document.getElementById('newsletterEmail').value)">Subscribe</button>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container" style="display:flex;gap:18px;align-items:flex-start;flex-wrap:wrap">
    <div style="flex:1;min-width:300px">
      <h4>Contact Us</h4>
      <p class="muted">support@bridgevestglobal.com <br>WhatsApp: Direct Investor Line</p>
      <div class="small muted">Offices: Washington DC | London | Netherlands | California | Belgium</div>
    </div>
    <div style="min-width:220px">
      <h4>Social</h4>
      <div style="display:flex;flex-direction:column;gap:6px">
        <a href="#" class="small muted">Telegram – BridgeVest Global</a>
        <a href="#" class="small muted">Subscribe to Newsletter</a>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="
