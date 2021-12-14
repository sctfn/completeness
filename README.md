# completeness
An automatic prover for tautologies in Metamath

This program implements the constructive proof of the Completeness Theorem
for propositional calculus. To use it, call it with a proof label and
a syntactically correct Metamath wff. This will produce an uncompressed
$p statement suitable for incorporation into set.mm. I highly recommend
running minimize_with over the resulting theorem. It will often reduce the
size of the proof by an order of magnitude.

Furthermore, if the script is called with "-d" instead of a proof label,
it will produce a D-rule proof of the theorem with the following conventions:
* B = df-bi
* K = df-an
* A = df-or
* k = df-3an
* a = df-3or
* d = df-nand
* t = df-tru
* f = df-fal
