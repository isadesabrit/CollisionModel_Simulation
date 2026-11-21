# CollisionModel_Simulation
This project uses Python and the Qiskit framework to simulate quantum coherence dynamics in an all-to-all collision model consisting of three system qubits and three reservoir qubits. The simulation investigates how interaction strength (eta) and reservoir depolarization (omega) affect coherent energy transport across repeated collision rounds.

**Methodology**
Each system-reservoir collision is modeled using a parameterized 4×4 partial-SWAP unitary matrix:
[
U(\eta)=\cos(\eta)I+i\sin(\eta)\mathrm{SWAP}
]
An 8×8 Hermitian Hamiltonian describes the evolution of the three-qubit system, with off-diagonal terms representing coherent energy transport and diagonal terms incorporating a magnetic-field parameter. 

An iterative algorithm constructs a nine-qubit circuit, applying partial-SWAP operations between all nine system-reservoir qubit pairs, followed by reservoir depolarization and Hamiltonian evolution. After each collision round, the algorithm extracts the reduced density matrix of the system and calculates the magnitude of the off-diagonal element:
[
C(k)=|\rho_{1,4}(k)|
]

This element represents coherence between the computational basis states (|001\rangle) and (|100\rangle), corresponding to excitations localized at the first and third system qubits.

**Results**

A nested-loop parameter sweep evaluates five interaction strengths ((0\leq\eta\leq\pi/2)) and five reservoir depolarization levels ((0\leq\omega\leq1)) over 30 collision rounds.

Results are organized using Pandas and visualized with Matplotlib. The simulations exhibit persistent coherence oscillations at low reservoir depolarization, while higher depolarization generally leads to faster coherence decay. These differences are especially pronounced at stronger interaction strengths.
