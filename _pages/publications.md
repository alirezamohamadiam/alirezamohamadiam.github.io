---
title: "My Publications"
permalink: /publications/
author_profile: true
---

You can find my articles on <a href="https://scholar.google.com/citations?user=qetrYAwAAAAJ&hl=en">my Google Scholar profile.</a>

<style>
/* ===== Publications page ===== */
.pub-wrap { margin-top: 1.5em; }

.pub-filters {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5em;
  margin-bottom: 1.8em;
}
.pub-filter {
  cursor: pointer;
  border: 1px solid #d6d6d6;
  background: #fff;
  color: #4a4a4a;
  padding: 0.45em 1.05em;
  border-radius: 999px;
  font-size: 0.82em;
  font-weight: 600;
  letter-spacing: 0.02em;
  transition: all 0.18s ease;
  -webkit-appearance: none;
}
.pub-filter:hover { border-color: #999; color: #111; }
.pub-filter.is-active {
  background: #2f5d8a;
  border-color: #2f5d8a;
  color: #fff;
  box-shadow: 0 3px 10px rgba(47,93,138,0.28);
}

.pub-section { margin-bottom: 2.4em; }
.pub-section-head {
  display: flex;
  align-items: center;
  gap: 0.6em;
  margin: 0 0 1em 0;
  padding-bottom: 0.45em;
  border-bottom: 2px solid #eee;
}
.pub-section-head .dot {
  width: 12px; height: 12px; border-radius: 50%;
  flex: 0 0 auto;
}
.pub-section-head h2 {
  margin: 0; font-size: 1.25em; font-weight: 700; color: #222; border: 0;
}
.pub-section-head .count {
  margin-left: auto; font-size: 0.78em; color: #888; font-weight: 600;
}

/* category accent colors */
.cat-aisci .dot { background: #1f8a70; }
.cat-xai   .dot { background: #7a4fd6; }
.cat-safety .dot { background: #d65f3f; }
.cat-aisci  .pub-card { border-left-color: #1f8a70; }
.cat-xai    .pub-card { border-left-color: #7a4fd6; }
.cat-safety .pub-card { border-left-color: #d65f3f; }

.pub-card {
  background: #fff;
  border: 1px solid #ececec;
  border-left: 4px solid #2f5d8a;
  border-radius: 8px;
  padding: 1em 1.2em;
  margin-bottom: 0.9em;
  box-shadow: 0 1px 3px rgba(0,0,0,0.04);
  transition: transform 0.16s ease, box-shadow 0.16s ease;
}
.pub-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 22px rgba(0,0,0,0.09);
}
.pub-title {
  font-size: 1.02em;
  font-weight: 700;
  color: #1a1a1a;
  line-height: 1.4;
  margin-bottom: 0.35em;
}
.pub-authors {
  font-size: 0.9em;
  color: #555;
  margin-bottom: 0.3em;
}
.pub-authors .me { color: #2f5d8a; font-weight: 700; }
.pub-venue {
  font-size: 0.85em;
  color: #777;
  font-style: italic;
  margin-bottom: 0.65em;
}
.pub-meta {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.5em;
}
.pub-tag {
  font-size: 0.7em;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  padding: 0.25em 0.7em;
  border-radius: 4px;
}
.tag-preprint { background: #eef4fb; color: #2f5d8a; }
.tag-if       { background: #fff3e0; color: #b96b00; }
.tag-ieee     { background: #eaf6ee; color: #1f8a70; }
.tag-review   { background: #f3eefb; color: #7a4fd6; }

.pub-links { display: flex; gap: 0.45em; margin-left: auto; }
.pub-links a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 30px; height: 30px;
  border-radius: 6px;
  background: #f4f4f4;
  color: #555 !important;
  font-size: 0.9em;
  text-decoration: none !important;
  transition: all 0.15s ease;
}
.pub-links a:hover { background: #2f5d8a; color: #fff !important; transform: translateY(-1px); }

.pub-hidden { display: none !important; }

@media (max-width: 600px) {
  .pub-links { margin-left: 0; margin-top: 0.5em; }
  .pub-meta { gap: 0.4em; }
}
</style>

<div class="pub-wrap" id="pubWrap">

  <div class="pub-filters" id="pubFilters">
    <button class="pub-filter is-active" data-filter="all">All</button>
    <button class="pub-filter" data-filter="aisci">AI for Science</button>
    <button class="pub-filter" data-filter="xai">XAI</button>
    <button class="pub-filter" data-filter="safety">AI Safety</button>
  </div>

  <!-- ============ AI SAFETY ============ -->
  <section class="pub-section cat-safety" data-cat="safety">
    <div class="pub-section-head">
      <span class="dot"></span>
      <h2>AI Safety</h2>
      <span class="count">2 papers</span>
    </div>

    <div class="pub-card">
      <div class="pub-title">Survival at Any Cost? LLMs and the Choice Between Self-Preservation and Human Harm</div>
      <div class="pub-authors"><span class="me">A. Mohammadi</span>, A. Yavari</div>
      <div class="pub-venue">Preprint, 2025</div>
      <div class="pub-meta">
        <span class="pub-tag tag-preprint">Preprint</span>
        <span class="pub-links">
          <a href="https://doi.org/10.48550/arXiv.2509.12190" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
          <a href="https://github.com/alirezamohamadiam/DECIDE-SIM" title="Code" target="_blank" rel="noopener"><i class="fab fa-github"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Securing Healthcare with Deep Learning: A CNN-Based Model for Medical IoT Threat Detection</div>
      <div class="pub-authors"><span class="me">A. Mohammadi</span>, H. Ghahramani, S. A. Asghari, M. Aminian</div>
      <div class="pub-venue">19th Iranian Conference on Intelligent Systems (ICIS), 2024</div>
      <div class="pub-meta">
        <span class="pub-tag tag-ieee">IEEE Indexed</span>
        <span class="pub-links">
          <a href="https://doi.org/10.1109/ICIS64839.2024.10887510" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
          <a href="https://arxiv.org/pdf/2410.23306" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
          <a href="https://github.com/alirezamohamadiam/Advanced-Cyberattack-Detection-in-IoMT-Using-CNN" title="Code" target="_blank" rel="noopener"><i class="fab fa-github"></i></a>
          <a href="https://youtu.be/hPV5H9kTbYM?si=fWtb_eaIiLQ3uGEy" title="Video" target="_blank" rel="noopener"><i class="fab fa-youtube"></i></a>
        </span>
      </div>
    </div>
  </section>

  <!-- ============ XAI ============ -->
  <section class="pub-section cat-xai" data-cat="xai">
    <div class="pub-section-head">
      <span class="dot"></span>
      <h2>Explainable AI (XAI)</h2>
      <span class="count">1 paper</span>
    </div>

    <div class="pub-card">
      <div class="pub-title">FreqAttXpose: Frequency-Aware Model Parameter Explorer — A New Attribution Method for Improving Explainability</div>
      <div class="pub-authors">A. Yavari, <span class="me">A. Mohammadi</span>, E. Beydagh, P. Seeböck, R. A. Leitgeb</div>
      <div class="pub-venue">Preprint, 2025</div>
      <div class="pub-meta">
        <span class="pub-tag tag-preprint">Preprint</span>
        <span class="pub-links">
          <a href="https://arxiv.org/abs/2510.03245" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>
  </section>

  <!-- ============ AI FOR SCIENCE ============ -->
  <section class="pub-section cat-aisci" data-cat="aisci">
    <div class="pub-section-head">
      <span class="dot"></span>
      <h2>AI for Science</h2>
      <span class="count">6 papers</span>
    </div>

    <div class="pub-card">
      <div class="pub-title">Meta-Learning and Formula Optimization for All-Optical XOR, OR, and NOT Logic Gates: The ML-FOLD Method</div>
      <div class="pub-authors"><span class="me">A. Mohammadi</span>, F. Parandin, P. Karami</div>
      <div class="pub-venue">Engineering Applications of Artificial Intelligence (EAAI) — Under second-round review</div>
      <div class="pub-meta">
        <span class="pub-tag tag-review">Under Review</span>
        <span class="pub-tag tag-if">IF: 8.0</span>
        <span class="pub-links">
          <a href="https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5115354" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Enhancing Integrated Optical Circuits: Optimizing All-Optical NAND and NOR Gates Through Deep Learning and Machine Learning</div>
      <div class="pub-authors">F. Parandin, <span class="me">A. Mohammadi</span>, P. Karami</div>
      <div class="pub-venue">Optical and Quantum Electronics, 2024</div>
      <div class="pub-meta">
        <span class="pub-tag tag-if">IF: 4.0</span>
        <span class="pub-links">
          <a href="https://doi.org/10.1007/s11082-024-07989-x" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
          <a href="https://alirezamohamadiam.github.io/files/Optical%20and%20Quantum%20Electronics.pdf" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Design and Optimization of Optical NAND and NOR Gates Using Photonic Crystals and the ML-FOLD Algorithm</div>
      <div class="pub-authors"><span class="me">A. Mohammadi</span>, F. Parandin, P. Karami, S. Olyaee</div>
      <div class="pub-venue">Photonics, 2025</div>
      <div class="pub-meta">
        <span class="pub-tag tag-if">IF: 2.1</span>
        <span class="pub-links">
          <a href="https://doi.org/10.3390/photonics12060576" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Machine Learning-Driven Optimization of Photonic Crystal Structures for Superior Optical NOR Gate Performance</div>
      <div class="pub-authors">F. Parandin, P. Karami, <span class="me">A. Mohammadi</span></div>
      <div class="pub-venue">Applied Optics, 2024</div>
      <div class="pub-meta">
        <span class="pub-tag tag-if">IF: 1.9</span>
        <span class="pub-links">
          <a href="https://doi.org/10.1364/AO.529142" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
          <a href="https://www.researchgate.net/publication/382986319_Machine_learning-driven_optimization_of_photonic_crystal_structures_for_superior_optical_NOR_gate_performance" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Neural Network-Driven Optimization of Photonic Crystal-Based All-Optical NOT Gate Design</div>
      <div class="pub-authors"><span class="me">A. Mohammadi</span>, F. Parandin, H. Ghahramani</div>
      <div class="pub-venue">International Conference on Distributed Computing and High Performance Computing, 2024</div>
      <div class="pub-meta">
        <span class="pub-tag tag-ieee">IEEE Indexed</span>
        <span class="pub-links">
          <a href="https://ieeexplore.ieee.org/document/10454088" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
          <a href="https://alirezamohamadiam.github.io/files/120.pdf" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>

    <div class="pub-card">
      <div class="pub-title">Enhancing the Performance of Photonic Crystal AND Gates with Machine Learning Optimization</div>
      <div class="pub-authors">F. Parandin, <span class="me">A. Mohammadi</span></div>
      <div class="pub-venue">International Conference on Distributed Computing and High Performance Computing, 2024</div>
      <div class="pub-meta">
        <span class="pub-tag tag-ieee">IEEE Indexed</span>
        <span class="pub-links">
          <a href="https://ieeexplore.ieee.org/abstract/document/10454025" title="Publisher" target="_blank" rel="noopener"><i class="fas fa-link"></i></a>
          <a href="https://alirezamohamadiam.github.io/files/115.pdf" title="PDF" target="_blank" rel="noopener"><i class="fas fa-file-pdf"></i></a>
        </span>
      </div>
    </div>
  </section>

</div>

<script>
(function () {
  var filters = document.querySelectorAll('#pubFilters .pub-filter');
  var sections = document.querySelectorAll('#pubWrap .pub-section');
  filters.forEach(function (btn) {
    btn.addEventListener('click', function () {
      filters.forEach(function (b) { b.classList.remove('is-active'); });
      btn.classList.add('is-active');
      var f = btn.getAttribute('data-filter');
      sections.forEach(function (sec) {
        var show = (f === 'all') || (sec.getAttribute('data-cat') === f);
        sec.classList.toggle('pub-hidden', !show);
      });
    });
  });
})();
</script>
