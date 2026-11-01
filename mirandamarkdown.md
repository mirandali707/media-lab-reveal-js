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
<img src="img/robot_is_math.jpg" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
<!-- reveal meme robots -> math with legs
there's nothing magical about robots. they are just math with legs.
To get intelligent, autonomous robots to work safely alongside humans, we need to specify what we care about in math. -->
<!-- we need robots to understand what we care about ("features"), which can often be hard to communicate -->



<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <div >
            <img src="img/personalrobot_features_1.png" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
        </div>
        <div class="fragment fade-in-then-out" data-fragment-index="3">
            <img src="img/personalrobot_features_2.png" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
        </div>
        <div class="fragment fade-in" data-fragment-index="4">
            <img src="img/personalrobot_features_3.png" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
        </div>
    </div>
    <div style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">
            $r(s)$: reward function ("how good is this state?")
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
            $\phi(s)$: features ("what is important about this state?")
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="5">
            We assume $r(s) = \theta \cdot \phi(s)$.
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="6">
            We want to teach the robot the features $\phi(s)$ we care about.
        </p>
    </div>
</div>



Existing methods are...

<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <div class="fragment fade-in-then-out" data-fragment-index="1">
            <p>
            labelled preference pairs
            </p>
            <img src="img/farpls_prefpairs.jpg" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
        </div>
        <div class="fragment fade-in-then-out" data-fragment-index="2">
            <p>
            demonstrations + corrections
            </p>
            <img src="img/demos_corrections.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
        </div>
        <div class="fragment fade-in-then-out" data-fragment-index="3">
            <p>
            language
            </p>
            <img src="img/cokecan_taylorswift.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
        </div>
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
<!-- * task success: scored against task-specific rubric -->



## evaluating the algorithm
$r(s) = \theta \cdot \phi(s)$

$$f(\phi_i, A) = \phi_i'$$

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