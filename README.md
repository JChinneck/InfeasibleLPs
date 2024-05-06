# InfeasibleLPs
May 6, 2024.

Two collection of infeasible linear programming models.

## Set 1: Infeasible LPs from Classification Data
John W. Chinneck. 

This is a collection of infeasible linear programming models that are
created from classification datasets, via the transformation described
in these papers:

 - J.W. Chinneck (2001), "Fast Heuristics for the Maximum Feasible 
   Subsystem Problem", INFORMS Journal on Computing, vol. 13, no. 3, 
   pp. 210-223.

 - J.W. Chinneck (2012), "Integrated Classifier Hyperplane Placement 
   and Feature Selection", Expert Systems with Applications, vol. 39, 
   no. 9, pp. 8193-8203.

 - J.W. Chinneck (2009), "Tailoring Classifier Hyperplanes to General 
   Metrics", in J.W. Chinneck, B. Kristjansson, M. Saltzman (eds.) 
   "Operations Research and Cyber-Infrastructure", 
   Springer Science+Media LLC.

As a consequence of how they are constructed, the models have these
characteristics:

  - There is no objective function.

  - All row constraints are inequalities. There are no equality
    constraints.

  - The constraint matrix is fully dense. All row constraints involve
    all variables.

  - Models have either all free variables, or all variables lower-bounded
    at zero. There are numerous pairs of models, one with free variables
    and one with lower-bounded variables.

  - Models typically have numerous Irreducible Infeasible Subsets (IISs) 
    of constraints. Different solvers will likely isolate different IISs.
    Because of the numerous IISs these are good models for testing methods
    for finding maximum feasible subsets (the maxFS problem).

The list of models follows below, with model size data and information on
the IIS isolated by the Gurobi 9.5.1 solver. All files are in MPS format.

**Naming conventions.** All models have an initial "IC" that indicates that it
is an "Infeasible model from Classification data". A trailing "-LB" indicates 
that all variables are lower bounded by zero. The remaining characters give
the name of the classification data set that the model is based on. Note
that any data rows with missing or erroneous data have been removed from the
models prior to conversion.

### MODELS ###

IC-balancescale.mps\
625 rows, 5 columns, 3125 nonzeros\
All variables free\
Gurobi IIS: 6 constraints and 0 bounds

IC-balancescale-LB.mps\
625 rows, 5 columns, 3125 nonzeros\
all variables lower bounded at zero\
Gurobi IIS: 5 constraints and 1 bounds

IC-breast1.mps\
683 rows, 10 columns, 6830 nonzeros\
All variables free\
Gurobi IIS: 11 constraints and zero bounds

IC-breast1-LB.mps\
683 rows, 10 columns, 6830 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 8 constraints and 3 bounds

IC-bupa.mps\
345 rows, 7 columns, 2406 nonzeros\
All variables free\
Gurobi IIS: 8 constraints and 0 bounds

IC-bupa-LB.mps\
345 rows, 7 columns, 2406 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 6 constraints and 2 bounds

IC-crx.mps\
666 rows, 7 columns, 3804 nonzeros\
All variables free\
Gurobi IIS: 8 constraints and 0 bounds

IC-crx-LB.mps\
666 rows, 7 columns, 3804 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 5 constraints and 3 bounds

IC-ionosphere.mps\
351 rows, 35 columns, 10864 nonzeros\
All variables free\
Gurobi IIS: 34 constraints and 0 bounds

IC-ionosphere-LB.mps\
351 rows, 35 columns, 10864 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 16 constraints and 18 bounds

IC-pima-LB.mps\
768 rows, 9 columns, 6149 nonzeros\
All variables free\
Gurobi IIS: 10 constraints and 0 bounds

IC-pima-LB.mps\
768 rows, 9 columns, 6149 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 7 constraints and 3 bounds

IC-satimage.mps\
4435 rows, 38 columns, 168530 nonzeros\
All variables free\
Gurobi IIS: 39 constraints and 0 bounds

IC-satimage-LB.mps\
4435 rows, 38 columns, 168530 nonzeros\
All variables lowered bounded at zero\
Gurobi IIS: 10 constraints and 29 bounds

IC-sick.mps\
2028 rows, 7 columns, 14196 nonzeros\
All variables free\
Gurobi IIS: 8 constraints and 0 bounds

IC-sick-LB.mps\
2028 rows, 7 columns, 14196 nonzeros\
All variables lowered bounded at zero\
Gurobi IIS: 5 constraints and 3 bounds

IC-sonar-LB.mps\
208 rows, 61 columns, 12679 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 26 constraints and 36 bounds

IC-vehicle.mps\
850 rows, 19 columns, 16042 nonzeros\
All variables free\
Gurobi IIS: 20 constraints and 0 bounds

IC-vehicle-LB.mps\
850 rows, 19 columns, 16042 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 8 constraints and 12 bounds

IC-wdbc-LB.mps\
569 rows, 31 columns, 17561 nonzeros\
All variables lowered bounded at zero\
Gurobi IIS: 12 constraints and 20 bounds

IC-wine-LB.mps\
178 rows, 14 columns, 2492 nonzeros\
All variables lower bounded at zero\
Gurobi IIS: 7 constraints and 8 bounds

## Set 2: Infeasible LPs by Converting Netlib LPs

These are based on feasible LPs in the netlib collection at 
https://www.netlib.org/lp/data/index.html that are converted by
(1) finding the minimum of the objective function, (2) constructing
a constraint using the objective function that limits its value
to no more than the optimum, and (3) flipping the sense of the
first loose inequality constraint in the optimum solution.

There are 26 models in this collection. The naming convention is
INF-<netlib model name>.mps.

These files are collected in a single zipped archive named 
INFfromNetlibLPs.7z
