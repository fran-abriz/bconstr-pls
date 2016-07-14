# bconstr-pls
Replacement for R pls library svdpc.fit() with optional lower bounds on the regression coefficients

This file is based on the original svdpc.fit.R from the pls library in the CRAN repository.
This version is proof-of-concept only.  The pls library construction makes it impossible to make this
file a drop-in replacement.  My goal is to include a minimal number of necessary replacement files for actual use.

Usage: The lower bound option for svdpc.fit() is lbd= and its default value is -Inf, which gives the original behavior.
If a value is given, it should be a scalar (example: lbd=0) or a vector whose length is the number of independent variables in the problem.  The parameter will be passed by mvs(), pcr(), and crossval().

Notes
1. I have tested that the bounds are applied correctly to the coefficients and that the residuals are computed correctly.
2. The bounds do not affect the loadings or projection.  I have to consider whether it makes sense to do so.
3. Depends: R >= 2.10

CREDITS
pls authors Bjorn-Helge Mevik, Ron Wehrens, and Kristian Hovde Liland <pls@mevik.net>
http://mevik.net/work/software/pls.html
pls date/publication 2015-08-22 14:57:19
