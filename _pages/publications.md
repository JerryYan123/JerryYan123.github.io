---
layout: page
permalink: /publications/
title: publications
description: "* equal contribution"
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

<h2 class="bibliography">first / co-first author</h2>
{% bibliography --group_by none --query @*[lead=true]* %}

<h2 class="bibliography">other contributions</h2>
{% bibliography --group_by none --query @*[lead=false]* %}

</div>
