---
title: "비전공자를 위한 Transmon Qubit 회로의 이해"
categories: Qiskit Metal
tags:
  - Quantum Computing
  - Qiskit
  - Qiskit-Metal
  - Lecture
use_math: true
last_modified_at: 2022-02-07T09:32:00+09:00
toc: true 
toc_label: "Table of Contents"
toc_icon: "cog" 
toc_sticky: true 
author_profile: true
comments: true
---

2022 Qiskit Hackathon Korea의 Qiskit Metal Challenge에 더 많은 사람들이 도전할 수 있도록 진입장벽을 낮추자는 목표에서 간단하게 강의를 준비했습니다.
이 강의에서는 축전기, 인덕터 등의 회로요소에서 시작해 Josephson Junction, Transmon Qubit, Coplanar waveguide, transmon resonator coupling까지 내용을 최대한 간단하게 정리하였습니다. 
비전공자를 대상으로 하기 때문에, 연산자와 양자화 등을 활용하는 것을 지양하여 최대한 단순하게 설명하는 것을 목표로 했고, 심화된 내용을 위해서는 레퍼런스 참고를 부탁드립니다. 
오류가 있다면 지적 부탁드리고, 질문이 있다면 Qiskit Slack을 활용해 "Gyeonghun Kim"에게 dm 주세요!

또한 2022 Qiskit Hackathon Korea 사전행사로 기획된 AiQyAm과 함께한 Qiskit Metal Study에서 제가 발표한 내용인 "Using QComponent for Parametric Design"의 영상을 보시고 Jupyter notebook을 다운받아서 실행해 보시면 도움이 될 거 같습니다.    
<https://github.com/GyeonghunKim/2022-Feb-Qiskit-Metal-Study>


[강의 자료](https://github.com/GyeonghunKim/gyeonghunkim.github.io/blob/0e4f42108047cb5982a615d6c6db3eef794b3c29/files/%EB%A9%94%ED%83%88%20%EA%B0%95%EC%9D%98%EB%85%B8%ED%8A%B8%203.pdf)     

강의 영상
### 0. 강의 목표 / 회로요소와 물리량
<iframe width="560" height="315" src="https://www.youtube.com/embed/Nss_3gYFcAY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. 축전기와 전기용량
<iframe width="560" height="315" src="https://www.youtube.com/embed/8mBjmanSt1A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 2. Maxwell Capacitance Matrix
<iframe width="560" height="315" src="https://www.youtube.com/embed/PtuHK5d_JBg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 3. 인덕터와 유도계수
<iframe width="560" height="315" src="https://www.youtube.com/embed/DHvz5Z8ohtI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 4. Josephson Junction
<iframe width="560" height="315" src="https://www.youtube.com/embed/rtHe1_Kr96E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 5. LC 회로와 단순조화진동
<iframe width="560" height="315" src="https://www.youtube.com/embed/RxGU61K-Ut0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 6. Josephson Junction이 포함된 회로
<iframe width="560" height="315" src="https://www.youtube.com/embed/qsNIr9381Zs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 7. 양자조화진동자(QHO)
<iframe width="560" height="315" src="https://www.youtube.com/embed/vCpgktTpATw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 8. Transmon Qubit
<iframe width="560" height="315" src="https://www.youtube.com/embed/st5PZqp_AzA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 9. Coplanar waveguide
<iframe width="560" height="315" src="https://www.youtube.com/embed/oYmtsU-DwFM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 10. Transmon Resonator Coupling
<iframe width="560" height="315" src="https://www.youtube.com/embed/0Y_W8bUeCUc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



References:    
<https://arxiv.org/pdf/1007.3520.pdf>    
<https://arxiv.org/pdf/2106.11352.pdf>   
<https://arxiv.org/pdf/2103.01225.pdf>    
<https://doi.org/10.1103/PhysRevA.76.042319>    
<https://drum.lib.umd.edu/handle/1903/16494>      
<https://repository.tudelft.nl/islandora/object/uuid%3A2ef95a55-b248-44a2-8aa5-8ae33fa604a0>    
<https://doi.org/10.1103/PhysRevA.76.042319>    
<https://arxiv.org/abs/1804.10648>   
<https://doi.org/10.1063/1.5089550>    
<https://qiskit.org/textbook/ch-quantum-hardware/transmon-physics.html>
