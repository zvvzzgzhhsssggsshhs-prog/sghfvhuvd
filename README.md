<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>💸 ইনকাম পয়েন্ট</title>
<style>
body {
  font-family: 'Noto Sans Bengali', sans-serif;
  background: linear-gradient(to bottom, #e9f8ec, #ffffff);
  margin: 0;
  padding: 0;
  color: #333;
}
header {
  background: linear-gradient(90deg, #2e8b57, #4CAF50);
  color: white;
  text-align: center;
  padding: 20px 0;
  font-size: 26px;
  font-weight: bold;
  letter-spacing: 1px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.2);
}
.container {
  padding: 22px;
  max-width: 520px;
  margin: auto;
}
.card {
  background: #fff;
  padding: 18px;
  border-radius: 14px;
  margin-bottom: 22px;
  box-shadow: 0 3px 10px rgba(0,0,0,0.08);
}
h2 {
  margin-top: 0;
  color: #2e8b57;
  font-size: 20px;
  border-bottom: 2px solid #e1f3e4;
  padding-bottom: 6px;
}
.btn {
  display: block;
  width: 100%;
  padding: 12px;
  margin-top: 12px;
  text-align: center;
  background: linear-gradient(90deg, #4CAF50, #2e8b57);
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  text-decoration: none;
  transition: 0.2s;
}
.btn:hover { transform: scale(1.03); }
.hidden { display: none; }
input, select {
  width: 100%;
  padding: 10px;
  margin-top: 8px;
  border-radius: 8px;
  border: 1px solid #ccc;
  font-size: 15px;
}
.balance-info {
  font-weight: bold;
  font-size: 18px;
  color: #2e8b57;
  margin-bottom: 8px;
}
.username {
  font-size: 16px;
  color: #555;
  font-weight: bold;
}
.switch {
  text-align: center;
  margin-top: 10px;
  color: #007b55;
  font-weight: bold;
  cursor: pointer;
}
.notice p { color: #c0392b; font-weight: bold; }
.copy-link { background: #1e8449; margin-top: 10px; }
</style>
</head>
<body>

<header>💸 ইনকাম পয়েন্ট</header>

<div class="container">

  <!-- রেজিস্ট্রেশন -->
  <div id="registerCard" class="card">
    <h2>📝 নতুন করে রেজিস্ট্রেশন করুন</h2>
    <input type="text" id="regName" placeholder="আপনার নাম লিখুন">
    <input type="text" id="regPhone" placeholder="মোবাইল নাম্বার দিন">
    <input type="password" id="regPass" placeholder="পাসওয়ার্ড দিন">
    <button class="btn" onclick="register()">রেজিস্ট্রেশন সম্পন্ন করুন</button>
    <div class="switch" onclick="showLogin()">🔑 আগে একাউন্ট আছে? লগইন করুন</div>
  </div>

  <!-- লগইন -->
  <div id="loginCard" class="card hidden">
    <h2>🔐 লগইন করুন</h2>
    <input type="text" id="loginPhone" placeholder="মোবাইল নাম্বার দিন">
    <input type="password" id="loginPass" placeholder="পাসওয়ার্ড দিন">
    <button class="btn" onclick="login()">লগইন</button>
    <div class="switch" onclick="showRegister()">🆕 নতুন একাউন্ট খুলুন</div>
  </div>

  <!-- মূল প্যানেল -->
  <div id="mainPanel" class="hidden">

    <div class="card balance">
      <div class="balance-info">💰 ব্যালেন্স: <span id="balance">0</span> টাকা</div>
      <p class="username">👤 ইউজার: <span id="userDisplay"></span></p>
      <p>মোট রেফার: <span id="refCount">0</span></p>
    </div>

    <div class="card">
      <h2>🔗 রেফার লিংক</h2>
      <p id="refLink" style="word-break:break-all;color:#006400;"></p>
      <button class="btn copy-link" onclick="copyRef()">📋 রেফার লিংক কপি করুন</button>
    </div>

    <div class="card">
      <h2>💬 টেলিগ্রাম ইনকাম</h2>
      <p>টেলিগ্রাম চ্যানেলে যোগ দিলে একবারে ১০০ টাকা পাবেন।</p>
      <a href="https://t.me/incomegfff" target="_blank" class="btn" onclick="telegramJoin()">টেলিগ্রাম চ্যানেলে যোগ দিন</a>
    </div>

    <div class="card">
      <h2>▶️ ইউটিউব ইনকাম</h2>
      <p>ইউটিউব চ্যানেল সাবস্ক্রাইব করলে একবারে ১৫০ টাকা পাবেন।</p>
      <a href="https://www.youtube.com/@%E0%A6%95%E0%A7%8D%E0%A6%AF%E0%A6%BE%E0%A6%B6%E0%A6%86%E0%A6%89%E0%A6%9F" target="_blank" class="btn" onclick="youtubeJoin()">ইউটিউব চ্যানেল সাবস্ক্রাইব করুন</a>
    </div>

    <div class="card daily">
      <h2>💰 দৈনিক ইনকাম</h2>
      <p>প্রতিদিন ৫ বার ১০ টাকা করে নিতে পারবেন (২৪ ঘণ্টা পর রিসেট হবে)।</p>
      <button class="btn" onclick="dailyIncome()">ইনকাম করুন</button>
      <p>আজকের ইনকাম: <span id="dailyClicks">0</span>/5</p>
    </div>

    <div class="card bonus">
      <h2>🎁 রেফার বোনাস নিন</h2>
      <p>দুইদিন পর আবার নিতে পারবেন। নিচে কোড লিখুন:</p>
      <input type="text" id="bonusCode" placeholder="বোনাস কোড লিখুন (যেমন 1122)">
      <button class="btn" onclick="claimBonus()">🎁 বোনাস নিন</button>
      <p id="bonusTimer" style="color:#e67e22;font-weight:bold;"></p>
      <p id="bonusMsg" style="color:#007b55;font-weight:bold;margin-top:10px;"></p>
    </div>

    <div class="card withdraw">
      <h2>💵 উইথড্র সিস্টেম</h2>
      <select id="method">
        <option value="">-- পেমেন্ট মেথড নির্বাচন করুন --</option>
        <option value="bKash">📱 বিকাশ</option>
        <option value="Nagad">💳 নগদ</option>
        <option value="Rocket">🚀 রকেট</option>
      </select>
      <input type="text" id="withdrawNumber" placeholder="আপনার নাম্বার দিন">
      <input type="number" id="withdrawAmount" placeholder="পরিমাণ লিখুন (৳)">
      <button class="btn" onclick="withdraw()">উইথড্র করুন</button>
      <p id="withdrawMsg" style="color:#c0392b;font-weight:bold;"></p>
    </div>

    <div class="card notice">
      <h2>⚠️ সতর্কবার্তা</h2>
      <p>এক ডিভাইসে একাধিক একাউন্ট করলে ব্যালেন্স নষ্ট হবে।</p>
      <button class="btn" style="background:#d63031" onclick="logout()">🚪 লগআউট</button>
    </div>

  </div>
</div>

<script>
let currentUser=null;
let users=JSON.parse(localStorage.getItem("users"))||{};
let referrer=null;
const validCodes=["1122","2432","2421","2321","5425","8888"];
const params=new URLSearchParams(window.location.search);
if(params.has("ref")) referrer=params.get("ref");

function getDeviceId(){
  let id=localStorage.getItem("deviceId");
  if(!id){
    id='dev-'+Math.random().toString(36).substring(2)+Date.now();
    localStorage.setItem("deviceId",id);
  }
  return id;
}
const deviceId=getDeviceId();

function saveData(){ localStorage.setItem("users",JSON.stringify(users)); }
function showLogin(){ registerCard.classList.add("hidden"); loginCard.classList.remove("hidden"); }
function showRegister(){ loginCard.classList.add("hidden"); registerCard.classList.remove("hidden"); }

function register(){
  const name=regName.value.trim(), phone=regPhone.value.trim(), pass=regPass.value.trim();
  if(!name||!phone||!pass) return alert("সব ঘর পূরণ করুন!");
  if(users[phone]) return alert("এই নাম্বারে একাউন্ট আছে!");

  for(let key in users){
    if(users[key].deviceId===deviceId){
      alert("⚠️ এই ডিভাইস দিয়ে ইতিমধ্যে একটি একাউন্ট করা হয়েছে!");
      return;
    }
  }

  users[phone]={name,password:pass,balance:0,dailyClicks:0,lastReset:0,refCount:0,tgJoined:false,ytJoined:false,bonusTime:0,deviceId};

  if(referrer && users[referrer]){
    users[referrer].refCount++;
    users[referrer].balance+=100;
    alert("🎉 রেফারারের ব্যালেন্সে ১০০ টাকা যোগ হয়েছে!");
  }

  saveData();
  alert("✅ রেজিস্ট্রেশন সম্পন্ন হয়েছে! এখন লগইন করুন।");
  showLogin();
}

function login(){
  const phone=loginPhone.value.trim(), pass=loginPass.value.trim();
  if(!users[phone]) return alert("❌ এই নাম্বারে কোনো একাউন্ট নেই!");
  if(users[phone].password!==pass) return alert("❌ ভুল পাসওয়ার্ড!");
  currentUser=phone; showMain();
}

function showMain(){
  registerCard.classList.add("hidden");
  loginCard.classList.add("hidden");
  mainPanel.classList.remove("hidden");
  userDisplay.innerText=users[currentUser].name+" ("+currentUser+")";
  document.getElementById("refLink").innerText=`https://gsgsgssggsgsgsgsgsgts.kesug.com/?ref=${currentUser}`;
  updateUI(); updateBonusTimer();
}

function updateUI(){
  const u=users[currentUser];
  balance.innerText=u.balance;
  dailyClicks.innerText=u.dailyClicks;
  refCount.innerText=u.refCount||0;
  saveData();
}

function copyRef(){
  const link=`https://gsgsgssggsgsgsgsgsgts.kesug.com/?ref=${currentUser}`;
  navigator.clipboard.writeText(link);
  alert("✅ রেফার লিংক কপি হয়েছে!");
}

function telegramJoin(){
  const u=users[currentUser];
  if(!u.tgJoined){ u.balance+=100; u.tgJoined=true; alert("✅ টেলিগ্রাম ইনকাম ১০০ টাকা যোগ হয়েছে!"); }
  else alert("⚠️ আপনি ইতিমধ্যে নিয়েছেন!");
  updateUI();
}

function youtubeJoin(){
  const u=users[currentUser];
  if(!u.ytJoined){ u.balance+=150; u.ytJoined=true; alert("✅ ইউটিউব ইনকাম ১৫০ টাকা যোগ হয়েছে!"); }
  else alert("⚠️ আপনি ইতিমধ্যে নিয়েছেন!");
  updateUI();
}

function dailyIncome(){
  const u=users[currentUser], now=Date.now();
  if(!u.lastReset) u.lastReset=now;
  if(now-u.lastReset>=24*60*60*1000){ u.dailyClicks=0; u.lastReset=now; }
  if(u.dailyClicks<5){ u.dailyClicks++; u.balance+=10; alert("✅ ১০ টাকা যোগ হয়েছে!"); }
  else alert("আজকের ইনকাম শেষ!");
  updateUI();
}

function claimBonus(){
  const u=users[currentUser], now=Date.now(), code=document.getElementById("bonusCode").value.trim();
  const cooldown=2*24*60*60*1000;
  if(u.bonusTime && now-u.bonusTime<cooldown){
    const left=cooldown-(now-u.bonusTime);
    bonusMsg.innerText=`⏳ ${Math.floor(left/3600000)} ঘণ্টা পরে আবার নিতে পারবেন।`; return;
  }
  if(!validCodes.includes(code)){ bonusMsg.innerText="❌ ভুল কোড!"; return; }
  u.balance+=150; u.bonusTime=now;
  bonusMsg.innerText="🎉 আপনার রেফার বোনাস পেয়েছেন!";
  document.getElementById("bonusCode").value=""; updateUI(); updateBonusTimer();
}

function updateBonusTimer(){
  const u=users[currentUser]; if(!u) return;
  const now=Date.now(), cooldown=2*24*60*60*1000;
  if(!u.bonusTime){ bonusTimer.innerText="✅ এখন বোনাস নিতে পারবেন!"; return; }
  const left=cooldown-(now-u.bonusTime);
  if(left<=0){ bonusTimer.innerText="✅ এখন বোনাস নিতে পারবেন!"; }
  else{
    const d=Math.floor(left/(24*60*60*1000));
    const h=Math.floor((left%(24*60*60*1000))/3600000);
    const m=Math.floor((left%3600000)/60000);
    bonusTimer.innerText=`⏳ আবার নিতে পারবেন: ${d} দিন ${h} ঘণ্টা ${m} মিনিট পর`;
  }
}
setInterval(updateBonusTimer,60000);

function withdraw(){
  const m=method.value, n=withdrawNumber.value.trim(), a=parseInt(withdrawAmount.value);
  const u=users[currentUser];
  if((u.refCount||0)<10){ withdrawMsg.innerText="⚠️ কমপক্ষে ১০টি রেফার করতে হবে!"; return; }
  if(!m||!n||!a) return withdrawMsg.innerText="⚠️ সব তথ্য দিন!";
  if(u.balance<a) return withdrawMsg.innerText="❌ পর্যাপ্ত ব্যালেন্স নেই!";
  u.balance-=a; withdrawMsg.innerText=`✅ ${m} এ ${a}৳ পাঠানো হয়েছে (${n})`; updateUI();
}

function logout(){ currentUser=null; mainPanel.classList.add("hidden"); loginCard.classList.remove("hidden"); }
</script>
</body>
</html><!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>💸 ইনকাম পয়েন্ট</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:"Poppins",sans-serif}
body{background:#0d1117;color:#fff;min-height:100vh;display:flex;flex-direction:column;align-items:center;}
header{background:linear-gradient(90deg,#007bff,#4dabff);width:100%;text-align:center;padding:15px 0;border-radius:0 0 20px 20px;}
header h2{font-size:22px;}
.card{background:#161b22;width:90%;max-width:400px;border-radius:15px;margin:15px 0;padding:20px;box-shadow:0 0 8px rgba(255,255,255,0.1);}
.btn{display:block;width:100%;background:#007bff;color:#fff;border:none;padding:10px;border-radius:10px;text-align:center;margin-top:10px;cursor:pointer;}
.btn:hover{background:#4dabff;}
.section{display:none;width:100%;flex-direction:column;align-items:center;}
.active-section{display:flex;}
footer{background:#161b22;position:fixed;bottom:0;width:100%;display:flex;justify-content:space-around;padding:8px 0;border-top:1px solid #222;}
footer div{text-align:center;font-size:12px;color:#aaa;cursor:pointer;}
footer div.active{color:#4dabff;}
input,select{width:100%;padding:8px;margin-top:8px;border:none;border-radius:8px;}
.history-item{background:#1e232b;padding:8px;margin:4px 0;border-radius:8px;text-align:center;font-size:13px;}
.success{color:#00ff88;margin-top:5px;}
#adModal{position:fixed;top:0;left:0;width:100%;height:100%;background:#000;display:none;justify-content:center;align-items:center;flex-direction:column;z-index:9999;text-align:center;}
#adModal video{width:100%;height:auto;max-height:70vh;border-radius:10px;}
#adModal h3{margin-top:15px;}
#adContinue{background:#00c851;color:#fff;border:none;padding:10px 25px;border-radius:10px;margin-top:15px;display:none;cursor:pointer;}
</style>
</head>
<body>

<header><h2>💸 ইনকাম পয়েন্ট</h2></header>

<!-- লগইন পেজ -->
<section id="loginSection" class="section active-section">
  <div class="card">
    <h3>🔐 লগইন করুন</h3>
    <input type="text" id="loginName" placeholder="নাম দিন">
    <input type="password" id="loginPass" placeholder="পাসওয়ার্ড দিন">
    <button class="btn" onclick="login()">লগইন</button>
  </div>
</section>

<!-- ১ম পেজ -->
<section id="home" class="section">
  <div class="card">
    <h3>📊 <span id="usernameDisplay"></span> এর তথ্য</h3>
    <p>মোট ব্যালেন্স: <b id="balance">0.00</b> TK</p>
    <p>মোট রেফার: <b id="refs">0</b></p>
    <p>বিজ্ঞাপন দেখা: <b id="ads">0</b>/5</p>
    <button class="btn" onclick="logout()">🚪 লগ আউট</button>
  </div>
</section>

<!-- ২য় পেজ -->
<section id="refer" class="section">
  <div class="card">
    <h3>🤝 রেফার ইনকাম</h3>
    <p>প্রতি রেফারে পাবেন ১০০ টাকা</p>
    <p class="success">আপনার লিংকে কেউ ঢুকলে অটোমেটিক ১০০ টাকা যুক্ত হবে</p>
    <p>মোট রেফার ইনকাম: <b id="refIncome">0</b> TK</p>
    <input type="text" id="refLink" readonly>
    <button class="btn" onclick="copyRef()">রেফার লিংক কপি করুন</button>
  </div>
</section>

<!-- ৩য় পেজ -->
<section id="withdraw" class="section">
  <div class="card">
    <h3>💰 Withdraw করুন</h3>
    <p>কমপক্ষে ১৫ রেফার এবং ৫০০ টাকা হলে উইথড্র করা যাবে।</p>
    <select id="method">
      <option value="bkash">বিকাশ</option>
      <option value="nagad">নগদ</option>
      <option value="rocket">রকেট</option>
    </select>
    <input type="text" id="phone" placeholder="নাম্বার দিন">
    <input type="number" id="amount" placeholder="পরিমাণ (মিনিমাম 500)">
    <button class="btn" onclick="withdraw()">Withdraw Request</button>
  </div>
</section>

<!-- ৪র্থ পেজ -->
<section id="adsPanel" class="section">
  <div class="card">
    <h3>🎬 বিজ্ঞাপন দেখুন</h3>
    <p>৩০ সেকেন্ডে ৩০ টাকা, দিনে ৫ বার পর্যন্ত।</p>
    <p>আজকের বিজ্ঞাপন: <b id="adCount">0/5</b></p>
    <button class="btn" id="adBtn" onclick="openAd()">Watch Ad</button>
  </div>

  <div class="card">
    <h3>📜 Withdraw History</h3>
    <div id="history"></div>
  </div>
</section>

<!-- ফুলস্ক্রিন অ্যাড -->
<div id="adModal">
  <video id="adVideo" autoplay muted>
    <source src="https://cdn.pixabay.com/video/2023/03/21/156226-810799777_large.mp4" type="video/mp4">
  </video>
  <h3 id="adTimer">30</h3>
  <button id="adContinue" onclick="closeAd()">✅ Continue</button>
</div>

<footer id="mainFooter" style="display:none;">
  <div id="btnHome" class="active" onclick="showSection('home',this)">🏠<br>Home</div>
  <div id="btnRefer" onclick="showSection('refer',this)">👥<br>Refer</div>
  <div id="btnWithdraw" onclick="showSection('withdraw',this)">💰<br>Withdraw</div>
  <div id="btnAds" onclick="showSection('adsPanel',this)">🎬<br>Ads</div>
</footer>

<script>
let currentUser=null;
let users=JSON.parse(localStorage.getItem("users")||"{}");

function login(){
  const name=document.getElementById("loginName").value.trim();
  const pass=document.getElementById("loginPass").value.trim();
  if(!name||!pass){alert("নাম ও পাসওয়ার্ড দিন!");return;}
  if(!users[name]) users[name]={pass:pass,bal:0,refs:0,ads:0,history:[]};
  else if(users[name].pass!==pass){alert("❌ ভুল পাসওয়ার্ড!");return;}
  currentUser=name;
  document.getElementById("usernameDisplay").innerText=name;
  document.getElementById("loginSection").style.display="none";
  document.getElementById("home").classList.add("active-section");
  document.getElementById("mainFooter").style.display="flex";
  updateUI();saveData();
}

function logout(){saveData();currentUser=null;
  document.getElementById("mainFooter").style.display="none";
  document.querySelectorAll(".section").forEach(s=>s.classList.remove("active-section"));
  document.getElementById("loginSection").style.display="flex";}

function saveData(){if(currentUser)localStorage.setItem("users",JSON.stringify(users));}

function updateUI(){
  if(!currentUser)return;
  const u=users[currentUser];
  document.getElementById("balance").innerText=u.bal.toFixed(2);
  document.getElementById("refs").innerText=u.refs;
  document.getElementById("ads").innerText=u.ads;
  document.getElementById("refIncome").innerText=(u.refs*100).toFixed(0);
  document.getElementById("adCount").innerText=u.ads+"/5";
  document.getElementById("history").innerHTML=u.history.map(h=>`<div class='history-item'>${h}</div>`).join("");
  document.getElementById("refLink").value=`https://t.me/IncomeSitezhzhzvvzvg6532_bot?start=ref${currentUser}`;
}

function copyRef(){navigator.clipboard.writeText(document.getElementById("refLink").value);alert("রেফার লিংক কপি হয়েছে!");}

function withdraw(){
  const u=users[currentUser];
  const phone=document.getElementById("phone").value;
  const amt=parseFloat(document.getElementById("amount").value);
  if(u.refs<15){alert("❌ ১৫ রেফার প্রয়োজন!");return;}
  if(amt<500){alert("❌ ৫০০ টাকা মিনিমাম!");return;}
  if(u.bal<amt){alert("❌ পর্যাপ্ত ব্যালেন্স নেই!");return;}
  u.bal-=amt;
  const mask=phone.substring(0,3)+"****"+phone.slice(-2);
  u.history.unshift(mask+" সফল ✅");
  if(u.history.length>10)u.history.pop();
  updateUI();saveData();alert("✅ Withdraw অনুরোধ গেছে!");
}

function openAd(){
  const u=users[currentUser];
  if(u.ads>=5){alert("আজকের বিজ্ঞাপন শেষ!");return;}
  document.getElementById("adModal").style.display="flex";
  let sec=30;document.getElementById("adTimer").innerText=sec;
  const timer=setInterval(()=>{
    sec--;document.getElementById("adTimer").innerText=sec;
    if(sec<=0){clearInterval(timer);document.getElementById("adContinue").style.display="inline-block";}
  },1000);
}

function closeAd(){
  const u=users[currentUser];
  u.ads++;u.bal+=30;
  document.getElementById("adModal").style.display="none";
  document.getElementById("adContinue").style.display="none";
  updateUI();saveData();
  alert("🎉 আপনি ৩০ টাকা পেয়েছেন!");
}

function showSection(id,btn){
  document.querySelectorAll(".section").forEach(s=>s.classList.remove("active-section"));
  document.getElementById(id).classList.add("active-section");
  document.querySelectorAll("footer div").forEach(b=>b.classList.remove("active"));
  btn.classList.add("active");
}
</script>

</body>
</html>
