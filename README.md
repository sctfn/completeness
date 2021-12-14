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

Example of usage: "./completeness foo '( ph <-> ph )'" prints out:

foo $p |- ( ph <-> ph ) $= wph wn wph wph wb wi wph wph wb wph wn wph wph wi wph wph wi wn wi wn wi wph wn wph wph wb wi wph wn wph wph wi wn wn wi wph wn wph wph wi wph wph wi wn wi wn wi wph wn wph wph wi wi wph wn wph wph wi wn wn wi wph wph pm2.21 wph wph wi wph wph wi wn wn wi wph wn wph wph wi wi wph wn wph wph wi wn wn wi wi wph wph wi notnot wph wph wi wph wph wi wn wn wph wn imim2 ax-mp ax-mp wph wn wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wn wph wph wi wn wn wi wph wn wph wph wi wph wph wi wn wi wn wi wi wph wn wph wph wi wi wph wn wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wph pm2.21 wph wph wi wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wn wph wph wi wi wph wn wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wi wph wph wi wph wph wi wn mth8 wph wph wi wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wph wn imim2 ax-mp ax-mp wph wn wph wph wi wn wn wph wph wi wph wph wi wn wi wn ax-2 ax-mp ax-mp wph wph wi wph wph wi wn wi wn wph wph wb wi wph wn wph wph wi wph wph wi wn wi wn wi wph wn wph wph wb wi wi wph wph wb wph wph wi wph wph wi wn wi wn wb wph wph wi wph wph wi wn wi wn wph wph wb wi wph wph dfbi1 wph wph wb wph wph wi wph wph wi wn wi wn biimpr ax-mp wph wph wi wph wph wi wn wi wn wph wph wb wph wn imim2 ax-mp ax-mp wph wph wph wb wi wph wn wph wph wb wi wph wph wb wi wph wph wph wi wph wph wi wn wi wn wi wph wph wph wb wi wph wph wph wi wn wn wi wph wph wph wi wph wph wi wn wi wn wi wph wph wph wi wi wph wph wph wi wn wn wi wph wph ax-1 wph wph wi wph wph wi wn wn wi wph wph wph wi wi wph wph wph wi wn wn wi wi wph wph wi notnot wph wph wi wph wph wi wn wn wph imim2 ax-mp ax-mp wph wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wph wph wi wn wn wi wph wph wph wi wph wph wi wn wi wn wi wi wph wph wph wi wi wph wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wph ax-1 wph wph wi wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wph wph wph wi wi wph wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wi wi wph wph wi wph wph wi wn mth8 wph wph wi wph wph wi wn wn wph wph wi wph wph wi wn wi wn wi wph imim2 ax-mp ax-mp wph wph wph wi wn wn wph wph wi wph wph wi wn wi wn ax-2 ax-mp ax-mp wph wph wi wph wph wi wn wi wn wph wph wb wi wph wph wph wi wph wph wi wn wi wn wi wph wph wph wb wi wi wph wph wb wph wph wi wph wph wi wn wi wn wb wph wph wi wph wph wi wn wi wn wph wph wb wi wph wph dfbi1 wph wph wb wph wph wi wph wph wi wn wi wn biimpr ax-mp wph wph wi wph wph wi wn wi wn wph wph wb wph imim2 ax-mp ax-mp wph wph wph wb pm2.61 ax-mp ax-mp $.
