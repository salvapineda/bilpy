# Bilevel Optimization in PYthon (PSOPY)

This repository includes Python codes to solve linear bilevel problems.

## Installation

```python
git clone https://github.com/salvapineda/bilpy.git

cd psopy
```

## Fortuny-Amat approach

Complementarity conditions are replaced by a set of linear inequalities according to Fortuny-Amat method [1,4]

```python
  # Import blp class
  from bilpy import blp

  # Generate a random linear bilevel problem with nvar variables and ncon constraints. Further info: help(blp)
  blp1 = blp(nvar=50,ncon=25)

  # Solve the bilevel problem using the Fortuny-Amat approah setting all bigM to 1000. Further info: help(blp.solve_mip)
  of,time = blp1.solve_mip(M=1000, lpsolver = 'cplex', mipsolver='cplex')
```

## Regularization approach

Complementarity conditions are regularized according to Scholtes approach [2,3,4]

```python
  # Import blp class
  from bilpy import blp

  # Generate a random linear bilevel problem with nvar variables and ncon constraints. Further info: help(blp)
  blp1 = blp(nvar=50,ncon=25)

  # Solve the bilevel problem using the Fortuny-Amat approah setting using the following values of the regularization parameter [10**6,10**4,10**2,1,0.1,0.01,0]. Further info: help(blp.solve_reg)
  of,time = blp1.solve_reg(vector_ep = [10**6,10**4,10**2,1,0.1,0.01,0], lpsolver='cplex', nlpsolver='ipopt')
```

## References

[1] Fortuny-Amat J, McCarl B (1981) A representation and economic interpretation of a two-level programming problem. J Oper Res Soc 32(9):783–792.

[2] Scheel H, Scholtes S (2000) Mathematical programs with complementarity constraints: stationarity, optimality, and sensitivity. Math Oper Res 25(1):1–22

[3] Scholtes S (2001) Convergence properties of a regularization scheme for mathematical programs with complementarity constraints. SIAM J Optim 11(4):918–936

[4] Pineda, S., Bylling, H. & Morales, J.M. Efficiently solving linear bilevel programming problems using off-the-shelf optimization software. Optim Eng 19, 187–211 (2018).

## Do you want to contribute?
 
 Any feedback is welcome so feel free to ask or comment anything you want via a Pull Request in this repo. If you need extra help, you can ask Salvador Pineda (spinedamorente@gmail.com).
 
 ## Contributors 
 
 * [OASYS group](http://oasys.uma.es) -  groupoasys@gmail.com
 
 ## Developed by 

 * [Salvador Pineda](https://www.researchgate.net/profile/Salvador_Pineda) - spinedamorente@gmail.com
