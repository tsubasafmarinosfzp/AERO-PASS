export default {
  async fetch(request, env, ctx) {
    const html = `
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>AERO PASS</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        :root {
            --ana-navy: #002D72; --ana-blue: #007FFF;
            --glass: rgba(255, 255, 255, 0.15); --glass-border: rgba(255, 255, 255, 0.3);
            --panel-dark: rgba(0, 20, 50, 0.8);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Helvetica Neue', Arial, sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: linear-gradient(135deg, #001f5c 0%, #003399 100%); color: white; height: 100vh; overflow: hidden; display: flex; flex-direction: column; }
        
        .screen { display: none; flex: 1; overflow-y: auto; padding: 20px 20px 100px 20px; animation: fadeIn 0.4s; }
        .screen.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; transform: scale(0.98); } to { opacity: 1; transform: scale(1); } }

        .panel { background: var(--glass); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); border: 1px solid var(--glass-border); border-radius: 24px; padding: 20px; margin-bottom: 20px; box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3); }

        /* 起動画面 (Image 5) */
        #launch-screen { display: flex; flex-direction: column; justify-content: center; align-items: center; position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 200; background: url('https://images.unsplash.com/photo-1436491865332-7a61a109cc05?auto=format&fit=crop&w=1000&q=80') center/cover; }
        #launch-screen::before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,45,114,0.5); z-index: -1; }
        
        /* ボトムナビ (白背景) */
        #bottom-nav { position: fixed; bottom: 0; left: 0; width: 100%; height: 80px; background: #ffffff; display: none; justify-content: space-around; align-items: center; border-top: 2px solid var(--ana-navy); z-index: 150; padding-bottom: env(safe-area-inset-bottom); }
        .nav-item { color: #888; font-size: 10px; text-align: center; flex: 1; display: flex; flex-direction: column; align-items: center; gap: 4px; cursor: pointer; }
        .nav-item.active { color: var(--ana-navy); font-weight: bold; }
        .nav-icon { font-size: 24px; }

        /* ホーム：3つの計器 (Image 4 左) */
        .dials-container { display: flex; justify-content: center; align-items: flex-end; gap: 10px; margin-bottom: 20px; }
        .dial { background: #111; border: 2px solid #555; border-radius: 50%; display: flex; align-items: center; justify-content: center; box-shadow: inset 0 0 15px #000; }
        .dial-sm { width: 55px; height: 55px; font-size: 9px; color: #888; }
        .dial-main { width: 90px; height: 90px; border-color: var(--ana-blue); font-size: 35px; color: white; }

        /* 進捗：滑走路 & 本棚 (Image 2) */
        .runway { height: 40px; background: #222; border: 1px dashed rgba(255,255,255,0.3); margin-bottom: 12px; position: relative; border-radius: 4px; display: flex; align-items: center; }
        .bookshelf { height: 115px; background: #6F4E37; border-bottom: 12px solid #3d2b1f; display: flex; align-items: flex-end; padding: 0 10px; gap: 4px; box-shadow: inset 0 -10px 20px rgba(0,0,0,0.5); }
        .book { width: 24px; height: 85px; background: #e74c3c; color: white; writing-mode: vertical-rl; font-size: 10px; text-align: center; border-left: 2px solid rgba(255,255,255,0.2); box-shadow: -2px 0 5px rgba(0,0,0,0.4); }

        .btn { background: var(--ana-blue); color: white; border: none; padding: 16px; border-radius: 40px; width: 100%; font-size: 18px; font-weight: bold; cursor: pointer; }
        input { width: 100%; background: rgba(0,0,0,0.4); border: 1px solid var(--glass-border); border-radius: 12px; padding: 12px; color: white; margin-top: 10px; outline: none; }
    </style>
</head>
<body onload="initApp()">
    <div id="launch-screen">
        <h1 style="font-size: 42px; font-style: italic; font-weight: 900; margin-bottom: 40px;">✈︎ AERO PASS</h1>
        <div class="panel" style="width: 85%; max-width: 400px;">
            <p style="text-align:center; font-size: 11px; margin-bottom:20px; letter-spacing: 2px;">TODAY'S FLIGHT PLAN</p>
            <input type="text" id="targetTime" placeholder="TARGET STUDY TIME (HOURS)">
            <input type="text" id="keyTask" placeholder="TODAY'S KEY TASK">
            <button class="btn" style="margin-top:20px;" onclick="takeOff()">Take Off!</button>
        </div>
    </div>

    <div id="home" class="screen">
        <h1 style="text-align:center; font-style:italic; margin-bottom:20px; font-weight: 900; letter-spacing: 2px;">AERO PASS</h1>
        <div class="dials-container">
            <div class="dial dial-sm">ALT</div>
            <div class="dial dial-main">✈️</div>
            <div class="dial dial-sm">HDG</div>
        </div>
        <div class="panel" style="text-align: center; background: var(--panel-dark);">
            <div style="font-size: 32px; font-weight: 900; border: 6px solid var(--ana-blue); width: 110px; height: 110px; border-radius: 50%; margin: 0 auto; display: flex; align-items: center; justify-content: center;">55%</div>
            <p style="margin-top:15px; font-size: 12px; color:#ccc;">ANA Tntpn/White 進捗 : 53%</p>
        </div>
        <div class="panel"><p id="dispTime" style="font-weight: bold; font-size: 18px;"></p><p id="dispTask" style="font-size: 14px; opacity: 0.8; margin-top: 5px;"></p></div>
    </div>

    <div id="schedule" class="screen">
        <div class="panel" style="border-left: 5px solid gold; background: rgba(0,0,0,0.3);">
            <h4 style="font-size: 13px; color: gold; margin-bottom:10px;">✈️ AI Captainの授業</h4>
            <p id="aiStrategyContent" style="font-size: 13px; font-style: italic; line-height: 1.6;">分析中...</p>
        </div>
        <div class="panel">
            <h4 style="font-size: 13px; margin-bottom:10px;">今日のタスクリスト</h4>
            <label style="display:block; margin-bottom:10px;"><input type="checkbox" checked> 物理は電磁気を重点的に</label>
            <label style="display:block;"><input type="checkbox"> 英語過去問演習 1年分</label>
        </div>
    </div>

    <div id="mock" class="screen">
        <div style="text-align:center; font-size:11px; margin-bottom:15px; background: rgba(255,255,255,0.1); padding: 5px;">FDR 記録 MODE</div>
        <div class="panel" style="background: white; color: black; padding: 10px;"><canvas id="mockChart" style="height: 180px;"></canvas></div>
        <div class="panel">
            <input type="number" id="engScore" placeholder="英語 / 100">
            <input type="number" id="gen1Score" placeholder="総合I / 100">
            <input type="number" id="gen2Score" placeholder="総合II / 150">
            <button class="btn" style="margin-top:15px; padding: 12px;" onclick="addMockRecord()">記録を保存</button>
        </div>
    </div>

    <div id="progress" class="screen">
        <h2 style="text-align:center; margin-bottom:20px; font-size: 20px;">進捗管理<br><small style="font-size: 12px;">(滑走路進行状況図)</small></h2>
        <div class="panel" style="background: rgba(0,0,0,0.5);">
            <div class="runway"><div style="position:absolute; left: 65%; font-size:24px;">✈️</div></div>
            <div class="runway"><div style="position:absolute; left: 30%; font-size:24px;">✈️</div></div>
        </div>
        <div class="bookshelf">
            <div class="book" style="background: #2ecc71;">青チャート</div>
            <div class="book" style="background: #e67e22;">漆原の物理</div>
            <div class="book" style="background: #3498db;">英語過去問</div>
            <div class="book" style="background: #f1c40f;">総合時事</div>
        </div>
    </div>

    <div id="settings" class="screen">
        <div class="panel" style="display:flex; align-items:center; gap:20px;">
            <div style="width:65px; height:65px; background:white; border-radius:50%; text-align:center; line-height:65px; font-size:35px; border: 3px solid var(--ana-blue);">👨‍✈️</div>
            <div><p style="font-weight: bold;">翼くん</p><p style="font-size:12px; color:#ccc;">目標：285/350点</p></div>
        </div>
        <div class="panel">
            <button class="btn" style="background:white; color:var(--ana-navy); margin-bottom:10px;">✈️ Export (データ出力)</button>
            <button class="btn" style="background:#ff4d4d;" onclick="clearData()">全リセット</button>
        </div>
    </div>

    <nav id="bottom-nav">
        <div class="nav-item active" onclick="showPage('home', this)"><span class="nav-icon">🏠</span>ホーム</div>
        <div class="nav-item" onclick="showPage('schedule', this)"><span class="nav-icon">📅</span>計画</div>
        <div class="nav-item" onclick="showPage('mock', this)"><span class="nav-icon">🏆</span>模試</div>
        <div class="nav-item" onclick="showPage('progress', this)"><span class="nav-icon">💼</span>進捗DB</div>
        <div class="nav-item" onclick="showPage('settings', this)"><span class="nav-icon">👤</span>設定</div>
    </nav>

    <script>
        const API_KEY = 'ここにあなたのAPIキーを入れる';
        let myChart;
        let mockRecords = JSON.parse(localStorage.getItem('mockRecords')) || [];
        function initApp() {
            const savedTime = localStorage.getItem('targetTime');
            const savedTask = localStorage.getItem('keyTask');
            if (savedTime && savedTask) {
                document.getElementById('dispTime').innerText = "目標: " + savedTime;
                document.getElementById('dispTask').innerText = "重点: " + savedTask;
                document.getElementById('launch-screen').style.display = 'none';
                document.getElementById('bottom-nav').style.display = 'flex';
                document.getElementById('aiStrategyContent').innerText = localStorage.getItem('lastAdvice') || "戦略待機中...";
            }
        }
        async function takeOff() {
            const time = document.getElementById('targetTime').value;
            const task = document.getElementById('keyTask').value;
            if(!time || !task) return alert('入力してください');
            localStorage.setItem('targetTime', time);
            localStorage.setItem('keyTask', task);
            try {
                const res = await fetch(\`https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=\${API_KEY}\`, {
                    method: 'POST', headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ contents: [{ parts: [{ text: "航空大合格コーチとして、今日の目標に向かう訓練生へANAパイロット風の熱い100文字アドバイスを。" }] }] })
                });
                const data = await res.json();
                localStorage.setItem('lastAdvice', data.candidates[0].content.parts[0].text);
            } catch (e) {
                localStorage.setItem('lastAdvice', "通信圏外。自力で高度を維持せよ！");
            }
            location.reload();
        }
        function showPage(pageId, element) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            document.querySelectorAll('.nav-item').forEach(i => i.classList.remove('active'));
            element.classList.add('active');
            if(pageId === 'mock') updateChart();
        }
        function updateChart() {
            const ctx = document.getElementById('mockChart').getContext('2d');
            if (myChart) myChart.destroy();
            myChart = new Chart(ctx, { type: 'line', data: { labels: mockRecords.map(r => r.date), datasets: [{ label: '総合', data: mockRecords.map(r => r.score), borderColor: '#002D72', fill: true, tension: 0.3 }] } });
        }
        function clearData() { if(confirm('リセット？')) { localStorage.clear(); location.reload(); } }
    </script>
</body>
</html>
    `;
    return new Response(html, { headers: { "content-type": "text/html;charset=UTF-8" } });
  },
};
