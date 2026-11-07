---
layout: post
title: "Halfway There: Learning to Write for Beginners"
date: 2026-11-05
description: "A midterm reflection on contributing to the ai4all textbook: what
  went well, what slowed me down, and the one habit I’m changing for the second
  half."
---
In my last post I said I expected my next update to look very different. It does. Most of the second half so far has gone into ai4all, an introductory AI textbook that Dr. Jan maintains on Runestone. Contributing to it has taught me more about open source than anything else this semester.

I ended up there almost by accident. I was waiting to be added to Dr. Jan’s Security book when she told me to pick issues from her pinned book repositories instead. I chose ai4all because AI is where I want to build my career, and because a beginner’s AI book is a place where a clear explanation matters. My first pull request, PR #225 for issue #216, adds an explanation of big data to Section 1.1. My second, PR #226 for issue #218, defines six terms in Section 4.4 that the book used without explaining: hyperparameter, ground truth, data leakage, the central limit theorem, binary classification, and classification threshold. Where I could, I used the chapter’s own loan example, so the definitions connect to something readers have already seen.

The review on #225 taught me the most. Dr. Jan said my paragraph needed better balance and flow, and that the ideas needed to connect. My draft was technically correct, but it read like a list of facts rather than an explanation. I rewrote it so that big data and deep learning lead into each other, and showed why deep learning needs so much data in the first place. The second version is clearly better. Writing for a textbook is its own kind of engineering. A definition can be accurate and still lose a beginner, and I had to learn to read my own sentences the way a beginner would.

What didn’t go as planned was setup. ai4all is written in PreTeXt, and the build kept failing with an error about a missing entities reference. I assumed it was a Windows problem and moved everything to WSL. The build failed the same way there. The actual cause was a newer version of lxml, and pinning it to an older version fixed it. Then I noticed my commits weren’t showing up under my GitHub account, because WSL had a different git identity configured. I had to rewrite the author on my commits and force-push both PRs. I also learned that a local build generates thousands of artifact files, so staging everything would have buried my real edits. Now I only add the specific source file I changed. None of these problems was hard on its own. Each one just took an afternoon, and I spent most of that afternoon trying to fix it alone.

Time management was the other problem. This is internship recruiting season, and applications, assessments, and recruiter conversations have taken a large share of my week. My contributions have come in bursts, not as steady progress.

The habit I want to change is working through blockers alone. My instinct when something breaks is to keep trying things until it works. It feels productive, but with the lxml error, an hour of writing down what I was seeing and asking for help would have saved me most of a day. Working alone also hides problems that affect other people. If the build breaks for me, it will break for the next contributor too.

My plan has four parts. First, when I’ve been stuck on the same problem for 45 minutes, I’ll stop and write it up, including the error, what I tried, and what I think is happening, and then ask. Second, I’ll set two fixed ai4all work sessions each week, so my contributions stop depending on whether recruiting leaves me a free evening. Third, I’ll file the lxml fix as an issue on the ai4all repo, so no one else loses the same afternoon. Fourth, I’ll keep a short setup log of every environment fix I make.

**Progress update**

I’ve completed 9 story points so far. Both ai4all PRs, #225 and #226, are open. #225 has already gone through a revision round based on Dr. Jan’s feedback. Both took longer than I estimated. Writing a definition looked like a small task, but each term needed a sentence that was accurate, short, and connected to the chapter. Then the review showed me that connecting ideas matters as much as defining them. Setup was the biggest delay, since I couldn’t build the book at all until the lxml problem was fixed.

I’m also working ahead while I wait for reviews. I posted a plan on issue #208 for Section 4.2, proposing a frequency table and a simpler introduction, and I’m waiting for Dr. Jan’s response before I write it. Meanwhile I’ve started issue #211 in Section 4.3. There I’m defining terms like central tendency, variability, standard deviation, population, and sample, and the first edit is done. Issue #149 is next.

Taken together, this work taught me the full open-source workflow from start to finish: forking, building locally, keeping build artifacts out of my commits, responding to a maintainer’s review, and making sure my work is credited to me. My goal for the next post is to have these PRs merged and to have the number reflect them.