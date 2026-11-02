# ($\phi$)toshop: 
## *human-robot alignment as craft*
*Miranda Li*




<h3>Thesis readers</h3>
<div style="display: flex; gap: 24px; width: 100%;">
    <p class="fragment fade-in" style="flex: 1; min-width: 0;">
        Cynthia Breazeal
        <img src="img/cynthia.jpg" style="height: 200px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in" style="flex: 1; min-width: 0;">
        Arvind Satyanarayan
        <img src="img/arvind.jpg" style="height: 200px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in" style="flex: 1; min-width: 0;">
        Andreea Bobu
        <img src="img/andreea.jpg" style="height: 200px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in" style="flex: 1; min-width: 0;">
        Crystal Lee
        <img src="img/crystal.jpeg" style="height: 200px; object-fit: contain; width: 100%;">
    </p>
</div>



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
        <div class="fragment fade-in-then-out" data-fragment-index="4">
            <img src="img/personalrobot_features_2.png" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
        </div>
        <div class="fragment fade-in" data-fragment-index="5">
            <img src="img/personalrobot_features_3.png" style="height: auto; width: 500px; max-width: 100%; max-height: 100%; margin: 0;">
        </div>
    </div>
    <div style="flex: 1; min-width: 0;">
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">
            $r(s)$: reward function ("how good is this state?")
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
            Learning <span style="color: green;">features</span>, then combining them into rewards, is more efficient and generalizable than learning rewards from the state directly.
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            Bobu, A., Wiggert, M., Tomlin, C., & Dragan, A. D. (2022). Inducing structure in reward learning by learning features. The International Journal of Robotics Research, 41(5), 497-518.
            </small>
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">
            <span style="color: green;">$\phi(s)$</span>: <span style="color: green;">features</span> ("what is important about this state?")
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="6">
            We assume $r(s) = \theta \cdot$<span style="color: green;">$\phi(s)$</span>.
        </p>
        <p style="padding-top:30px" class="fragment fade-in-then-semi-out" data-fragment-index="7">
            How do we teach the robot the <span style="color: green;">features $\phi(s)$</span> we care about?
        </p>
    </div>
</div>



Existing methods are...

<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <div class="fragment fade-out" data-fragment-index="3">
        <div class="fragment fade-in" data-fragment-index="1">
            <p>
            labelled preference pairs
            </p>
            <img src="img/farpls_prefpairs.jpg" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            Lyu, H., Bai, Y., Liang, X., Das, U., Shi, C., Gong, L., ... & Ma, X. (2024, March). FARPLS: A feature-augmented robot trajectory preference labeling system to assist human labelers’ preference elicitation. In Proceedings of the 29th International Conference on Intelligent User Interfaces (pp. 344-369).
            </small>
        </div>
        </div>
        <div class="fragment fade-out" data-fragment-index="5">
        <div class="fragment fade-in" data-fragment-index="3">
            <p>
            demonstrations + corrections
            </p>
            <img src="img/demos_corrections.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            For example, (not pictured):
            </br>
            Demonstrations:
            </br>
            Finn, C., Levine, S., & Abbeel, P. (2016, June). Guided cost learning: Deep inverse optimal control via policy optimization. In International conference on machine learning (pp. 49-58). PMLR.
            </br>
            Corrections:
            </br>
            Bajcsy, A., Losey, D. P., O’malley, M. K., & Dragan, A. D. (2017, October). Learning robot objectives from physical human interaction. In Conference on robot learning (pp. 217-226). PMLR.
            </small>
        </div>
        </div>
        <div class="fragment fade-in" data-fragment-index="5">
            <p>
            language
            </p>
            <img src="img/cokecan_taylorswift.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            Kim, M. J., Pertsch, K., Karamcheti, S., Xiao, T., Balakrishna, A., Nair, S., ... & Finn, C. (2024). OpenVLA: An open-source vision-language-action model. arXiv preprint arXiv:2406.09246.
            </small>
        </div>
    </div>
    <div style="flex: 1; min-width: 0; display: flex; flex-direction: column; justify-content: center;">
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
        tedious
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="4">
        expensive
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="6">
        ambiguous
        </p>
    </div>
