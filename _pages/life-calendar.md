---
layout: single
permalink: /life-calendar/
author_profile: true
---

<style>
.existential-container {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  background-color: #faf9f6;
  color: #282828;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 30px 15px;
  border-radius: 8px;
  max-width: 550px;
  margin: 0 auto;
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  border: 1px solid #e1e0dc;
}
.existential-title {
  font-weight: 600;
  letter-spacing: 2px;
  margin-top: 0;
  margin-bottom: 5px;
  font-size: 1.3rem;
  text-align: center;
}
.existential-subtitle {
  color: #787878;
  font-size: 0.85rem;
  margin-bottom: 25px;
  text-align: center;
}
.existential-rows {
  display: flex;
  flex-direction: column;
  gap: 2px;
  width: 100%;
}
.existential-year-row {
  display: flex;
  align-items: center;
  gap: 4px;
}
.existential-year-label {
  font-size: 0.6rem;
  color: #888;
  width: 22px;
  text-align: right;
  flex-shrink: 0;
  line-height: 1;
}
.existential-year-grid {
  display: grid;
  grid-template-columns: repeat(52, 1fr);
  gap: 2px;
  flex: 1;
}
.existential-cell {
  aspect-ratio: 1;
  background-color: transparent;
  box-sizing: border-box;
}
.existential-cell.past {
  background-color: #282828;
}
.existential-cell.current {
  background-color: #c0392b;
  animation: existential-pulse 2s infinite;
}
.existential-cell.future {
  border: 1px solid #d8d8d8;
}
.existential-footer {
  margin-top: 25px;
  text-align: center;
  font-size: 0.9rem;
  width: 100%;
}
.existential-footer p {
  margin: 4px 0;
}
.memento-mori {
  color: #c0392b;
  font-weight: bold;
  margin-top: 12px;
  letter-spacing: 1px;
}
@keyframes existential-pulse {
  0% { opacity: 0.5; }
  50% { opacity: 1; }
  100% { opacity: 0.5; }
}
</style>

<div class="existential-container">
  <h2 class="existential-title">MY LIFE IN WEEKS</h2>
  <div class="existential-subtitle">Based on a 75-Year Lifespan </div>

  <div class="existential-rows" id="lifeRows"></div>

  <div class="existential-footer">
    <p id="spentText">Spent: -- weeks (--%)</p>
    <p id="remainingText">Remaining: -- weeks</p>
    <p class="memento-mori">Memento Mori — Make every week count.</p>
    <p style="font-size:0.75rem;color:#999;margin-top:8px;font-style:italic;">JUST a simple reminder to myself: I have limited time to do things</p>
  </div>
</div>

<script>
(function() {
  const birthDate = new Date('2000-12-04');
  const totalRows = 75;
  const totalCols = 52;
  const totalWeeks = totalRows * totalCols;
  const today = new Date();
  let ageYears = today.getFullYear() - birthDate.getFullYear();
  const monthDiff = today.getMonth() - birthDate.getMonth();
  if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < birthDate.getDate())) {
    ageYears--;
  }
  const thisYearBirth = new Date(birthDate.getFullYear() + ageYears, birthDate.getMonth(), birthDate.getDate());
  const msInWeek = 1000 * 60 * 60 * 24 * 7;
  const weeksInCurrentYear = Math.floor((today - thisYearBirth) / msInWeek);
  const currentWeekIndex = (ageYears * totalCols) + weeksInCurrentYear;
  const rowsContainer = document.getElementById('lifeRows');
  if (rowsContainer) {
    for (let year = 0; year < totalRows; year++) {
      const yearRow = document.createElement('div');
      yearRow.className = 'existential-year-row';

      const yearLabel = document.createElement('div');
      yearLabel.className = 'existential-year-label';
      yearLabel.textContent = 'Y' + (year + 1);
      yearRow.appendChild(yearLabel);

      const yearGrid = document.createElement('div');
      yearGrid.className = 'existential-year-grid';

      for (let week = 0; week < totalCols; week++) {
        const i = year * totalCols + week;
        const cell = document.createElement('div');
        cell.classList.add('existential-cell');
        if (i < currentWeekIndex) {
          cell.classList.add('past');
        } else if (i === currentWeekIndex) {
          cell.classList.add('current');
        } else {
          cell.classList.add('future');
        }
        yearGrid.appendChild(cell);
      }

      yearRow.appendChild(yearGrid);
      rowsContainer.appendChild(yearRow);
    }
    const percentSpent = ((currentWeekIndex / totalWeeks) * 100).toFixed(1);
    const remainingWeeks = totalWeeks - currentWeekIndex;
    document.getElementById('spentText').innerText = 'Spent: ' + currentWeekIndex.toLocaleString() + ' weeks (' + percentSpent + '%)';
    document.getElementById('remainingText').innerText = 'Remaining: ' + remainingWeeks.toLocaleString() + ' weeks';
  }
})();
</script>
