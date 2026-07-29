---
layout: page
permalink: /publications/
title: publications
nav: true
nav_order: 2
---
If you cannot access papers, code or data, do not hesitate to reach out, I am happy to share what I can. 

<h2 class="pub-section">Peer-reviewed articles</h2>
{% bibliography --file papers %}

<h2 class="pub-section">Policy briefs</h2>
{% bibliography --file policy-briefs %}

<h2 class="pub-section">Datasets</h2>
{% bibliography --file datasets %}

<script>
document.addEventListener('DOMContentLoaded', function () {
  document.querySelectorAll('a.abstract.btn').forEach(function (btn) {
    btn.textContent = 'abstract';
    btn.addEventListener('click', function (e) {
      e.preventDefault();
      var container = btn.closest('[id]') || btn.parentElement;
      var abs = container ? container.querySelector('div.abstract') : null;
      if (abs) {
        abs.classList.toggle('open');
        abs.classList.toggle('hidden');
      }
    });
  });

  document.querySelectorAll('.links a.btn').forEach(function (btn) {
    if (btn.textContent.trim() === 'HTML') {
      btn.textContent = 'link';
    }
  });
});
</script>
