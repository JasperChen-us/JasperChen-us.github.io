---
layout: post
title: "From 200 to 20,000: My Poker Journey"
date: 2026-10-18
permalink: /blog/wpt-poker-results/
---

## Lessons and Reminders

1. Do not move up in stakes too soon. For now, stick to **0.05/0.1/0.2 (0.05)** or **0.1/0.2/0.4 (0.1)**.
2. After several coolers or bad beats, take a break to cool down and stop playing for the rest of the day.

3. After a combined total of 5 river suckouts or coolers in a day, stop playing for the rest of the day.

## WPT Results

Starting stack: **216**. This journal tracks my progress toward **20,000**, beginning on October 18, 2026.

| Date | Level | Total stack | Daily profit/loss |
| --- | --- | ---: | ---: |
| 2026-10-18 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 252.39 | +36.39 |
| 2026-10-19 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 233.15 | -19.24 |
| 2026-10-20 | 0.05/0.1/0.2 (0.05) | 260.55 | +27.40 |
| 2026-10-21 | 0.05/0.1/0.2 (0.05) | 295.72 | +35.17 |
| 2026-10-22 | 0.05/0.1/0.2 (0.05) | 272.34 | -23.38 |
| 2026-10-23 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 324.21 | +51.87 |
| 2026-10-24 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 378.21 | +54.00 |
| 2026-10-25 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 394.08 | +15.87 |
| 2026-10-26 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 453.89 | +59.81 |
| 2026-10-27 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 473.46 | +19.57 |
| 2026-10-28 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 516.38 | +42.92 |
| 2026-10-29 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 475.65 | -40.73 |
| 2026-10-30 | 0.05/0.1/0.2 (0.05), 0.1/0.2/0.4 (0.1) | 520.10 | +44.45 |
| 2026-11-01 | 0.1/0.2/0.4 (0.1) | 558.25 | +38.15 |
| 2026-11-02 | 0.1/0.2/0.4 (0.1) | 579.66 | +21.41 |
| 2026-11-03 | 0.1/0.2/0.4 (0.1) | 382.39 | -197.27 |

Profit to date = **+166.39**

## Profit Progress

Cumulative profit relative to the starting stack of 216. Hover over a point for details. Dates without a recorded session are not plotted.

<div id="poker-profit-chart" style="margin:24px 0; color:#334155;"></div>
<script>
(function () {
  var host = document.getElementById('poker-profit-chart');
  var table = Array.from(document.querySelectorAll('table')).find(function (t) {
    return t.rows.length && t.rows[0].textContent.includes('Total stack');
  });
  if (!host || !table) return;
  var data = Array.from(table.rows).slice(1).map(function (r) {
    return {date:r.cells[0].textContent.trim(), profit: Number(r.cells[2].textContent.trim()) - 216};
  }).filter(function (d) {return Number.isFinite(d.profit);});
  if (!data.length) return;
  var ns = 'http://www.w3.org/2000/svg';
  function el(tag, attrs, text, parent) {
    var n = document.createElementNS(ns, tag);
    Object.keys(attrs).forEach(function (k) {n.setAttribute(k, attrs[k]);});
    if (text !== undefined) n.textContent = text;
    (parent || svg).appendChild(n); return n;
  }
  var svg = document.createElementNS(ns, 'svg');
  svg.setAttribute('viewBox','0 0 900 440');
  svg.setAttribute('role','img');
  svg.setAttribute('aria-label','Cumulative poker profit by date, relative to starting stack 216');
  svg.style.cssText='display:block;width:100%;height:auto;background:#f8fafc;border:1px solid #e2e8f0;border-radius:12px;font-family:system-ui,sans-serif';
  host.appendChild(svg);
  el('title', {}, 'Cumulative poker profit');
  el('text',{x:70,y:36,'font-size':20,'font-weight':600,fill:'#0f172a'},'Cumulative profit');
  var last=data[data.length-1];
  el('text',{x:830,y:36,'text-anchor':'end','font-size':18,'font-weight':600,fill:last.profit>=0?'#047857':'#be123c'},(last.profit>=0?'+':'')+last.profit.toFixed(2));
  var low=Math.floor(Math.min(0,...data.map(function(d){return d.profit;}))/100)*100;
  var high=Math.max(100,Math.ceil(Math.max(...data.map(function(d){return d.profit;}))/100)*100);
  var start=Date.parse(data[0].date+'T00:00:00Z'), end=Date.parse(last.date+'T00:00:00Z');
  function x(d){return 70+(Date.parse(d.date+'T00:00:00Z')-start)/Math.max(86400000,end-start)*760;}
  function y(v){return 350-(v-low)/(high-low)*270;}
  for(var v=low;v<=high;v+=100){
    el('line',{x1:70,x2:830,y1:y(v),y2:y(v),stroke:v===0?'#94a3b8':'#e2e8f0','stroke-dasharray':v===0?'5 4':'none'});
    el('text',{x:56,y:y(v)+5,'text-anchor':'end','font-size':14,fill:'#64748b'},String(v));
  }
  var points=data.map(function(d){return x(d)+','+y(d.profit);}).join(' ');
  el('polygon',{points:x(data[0])+','+y(0)+' '+points+' '+x(last)+','+y(0),fill:'#10b981','fill-opacity':0.1});
  el('polyline',{points:points,fill:'none',stroke:'#059669','stroke-width':3,'stroke-linejoin':'round','stroke-linecap':'round'});
  data.forEach(function(d,i){
    var dot=el('circle',{cx:x(d),cy:y(d.profit),r:5,fill:'#059669',stroke:'#fff','stroke-width':2,tabindex:0});
    el('title',{},d.date+': '+(d.profit>=0?'+':'')+d.profit.toFixed(2),dot);
    if(i===0 || d.date.slice(0,7)!==data[i-1].date.slice(0,7)) el('text',{x:x(d),y:378,'text-anchor':'middle','font-size':14,fill:'#64748b'},Number(d.date.slice(5,7))+'月');
  });
  el('text',{x:450,y:414,'text-anchor':'middle','font-size':14,fill:'#64748b'},'Month · '+data[0].date.slice(0,4));
})();
</script>