</div>




Existing methods **cast the human as** a...

<div style="display: flex; gap: 24px; width: 100%;">
    <div class="r-stack" style="flex: 1; min-width: 0;">
        <div class="fragment fade-out" data-fragment-index="3">
        <div class="fragment fade-in" data-fragment-index="1">
            <p>
            labelled preference pairs
            </p>
            <img src="img/farpls_prefpairs.jpg" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            Lyu, H., Bai, Y., Liang, X., Das, U., Shi, C., Gong, L., ... & Ma, X. (2024, March). FARPLS: A feature-augmented robot trajectory preference labeling system to assist human labelers’ preference elicitation. In Proceedings of the 29th International Conference on Intelligent User Interfaces (pp. 344-369).
            </small>
        </div>
        </div>
        <div class="fragment fade-out" data-fragment-index="5">
        <div class="fragment fade-in" data-fragment-index="3">
            <p>
            demonstrations + corrections
            </p>
            <img src="img/demos_corrections.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            For example, (not pictured):
            </br>
            Demonstrations:
            </br>
            Finn, C., Levine, S., & Abbeel, P. (2016, June). Guided cost learning: Deep inverse optimal control via policy optimization. In International conference on machine learning (pp. 49-58). PMLR.
            </br>
            Corrections:
            </br>
            Bajcsy, A., Losey, D. P., O’malley, M. K., & Dragan, A. D. (2017, October). Learning robot objectives from physical human interaction. In Conference on robot learning (pp. 217-226). PMLR.
            </small>
        </div>
        </div>
        <div class="fragment fade-in" data-fragment-index="5">
            <p>
            language
            </p>
            <img src="img/cokecan_taylorswift.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;">
            <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
            Kim, M. J., Pertsch, K., Karamcheti, S., Xiao, T., Balakrishna, A., Nair, S., ... & Finn, C. (2024). OpenVLA: An open-source vision-language-action model. arXiv preprint arXiv:2406.09246.
            </small>
        </div>
    </div>
    <div style="flex: 1; min-width: 0; display: flex; flex-direction: column; justify-content: center;">
        <div class="fragment fade-in-then-semi-out" data-fragment-index="2">
            <p>
            data labeller
            </p>
            <!-- <img src="img/faceplant.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;"> -->
        </div>
        <div class="fragment fade-in-then-semi-out" data-fragment-index="4">
            <p>
            data labeller but with more steps
            </p>
            <!-- <img src="img/faceplant_vr.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;"> -->
        </div>
        <div class="fragment fade-in-then-semi-out" data-fragment-index="6">
            <p>
            prompt engineer
            </p>
            <!-- <img src="img/faceplant_vr.png" style="display: block; height: auto; width: 100%; max-width: 100%; max-height: none; margin: 0;"> -->
        </div>
        <!-- images -->
        <div class="r-stack" style="flex: 1; min-width: 0;">
            <div class="fragment fade-out" data-fragment-index="4">
                <img class="fragment fade-in" src="img/faceplant.png" style="display: block; height: auto; width: 200px;" data-fragment-index="2">
            </div>
            <div class="fragment fade-out" data-fragment-index="6">
                <img class="fragment fade-in" src="img/faceplant_vr.png" style="display: block; height: auto; width: 200px;" data-fragment-index="4">
            </div>
            <img class="fragment fade-in" src="img/faceplant.png" style="display: block; height: auto; width: 200px;" data-fragment-index="6">
        </div>
    </div>
</div>



<!-- .slide: data-auto-animate data-background-color="black" data-transition="zoom"-->
# ($\phi$)toshop: 
## *human-robot alignment as craft*

<img src="img/phitoshop_logo.png" style="height: 300px">



<!-- .slide: data-auto-animate -->
<div style="display: flex; gap: 24px; align-items: center; justify-content: center;">
<img src="img/phitoshop_logo.png" style="height: 100px; margin: 0;">
<h3>Workflow</h3>
</div>

