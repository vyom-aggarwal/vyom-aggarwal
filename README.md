<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=230&color=0:0d1117,30:1f6feb,65:7c3aed,100:0d1117&text=VYOM%20AGGARWAL&fontSize=56&fontColor=ffffff&fontAlignY=33&desc=robotics%20%C2%B7%20machine%20learning%20%C2%B7%20the%20mathematics%20underneath&descSize=15&descAlignY=53&animation=fadeIn" width="100%" alt="Vyom Aggarwal" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=21&duration=2600&pause=850&color=58A6FF&center=true&vCenter=true&repeat=true&width=900&height=45&lines=DS/ML+Research+@+MIT,+UCSC;Sophomore+at+RIHS;Robotics+·+Machine+Learning+·+Math+·+Aerospace+·+Engineering)](https://vyom-aggarwal.github.io/)

<br>

[![Portfolio](https://img.shields.io/badge/PORTFOLIO-vyom--aggarwal.github.io-58A6FF?style=for-the-badge&logo=googlechrome&logoColor=58A6FF&labelColor=0D1117)](https://vyom-aggarwal.github.io/)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-Vyom%20Aggarwal-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0D1117)](https://www.linkedin.com/in/vyom-aggarwal-681764313/)
[![Email](https://img.shields.io/badge/EMAIL-aggarw.vyom%40gmail.com-7C3AED?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0D1117)](mailto:aggarw.vyom@gmail.com)

![Followers](https://img.shields.io/github/followers/vyom-aggarwal?style=for-the-badge&logo=github&label=FOLLOWERS&labelColor=0D1117&color=1F6FEB)
![Profile Views](https://komarev.com/ghpvc/?username=vyom-aggarwal&style=for-the-badge&label=PROFILE+VIEWS&color=7C3AED)

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1f6feb,50:7c3aed,100:1f6feb&height=2&section=header" width="100%" alt="" />

</div>

## ▸ 01 — About me

I'm a sophomore at **River Islands High School**, dual-enrolled at **San Joaquin Delta College**. I specialize in the **integration of AI and machine learning into engineering disciplines — mechatronics and aerospace in particular** — along with the mathematics, simulation, and control that has to hold underneath for that integration to mean anything.

I like problems that stay interesting after the first correct answer: **Is this number real, or is my instrument lying to me? Which assumption breaks first? What does the system do the moment it does?** That's why I work where ML meets hardware. A model that scores well on a benchmark and a model you would trust to run a physical system are not the same object, and the distance between them is where the engineering actually lives.

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1f6feb,50:7c3aed,100:1f6feb&height=2&section=header" width="100%" alt="" />

## ▸ 02 — Experience

### Student Researcher — MIT CSAIL
Member of the Computer Science and Artificial Intelligence Laboratory, assisting the development of a system that changes the way data can be visualized. The interesting part of the problem sits underneath the interface: what a system has to compute, and how it has to represent what it knows, before a person can look at the result and see something they couldn't see before.

### Student Researcher — UC Santa Cruz
Machine learning applications in robotics, and what it actually takes to move them into the real world. My current project asks whether a quadruped can recover its gait after an actuator or sensor fault by learning a small correction online — without retraining the policy underneath. So far the work has been as much about building trustworthy measurement as building the method: the first substantive result was discovering that the recovery criterion was crediting recoveries that never happened.

### Research Fellow — Lumiere Education
Conducting an independent research project under the mentorship of Fernanda-Maria Lugo-Bolanos of Brown University. I was accepted into the program with a merit-based scholarship for a revolutionary research idea proposal video. In this project, I am currently investigating whether a skin lesion classifier trained on the ISIC dataset relies genuinely on actual lesion features or inadvertently keys off confounding artifacts like surgical ink marks, rulers, and hair.

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1f6feb,50:7c3aed,100:1f6feb&height=2&section=header" width="100%" alt="" />

## ▸ 03 — Active research

<div align="center">

### `Fault Recovery in RL Locomotion Through Online Residual Adaptation`
**UC Santa Cruz · AIEA Lab**

*Can a small correction module, updated* ***during*** *execution, restore a quadruped's gait after a hardware fault — without retraining the policy underneath?*

</div>

### The loop

```mermaid
flowchart LR
    OBS["observation<br/><b>34-dim</b>"] --> PI["π_base<br/>PPO · <b>frozen</b><br/>5 seeds · gait-gated"]
    OBS --> RES["residual Δa<br/><i>updated online</i>"]
    PI --> SUM(("+"))
    RES -.-> SUM
    SUM --> ACT["action<br/><b>12-dim</b> · 60 Hz"]
    ACT --> ENV["PyBullet quadruped<br/>12 joints · 240 Hz physics"]
    ENV --> OBS
    FAULT["⚠ fault injected<br/>@ step 200"] --> ENV

    classDef core fill:#1f6feb,stroke:#58a6ff,stroke-width:1px,color:#ffffff
    classDef wip fill:#7c3aed,stroke:#a78bfa,stroke-width:1px,color:#ffffff,stroke-dasharray:4 3
    classDef env fill:#0f766e,stroke:#2dd4bf,stroke-width:1px,color:#ffffff
    classDef bad fill:#b91c1c,stroke:#f87171,stroke-width:1px,color:#ffffff
    class OBS,PI,ACT,SUM core
    class RES wip
    class ENV env
    class FAULT bad
```

The seized joint **stays seized.** The residual redistributes the gait around it:

$$a_t \;=\; \underbrace{\pi_{\text{base}}(o_t)}_{\text{frozen}} \;+\; \underbrace{\Delta_\theta(o_t)}_{\text{online}}, \qquad \theta \leftarrow \theta - \eta\,\nabla_\theta \mathcal{L}\big(\tau_{t-k:t}\big)$$

Measured against two bounds — **no adaptation** (Baseline A) and **full retraining** (Baseline B).

<div align="center">

[![Repo](https://img.shields.io/badge/REPOSITORY-fault--recovery--quadruped--rl-1F6FEB?style=for-the-badge&logo=github&logoColor=white&labelColor=0D1117&color=1F6FEB)](https://github.com/vyom-aggarwal/fault-recovery-quadruped-rl)

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1f6feb,50:7c3aed,100:1f6feb&height=2&section=header" width="100%" alt="" />

## ▸ 04 — Toolchain

<table>
<tr><td><b>Languages</b></td><td>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

</td></tr>
<tr><td><b>ML & research</b></td><td>

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![PyBullet](https://img.shields.io/badge/PyBullet-0F766E?style=flat-square&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Reinforcement Learning](https://img.shields.io/badge/PPO%20%C2%B7%20Reinforcement%20Learning-7C3AED?style=flat-square)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

</td></tr>
<tr><td><b>Web & systems</b></td><td>

![WebGL](https://img.shields.io/badge/WebGL-990000?style=flat-square&logo=webgl&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?style=flat-square&logo=githubpages&logoColor=white)

</td></tr>
<tr><td><b>Mechatronics & CAD</b></td><td>

![FTC](https://img.shields.io/badge/FIRST%20Tech%20Challenge-F57F17?style=flat-square)
![VEX](https://img.shields.io/badge/VEX%20V5-B71C1C?style=flat-square)
![CAD](https://img.shields.io/badge/CAD%20%C2%B7%20mechanical%20design-455A64?style=flat-square)
![Control](https://img.shields.io/badge/control%20systems-1F6FEB?style=flat-square)
![Simulation](https://img.shields.io/badge/physics%20simulation-0F766E?style=flat-square)

</td></tr>
<tr><td><b>Writing</b></td><td>

![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=flat-square&logo=latex&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat-square&logo=markdown&logoColor=white)

</td></tr>
</table>

<img src="https://capsule-render.vercel.app/api?type=rect&color=0:1f6feb,50:7c3aed,100:1f6feb&height=2&section=header" width="100%" alt="" />


## Let's build something.

Open to **research collaborations** and **AI/ML internships**.

[![Email](https://img.shields.io/badge/aggarw.vyom%40gmail.com-7C3AED?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0D1117)](mailto:aggarw.vyom@gmail.com)
[![Portfolio](https://img.shields.io/badge/vyom--aggarwal.github.io-58A6FF?style=for-the-badge&logo=googlechrome&logoColor=white&labelColor=0D1117)](https://vyom-aggarwal.github.io/)
[![LinkedIn](https://img.shields.io/badge/in%2Fvyom--aggarwal-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0D1117)](https://www.linkedin.com/in/vyom-aggarwal-681764313/)

`robotics` · `machine learning` · `mathematics` · `research` · `CAD`

<br>

***"Anyone can make it work once. Engineering is knowing which assumption breaks first — and what the system does the moment it does."***

<img src="https://capsule-render.vercel.app/api?type=waving&height=140&section=footer&color=0:0d1117,30:7c3aed,70:1f6feb,100:0d1117" width="100%" alt="" />

</div>
