# Info
The CALPHAD (CALculation of PHAse Diagrams) method takes in much, if not all, available experimental, thermochemical, and thermophysical data on a system and uses them to produce equilibrium phase diagrams. These phase diagrams can then be used to find compositions where a particular system will be stable. For example, if one was looking for a new aluminum alloy that is stable above 1700 degrees Celsius for a jet engine component, it would be relatively trivial to produce a phase diagram for an alloy that was 80% aluminum, 10% chromium, and 10% titanium. Such a calculation can be done in a matter of seconds using something like OpenCalphad or Thermo-Calc. Generating entire catalogs of phase diagrams with all possible percent compositions of alloying elements takes considerably longer, however.

Using a significantly reduced phase dataset, I wanted to see how feasible it would be to predict stability just based off of an alloy's percent composition using simple neural networks. 

# Data
The data consists of approximately 50,000 quaternary alloys at atmospheric pressure and 1000 degrees Kelvin. 

| Column | Description |
| --- | --- |
| el0 | element 1 |
| el1 | element 2 |
| el3 | element 3 |
| x0 | molar fraction of el0 |
| x1 | molar fraction of el1 |
| x2 | molar fraction of el2 |
| x3 | molar fraction of el3 |
| phase_1_name | name of phase present at equilibrium* |
| phase_2_name | see above |
| phase_3_name | see above |
| phase_4_name | see above |
| phase_5_name | see above |
| phase_1_frac | fraction of phase 1 at equilibrium |
| phase_2_frac | fraction of phase 2 at equilibrium |
| phase_3_frac | fraction of phase 3 at equilibrium |
| phase_4_frac | fraction of phase 4 at equilibrium |
| phase_5_frac | fraction of phase 5 at equilibrium |

\* There are several possible phases that can arise from the combination of elements present in the dataset. They have names such as AL3M_D022, ALCR2, BCC_B2, LAVES_C15, etc. The naming conventions can be pretty weird, and can change depending on constituent elements. For the purposes of this exervise, as long as none of the the phases are LIQUID then the alloy is considered stable. 


If you see this, thanks Sam for putting the data together!
