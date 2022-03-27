# TrajectoryLearning

<p align="center">
<img src="https://i.natgeofe.com/k/88de42b8-764c-40d2-89ee-e72d55dc95b8/emperor-penguin-chicks_4x3.jpg" width="700" height="500">
</p>

### Changes to improve accuracy in Orbit learning:

1. first decrease the meash grid, as they are not so necessary ($m = 5$ works fine)
2. create vector field around the teacher trajectory with some $radius$
3. join (1) and (2); i.e vector field of both mesh grid and extra points around the trajectory.
4. decrease the influence of mesh grid poiints as they are not so important, they are required to give initial trasients to show direction towards the real orbit; so while joining (1) and (2) multiply vector field of (1) by mesh-influence factor ($\texttt{mesh_inf}$)
5. train it and while testing; add a $\texttt{point-momentum}$ factor while updating the new point  

6. $\underline{\textbf{Best parameters found:}}$ (weights) momentum = 0.9999, $(\eta)eta = 0.0000001$, b1 = 0.01, b2 = 0.01, $\texttt{b_out}$ = 0.01, L1 and L2 = 20, epochs = 40000, $radius = 0.2$, $\texttt{mesh_inf} = 0.8$, $\texttt{point-momentum} = 0.01$
