---
title       : Calculation of height of an object thrown vertically
subtitle    : (Developing Data Products)
author      : Ladislav Zan
job         : Passionate student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light      # 
widgets     : [mathjax, bootstrap, shiny, interactive]
mode        : selfcontained # {standalone, draft}
ext_widgets : {rCharts: [libraries/nvd3]}
---
## Problem Definition

Suppose, you want to throw a ball straight up into the air. You may be interrested in how long does it take the ball hit the ground? You may ignore any effects of air resistance throughout this problem.

--- .class #id

## Standard Equation

We can use folliwing equation:
$$y = y_0 + v_0 \times t - 0.5 \times g \times t^2$$
where
$$y_0$$ is initial height 
$$v_0$$ is initial velocity
$$t$$ is time
$$g$$ is gravitational accleration

--- .class #id

## Solving a problem

In order to gain time when an object hit a ground we need to switch this task to algebra.
Look at original equation once again and start think about it as it is quadratic formula.
Basic quadratic formula:
$$y = a \times x^2 + b \times t + c$$
With basic rules of algebra
$$x = \frac{-b \pm \sqrt{b^2 - 4 a c}}{2a}$$
we can get following equation
$$t = \frac{v_0 \pm \sqrt {v_0^2 + 2y_0g}}{g}$$
What is actually used in my Shiny application.

--- .class #id

## Embedded R Code


<div class="row-fluid">
  <div class="col-sm-4">
    <form class="well">
      <div class="form-group shiny-input-container">
        <label class="control-label" for="sex">Choose Sex</label>
        <div>
          <select id="sex"><option value="Male" selected>Male</option>
<option value="Female">Female</option></select>
          <script type="application/json" data-for="sex" data-nonempty="">{}</script>
        </div>
      </div>
      <div class="form-group shiny-input-container">
        <label class="control-label" for="type">Choose Type</label>
        <div>
          <select id="type"><option value="multiBarChart" selected>multiBarChart</option>
<option value="multiBarHorizontalChart">multiBarHorizontalChart</option></select>
          <script type="application/json" data-for="type" data-nonempty="">{}</script>
        </div>
      </div>
    </form>
  </div>
  <div class="col-sm-8">
    <div id="nvd3plot" class="shiny-html-output nvd3 rChart"></div>
  </div>
</div>
