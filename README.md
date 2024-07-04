# Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System
Neural Network-Based Prescribed-Time Formation Control of Caputo Fractional Order Multi-Agent Systems 

(codes will soon be uploaded) 

A neural network model is integrated with gradient descent as an optimization method to learn to determine a positive definite matrix $\bar{P}$, such that the inequality

$_{t_0}^C D_t^\gamma(\phi_{\sigma(t)}^{-k_3}(t)H(t)) \leq -q_1 (\phi_{\sigma(t)}^{-k_3}(t)H(t))$

holds within the time interval $t \in [t_0, \thinspace t_p)$. 

It computes out the Lyapunov function through matrix multiplications of each time step ($H(t) = \bar{\xi}^T(t) \bar{P} \bar{\xi}(t)$) at every forward propagation stage, and then updates its model weight through gradient descent at the corresponding back propagation stage, i.e., $w_{t+1} \leftarrow w_{t} - lr \cdot \mathcal{L}$. In this simulation, the model's learning rate $lr$ is set to 0.001, and the loss function $\mathcal{L}$ is defined as 

$\mathcal{L} \hspace{2pt} = \hspace{2pt} max(0,H(t)) + max((0,-min(eig(\bar{P}))) + \hspace{2pt} max(0,-R(t))$

as we want the Lyapunov function $H(t)$ to reach 0 for system stability with a positive definite Lyapunov matrix $\bar{P}$. We also want the residual function $R(t)$ to be positive so that the inequality holds.


Desired Final Positions for the Agents (0 the leader and 1234 the followers)
-
![PTSdesired](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/907a545d-ac9e-47aa-97aa-d508053f8fb5)


Random Initial States
-
![PTSis](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/1b4d091d-afbe-4e01-ac4b-b34b48bc833c)


Numerical Simulation Result (3D Plot)
-
![PTS](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/ccb59a27-3fea-4c8d-b637-0ce9eb2aa958)


Numerical Simulation Result (2D Plots)
-
![PTSxx](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/5f72e606-be8e-4402-8bf3-f9bf334a4310)
-
![PTSyy](https://github.com/Ekeulseuji/Neural-Network-Based-Prescribed-Time-Formation-Control-of-Caputo-Fractional-Order-Multi-Agent-System/assets/105386037/ffa45a73-0d10-49f8-9465-a3ef75276046)
