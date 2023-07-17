# Hodgking and Huxley model for the membrane action potential

This is a study on the Hodgking-Huxley model (HHM) for the action potential. The code in this repository is based on differential equations derived from the cell membrane's equivalent circuits. The reader will find two main sets of equations: the ones describing the generation of the action potential (AP), and the ones describing the AP propagation throughout axons. 

For the first set of equations, we employ Euler's method for differential equations solving. For the latter, we aimed at developing the set of equations.

## Modelling the potential across the cell membrane

The cell membrane is typically composed of a lipidic and proteic structure that insulates the intra from the extracellular medium. Additionally, some specific types of protein can transverse the membrane structure, forming conduction channels from ions to flow between these two mediuns (ionic channels). Different concentrations of ions between the intra and extracellular environments causes an eletric potential difference to form across the cell membrane, yield ions flows throughout the membrane. The lipidic structure can be modelled as a capacitor, whereas the ionic channels can be regarded as resistors when using the equivalent circuit model for the cell membrane.

The main ions that contribute to the action potential are sodium (Na) and potassium (K). The membrane has specific conductances for each type of ion. Therefore, let us define $g_{Na}$ and $g_{K}$ as the conductantes for the sodium and potassium ions, respectively. Applying Kirchoff's Law for electrical circuits, the following can be obtained for the membrane potential (V):

$C_{M}\frac{dV}{dt} + g_{Na}(V - E_{Na}) + g_{K}(V - E_{K}) + g_{l}(V - E_{l}) = 0$,

in which:

- $C_{M}$ represents the membrane capacitance;
- $t$ stands for the time instant;
- $E_{i}'s$ are the membrane's equilibrium potential for ion $i$;
- and the indice $l$ denotes current leakage.

In HHM, the sodium and potassium conductances are potential-dependant, whereas $g_{l}$ is considered to be constant. $g_{Na}$ and $g_{K}$ vary according to "gate particles" that control that ion's channel permeability. Thus, both conductances can be written as products between a function $f = f(V,t)$, whose values fall within [0,1], and a maximum conduction; that is:

$g_{i} = f_{i}(V,t)g_{i}^{max}$.

## Modelling the ionic channels

Let us assume that ionic channels can be characterized by two states: 'open' (O) and 'closed' (C). Conformational changes in the ionic channels caused by electrical field variations can yield transition from one state to the other. Such transitions occur on rates that are, hence, dependant upon the membrane's potential. This process is illustrated below by Fig. 1, in which 'a' and 'b' denote the transition rates from 'O' to 'C', and from 'C' to 'O', respectively.

![Ionic channel transition rates](/images/ionic-channel-probabilities.png)
*Figure 1. Ionic channel transition rates illustration.*