<div class="r-stack">
    <p class="fragment fade-in-then-out" data-fragment-index="1">
        <img src="img/phis_workflow_0.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="2">
        <img src="img/phis_workflow_1.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="3">
        <img src="img/phis_workflow_select.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="4">
        <img src="img/phis_workflow_2.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-semi-out" data-fragment-index="5">
        <img src="img/phis_workflow_3.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in" data-fragment-index="6">
        <img src="img/happy_harold_paintbrush.png" style="height: 300px; object-fit: contain; width: 100%;">
    </p>
</div>
<div class="r-stack">
    <p class="fragment fade-in-then-out" data-fragment-index="1">
        Editing a single feature $\phi_i$: spoon distance
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="2">
        Visualize robot's current feature network $\phi_i$ for all states
        </br>
        (orange = high value, purple = low value)
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="3">
        User selects annotation tool
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="4">
        User makes annotations $A$
    </p>
    <p class="fragment fade-in-then-out" data-fragment-index="5">
    	Algorithm $f(\phi_i, A)$ updates previous feature network $\phi_i$ to $\phi_i'$ according to annotations
    </p>
    <!-- <p class="fragment fade-in-then-out" data-fragment-index="6">
       hello 
    </p> -->
</div>



## Interface
<img src="img/phis_workflow_2.png" style="height: 400px; object-fit: contain; width: 100%;">
<!-- 
* Direct manipulation
<small style="font-size: 0.45em; color: #666;width:400px">
Hutchins, E. L., Hollan, J. D., & Norman, D. A. (1986). Direct manipulation interfaces. In User centered system design (pp. 87-124). CRC Press.
</small>

* Interpretability interfaces
<small style="font-size: 0.45em; color: #666;width:400px">
Boggust, A., Bang, H., Strobelt, H., & Satyanarayan, A. (2025, April). Abstraction alignment: comparing model-learned and human-encoded conceptual relationships. In Proceedings of the 2025 CHI Conference on Human Factors in Computing Systems (pp. 1-20).
</small> -->
<!-- * End-user programming -->



## Interface: tools
<div style="display: flex; gap: 24px; width: 100%;">
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        Paintbrush
        <img src="img/annotation.png" style="height: 200px; object-fit: contain; width: 100%;">
    </p>
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        Monotonic lines
        <img src="img/ferl.png" style="height: 200px; object-fit: contain; width: 100%;">
        <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
        Bobu, A., Wiggert, M., Tomlin, C., & Dragan, A. D. (2022). Inducing structure in reward learning by learning features. The International Journal of Robotics Research, 41(5), 497-518.
        </small>
    </p>
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        Language (chat)
        <img src="img/flex.png" style="height: 200px; object-fit: contain; width: 100%;">
        <small style="display: block; margin-top: 0.75em; font-size: 0.45em; color: #666;">
        Lee, A., Dennler, N., Sucholutsky, I., & Bobu, A. (2026). Flexible Language-Guided Representation Editing for Adaptive Robot Behavior. arXiv preprint arXiv:2610.28893.
        </small>
    </p>
</div>



## Interface: evaluation
<img src="img/phitoshop_interface.png" style="height: 250px; object-fit: contain; width: 100%;">

<!-- direct manipulation
interpretability interfaces -->
* NASA TLX: task load index
<small style="font-size: 0.45em; color: #666; width:400px">
Hart, S. G., & Staveland, L. E. (1988). Development of NASA-TLX (Task Load Index): Results of empirical and theoretical research. In Advances in psychology (Vol. 52, pp. 139-183). North-holland.
</small>

* Clicks, keystrokes, time taken
* Perceived control and usefulness
<!-- * task success: scored against task-specific rubric -->



<!-- .slide: data-auto-animate -->
## Algorithm
<img src="img/phitoshop_algo.png" style="height: 400px;">



<!-- .slide: data-auto-animate -->
## Algorithm: evaluation
<img src="img/phitoshop_algo.png" style="height: 240px">

* Reaction: annotations move feature towards ground truth values
* Isolation: annotations do not affect irrelevant dimensions of state
* Efficiency: update duration



