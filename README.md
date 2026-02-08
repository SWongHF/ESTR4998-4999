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
