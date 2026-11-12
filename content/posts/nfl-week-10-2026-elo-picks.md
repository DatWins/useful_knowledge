---
title: "NFL Week 10 · 2026 — My Elo Model Picks"
date: 2026-11-10
draft: false
categories:
  - NFL
  - Sports Analytics
tags:
  - Elo
  - NFL Predictions
  - FiveThirtyEight
---

<style>
.elo-wrap { font-family: -apple-system, 'Segoe UI', sans-serif; margin: 24px 0; }
.elo-intro { background: #161b22; border: 1px solid #30363d; border-radius: 10px; padding: 20px 24px; margin-bottom: 20px; color: #e6edf3; }
.elo-intro p { margin: 0 0 10px; font-size: 1rem; line-height: 1.7; color: #EFE8D6; }
.elo-intro p:last-child { margin: 0; }
.elo-intro strong { color: #e6edf3; }
.elo-intro a { color: #58a6ff; text-decoration: none; }
.elo-stat-row { display: flex; gap: 10px; margin-bottom: 20px; flex-wrap: wrap; }
.elo-stat { background: #161b22; border: 1px solid #30363d; border-radius: 8px; padding: 14px 18px; flex: 1; min-width: 130px; }
.elo-stat-label { font-size: 0.68rem; text-transform: uppercase; letter-spacing: 0.08em; color: #7d8590; margin-bottom: 4px; }
.elo-stat-value { font-size: 1.5rem; font-weight: 800; letter-spacing: -0.02em; }
.elo-section-title { font-size: 0.72rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.1em; color: #c9d1d9; background: #161b22; border: 1px solid #30363d; border-radius: 6px; padding: 10px 14px; margin-bottom: 10px; }
.elo-table-wrap { border: 1px solid #30363d; border-radius: 10px; overflow: hidden; margin-bottom: 8px; }
.elo-table { width: 100%; border-collapse: collapse; font-size: 0.84rem; }
.elo-table thead th { background: #1c2128; color: #7d8590; font-size: 0.68rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.07em; padding: 10px 14px; text-align: left; border-bottom: 1px solid #30363d; white-space: nowrap; }
.elo-table tbody tr { border-bottom: 1px solid #21262d; background: #0d1117; }
.elo-table tbody tr:last-child { border-bottom: none; }
.elo-table tbody tr:hover { background: #161b22; }
.elo-table td { padding: 11px 14px; color: #e6edf3; vertical-align: middle; }
.conf-pill { display: inline-block; width: 26px; height: 26px; border-radius: 50%; background: #21262d; color: #7d8590; font-size: 0.75rem; font-weight: 800; text-align: center; line-height: 26px; }
.conf-pill.high { background: rgba(63,185,80,0.15); color: #3fb950; }
.conf-pill.mid { background: rgba(88,166,255,0.12); color: #58a6ff; }
.away-label { color: #7d8590; font-size: 0.82rem; }
.pick-name { font-weight: 800; font-size: 0.95rem; }
.pick-green { color: #3fb950; }
.pick-blue { color: #58a6ff; }
.pick-yellow { color: #d29922; }
.pick-red { color: #f85149; }
.bar-wrap { display: flex; align-items: center; gap: 8px; }
.bar-track { width: 80px; height: 5px; background: #21262d; border-radius: 3px; overflow: hidden; flex-shrink: 0; }
.bar-fill { height: 100%; border-radius: 3px; }
.bar-pct { font-size: 0.8rem; font-weight: 700; min-width: 38px; }
.spread-txt { color: #7d8590; font-size: 0.82rem; white-space: nowrap; }
.date-txt { color: #7d8590; font-size: 0.78rem; white-space: nowrap; }
.result-pending { color: #7d8590; font-size: 0.75rem; font-style: italic; }
.result-win { color: #3fb950; font-weight: 800; }
.result-loss { color: #f85149; font-weight: 800; }
.elo-note { font-size: 0.75rem; color: #7d8590; margin-top: 8px; line-height: 1.6; }
.elo-note a { color: #58a6ff; text-decoration: none; }
.results-box { background: #161b22; border: 1px solid #30363d; border-radius: 10px; padding: 20px 24px; margin-top: 20px; color: #adbac7; font-size: 0.88rem; line-height: 1.7; }
.results-box strong { color: #e6edf3; }
</style>

<div class="elo-wrap">

<div class="elo-intro">
<p>I built a reimplementation of <a href="https://github.com/fivethirtyeight/nfl-elo-game">FiveThirtyEight's Elo rating system</a> for NFL games, backtested it against historical data, and now I log picks every week before kickoff — no editing afterward.</p>
<p>The model rates every team after every game going back to 1920 and computes win probabilities from the rating difference. <strong>No injuries, no weather, no gut feel. Just Elo.</strong></p>
</div>

<div class="elo-stat-row">
  <div class="elo-stat">
    <div class="elo-stat-label">Backtest accuracy</div>
    <div class="elo-stat-value" style="color:#3fb950">63.3%</div>
  </div>
  <div class="elo-stat">
    <div class="elo-stat-label">Sample size</div>
    <div class="elo-stat-value" style="color:#58a6ff">1,420</div>
  </div>
  <div class="elo-stat">
    <div class="elo-stat-label">Seasons</div>
    <div class="elo-stat-value" style="color:#d29922">2021–25</div>
  </div>
  <div class="elo-stat">
    <div class="elo-stat-label">Week 10 record</div>
    <div class="elo-stat-value" style="color:#7d8590" id="w10rec">—/14</div>
  </div>
</div>

<div class="elo-section-title">Week 10 · Nov 12–16 · 14 games · all picks follow model direction</div>

<div class="elo-table-wrap">
<table class="elo-table">
<thead>
<tr><th>Conf</th><th>Date</th><th>Matchup</th><th>My Pick</th><th>Elo Win %</th><th>Spread</th><th>Result</th></tr>
</thead>
<tbody id="picks-rows"></tbody>
</table>
</div>

<p class="elo-note">Conf = confidence rank out of 14 (14 = most confident pick). Picks committed to <a href="https://github.com/DatWins/nfl_predictor/blob/main/predictions/2026-week10.csv">GitHub</a> before Thursday kickoff. 🌍 = neutral site (Munich), home-field advantage not applied.</p>

<div class="results-box" id="results-box">
  <strong>Results</strong> — to be filled in after Monday Night Football, Nov 16.
</div>

</div>

<script>
(function(){
  var games = [
    {date:'Thu 11/12',away:'WAS',home:'NYG',pick:'NYG',pct:53.9,spread:'NYG -1.5',result:null},
    {date:'Thu 11/13 🌍',away:'NE',home:'DET',pick:'DET',pct:55.7,spread:'DET -3.5',result:null},
    {date:'Sun 11/15',away:'CIN',home:'ATL',pick:'CIN',pct:41.8,spread:'ATL -2.5',result:null},
    {date:'Sun 11/15',away:'DEN',home:'CAR',pick:'DEN',pct:65.3,spread:'DEN -6.5',result:null},
    {date:'Sun 11/15',away:'KC',home:'DAL',pick:'KC',pct:45.1,spread:'DAL -1.5',result:null},
    {date:'Sun 11/15',away:'JAX',home:'CLE',pick:'JAX',pct:61.3,spread:'JAX -9.5',result:null},
    {date:'Sun 11/15',away:'MIN',home:'GB',pick:'GB',pct:56.1,spread:'GB -2.5',result:null},
    {date:'Sun 11/15',away:'TEN',home:'IND',pick:'TEN',pct:26.6,spread:'IND -6.0',result:null},
    {date:'Sun 11/15',away:'BUF',home:'MIA',pick:'BUF',pct:61.7,spread:'BUF -9.5',result:null},
    {date:'Sun 11/15',away:'NYJ',home:'NO',pick:'NO',pct:69.3,spread:'NO -4.5',result:null},
    {date:'Sun 11/15',away:'SF',home:'ARI',pick:'SF',pct:64.4,spread:'SF -6.0',result:null},
    {date:'Sun 11/15',away:'LV',home:'SEA',pick:'SEA',pct:90.4,spread:'SEA -13.5',result:null},
    {date:'Sun 11/15',away:'PIT',home:'HOU',pick:'PIT',pct:28.1,spread:'HOU -4.5',result:null},
    {date:'Mon 11/16',away:'LAC',home:'BAL',pick:'BAL',pct:61.5,spread:'BAL -3.5',result:null},
  ];

  // assign confidence ranks
  var sorted = games.slice().sort(function(a,b){return b.pct-a.pct;});
  sorted.forEach(function(g,i){g.conf=games.length-i;});

  function barColor(p){
    if(p>=75) return '#3fb950';
    if(p>=60) return '#58a6ff';
    if(p>=50) return '#d29922';
    return '#f85149';
  }
  function pickColor(p){
    if(p>=75) return 'pick-green';
    if(p>=60) return 'pick-blue';
    if(p>=50) return 'pick-yellow';
    return 'pick-red';
  }
  function confClass(c){
    if(c>=11) return 'high';
    if(c>=7)  return 'mid';
    return '';
  }

  var tbody = document.getElementById('picks-rows');
  if(!tbody) return;
  games.forEach(function(g){
    var resultHtml = g.result==='W' ? '<span class="result-win">✓ W</span>'
      : g.result==='L' ? '<span class="result-loss">✗ L</span>'
      : '<span class="result-pending">pending</span>';
    var away = g.away.replace('🌍','').trim();
    var home = g.home;
    var matchup = '<span class="away-label">'+away+'</span> @ <strong>'+home+'</strong>';
    var tr = document.createElement('tr');
    tr.innerHTML =
      '<td><span class="conf-pill '+confClass(g.conf)+'">'+g.conf+'</span></td>'+
      '<td class="date-txt">'+g.date+'</td>'+
      '<td>'+matchup+'</td>'+
      '<td><span class="pick-name '+pickColor(g.pct)+'">'+g.pick+'</span></td>'+
      '<td><div class="bar-wrap"><div class="bar-track"><div class="bar-fill" style="width:'+g.pct+'%;background:'+barColor(g.pct)+'"></div></div><span class="bar-pct" style="color:'+barColor(g.pct)+'">'+g.pct.toFixed(1)+'%</span></div></td>'+
      '<td class="spread-txt">'+g.spread+'</td>'+
      '<td>'+resultHtml+'</td>';
    tbody.appendChild(tr);
  });

  // season record card
  var wins=games.filter(function(g){return g.result==='W';}).length;
  var played=games.filter(function(g){return g.result!==null;}).length;
  var rec = document.getElementById('w10rec');
  if(rec && played) rec.textContent = wins+'/'+played;
})();
</script>
