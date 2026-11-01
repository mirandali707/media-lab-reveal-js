# ($\phi$)toshop: *human-robot alignment as craft*
*Miranda Li*
<!-- TODO design this slide! maybe make a collage? -->
Advisor: Cynthia Breazeal
<!-- at prg we are ... -->

Thesis readers: Arvind Satyanarayan, Andreea Bobu, Crystal Lee
<!-- arvind does ..., andreea does ..., crystal does ... -->



<!-- # Motivation -->
<!-- <img src="img/calibratedfeats.png" style="height: 300px; object-fit: contain; width: 100%;"> -->
<div style="display: flex; gap: 24px; width: 100%; align-items: flex-end;">
<figure style="flex: 1; min-width: 0; margin: 0;">
<img src="img/personalrobot.webp" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
<figcaption style="font-size: 0.6em;">If I Had a Robot: What to Expect from the Personal Robot, 1984</figcaption>
<!-- src: https://paleofuture.com/blog/2008/7/21/if-i-had-a-robot-1984.html -->
</figure>
<figure style="flex: 1; min-width: 0; margin: 0;">
<img src="img/robotsarecoming.jpg" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
<figcaption style="font-size: 0.6em;">Shenzhen, 2025</figcaption>
<!-- src: https://www.chinadailyhk.com/hk/article/605439 -->
</figure>
</div>



<!-- # Existing work -->
<!-- annotate personal robot image: what matters: stove is hot, keep knife away from person, butter goes on toast not plate... -->
To get intelligent, autonomous robots to work safely alongside humans, we need robots to understand what we care about ("features"), which can often be hard to communicate



<!-- math slide -->
<!-- .slide: data-auto-animate -->
<h1>Auto-Animate</h1>


<!-- .slide: data-auto-animate -->
<h1 style="margin-top: 100px; color: red;">Auto-Animate</h1>


$r(s)$: reward function

$\phi(s)$: reward function

$r(s) = \theta \cdot \phi(s)$
<!-- Algorithmic human-robot interaction models human preferences as a reward function over the state, r(s). The robot chooses its actions to maximize expected reward. 
Rather than learning this reward directly from the raw state s, the robot can first learn features phi(s) that capture what the human cares about (e.g., distance to the person, efficiency), and then learn a reward over those features, often as a weighted sum,
theta dot phi(s). -->



Existing methods are...

<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-out" data-fragment-index="1">preference pairs</p>
        <p class="fragment fade-in-then-out" data-fragment-index="2">demonstrations + corrections</p>
        <p class="fragment fade-in-then-out" data-fragment-index="3">language</p>
        <!-- <p class="fragment fade-in-then-out" data-fragment-index="3">NNs in general</p> -->
    </div>
    <div style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">
        tedious
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
        expensive
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">
        ambiguous
        </p>
        <!-- <p class="fragment fade-in-then-semi-out" data-fragment-index="3">
        uninterpretable
        </p> -->
    </div>
</div>
<!-- Maybe LLMs / VLMs are the answer?
<div class="fragment fade-in-then-semi-out" data-fragment-index="1">
How close is "too close"?
</div> -->
<!-- 
<p class="fragment fade-in-then-semi-out" data-fragment-index="2">
Language is too ambiguous for specific spatial relationships, and LLMs encode strong priors.
</p> -->



<!-- # ($\phi$)toshop -->
<section data-auto-animate>
    <img src="img/phitoshop_logo.jpeg" style="height: 300px; object-fit: contain; width: 100%;">
    <!-- <h1>($\phi$)toshop</h1> -->
<!-- 
an interactive visual interface 
which makes the robot's representation directly manipulable 
via visual annotation,
and the algorithm to make this possible. -->
<div class="r-stack">
    <p class="fragment fade-in-then-out">
        <img src="img/phitoshop_mockup.jpeg" style="height: 400px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-out">
        <img src="img/phitoshop_mockup2.jpeg" style="height: 400px; object-fit: contain; width: 100%;">
    </p>
</div>
</section>



## evaluating the interface
<!-- direct manipulation
interpretability interfaces -->
* NASA TLX: task load index
* effort: clicks, keystrokes, time taken
* perceived control and usefulness
* task success: scored against task-specific rubric



## evaluating the algorithm
$r(s) = \theta \cdot \phi(s)$
* reaction: oracle annotations move feature towards ground truth values
* isolation: oracle annotations do not affect elems of state irrelevant to feature
* efficiency: ms taken to update



## tasks / baselines
gridrobot
vehicle parking
swimmer letters (if time)



<div style="display: flex; gap: 24px; width: 100%;">
    <div style="flex: 1; min-width: 0;">
        <div style="height: 100px">
        <h3 > Existing methods</h3>
        </div>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">tedious</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">expensive</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">ambiguous</p>
        <!-- <p class="fragment fade-in-then-semi-out" data-fragment-index="4">uninterpretable</p> -->
    </div>
    <div style="flex: 1; min-width: 0;">
    <div style="height: 100px">
        <img src="img/phitoshop_logo.jpeg" style="height: 100%; object-fit: contain; width: 100%;">
        </div>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">
        intuitive
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
        efficient
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">
        precise
        </p>
        <!-- <p class="fragment fade-in-then-semi-out" data-fragment-index="4">
        interpretable by design
        </p> -->
    </div>
</div>



# goal
representational alignment as craft
end-user robot programming
(same image as title slide)



# Thank you!



# appendix
timeline
phitoshop sketches
tool descriptions