## Tasks
<div style="display: flex; gap: 24px; width: 100%;">
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        2D navigation
        <img src="img/gridrobot.png" style="height: 200px; object-fit: contain; width: 100%;">
        <small style="font-size: 0.45em; color: #666;">
        Bobu, A., Liu, Y., Shah, R., Brown, D. S., & Dragan, A. D. (2023, March). Sirl: Similarity-based implicit representation learning. In Proceedings of the 2023 ACM/IEEE International Conference on Human-Robot Interaction (pp. 565-574).
        </small>
    </p>
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        Vehicle parking
        <img src="img/vehicleparking.png" style="height: 200px; object-fit: contain; width: 100%;">
        <small style="font-size: 0.45em; color: #666;">
        Srivastava, M., Goodman, N., & Sadigh, D. (2023, July). Generating language corrections for teaching physical control tasks. In International Conference on Machine Learning (pp. 32561-32574). PMLR.
        </small>
    </p>
    <p class="fragment fade-in-then-semi-out" style="flex: 1; min-width: 0;">
        Swimmer (stretch)
        <img src="img/swimmer.png" style="height: 200px; object-fit: contain; width: 100%;">
        <small style="font-size: 0.45em; color: #666;">
        Zhang, D., Carroll, M., Bobu, A., & Dragan, A. (2022). Time-efficient reward learning via visually assisted cluster ranking. arXiv preprint arXiv:2212.00169.
        </small>
    </p>
</div>



<div style="display: flex; gap: 24px; width: 100%;">
    <div style="flex: 1; min-width: 0;">
    <h3>We want to specify <span style="color: green;">features $\phi(s)$</span></h3>
    <img src="img/personalrobot_features_3.png" style="height: auto; max-width: 100%; max-height: 100%; margin: 0;">
    </div>
    <div style="flex: 1; min-width: 0;display: flex; flex-direction: column; justify-content: center;">
        <div style="height: 100px; margin-bottom: 24px; display: flex; align-items: center; justify-content: center;">
        <strong> Existing methods</strong>
        </div>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="1">tedious</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="3">expensive</p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="5">ambiguous</p>
        <!-- <p class="fragment fade-in-then-semi-out" data-fragment-index="4">uninterpretable</p> -->
    </div>
    <div style="flex: 1; min-width: 0;display: flex; flex-direction: column; justify-content: center;">
    <div style="height: 100px; margin-bottom: 24px;">
        <img src="img/phitoshop_logo.png" style="height: 100%; object-fit: contain; width: 100%;">
        </div>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="2">
        intuitive
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="4">
        efficient
        </p>
        <p class="fragment fade-in-then-semi-out" data-fragment-index="6">
        precise
        </p>
        <!-- <p class="fragment fade-in-then-semi-out" data-fragment-index="4">
        interpretable by design
        </p> -->
    </div>
</div>



<!-- .slide: data-auto-animate -->
Who is the human, in <strong>human</strong>-robot interaction?

<div style="display: flex; gap: 24px; width: 100%; align-items: center;">
    <div class="fragment" data-fragment-index="1" style="flex: 1; min-width: 0;">
        <img src="img/faceplant.png" style="height: 200px;">
    </div>
    <div style="flex: 1; min-width: 0;">
        <img src="img/personalrobot_human.png" style="height: 340px;">
    </div>
    <div class="fragment" data-fragment-index="1" style="flex: 1; min-width: 0;">
        <img src="img/happy_harold_paintbrush.png" style="height: 300px;">
    </div>
</div>



<!-- .slide: data-auto-animate -->
# Thank you!
<div style="display: flex; gap: 4px; width: 100%;">
<!-- <img src="img/phitoshop_logo.png" style="flex: 1; min-width: 0; height: 400px; object-fit: contain; margin: 0;"> -->
    <div style="flex: 1; min-width: 0;">
        <img src="img/happy_harold_paintbrush.png" style="height: 400px;">
    </div>
</div>



# Appendix


<img src="img/timeline.png" style="flex: 1; min-width: 0; height: 400px; object-fit: contain; margin: 0;">


<img src="img/phitoshop_1.png" style="flex: 1; min-width: 0; height: 400px; object-fit: contain; margin: 0;">


<img src="img/phitoshop_2.png" style="flex: 1; min-width: 0; height: 400px; object-fit: contain; margin: 0;">