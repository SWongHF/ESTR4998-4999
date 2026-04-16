# ESTR4998/4999 Graduation Thesis I/II

Recent works have identified some main features driving the unstable convergence behavior 
at the Edge-of-Stability (EoS) in modern machine learning; however, the precise
dynamics of this phenomenon in fundamental classification settings are still largely
unexplored.

In this thesis project, we aim to generalize the recent findings on large-stepsize optimization
on logistic loss to the multiclass setting. We analyze and characterize the optimization
dynamics of gradient descent (GD) with a large constant stepsize applied to multinomial
logistic regression, challenging the traditional “stable descent” wisdom in classical GD
theory.

The first part, associated with ESTR4998, builds upon three complementary lines of research.
We study the dynamics of GD on multinomial logistic regression with separable data.

First, the recent work of Tyurin (2025) revealed the fundamental connection between
large-stepsize GD and perceptron algorithms, showing that as $\eta \to \infty$, binary logistic
regression with GD reduces to a batch version of the perceptron algorithm. This connection 
explains the empirical success of large-stepsize training and provides geometric
intuition for the optimization dynamics.

Second, the seminal analysis of Wu et al. (2024) provided the first complete characterization 
of large-stepsize GD dynamics for binary logistic regression on separable data,
establishing that:

- In the EoS phase, GD initially induces a non-monotonic loss. However, the averaged
- loss decreases at rate $\tilde{O}((1 + \eta^2)/(\eta t))$ during the EoS phase;
- During the phase transition, the loss decreases monotonically after $O(\eta)$ steps;
- After the transition, GD enters the stable phase, the loss decreases monotonically
  at an $\tilde{O}(1/(\eta t))$ rate after given $t$ extra iterations.

Thirdly, two cornerstone papers by Soudry et al. (2018) and Lyu and Li (2019) also show that
gradient descent naturally drives homogeneous neural networks toward large-margin
solutions for small enough stepsizes. We justify for our setup and show that the max-margin 
bias is an inherent property of GD across the entire stepsize spectrum.

The second part, associated with ESTR4999, studies two important settings: 
large‑stepsize federated learning under heterogeneous devices and *separable* data, 
and the dynamics of gradient descent on *non‑separable* multinomial logistic regression.

First, we extend the large‑stepsize GD analysis to the distributed setting, studying the eminent 
${\tt FedAvg}$ algorithm under *heterogeneous* client updates and separable multinomial logistic 
regression. As a counterpart of the analysis by Crawshaw et al. (2025), we develop a new proof 
technique that relates the loss geometry to client drift and shows that ${\tt FedAvg}$ is stable 
for any constant local and global stepsizes. Similar to the centralized case, ${\tt FedAvg}$ 
enters a stable regime after an initial edge‑of‑stability (EoS) phase, where the loss then 
decreases monotonically at a rate of $O(1/(RT_{\text {avg}}))$ with $R$ communication rounds 
and $T_{\text {avg}}$ the sample‑weighted average number of local steps. 
Notably, the effect of device heterogeneity vanishes asymptotically, so convergence is governed 
primarily by the average local computation. Our analysis provides the first non‑asymptotic bounds 
for large‑stepsize ${\tt FedAvg}$ in separable multiclass problems, establishing that the stable‑phase 
behavior extends naturally to the distributed setting. Surprisingly, our results also imply that 
${\tt FedAvg}$ converges asymptotically to the unbiased optimal solution, challenging the conventional 
wisdom that heterogeneity inevitably leads to bias in federated optimization.

Second, we analyze GD with large stepsizes on multinomial logistic regression for *non‑separable* data 
under an *adaptive stepsize schedule*. For strictly non‑separable datasets, we prove that the schedule 
$\eta t\leq \gamma/(K\mathcal{L}(\mathbf{W}^{(t)}))$ (with $\gamma \in (0,1]$) guarantees monotonic 
convergence to a finite global minimizer at a rate of $\tilde{O}(1/t)$, without requiring prior 
knowledge of the global smoothness constant.

Thirdly, for constant stepsizes on *non‑separable* data, we show that the two‑class multinomial logistic 
regression reduces exactly to binary logistic regression, allowing us to import recent results by Meng et al. (2024) on 
cyclic behavior: convergence below $\eta=1/\lambda$ (where $\lambda$ is the largest Hessian eigenvalue at 
the minimizer) and existence of stable cycles for stepsizes $\eta=\gamma/\lambda$ with $\gamma\in(0,2]$ 
in one, two, and arbitrarily many dimensions via a stacking construction. For $K\geq 3$, we formulate 
the conjecture that cycles exist generally and provide a constructive partial answer via orthogonal 
decoupling of classes: by placing each class on disjoint coordinates, we produce $K$-class datasets 
on which GD with constant stepsize converges to stable cycles for any $\gamma\in(1,2]$. Numerical 
experiments validate the construction for $K$ up to 50. Together, these results delineate the 
contrasting dynamics of adaptive and constant stepsizes in non‑separable multiclass problems and 
identify open questions for the fully coupled setting.
