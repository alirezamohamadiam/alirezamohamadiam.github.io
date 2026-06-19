---
layout: single
title: "Life Calendar"
permalink: /life-calendar/
author_profile: true
---

<style>
.life-calendar-container {
  max-width: 1200px;
  margin: 0 auto;
}

.life-header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.life-header h2 {
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.life-stats {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
  margin-bottom: 1.5rem;
}

.stat-box {
  text-align: center;
  padding: 1rem 1.5rem;
  border-radius: 8px;
  background: #f5f5f5;
  min-width: 120px;
}

.stat-number {
  font-size: 1.8rem;
  font-weight: 700;
  display: block;
}

.stat-label {
  font-size: 0.85rem;
  color: #666;
  text-transform: uppercase;
  letter-spacing: 0.05em;
}

.lived { color: #2e7d32; }
.remaining { color: #1565c0; }
.total { color: #424242; }
.percent { color: #6a1b9a; }

.weeks-legend {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  margin-bottom: 1.5rem;
  font-size: 0.85rem;
  color: #555;
}

.legend-item {
  display: flex;
  align-items: center;
  gap: 0.4rem;
}

.legend-box {
  width: 14px;
  height: 14px;
  border-radius: 2px;
  border: 1px solid #ccc;
}

.legend-filled { background: #2e7d32; border-color: #2e7d32; }
.legend-empty { background: #fff; }

.calendar-scroll {
  overflow-x: auto;
  padding-bottom: 1rem;
}

.weeks-grid {
  display: grid;
  grid-template-columns: 36px repeat(52, 1fr);
  gap: 3px;
  min-width: 800px;
}

.year-label {
  font-size: 0.7rem;
  color: #888;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-right: 6px;
  font-weight: 500;
}

.week-cell {
  aspect-ratio: 1;
  border-radius: 2px;
  border: 1px solid #e0e0e0;
  background: #fff;
  transition: transform 0.15s ease;
  cursor: default;
}

.week-cell.filled {
  background: #2e7d32;
  border-color: #2e7d32;
}

.week-cell.filled:hover {
  transform: scale(1.4);
  z-index: 10;
  position: relative;
  box-shadow: 0 2px 6px rgba(0,0,0,0.2);
}

.week-cell.empty:hover {
  transform: scale(1.4);
  z-index: 10;
  position: relative;
  background: #bbdefb;
  border-color: #1565c0;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
}

.tooltip {
  position: absolute;
  bottom: 130%;
  left: 50%;
  transform: translateX(-50%);
  background: #333;
  color: #fff;
  padding: 4px 10px;
  border-radius: 4px;
  font-size: 0.7rem;
  white-space: nowrap;
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.15s ease;
  z-index: 20;
}

.week-cell:hover .tooltip {
  opacity: 1;
}

.life-quote {
  text-align: center;
  margin-top: 2.5rem;
  font-style: italic;
  color: #666;
  font-size: 1.05rem;
}

@media (max-width: 768px) {
  .weeks-grid {
    gap: 2px;
  }
  .stat-number {
    font-size: 1.4rem;
  }
  .life-stats {
    gap: 0.8rem;
  }
}
</style>

<div class="life-calendar-container">
  <div class="life-header">
    <h2>My Life in Weeks</h2>
    <p style="color:#666; margin-top:0.3rem;">Born December 4, 2000 &mdash; expecting ~75 years</p>
  </div>

  <div class="life-stats">
    <div class="stat-box">
      <span class="stat-number lived" id="lived-count">&mdash;</span>
      <span class="stat-label">Weeks Lived</span>
    </div>
    <div class="stat-box">
      <span class="stat-number remaining" id="remaining-count">&mdash;</span>
      <span class="stat-label">Weeks Left</span>
    </div>
    <div class="stat-box">
      <span class="stat-number total" id="total-count">&mdash;</span>
      <span class="stat-label">Total Weeks</span>
    </div>
    <div class="stat-box">
      <span class="stat-number percent" id="percent-count">&mdash;</span>
      <span class="stat-label">% Completed</span>
    </div>
  </div>

  <div class="weeks-legend">
    <div class="legend-item">
      <div class="legend-box legend-filled"></div>
      <span>Lived</span>
    </div>
    <div class="legend-item">
      <div class="legend-box legend-empty"></div>
      <span>Remaining</span>
    </div>
    <div class="legend-item">
      <span>Each row = 1 year (52 weeks)</span>
    </div>
  </div>

  <div class="calendar-scroll">
    <div class="weeks-grid" id="weeks-grid"></div>
  </div>

  <div class="life-quote">
    "We are what we repeatedly do. Excellence, then, is not an act, but a habit." — Will Durant
  </div>
</div>

<script>
(function() {
  const BIRTH_DATE = new Date('2000-12-04T00:00:00');
  const EXPECTED_YEARS = 75;
  const WEEKS_PER_YEAR = 52;
  const TOTAL_WEEKS = EXPECTED_YEARS * WEEKS_PER_YEAR;

  const now = new Date();
  const msPerWeek = 1000 * 60 * 60 * 24 * 7;
  const livedMs = now - BIRTH_DATE;
  const livedWeeks = Math.floor(livedMs / msPerWeek);
  const remainingWeeks = Math.max(0, TOTAL_WEEKS - livedWeeks);
  const percent = Math.min(100, (livedWeeks / TOTAL_WEEKS * 100)).toFixed(1);

  document.getElementById('lived-count').textContent = livedWeeks.toLocaleString();
  document.getElementById('remaining-count').textContent = remainingWeeks.toLocaleString();
  document.getElementById('total-count').textContent = TOTAL_WEEKS.toLocaleString();
  document.getElementById('percent-count').textContent = percent + '%';

  const grid = document.getElementById('weeks-grid');

  // Top header row with week numbers (every 4 weeks)
  const emptyCorner = document.createElement('div');
  emptyCorner.className = 'year-label';
  grid.appendChild(emptyCorner);

  for (let w = 1; w <= 52; w++) {
    const header = document.createElement('div');
    header.className = 'year-label';
    header.style.justifyContent = 'center';
    header.style.fontSize = '0.6rem';
    header.textContent = (w % 4 === 1 || w === 52) ? w : '';
    grid.appendChild(header);
  }

  for (let year = 1; year <= EXPECTED_YEARS; year++) {
    const yearLabel = document.createElement('div');
    yearLabel.className = 'year-label';
    yearLabel.textContent = 'Y' + year;
    grid.appendChild(yearLabel);

    for (let week = 1; week <= 52; week++) {
      const globalWeek = (year - 1) * 52 + week;
      const cell = document.createElement('div');
      cell.className = 'week-cell' + (globalWeek <= livedWeeks ? ' filled' : ' empty');

      const tooltip = document.createElement('div');
      tooltip.className = 'tooltip';
      tooltip.textContent = 'Year ' + year + ', Week ' + week;
      cell.appendChild(tooltip);

      grid.appendChild(cell);
    }
  }
})();
</script>
