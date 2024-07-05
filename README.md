# Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System


Neural Network-Based Prescribed-Time Formation Control of Caputo Fractional Order Multi-Agent Systems 


**(codes will soon be uploaded)**

.

A neural network model is integrated with gradient descent as an optimization method to learn to determine a positive definite matrix $\bar{P}$, such that the inequality 

<p align="center">
$_{t_0}^C D_t^\gamma (\phi _{\sigma(t)} ^{-k_3}(t) H(t)) \leq -q_1 (\phi _{\sigma(t)} ^{-k_3}(t) H(t))$ 
</p>

holds within the time interval $t \in [t_0, \thinspace t_p)$.  

.

It computes out the Lyapunov function through matrix multiplications of each time step ($H(t) = \bar{\xi}^T(t) \bar{P} \bar{\xi}(t)$) at every forward propagation stage, and then updates its model weight through gradient descent at the corresponding back propagation stage, i.e., $w_{t+1} \leftarrow w_{t} - lr \cdot \mathcal{L}$. In this simulation, the model's learning rate $lr$ is set to 0.001, and the loss function $\mathcal{L}$ is defined as 

<p align="center">
$\mathcal{L} \hspace{2pt} = \hspace{2pt} max(0,H(t)) + max((0,-min(eig(\bar{P}))) + \hspace{2pt} max(0,-R(t))$
</p>

as we want the Lyapunov function $H(t)$ to reach 0 for system stability with a positive definite Lyapunov matrix $\bar{P}$. We also want the residual function $R(t)$ to be positive so that the inequality holds.

.

.<div align="center">
<h2>Desired Final Positions for the Agents
</div>

<div align=center>
<img src="https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/907a545d-ac9e-47aa-97aa-d508053f8fb5" width="450" height="182" />
</div>

<p align="center">
The leader is labelled as 0; And the followers are labelled as 1, 2, 3, 4.
</p>
.

.<div align="center">
<h2>Random Initial States ($t=t_{init}$) and the Final Controlled States ($t=t_p$)
</div>

<div align=center>
<img src="https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/4d0d6fc4-88b3-4407-90b3-358b67f805af" width="490" height="270" />
<img src="https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/98732869-d8ad-49b5-93b5-366a6982f881" width="440" height="275" />
</div>

.




.<div align="center">
<h2>Numerical Simulation Result (3D Plot)
</div>
  
.

As time progresses, the followers (colored) will move closer towards the leader (black) from random starting points and together form the desired topological structure as shown in the first figure at time $t=t_p=3.78$. 

The 3-Dimensional plot adds variable $time \hspace{3pt} step = \frac{t}{h}$ on the z-axis to demonstrate the effect of formation control over time.

.<div align=center>
![PTS](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/ccb59a27-3fea-4c8d-b637-0ce9eb2aa958)
</div>


.

<div align=center>
<h2>Numerical Simulation Result (2D Plots)
</div>

.

The 2-Dimensional plots intuitively demonstrates how formation control affects the positional dynamics of the agents in the x and y axes. During the starting time period, the behavior of each agent can be seen as unordered, as they are each set at random starting points and possess different initial velocities as described in the table above. As time step increases, the followers will gradually be controlled to maintain a pre-determined distance $p_{di}$ from the leader. The leading agent's x- and y-axis positions were shown in black dashes as a reference.

.<div align=center>
<img src="https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/5f72e606-be8e-4402-8bf3-f9bf334a4310" width="400" height="310" />
<img src="https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/ffa45a73-0d10-49f8-9465-a3ef75276046" width="400" height="310" />
</div>


.

<div align=center>
<h2>$H(t)$, $R(t)$, and $\|\hat{\xi}(t)\|$ Values Over Time 
</div>

.

$\|\| \hat{\xi}(t) \|\|$ quantifies all followers' position differences and velocity differences between the desired ones. i.e., $\|\| \hat{\xi}(t) \|\| = \sqrt{\sum ((p_0(t)-p_i(t)-p_{di}(t))+(v_0(t)-v_i(t)))}$. Its trend over time, along with $H(t)$ and $R(t)$ values, are all illustrated. A dashed magenta line representing $(\|\|\hat{\xi}(t)\|\|)^2$ is plotted only to see a clearer trend of $\|\hat{\xi}(t)\|$ over time, because the calculation result of $\|\| \hat{\xi}(t) \|\|$ is relatively small as the agents' initial states are set small.

$H(t)$ and $\|\|\hat{\xi}(t)\|\|$ values approached 0 from positive y-direction, signifying that the system is indeed converging towards its equilibrium state. Throughout the simulation, the function $H(t)$ keeps being positive definite while its derivative $\frac{\mathit{d}}{\mathit{d}t}H(t)\leq0$ as shown in the figure. Therefore, it can be concluded that the controlled multi-agent system's equilibrium state is asymptotically stable and it will tend towards a stable state without diverging as time increases. $H(t)$ is a valid Lyapunov function for the system.

Starting from time $t_0 = 0.03$, all three conditions: the Lyapunov function $H(t) > 0$, the residual function $R(t) \hspace{-3pt} \geq \hspace{-3pt} 0$, and the eigenvalue of the Lyapunove matrix $min(eig(\bar{P})) \hspace{-3pt} > \hspace{-3pt} 0$ are all satisfied, corroborating the aforementioned inequality.

Residual function $R(t)$ (defined as Equation 16 in the paper): $R(t) = \phi^{-k_{3}} _ {\sigma(t)}(t) { _ {t_{0}}^C}D_{t}^{\gamma}{H}(t)-k_{3}\phi^{-k_{3}-1} _ {\sigma(t)}(t) \dot{\phi} _ {\sigma(t)}(t)H(t) -{ _ {t_{0}}^C}D_{t}^{\gamma}(\phi^{-k_{3}}_{\sigma(t)}(t){H}(t))$.

.<div align=center>
![PTShrxx](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/1d47fa18-8097-4e4e-a450-e497ee38769e)
<h3>Final values: $H(t_p)=0.005812$, $R(t_p)=130.8578$, and $\|\hat{\xi}(t_p)\|=0.099575$. 
</div>




