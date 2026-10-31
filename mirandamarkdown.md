# ($\phi$)toshop: *human-robot alignment as craft*
*Miranda Li*
<!-- TODO design this slide! maybe make a collage? -->



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



Existing methods are...

<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-out" data-fragment-index="1">preference pairs</p>
        <p class="fragment fade-in-then-out" data-fragment-index="2">demonstrations</p>
        <p class="fragment fade-in-then-out" data-fragment-index="3">corrections</p>
    </div>
    <div style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">
        tedious
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
        expensive
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">
        uninterpretable
        </p>
    </div>
</div>



Maybe LLMs / VLMs are the answer?

<div class="fragment fade-in-then-semi-out" data-fragment-index="1">
    "the sharper the utensil the further away from the person it should be"
    <img src="img/vlm_human.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
</div>

<p class="fragment fade-in-then-semi-out" data-fragment-index="2">
Language is too ambiguous to capture specific spatial relationships.
</p>




<!-- # ($\phi$)toshop -->
<section data-auto-animate>
    <img src="img/phitoshop_logo.jpeg" style="height: 300px; object-fit: contain; width: 100%;">
    <!-- <h1>($\phi$)toshop</h1> -->

An interactive visual interface 

which makes the robot's representation directly manipulable 

via visual annotation,

and the algorithm to make this possible.
</section>



<div style="display: flex; gap: 24px; width: 100%;">
    <div style="flex: 1; min-width: 0;">
        <div style="height: 100px">
        <h3 > Existing methods</h3>
        </div>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">tedious</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">expensive</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">uninterpretable</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="4">ambiguous</p>
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
        interpretable by design
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="4">
        precise
        </p>
    </div>
</div>



## interface
direct manipulation
interpretability interfaces



## algo
$r(s) = \theta \cdot \phi(s)$
targeted ...



## eval



## tasks / baselines



# goal
representational alignment as craft
end-user robot programming



# thanks for listening
Advisor: Cynthia Breazeal

Thesis readers: Arvind Satyanarayan, Andreea Bobu, Crystal Lee



# appendix
timeline