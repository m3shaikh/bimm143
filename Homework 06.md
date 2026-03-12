# Homework 06
Maleeha Shaikh (PID: A18541405)

## Code

``` r
library(bio3d)
```

``` r
analyze_drug_binding <- function(pdb_id) {

  pdb <- read.pdb(pdb_id)
  pdb_chainA <- trim.pdb(pdb, chain = "A", elety = "CA")
  b_factors <- pdb_chainA$atom$b

  plotb3(b_factors,
         sse = pdb_chainA,
         typ = "l",
         ylab = "B-factor",
         main = paste("B-factor plot for", pdb_id))

  return(b_factors)
}
```

``` r
b1 <- analyze_drug_binding("4AKE")
```

      Note: Accessing on-line PDB file

![](Homework-06.markdown_strict_files/figure-markdown_strict/unnamed-chunk-3-1.png)

``` r
b2 <- analyze_drug_binding("1AKE")
```

      Note: Accessing on-line PDB file
       PDB has ALT records, taking A only, rm.alt=TRUE

![](Homework-06.markdown_strict_files/figure-markdown_strict/unnamed-chunk-3-2.png)

``` r
b3 <- analyze_drug_binding("1E4Y")
```

      Note: Accessing on-line PDB file

![](Homework-06.markdown_strict_files/figure-markdown_strict/unnamed-chunk-3-3.png)

## Explanation

Q1. What are the inputs to the function?

The function analyze_drug_binding() takes one input, pdb_id, which is a
character string representing the PDB ID of the protein that is being
analyzed.

Q2. What the function does and how to use it?

The function reads a protein PDB file, trims the structure to chain A
and carbon alpha atoms, extracts B-factor values, and generates a
B-factor plot. The function is used by calling it with a PDB ID string
as input.

Q3. What is the output of the function?

The output of the function is a numeric vector containing the B-factor
values for the specific protein structure.
