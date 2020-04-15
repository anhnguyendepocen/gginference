README
================

Overview
========

Visualise the results of F test to compare two variances, Student's t-test, test of equal or given proportions, Pearson's chi-squared test for count data and test for association/correlation between paired samples.

Installation
============

``` r
# CRAN installation:
install.packages("gginference")

# Or the development version from GitHub:
# install.packages("devtools")
devtools::install_github("okgreece/gginference")
```

Usage
=====

One sample
----------

### One sample z-test with Normal population or *n* ≥ 30 and σ^2 known or unknown

The following table shows the rejection region which is calculated in and the parameters of `t.test`.

<table>
<colgroup>
<col width="10%" />
<col width="13%" />
<col width="30%" />
<col width="45%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em> = <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em> &lt; <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &lt; −<em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em> &gt; <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &gt; <em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em> ≠ <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>z</em>|&gt;<em>z</em><sub><em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $z=\\frac{\\overline{X}-\\mu\_0}{\\frac{\\sigma}{\\sqrt{n}}}$

where $z=\\frac{\\overline{X}-\\mu\_0}{s/\\sqrt{n}}$

### One sample t-test with Normal population and *n* &lt; 30 and σ^2 unknown

<table>
<colgroup>
<col width="10%" />
<col width="13%" />
<col width="30%" />
<col width="45%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em> = <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em> &lt; <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &lt; −<em>t</em><sub><em>n</em> − 1, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em> &gt; <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &gt; <em>t</em><sub><em>n</em> − 1, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em> ≠ <em>μ</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>t</em>|&gt;<em>t</em><sub><em>n</em> − 1, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $t=\\frac{\\overline{X}-\\mu\_0}{s/\\sqrt{n}}$

Two samples
-----------

### Two independent samples z-test with Normal population, *n*<sub>1</sub>, *n*<sub>2</sub> &gt; 30 and *σ*<sub>1</sub><sup>2</sup> and *σ*<sub>2</sub><sup>2</sup> are known or unknown

<table>
<colgroup>
<col width="15%" />
<col width="17%" />
<col width="26%" />
<col width="40%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> = <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &lt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &lt; −<em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &gt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &gt; <em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> ≠ <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>z</em>|&gt;<em>z</em><sub><em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where

$z=\\frac{\\overline{x\_1}-\\overline{x\_2}-d\_0}{ \\sqrt{\\frac{\\sigma\_{1}^2}{n\_1} + \\frac{\\sigma\_2^2}{n\_2}}}$

where

$z=\\frac{\\overline{x\_1}-\\overline{x\_2}-d\_0}{ \\sqrt{\\frac{s\_{1}^2}{n\_1} + \\frac{s\_2^2}{n\_2}}}$

### Two independent samples t-test with Normal population *n*<sub>1</sub>, *n*<sub>2</sub> &lt; 30 and *σ*<sub>1</sub><sup>2</sup> = *σ*<sub>2</sub><sup>2</sup> = *σ*<sup>2</sup>

<table>
<colgroup>
<col width="15%" />
<col width="17%" />
<col width="26%" />
<col width="40%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> = <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &lt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &lt; −<em>t</em><sub><em>n</em><sub>1</sub> + <em>n</em><sub>2</sub> − 2, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = TRUE,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &gt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &gt; <em>t</em><sub><em>n</em><sub>1</sub> + <em>n</em><sub>2</sub> − 2, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = TRUE,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> ≠ <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>t</em>|&gt;<em>t</em><sub><em>n</em><sub>1</sub> + <em>n</em><sub>2</sub> − 2, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = TRUE,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $t=\\frac{\\overline{x\_1}-\\overline{x\_2}-d\_0}{ \\sqrt{\\frac{(n\_1-1) s\_{1}^2+(n\_2-1)s\_{2}^2}{n\_{1}+n\_{2}-2}}\\sqrt{\\frac{1}{n\_1}+\\frac{1}{n\_2}}}$

### Two independent samples t-test with Normal population *n*<sub>1</sub>, *n*<sub>2</sub> &lt; 30 equal or unequal sizes and *σ*<sub>1</sub><sup>2</sup> ≠ *σ*<sub>2</sub><sup>2</sup>

<table>
<colgroup>
<col width="15%" />
<col width="17%" />
<col width="26%" />
<col width="40%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> = <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &lt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &lt; −<em>t</em><sub><em>ν</em>, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &gt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &gt; <em>t</em><sub><em>ν</em>, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> ≠ <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>t</em>|&gt;<em>t</em><sub><em>ν</em>, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $t=\\frac{\\overline{x\_1}-\\overline{x\_2}-d\_0}{ \\sqrt{\\frac{s\_{1}^2}{n\_1} + \\frac{s\_2^2}{n\_2}}}$

