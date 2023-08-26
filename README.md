# Online SSB calculator
Author: Dustin_Chen Email: Dustin_Chen@compal.com or chuhpsdustin@gmail.com

● ssb_basic : https://dustinchen26.github.io/ssb_calculate/

● ssb_advance : https://dustinchen26.github.io/ssb_calculator_advance/

● ssb_xml : https://dustinchen26.github.io/ssb_xml/

## freq to arfcn convert
ex:
Input freq(Hz): 3603840 => Output arfcn = 640256.00

## arfcn to freq convert
ex:
Input arfcn: 640256.00 => Output Freq = 3603840.00 Hz

## gscn calculator
```
[Purpose]: Input (band, carrierBw(RB), freq_low, freq_high), then it will calculate the valid (gscn /absFreqPointA /absArfcnPointA /absFreqSsb /absArfcnSsb /dlEarfcn /nDlCenterFreq /Kssb /offsetToPointA )
	n41 => freq range [2496000, 2690000]
	n48 => freq range [3550000, 3700000]
	n78 => freq range [3300000, 3800000]
	n79 => freq range [4400000, 5000000]
(RadiSys code):For n79, CORESET0 use 38.213 Table 13-6 Index 4.
(RadiSys code):For others, if BW>=48, CORESET0 use Table 13-4 Index 10. // Try to have 48 RB size for CS-0 to avoid allocation failure for SIB1 during SSB(20RBs) overlap
(RadiSys code):For others, if BW<48, CORESET0 use Table Index 0. // if 48 RB is not available, get the best fit CS0
```
## Example
```
● Please input
ex:(band, carrierBw(RB), freq_low, freq_high)=(78, 273, 3603840, 3603840)
● Calculate:
gscn=7890, absFreqPointA=3554700, absArfcnPointA=636980, absFreqSsb=3563040, absArfcnSsb=637536, dlEarfcn=640256, nDlCenterFreq=3603840, Kssb=4, offsetToPointA=26
gscn=7891, absFreqPointA=3554700, absArfcnPointA=636980, absFreqSsb=3564480, absArfcnSsb=637632, dlEarfcn=640256, nDlCenterFreq=3603840, Kssb=4, offsetToPointA=34
gscn=7892, absFreqPointA=3554700, absArfcnPointA=636980, absFreqSsb=3565920, absArfcnSsb=637728, dlEarfcn=640256, nDlCenterFreq=3603840, Kssb=4, offsetToPointA=42
... etc

```
