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


language as a solution
also bad: ambiguous



# ($\phi$)toshop
what it is: interface and algorithm

existing methods vs ($\phi$)toshop

tedious -> intuitive
expensive -> efficient
uninterpretable -> interpretable by design
ambiguous -> precise
<p class="fragment fade-in-then-semi-out">
fragement
</p>
<p class="fragment fade-in-then-semi-out">
fragement
</p>


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