*ν* degrees of freedom, if

-   *n*<sub>1</sub> = *n*<sub>2</sub>, *ν* = 2(*n* − 1)

-   *n*<sub>1</sub> ≠ *n*<sub>2</sub>, $\\nu = \\frac{(\\frac{s\_1^2}{n\_1}+\\frac{s\_2^2}{n\_2})^2}{\\frac{(\\frac{s\_1^2}{n\_1})^2}{n\_1-1}+\\frac{(\\frac{s\_2^2}{n\_2})^2}{n\_2-2}})$

Paired samples with Normal population *n* ≤ 30
----------------------------------------------

<table>
<colgroup>
<col width="14%" />
<col width="17%" />
<col width="27%" />
<col width="40%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>t.test()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> = <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &lt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &lt; −<em>t</em><sub><em>n</em> − 1, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> &gt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>t</em> &gt; <em>t</em><sub><em>n</em> − 1, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>μ</em><sub>1</sub> − <em>μ</em><sub>2</sub> ≠ <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>t</em>|&gt;<em>t</em><sub><em>n</em> − 1, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $t=\\frac{\\overline{d}-d\_0}{ s\_d/\\sqrt{n}}$

$\\overline{d}=\\frac{1}{n} \\sum\_{i=1}^{n}(x\_{1\_i}-x\_{2\_i})=\\frac{1}{n} \\sum\_{i=1}^{n}d\_i$

$s\_d^2= \\frac{1}{n-1} \\sum\_{i=1}^n(d\_i- \\overline{d})^2$

Proportion test
---------------

### One-proportion z-test

<table>
<colgroup>
<col width="10%" />
<col width="13%" />
<col width="30%" />
<col width="45%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggproptest()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>p</em> = <em>p</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>p</em> &lt; <em>p</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &lt; −<em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>p</em> &gt; <em>p</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &gt; <em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>p</em> ≠ <em>p</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>z</em>|&gt;<em>z</em><sub><em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $z=\\frac{\\hat{p}-p\_0}{\\sqrt{p\_0(1-p\_0)}}\\sqrt{n}$

$\\hat{p}=\\frac{x}{n}$

### Two-proportion z-test

<table>
<colgroup>
<col width="14%" />
<col width="17%" />
<col width="27%" />
<col width="41%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggproptest()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>p</em><sub>1</sub> − <em>p</em><sub>2</sub> = <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>p</em><sub>1</sub> − <em>p</em><sub>2</sub> &lt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &lt; −<em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline"><em>p</em><sub>1</sub> − <em>p</em><sub>2</sub> &gt; <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>z</em> &gt; <em>z</em><sub><em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline"><em>p</em><sub>1</sub> − <em>p</em><sub>2</sub> ≠ <em>d</em><sub>0</sub></span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>z</em>|&gt;<em>z</em><sub><em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>paired</em> = FALSE,</li>
<li><em>var.equal</em> = FALSE,</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $z=\\frac{\\hat{p\_1}-\\hat{p\_2}-d\_0}{s}$

if *d*<sub>0</sub> = 0, $s \\approx \\sqrt{\\hat{p}(1-\\hat{p}) (\\frac{1}{n\_1}+\\frac{1}{n\_2})}$

if *d*<sub>0</sub> ≠ 0, $s = $

$\\hat{p\_1} = \\frac{x\_1}{n\_1}$

$\\hat{p\_2} = \\frac{x\_1}{n\_2}$

$\\hat{p} = \\frac{x\_1+x\_2}{n\_1+n\_2}$

Two-sample F test for equality of variances
-------------------------------------------

