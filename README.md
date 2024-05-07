# InfeasibleLPs
May 7, 2024.

Two collections of infeasible linear programming models.

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

## Set 2: Infeasible LPs Derived from Netlib LPs

These infeasible models are derived from feasible LPs in the netlib collection at 
https://www.netlib.org/lp/data/index.html. They are made infeasible
in two different ways. The naming convention is
INF-(netlib model name).mps or INF2-(netlib model name).mps,
depending on the conversion technique applied. Some models were
converted both ways. There are 37 models in this collection. 

These files are collected in a single zipped archive named 
INFfromNetlibLPs.7z

Statistics on the sizes of the IISs found by Gurobi 9.5.1
follow below:

INF-adlittle: 46 rows, 32 bounds\
INF2-adlittle: 3 rows, 6 bounds\
INF-agg2: 7 rows, 22 bounds\
INF2-agg2: 4 rows, 5 bounds\
INF-agg3: 4 rows, 6 bounds\
INF2-agg3: 4 rows, 5 bounds\
INF-brandy: 152 rows, 85 bounds\
INF2-brandy: 8 rows, 0 bounds\
INF-capri: 190 rows, 98 bounds\
INF-d2q06c: 1737 rows, 3555 bounds\
INF2-d2q06c: 58 rows, 251 bounds\
INF-fffff800: 389 rows, 259 bounds\
INF2-fffff800: 3 rows, 3 bounds\
INF-fit2d: 22 rows, 10479 bounds\
INF2-fit2d: 22 rows, 10476 bounds\
INF-israel: 55 rows, 66 bounds\
INF-lotfi: 91 rows, 178 bounds\
INF2-lotfi: 27 rows, 33 bounds\
INF-osa-14: 783 rows, 51674 bounds\
INF-osa-30: 1518 rows, 98318 bounds\
INF-pilot4: 332 rows, 518 bounds\
INF-pilot-we: 678 rows, 2092 bounds\
INF-sc50a: 36 rows, 3 bounds\
INF-sc105: 7 rows, 1 bound\
INF-sc205: 7 rows, 1 bound\
INF-scfxm1: 20 rows, 22 bounds\
INF2-scfxm1: 13 rows, 16 bounds\
INF-scfxm2: 20 rows, 22 bounds\
INF-scfxm3: 25 rows, 24 bounds\
INF2-scfxm3: 13 rows, 16 bounds\
INF-share1b: 88 rows, 131 bounds\
INF2-share1b: 2 rows, 10 bounds\
INF-ship04l: 316 rows, 3 bounds\
INF-ship08l: 478 rows, 17 bounds\
INF-ship12l: 938 rows, 10 bounds\
INF-stocfor3: 12567 rows, 3129 bounds

