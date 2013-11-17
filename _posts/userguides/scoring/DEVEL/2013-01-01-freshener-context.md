---
layout: post
title: FreshenerContext
categories: [userguides, scoring, devel]
tags : [scoring-ug]
order : 4
version : devel
description: Description of FreshenerContext API.
---

<div id="accordion-container">
  <h2 class="accordion-header"> FreshenerContext.java </h2>
    <div class="accordion-content">
    <script src="http://gist-it.appspot.com/github/kijiproject/kiji-scoring/raw/{{site.scoring_devel_branch}}/src/main/java/org/kiji/scoring/FreshenerContext.java"> </script>
  </div>
</div>

<h3 style="margin-top:0px;padding-top:10px;"> FreshenerContext </h3>
The KijiFreshnessPolicy and ScoreFunction interfaces are designed to enable easy development of robust, thread-safe code. One of the main ways in which the interfaces accomplish this is through the use of context objects to expose environmental state to computation. By bundling state into context objects, a Freshener may be written which requires no internal fields, which are common causes of thread unsafety. Data from each invocation of a Freshener is isolated from other invocations through this abstraction. Within one request, all request time methods of both the policy and score function will have access to the same FreshenerContext instance.

There are two narrower versions of FreshenerContext called FreshenerGetStoresContext and FreshenerSetupContext for use when the full set of state of a FreshenerContext is unavailable. These interfaces provide a strict subset of FreshenerContext’s methods and the behavior of the methods they do expose is identical to FreshenerContext.