<table>
<colgroup>
<col width="21%" />
<col width="23%" />
<col width="22%" />
<col width="32%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggvartest()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline">$\frac{\sigma_1^2}{\sigma_2^2} = 1$</span></p></td>
<td><p><span class="math inline">$\frac{\sigma_1^2}{\sigma_2^2} &lt; 1$</span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>F</em> &gt; <em>F</em><sub><em>n</em><sub>1</sub> − 1, <em>n</em><sub>2</sub> − 1, 1 − <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample 1 data,</li>
<li><em>y</em> = vector of sample 2 data,</li>
<li><em>ratio</em> = 1</li>
<li><em>alternative</em> = &quot;less&quot;</li>
</ul></td>
</tr>
<tr class="even">
<td></td>
<td><p><span class="math inline">$\frac{\sigma_1^2}{\sigma_2^2} &gt; 1$</span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>F</em> &gt; <em>F</em><sub><em>n</em><sub>1</sub> − 1, <em>n</em><sub>2</sub> − 1, <em>a</em></sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>ratio</em> = 1</li>
<li><em>alternative</em> = &quot;greater&quot;</li>
</ul></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span class="math inline">$\frac{\sigma_1^2}{\sigma_2^2} \neq 1$</span></p></td>
<td><p><span class="math inline"><em>R</em> = {<em>F</em> &gt; <em>F</em><sub><em>n</em><sub>1</sub> − 1, <em>n</em><sub>2</sub> − 1, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = vector of sample data,</li>
<li><em>mu</em> = <span class="math inline"><em>μ</em><sub>0</sub></span>,</li>
<li><em>ratio</em> = 1</li>
<li><em>alternative</em> = &quot;two.sided&quot;</li>
</ul></td>
</tr>
</tbody>
</table>

where $F=\\frac{s\_1^2}{s\_2^2}, s\_1^2&gt;s\_2^2$

`ggcortest()`
-------------

<table>
<colgroup>
<col width="15%" />
<col width="24%" />
<col width="23%" />
<col width="35%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggcortest()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span class="math inline"><em>ρ</em> = 0</span></p></td>
<td><p><span class="math inline"><em>ρ</em> ≠ 0</span></p></td>
<td><p><span class="math inline"><em>R</em> = {|<em>t</em>|&gt;<em>t</em><sub><em>n</em> − 2, <em>a</em>/2</sub>}</span></p></td>
<td><ul>
<li><em>x</em> = 2-dimensional contingency table</li>
</ul></td>
</tr>
</tbody>
</table>

where $|t|= \\frac{|r \\sqrt{n-2}|}{\\sqrt{1-r^2}}$

|t|=

| Test             | *H*<sub>0</sub> | *H*<sub>1</sub> | Rejection Region | Definition |
|------------------|-----------------|-----------------|------------------|------------|
| Correlation test | 𝜚 = 0           | 𝜚 ≠ 0           | $R= {            | t          |

Chi-squared Test of Independence
--------------------------------

<table>
<colgroup>
<col width="15%" />
<col width="24%" />
<col width="23%" />
<col width="35%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggchisqtest()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Two variables are independent</p></td>
<td><pre><code>   Two variables
are not independent</code></pre></td>
<td><p><span class="math inline"><em>R</em> = {<em>X</em><sup>2</sup> &gt; <em>χ</em><sub><em>a</em>/2</sub><sup>2</sup>}</span></p></td>
<td><ul>
<li><em>x</em> = 2-dimensional contingency table</li>
</ul></td>
</tr>
</tbody>
</table>

where $\\chi^2= \\sum\_{n=1}^{n}\\frac{(O\_i-E\_i)^2}{Ei}$

ANOVA F-test
------------

<table>
<colgroup>
<col width="16%" />
<col width="17%" />
<col width="24%" />
<col width="42%" />
</colgroup>
<thead>
<tr class="header">
<th><span class="math inline"><em>H</em><sub>0</sub></span></th>
<th><span class="math inline"><em>H</em><sub>1</sub></span></th>
<th>Rejection Region of <strong><em>gginference</em></strong></th>
<th>Parameters of <code>ggaov()</code></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>$H_0: _1 = _2 = $ <span class="math inline">... = <em>μ</em><sub><em>k</em></sub></span></p></td>
<td><p>Not all three population means are equal</p></td>
<td><p><span class="math inline"><em>R</em> = {<em>F</em> &gt; <em>F</em><sub><em>k</em></sub> − 1, <em>n</em> − <em>k</em>, <em>a</em>}</span></p></td>
<td><ul>
<li><em>formula</em> = 2-dimensional contingency table</li>
<li><em>data</em> = data frame with the variables specified in the formula</li>
</ul></td>
</tr>
</tbody>
</table>

where $F=\\frac{\\sum\_{i=1}^kn\_i(\\overline{Y}\_i-\\overline{Y})^2/(k-1)}{\\sum\_{i=1}^k\\sum\_{j=1}^{n\_i}(Y\_{ij}-\\overline{Y}\_i)^2/(n-k)}$

Getting help
============

If you encounter a bug, please feel free to open an [issue](https://github.com/okgreece/gginference/issues) with a minimal reproducible example.
