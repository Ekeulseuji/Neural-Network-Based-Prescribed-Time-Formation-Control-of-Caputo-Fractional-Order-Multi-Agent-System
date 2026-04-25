# Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System


Neural Network-Based Prescribed-Time Formation Control of Caputo Fractional Order Multi-Agent Systems 




A neural network model is integrated with gradient descent optimization to learn two positive definite matrices, $M_1$ and $M_2$, such that the following inequality is satisfied: 

<p align="center">
$_{t_0}^C D_t^q \big(\phi _{\sigma(t)} ^{-k_3}(t) H(t)\big) \leq -\varphi \big(\phi _{\sigma(t)} ^{-k_3}(t) H(t)\big)$ 
</p>

for all $t \in [t_0, \thinspace t_p)$. Satisfying this inequality guarantees the asymptotic stability of the Caputo fractional-order multi-agent system.



It computes out the Lyapunov function through matrix multiplications of each time step at every forward propagation stage, and then updates its model weight through gradient descent at the corresponding back propagation stage, i.e., $w_{t+1} \leftarrow w_{t} - lr \cdot \mathcal{L}$. In this simulation, the model's learning rate $lr$ is set to 0.005, and the loss function $\mathcal{L}$ is characterized by: 

<p align="center">
$\mathcal{L} \hspace{2pt} = \hspace{2pt} max\big(0,-\varphi H(t)\big) + \max\Big(0, \, _{t_0} \hspace{-1pt} I_t^{1-q}\hspace{-1pt}\left(-W(t)\right) - \, {_{t_{0}}^C}\hspace{-1pt}D_{t}^{q}\hspace{-1pt}\left((\phi_{1}(t))^{-k_{3}} {H}(t)\right) \hspace{-1pt}\Big) + \max\big(0, \, -\min(eig(M_1))\big) + \max\big(0, \, -\min(eig(M_2))\big)$
</p>

as we are trying to find the valid Lyapunov-like function $H(t) = \bar{X}^T M_1 \, \bar{X}$ and the valid auxiliary function $W(t) = \bar{X}^T M_2 \, \bar{X}$ at the same time to satisfy stability conditions (10) and (11).



  

<div align="center">
<h2>Desired Final Positions for the Agents
</div>

  
<div align=center>
<img src="https://github.com/user-attachments/assets/0cda892b-a6b4-41a2-9952-c06b454323e5" width="420" height="220" />
</div>

<p align="center">
The leader (0) and the followers (1, 2, 3, 4).
</p>


  

<div align="center">
<h2>NN-Assisted Stability Analysis Result 
</div>

<div align=center>
<img src="https://github.com/user-attachments/assets/7c0d2e3e-aeaf-4acd-a2bc-b00154c5cebe" width="420" height="340" />
</div>



The results indicate that the Caputo fractional-order multi-UAV system achieves control within the prescribed time interval.



<!---  -->


<div align="center">
<h2>Random Initial States ($t=t_{init}$) and the Final Controlled States ($t=t_p$)
</div>

<div align=center>
<img src="https://github.com/user-attachments/assets/2f07b903-bee2-437b-9383-993376878b72" width="325" height="215" />
<img src="https://github.com/user-attachments/assets/65b6b822-3d35-4db0-86e9-426808269347" width="325" height="215" />
</div>


<!---  -->

<div align="center">
<h2>Random Initial States ($t=t_{init}$) and the Final Controlled States ($t=t_p$) for The Revised Version
</div>

  
<div align=center>
<img src="https://github.com/user-attachments/assets/2f07b903-bee2-437b-9383-993376878b72" width="325" height="215" />
<img src="https://github.com/user-attachments/assets/2bb3823f-7c64-49b9-89ed-6e01979be47d" width="325" height="215" />
</div>



<!---  -->

<div align="center">
<h2>Numerical Simulation Result (3D Plot)
</div>



As time progresses, the followers (colored) will move closer towards the leader (black) from random starting points and together form the desired topological structure as shown in the first figure starting from the time point $t=t_p$. 

The 3-Dimensional plot adds variable $time \hspace{3pt} step = \frac{t}{h}$ on the z-axis to demonstrate the effect of formation control over time.

<!---  -->


<div align=center>
<img src="https://github.com/user-attachments/assets/629b10fe-c496-4b07-908d-c8b9aff7b03e" width="600" height="590" />
</div>




<!---  -->  



<div align=center>
<h2>Numerical Simulation Result (2D Plots)
</div>



The 2-Dimensional plots intuitively demonstrates how formation control affects the positional dynamics of the agents in the x and y axes. During the starting time period, the behavior of each agent can be seen as unordered, as they are each set at random starting points and possess different initial velocities as described in the table above. As time step increases, the followers will gradually be controlled to maintain a pre-determined distance $p_{di}$ from the leader. The leading agent's x- and y-axis positions were shown in black dashes as a reference.

<div align=center>
<img src="https://github.com/user-attachments/assets/33edea05-92ae-4cd5-b282-7e4c39314071" width="530" height="310" />
<img src="https://github.com/user-attachments/assets/c10dfaf0-6a9e-400b-a647-ccb496bbbd25" width="530" height="310" />
</div>


