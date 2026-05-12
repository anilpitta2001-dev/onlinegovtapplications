# onlinegovtapplications
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>India Gov Services Portal</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=Noto+Sans:ital,wght@0,300;0,400;0,500;1,400&display=swap" rel="stylesheet">
<style>
:root {
  --saffron: #FF6B00;
  --saffron2: #ff8c00;
  --green: #138808;
  --navy: #000080;
  --navy2: #1a1aaa;
  --bg: #eef2ff;
  --card: #ffffff;
  --text: #1a1a2e;
  --muted: #5a5a7a;
  --gold: #FFD700;
  --shadow: 0 4px 24px rgba(0,0,100,0.10);
}
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: 'Noto Sans', sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }

.tribar { height:6px; background: linear-gradient(to right, #FF6B00 33.33%, #fff 33.33%, #fff 66.66%, #138808 66.66%); }

header {
  background: linear-gradient(135deg, #000060 0%, #00008a 100%);
  padding: 22px 48px;
  display: flex; align-items: center; gap: 20px;
  position: relative; overflow: hidden;
}
header::after {
  content: ''; position: absolute; right: -80px; top: -80px;
  width: 300px; height: 300px;
  background: radial-gradient(circle, rgba(255,215,0,0.07), transparent 70%);
  border-radius: 50%; pointer-events: none;
}
.emblem {
  width: 68px; height: 68px;
  background: radial-gradient(circle at 40% 35%, #ffe566, #c9a400);
  border-radius: 50%; display: flex; align-items: center; justify-content: center;
  font-size: 34px; flex-shrink: 0;
  box-shadow: 0 0 0 3px rgba(255,215,0,0.25), 0 6px 24px rgba(0,0,0,0.4);
}
.header-text h1 { font-family:'Rajdhani',sans-serif; font-size:1.85rem; font-weight:700; color:#fff; letter-spacing:0.5px; line-height:1.15; }
.header-text h1 span { color: var(--gold); }
.header-text p { color: rgba(255,255,255,0.55); font-size: 0.82rem; margin-top: 4px; }
.header-right { margin-left: auto; display: flex; gap: 10px; }
.badge { background: rgba(255,255,255,0.08); border: 1px solid rgba(255,255,255,0.18); color: rgba(255,255,255,0.85); padding: 6px 14px; border-radius: 20px; font-size: 0.73rem; font-weight: 500; white-space: nowrap; }

nav { background: #00005a; border-bottom: 2px solid var(--saffron); padding: 0 40px; display: flex; gap: 2px; overflow-x: auto; }
nav a { color: rgba(255,255,255,0.7); text-decoration: none; padding: 13px 16px; font-family:'Rajdhani',sans-serif; font-size:0.85rem; font-weight:600; letter-spacing:0.4px; white-space:nowrap; border-bottom:3px solid transparent; transition:all 0.2s; cursor:pointer; }
nav a:hover { color: var(--gold); border-bottom-color: var(--gold); }

.hero { background: linear-gradient(160deg, #fff 0%, #e6ecff 60%, #d8e6ff 100%); padding: 52px 48px 36px; text-align: center; border-bottom: 4px solid; border-image: linear-gradient(to right, var(--saffron), #fff 40%, #fff 60%, var(--green)) 1; }
.hero h2 { font-family:'Rajdhani',sans-serif; font-size:2.3rem; font-weight:700; color:var(--navy); }
.hero h2 em { font-style:normal; color:var(--saffron); }
.hero p { color:var(--muted); font-size:0.97rem; margin:12px auto 0; max-width:560px; line-height:1.65; }
.hero-stats { display:flex; justify-content:center; gap:48px; margin-top:30px; flex-wrap:wrap; }
.stat-num { font-family:'Rajdhani',sans-serif; font-size:2rem; font-weight:700; color:var(--navy); }
.stat-label { font-size:0.75rem; color:var(--muted); text-transform:uppercase; letter-spacing:0.5px; }

main { max-width:1260px; margin:0 auto; padding:44px 28px 60px; }

.notice { background:#fffbeb; border:1px solid #fde68a; border-left:5px solid var(--saffron); border-radius:10px; padding:14px 18px; margin-bottom:36px; display:flex; align-items:flex-start; gap:12px; font-size:0.84rem; color:#78350f; line-height:1.55; }
.notice .ni { font-size:1.3rem; flex-shrink:0; }
.notice strong { color:#92400e; }

.sec-head { font-family:'Rajdhani',sans-serif; font-size:1.55rem; font-weight:700; color:var(--navy); display:flex; align-items:center; gap:12px; margin-bottom:6px; }
.sec-head::after { content:''; flex:1; height:2px; background:linear-gradient(to right, var(--saffron), transparent); }
.sec-sub { color:var(--muted); font-size:0.84rem; margin-bottom:28px; }

.grid { display:grid; grid-template-columns:repeat(auto-fill, minmax(310px, 1fr)); gap:22px; margin-bottom:56px; }

.card { background:var(--card); border-radius:16px; overflow:hidden; border:1px solid rgba(0,0,128,0.07); box-shadow:var(--shadow); transition:transform 0.25s, box-shadow 0.25s; animation:fadeUp 0.45s ease both; position:relative; }
.card:hover { transform:translateY(-6px); box-shadow:0 16px 48px rgba(0,0,128,0.14); }
@keyframes fadeUp { from{opacity:0;transform:translateY(28px)} to{opacity:1;transform:translateY(0)} }
.card:nth-child(1){animation-delay:.05s}.card:nth-child(2){animation-delay:.1s}
.card:nth-child(3){animation-delay:.15s}.card:nth-child(4){animation-delay:.2s}
.card:nth-child(5){animation-delay:.25s}.card:nth-child(6){animation-delay:.3s}
.card:nth-child(7){animation-delay:.35s}.card:nth-child(8){animation-delay:.4s}

.card-stripe { height:5px; }
.card-body { padding:22px 22px 20px; }
.card-top { display:flex; align-items:flex-start; gap:14px; margin-bottom:14px; }
.card-ico { width:52px; height:52px; border-radius:13px; display:flex; align-items:center; justify-content:center; font-size:26px; flex-shrink:0; }
.card-title { font-family:'Rajdhani',sans-serif; font-size:1.18rem; font-weight:700; color:var(--navy); line-height:1.2; }
.card-min { font-size:0.72rem; color:var(--muted); margin-top:2px; }
.card-tag { position:absolute; top:14px; right:14px; background:var(--green); color:#fff; font-size:0.65rem; font-weight:700; padding:3px 9px; border-radius:20px; text-transform:uppercase; letter-spacing:0.5px; }
.card-desc { font-size:0.83rem; color:var(--muted); line-height:1.6; margin-bottom:16px; }
.card-feat { list-style:none; margin-bottom:18px; }
.card-feat li { font-size:0.79rem; color:#444; padding:3px 0; display:flex; align-items:center; gap:8px; }
.card-feat li::before { content:'✓'; color:var(--green); font-weight:700; flex-shrink:0; }
.card-btns { display:flex; gap:9px; flex-wrap:wrap; }

.btn { flex:1; min-width:110px; display:inline-flex; align-items:center; justify-content:center; gap:5px; padding:10px 16px; border-radius:8px; font-family:'Rajdhani',sans-serif; font-size:0.88rem; font-weight:700; letter-spacing:0.4px; cursor:pointer; border:none; text-decoration:none; transition:all 0.2s; }
.btn-main { background:linear-gradient(135deg, var(--navy), var(--navy2)); color:#fff; }
.btn-main:hover { background:linear-gradient(135deg, var(--saffron), var(--saffron2)); }
.btn-alt { background:transparent; border:2px solid var(--navy) !important; color:var(--navy); }
.btn-alt:hover { background:var(--navy); color:#fff; }

.ql-section { background:linear-gradient(135deg,#000065,#00008f); border-radius:20px; padding:38px 36px; margin-bottom:56px; position:relative; overflow:hidden; }
.ql-section::before { content:''; position:absolute; top:-60px; right:-60px; width:320px; height:320px; background:radial-gradient(circle,rgba(255,215,0,0.07),transparent 70%); border-radius:50%; pointer-events:none; }
.ql-section h3 { font-family:'Rajdhani',sans-serif; font-size:1.45rem; color:#fff; margin-bottom:6px; }
.ql-section > p { color:rgba(255,255,255,0.55); font-size:0.83rem; margin-bottom:24px; }
.ql-grid { display:grid; grid-template-columns:repeat(auto-fill, minmax(160px, 1fr)); gap:11px; }
.ql { background:rgba(255,255,255,0.07); border:1px solid rgba(255,255,255,0.14); border-radius:12px; padding:15px 10px; color:#fff; display:flex; flex-direction:column; align-items:center; gap:7px; text-align:center; font-size:0.8rem; font-weight:500; cursor:pointer; transition:all 0.2s; user-select:none; }
.ql:hover { background:rgba(255,140,0,0.22); border-color:var(--saffron); transform:scale(1.04); }
.ql .qi { font-size:1.7rem; }

footer { background:#08083a; color:rgba(255,255,255,0.55); padding:38px 48px 22px; }
.foot-grid { display:grid; grid-template-columns:2fr 1fr 1fr 1fr; gap:36px; padding-bottom:28px; border-bottom:1px solid rgba(255,255,255,0.09); margin-bottom:20px; }
.foot-brand h4 { font-family:'Rajdhani',sans-serif; color:#fff; font-size:1.15rem; margin-bottom:8px; }
.foot-brand p { font-size:0.78rem; line-height:1.65; }
.foot-col h5 { color:rgba(255,255,255,0.8); font-family:'Rajdhani',sans-serif; font-size:0.92rem; margin-bottom:10px; letter-spacing:0.3px; }
.foot-col span { display:block; color:rgba(255,255,255,0.45); font-size:0.78rem; padding:3px 0; cursor:pointer; transition:color 0.2s; }
.foot-col span:hover { color:var(--gold); }
.foot-bottom { display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:10px; font-size:0.76rem; }
.foot-bottom strong { color:var(--gold); }

@media(max-width:768px){
  header{padding:18px 18px;flex-wrap:wrap}
  .header-right{display:none}
  nav{padding:0 12px}
  .hero{padding:36px 18px 28px}
  .hero h2{font-size:1.65rem}
  main{padding:28px 14px 48px}
  .grid{grid-template-columns:1fr}
  .ql-section{padding:26px 18px}
  .foot-grid{grid-template-columns:1fr 1fr;gap:22px}
  .foot-bottom{flex-direction:column;text-align:center}
}
</style>
</head>
<body>

<div class="tribar"></div>

<header>
  <div class="emblem">🦁</div>
  <div class="header-text">
    <h1>भारत सरकार <span>|</span> Government of India</h1>
    <p>National Citizen Services Portal &nbsp;·&nbsp; DigiSeva Gateway &nbsp;·&nbsp; Digital India</p>
  </div>
  <div class="header-right">
    <span class="badge">🔒 Secure</span>
    <span class="badge">🇮🇳 Official Links</span>
    <span class="badge">24×7</span>
  </div>
</header>

<nav>
  <a>🏠 Home</a>
  <a>📋 Documents</a>
  <a>🚌 Transport</a>
  <a>🗳 Voter Services</a>
  <a>🍚 Food & Civil Supplies</a>
  <a>💡 Help & Support</a>
  <a>📞 1800-111-555</a>
</nav>

<section class="hero">
  <h2>Apply for <em>Government Documents</em> Online</h2>
  <p>Access all essential citizen services from one place. Click any service to go directly to the official government website — opens in a new tab instantly.</p>
  <div class="hero-stats">
    <div><div class="stat-num">8+</div><div class="stat-label">Services</div></div>
    <div><div class="stat-num">100%</div><div class="stat-label">Online</div></div>
    <div><div class="stat-num">24×7</div><div class="stat-label">Available</div></div>
    <div><div class="stat-num">Free</div><div class="stat-label">To Apply</div></div>
  </div>
</section>

<main>

  <div class="notice">
    <span class="ni">📢</span>
    <div><strong>Notice:</strong> All buttons below open the <strong>official Government of India / State Government website</strong> in a new browser tab. Services are completely free — never pay any middlemen. Keep your Aadhaar, mobile number &amp; documents ready.</div>
  </div>

  <div class="sec-head">Essential Documents &amp; Services</div>
  <p class="sec-sub">Click "Apply Now" to go directly to the official government portal — opens in a new tab instantly</p>

  <div class="grid">

    <!-- Aadhaar -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#FF6B00,#FF9A00)"></div>
      <div class="card-body">
        <span class="card-tag">UIDAI</span>
        <div class="card-top">
          <div class="card-ico" style="background:#fff4e6">🪪</div>
          <div>
            <div class="card-title">Aadhaar Card</div>
            <div class="card-min">Ministry of Electronics &amp; IT · UIDAI</div>
          </div>
        </div>
        <p class="card-desc">India's 12-digit biometric identity card issued by UIDAI to every resident. Required for most government services.</p>
        <ul class="card-feat">
          <li>New Enrollment / Update Details</li>
          <li>Download e-Aadhaar / mAadhaar</li>
          <li>Address, DOB &amp; Name Correction</li>
          <li>Order PVC Aadhaar Card</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://myaadhaar.uidai.gov.in/')">🔗 Apply / Update</button>
          <button class="btn btn-alt" onclick="go('https://eaadhaar.uidai.gov.in/')">⬇ Download</button>
        </div>
      </div>
    </div>

    <!-- PAN Card -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#138808,#1db010)"></div>
      <div class="card-body">
        <span class="card-tag">Income Tax</span>
        <div class="card-top">
          <div class="card-ico" style="background:#e6f7e6">💳</div>
          <div>
            <div class="card-title">PAN Card</div>
            <div class="card-min">Income Tax Dept · Ministry of Finance</div>
          </div>
        </div>
        <p class="card-desc">Permanent Account Number — 10-digit alphanumeric identifier for financial transactions, IT filing &amp; banking.</p>
        <ul class="card-feat">
          <li>New PAN Application (Form 49A)</li>
          <li>Instant e-PAN via Aadhaar OTP</li>
          <li>PAN Correction / Reprint</li>
          <li>Link PAN with Aadhaar</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://www.onlineservices.nsdl.com/paam/endUserRegisterContact.html')">🔗 Apply via NSDL</button>
          <button class="btn btn-alt" onclick="go('https://eportal.incometax.gov.in/iec/foservices/#/pre-login/instant-e-pan')">⚡ Instant e-PAN</button>
        </div>
      </div>
    </div>

    <!-- Voter ID -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#000080,#1a1aaa)"></div>
      <div class="card-body">
        <span class="card-tag">ECI</span>
        <div class="card-top">
          <div class="card-ico" style="background:#e6e6ff">🗳️</div>
          <div>
            <div class="card-title">Voter ID (EPIC)</div>
            <div class="card-min">Election Commission of India</div>
          </div>
        </div>
        <p class="card-desc">Electors' Photo Identity Card — mandatory document to exercise your right to vote in Indian elections.</p>
        <ul class="card-feat">
          <li>New Voter Registration (Form 6)</li>
          <li>Correction in Voter Details (Form 8)</li>
          <li>Download e-EPIC Digital Voter ID</li>
          <li>Shift of Residence (Form 8A)</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://voters.eci.gov.in/')">🔗 Voter Portal</button>
          <button class="btn btn-alt" onclick="go('https://electoralsearch.eci.gov.in/')">🔍 Search Name</button>
        </div>
      </div>
    </div>

    <!-- Driving Licence -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#c0392b,#e74c3c)"></div>
      <div class="card-body">
        <span class="card-tag">MoRTH</span>
        <div class="card-top">
          <div class="card-ico" style="background:#fdecea">🚗</div>
          <div>
            <div class="card-title">Driving Licence</div>
            <div class="card-min">MoRTH · Sarathi Parivahan Portal</div>
          </div>
        </div>
        <p class="card-desc">Authorizes you to drive motor vehicles. Apply for Learner's Licence first, then Driving Licence from your RTO.</p>
        <ul class="card-feat">
          <li>Apply for Learner's Licence (LL)</li>
          <li>Apply / Renew Driving Licence (DL)</li>
          <li>International Driving Permit</li>
          <li>Duplicate DL &amp; Address Change</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://sarathi.parivahan.gov.in/sarathiservice/stateSelection.do')">🔗 Apply on Sarathi</button>
          <button class="btn btn-alt" onclick="go('https://parivahan.gov.in/parivahan/')">🌐 Parivahan</button>
        </div>
      </div>
    </div>

    <!-- RTC Bus Pass -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#16a085,#1abc9c)"></div>
      <div class="card-body">
        <span class="card-tag">APSRTC</span>
        <div class="card-top">
          <div class="card-ico" style="background:#e0fff8">🚌</div>
          <div>
            <div class="card-title">RTC Bus Pass</div>
            <div class="card-min">APSRTC / TSRTC · State Transport</div>
          </div>
        </div>
        <p class="card-desc">Monthly/quarterly/annual bus passes for students, senior citizens, differently-abled and daily commuters on RTC routes.</p>
        <ul class="card-feat">
          <li>Student Concession Pass</li>
          <li>Senior Citizen Free / Concession Pass</li>
          <li>Monthly Commuter Pass</li>
          <li>Freedom Pass (Differently Abled)</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://www.apsrtconline.in/')">🔗 APSRTC Online</button>
          <button class="btn btn-alt" onclick="go('https://www.tsrtconline.in/')">🌐 TSRTC Portal</button>
        </div>
      </div>
    </div>

    <!-- Ration Card -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#8e44ad,#9b59b6)"></div>
      <div class="card-body">
        <span class="card-tag">Food Dept</span>
        <div class="card-top">
          <div class="card-ico" style="background:#f3e6ff">🍚</div>
          <div>
            <div class="card-title">Ration Card</div>
            <div class="card-min">Dept of Food &amp; Civil Supplies · State</div>
          </div>
        </div>
        <p class="card-desc">Entitles eligible families to subsidized food grains under NFSA (National Food Security Act).</p>
        <ul class="card-feat">
          <li>New Ration Card Application</li>
          <li>Add / Remove Family Members</li>
          <li>Surrender &amp; Type Change</li>
          <li>Download &amp; Track Status</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://nfsa.gov.in/portal/ration_card_state_portals_nfsa')">🔗 State Portals</button>
          <button class="btn btn-alt" onclick="go('https://epds.ap.gov.in/')">🌐 AP EPDS</button>
        </div>
      </div>
    </div>

    <!-- Passport -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#2980b9,#3498db)"></div>
      <div class="card-body">
        <span class="card-tag">MEA</span>
        <div class="card-top">
          <div class="card-ico" style="background:#e6f3ff">🛂</div>
          <div>
            <div class="card-title">Passport</div>
            <div class="card-min">Ministry of External Affairs · PSP Division</div>
          </div>
        </div>
        <p class="card-desc">Primary travel document and proof of citizenship for international travel, issued by MEA Passport Seva Kendras.</p>
        <ul class="card-feat">
          <li>Fresh Passport Application</li>
          <li>Passport Renewal / Reissue</li>
          <li>Tatkaal (Urgent) Passport</li>
          <li>Track Application Status</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://www.passportindia.gov.in/AppOnlineProject/welcomeLink')">🔗 Passport Seva</button>
          <button class="btn btn-alt" onclick="go('https://portal2.passportindia.gov.in/AppOnlineProject/statusTracker/trackStatusInpNew')">📍 Track Status</button>
        </div>
      </div>
    </div>

    <!-- Birth Certificate -->
    <div class="card">
      <div class="card-stripe" style="background:linear-gradient(to right,#e67e22,#f39c12)"></div>
      <div class="card-body">
        <div class="card-top">
          <div class="card-ico" style="background:#fff8e6">👶</div>
          <div>
            <div class="card-title">Birth Certificate</div>
            <div class="card-min">State Registrar · Municipal / Panchayat</div>
          </div>
        </div>
        <p class="card-desc">Official proof of birth under the Registration of Births &amp; Deaths Act — needed for admissions, passports &amp; more.</p>
        <ul class="card-feat">
          <li>Apply for Birth Certificate</li>
          <li>Download &amp; Verify Certificate</li>
          <li>Name Inclusion after 1 year</li>
          <li>Delayed Registration</li>
        </ul>
        <div class="card-btns">
          <button class="btn btn-main" onclick="go('https://crsorgi.gov.in/web/index.php/auth/login')">🔗 CRS National Portal</button>
          <button class="btn btn-alt" onclick="go('https://meeseva.ap.gov.in/')">🌐 MeeSeva AP</button>
        </div>
      </div>
    </div>

  </div>

  <!-- QUICK LINKS -->
  <div class="ql-section">
    <h3>⚡ Quick Access — Direct Apply Links</h3>
    <p>Click any tile below to jump instantly to the official government application page</p>
    <div class="ql-grid">
      <div class="ql" onclick="go('https://myaadhaar.uidai.gov.in/')"><span class="qi">🪪</span><span>Aadhaar Update</span></div>
      <div class="ql" onclick="go('https://eportal.incometax.gov.in/iec/foservices/#/pre-login/instant-e-pan')"><span class="qi">💳</span><span>Instant e-PAN</span></div>
      <div class="ql" onclick="go('https://voters.eci.gov.in/')"><span class="qi">🗳️</span><span>Voter Registration</span></div>
      <div class="ql" onclick="go('https://sarathi.parivahan.gov.in/sarathiservice/stateSelection.do')"><span class="qi">🚗</span><span>Driving Licence</span></div>
      <div class="ql" onclick="go('https://nfsa.gov.in/portal/ration_card_state_portals_nfsa')"><span class="qi">🍚</span><span>Ration Card</span></div>
      <div class="ql" onclick="go('https://www.apsrtconline.in/')"><span class="qi">🚌</span><span>APSRTC Bus Pass</span></div>
      <div class="ql" onclick="go('https://www.passportindia.gov.in/AppOnlineProject/welcomeLink')"><span class="qi">🛂</span><span>Passport Apply</span></div>
      <div class="ql" onclick="go('https://crsorgi.gov.in/web/index.php/auth/login')"><span class="qi">👶</span><span>Birth Certificate</span></div>
      <div class="ql" onclick="go('https://meeseva.ap.gov.in/')"><span class="qi">🏛️</span><span>MeeSeva (AP)</span></div>
      <div class="ql" onclick="go('https://ts.meeseva.telangana.gov.in/meeseva/home.htm')"><span class="qi">🏛️</span><span>MeeSeva (TS)</span></div>
      <div class="ql" onclick="go('https://services.india.gov.in/')"><span class="qi">🇮🇳</span><span>India.gov.in</span></div>
      <div class="ql" onclick="go('https://umang.gov.in/')"><span class="qi">📱</span><span>UMANG App</span></div>
    </div>
  </div>

</main>

<footer>
  <div class="foot-grid">
    <div class="foot-brand">
      <h4>🦁 Bharat Gov Services Portal</h4>
      <p>An informational citizen services aggregator that links directly to official Government of India and State Government portals. All services are provided by the respective ministries and departments. This portal does not collect or store any personal data.</p>
    </div>
    <div class="foot-col">
      <h5>Identity Docs</h5>
      <span onclick="go('https://myaadhaar.uidai.gov.in/')">Aadhaar Card</span>
      <span onclick="go('https://www.onlineservices.nsdl.com/paam/endUserRegisterContact.html')">PAN Card</span>
      <span onclick="go('https://voters.eci.gov.in/')">Voter ID</span>
      <span onclick="go('https://www.passportindia.gov.in/AppOnlineProject/welcomeLink')">Passport</span>
    </div>
    <div class="foot-col">
      <h5>Transport</h5>
      <span onclick="go('https://sarathi.parivahan.gov.in/sarathiservice/stateSelection.do')">Driving Licence</span>
      <span onclick="go('https://vahan.parivahan.gov.in/vahanservice/')">Vehicle Registration</span>
      <span onclick="go('https://www.apsrtconline.in/')">APSRTC Bus Pass</span>
      <span onclick="go('https://www.tsrtconline.in/')">TSRTC Bus Pass</span>
    </div>
    <div class="foot-col">
      <h5>State &amp; Civil</h5>
      <span onclick="go('https://nfsa.gov.in/portal/ration_card_state_portals_nfsa')">Ration Card</span>
      <span onclick="go('https://crsorgi.gov.in/web/index.php/auth/login')">Birth Certificate</span>
      <span onclick="go('https://meeseva.ap.gov.in/')">MeeSeva AP</span>
      <span onclick="go('https://umang.gov.in/')">UMANG App</span>
    </div>
  </div>
  <div class="foot-bottom">
    <span>© 2025 Bharat Gov Services Aggregator &nbsp;·&nbsp; Not an official Government website — all buttons redirect to official portals</span>
    <span>Helpline: <strong>1800-111-555</strong> &nbsp;·&nbsp; All services are FREE</span>
  </div>
  <div class="tribar" style="margin-top:20px"></div>
</footer>

<script>
// Opens official govt site in a new tab reliably
function go(url) {
  var win = window.open(url, '_blank', 'noopener,noreferrer');
  if (!win || win.closed || typeof win.closed === 'undefined') {
    // Popup blocked fallback — create a real <a> and click it
    var a = document.createElement('a');
    a.href = url;
    a.target = '_blank';
    a.rel = 'noopener noreferrer';
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
  }
}
</script>

</body>
</html>
