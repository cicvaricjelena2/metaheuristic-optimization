# Metaheuristic Optimization Algorithms

This project explores and compares three stochastic metaheuristic optimization algorithms for solving a continuous optimization problem:

* Simulated Annealing (SA)
* Genetic Algorithm (GA)
* Particle Swarm Optimization (PSO)

The objective is to find the global minimum of a three-dimensional objective function using different optimization strategies and compare their performance through repeated independent experiments.

Optimization Problem

The objective function is defined as:

[
f(x) = \frac{4}{3}(x_1^2+x_2^2-x_1x_2)^{1.5}+|x_3|
]

subject to:

[
x_1,x_2,x_3 \in [-1,1]
]

The theoretical global minimum is:

[
f^=0,\qquad x^=[0,0,0]
]

The algorithms attempt to discover this solution through stochastic search, without using the analytical solution during optimization.

Algorithms

1. Simulated Annealing (SA)

A single-solution optimization algorithm inspired by the physical annealing process.

Implementation includes:

* Random initialization within the search domain.
* Gaussian perturbations for generating neighboring solutions.
* Metropolis acceptance criterion.
* Geometric cooling schedule.
* Tracking of the best solution found.

Main parameters:

* Initial temperature: 1.0
* Cooling factor: 0.995
* Minimum temperature: (10^{-5})
* Perturbation standard deviation: 0.1

2. Genetic Algorithm (GA)

A population-based optimization algorithm inspired by biological evolution.

Implementation includes:

* Real-valued chromosome representation.
* Population initialization.
* Tournament selection (k = 3).
* Uniform crossover.
* Gaussian mutation.
* Elitism to preserve the best individual.

Main parameters:

* Population size: 100
* Number of generations: 300
* Mutation probability: 0.1
* Mutation standard deviation: 0.05

3. Particle Swarm Optimization (PSO)

A population-based optimization algorithm inspired by collective behavior in nature.

Each particle represents a candidate solution and updates its position based on its individual best position and the global best position found by the swarm.

Main parameters:

* Number of particles: 30
* Number of iterations: 200
* Inertia weight: 0.7
* Cognitive coefficient: 1.5
* Social coefficient: 1.5

Experimental Evaluation

Since all three algorithms are stochastic, each was evaluated through 20 independent runs with different random seeds.

The following metrics were used:

* Mean best objective function value.
* Standard deviation across independent runs.
* Convergence behavior.
* Number of objective function evaluations.
* Sensitivity to algorithm parameters.

Results

The reported experimental results are summarized below:

Algorithm	Mean Best Objective Value	Standard Deviation
Simulated Annealing	0.004276	0.00285
Genetic Algorithm	0.000024	0.000025
Particle Swarm Optimization	(1.05 \times 10^{-13})	(1.34 \times 10^{-13})

Comparison and Observations

* Simulated Annealing successfully approaches the global minimum but exhibits greater variability across independent runs.
* Genetic Algorithm achieves better average results and more consistent convergence than Simulated Annealing.
* Particle Swarm Optimization achieves the smallest average objective function value and the lowest variability in this experiment.

The reported results indicate that PSO performed best for the selected objective function and experimental parameters.

Technologies

* Python
* NumPy
* Matplotlib
* Jupyter Notebook

Repository Structure

metaheuristic-optimization/
│
├── metaheuristic_optimization.ipynb
├── requirements.txt
├── .gitignore
└── README.md

How to Run

Clone the repository:

git clone https://github.com/cicvaricjelena2/metaheuristic-optimization.git

Install dependencies:

pip install -r requirements.txt

Launch Jupyter Notebook:

jupyter notebook

Open metaheuristic_optimization.ipynb and run the cells.

Conclusion

This project demonstrates the implementation and comparative evaluation of three metaheuristic optimization techniques.

The experiments highlight the differences between single-solution and population-based search strategies, as well as the importance of parameter selection, convergence analysis, and repeated stochastic experiments.
