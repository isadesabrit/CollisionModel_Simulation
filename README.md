# CollisionModel_Simulation 

**Project Overview**
This project uses Python and the Qiskit framework to simulate quantum coherence dynamics in an all-to-all collision model consisting of three system qubits and three reservoir qubits. The simulation investigates how interaction strength (eta) and reservoir depolarization (omega) affect coherent energy transport across repeated collision rounds.

**Language**: Python
**Framework**: Qiskit
**Libraries**: NumPy, Qiskit Aer, Pandas, Matplotlib

**Methodology**

The simulation constructs a 4×4 partial-SWAP unitary operator for system-reservoir interactions and an 8×8 Hermitian Hamiltonian for system evolution. An iterative algorithm constructs a nine-qubit circuit, applying partial-SWAP operations across all nine system-reservoir qubit pairs, followed by reservoir depolarization and Hamiltonian evolution. After each round, the reduced density matrix is extracted, and the magnitude of its off-diagonal element at indices [1, 4] is calculated to measure coherence between the computational basis states |001⟩ and |100⟩.

**Results**

A nested-loop parameter sweep evaluates five interaction strengths (eta ranging from 0 to π/2) and five reservoir depolarization levels (omega ranging from 0 to 1) over 30 collision rounds.

Numerical results are organized using Pandas and visualized with Matplotlib. The simulations show persistent coherence oscillations at low depolarization levels, while increased depolarization generally suppresses coherence, particularly at stronger interaction strengths.

**How to Run**
  1. Open the .ipynb notebook in Google Colab.
  2. Run the installation cell to install the required Python packages.
  3. Execute the remaining cells sequentially to generate the numerical results and coherence plots.
