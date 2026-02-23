# Mystery App
A PDF version of the Mystery Application Challenge is available [here](https://drive.google.com/file/d/17zG2p2sK_SLt0TN21CrCSXAeB67YMGdg/view?usp=sharing).

## Introduction
Warping large volume meshes has applications in biomechanics, aerodynamics, and cardiology. However, warping large meshes is computationally expensive, and calls for efficient parallelization to reduce overall computation time. This year's mystery application is Parallel FEMWARP (ParFEMWARP). ParFEMWARP is a software package for warping large, tetrahedral volume meshes. Specifically, ParFEMWARP is a  parallelization for the finite element-based mesh warping algorithm (FEMWARP). The paper describing ParFEMWARP from a numerical and algorithmic point of view is available [here](https://internationalmeshingroundtable.com/assets/papers/2025/1018-compressed.pdf).

## Setting Up ParFEMWARP
As of now, you must build ParFEMWARP from source. ParFEMWARP is available at the following GitHub repository: [https://github.com/AbirHaque/ParFEMWARP](https://github.com/AbirHaque/ParFEMWARP). This section provides a high level description of how you can compile ParFEMWARP. Specific commands are available in ParFEMWARP/README.md.

## Dependencies
The only requirements to compile and run ParFEMWARP are MPI and Eigen. As a result, the process of setting ParFEMWARP is extremely lightweight and hassle-free. 

## MPI
MPI is a standard for parallel programming across distributed memory. Note that ParFEMWARP has only been tested with OpenMPI 4.1. You are welcome to use other implementations and versions of MPI. However, your MPI implementation must support the MPI 3.0 standard at the bare minimum, as ParFEMWARP utilizes several RMA functions (including shared memory) that are only available in MPI 3.0 and above.

## Eigen
Eigen is a template library for linear algebra. Note that ParFEMWARP has only been tested with Eigen 3.4.0. Considering the latest stable release of Eigen is version 3.4.0, it is recommended you utilize that version. 

## Building ParFEMWARP
We provide a Makefile that generates a static library for ParFEMWARP. This Makefile is located in ParFEMWARP/src/Makefile. You simply need to provide the location of Eigen and set it as EIGEN\_DIR when making ParFEMWARP. This will generate a static library in ParFEMWARP/lib

## Compile Programs that Utilize ParFEMWARP
Due to the presence of both MPI and C++ code in ParFEMWARP, it is recommended you use mpic++ to compile ParFEMWARP. This should be provided by many MPI implementations. You simply need to include Eigen headers, ParFEMWARP headers (FEMWARP.hpp, matrix\_helper.hpp, csr.hpp), and link ParFEMWARP. 

## Execute Programs that Utilize ParFEMWARP
If your application only uses serial ParFEMWARP functions (i.e. does not utilize MPI), then you can execute your application without mpirun. If your application utilizes parallel ParFEMWARP functions (i.e. does utilize MPI), then you must use mpirun. Note that depending on your hardware and system configuration, you may need to explicitly supply mpirun with various MCA parameters to support shared memory and/or inter-node communication.

![body](./images/body.png "body.png")

*Tetrahedral mesh of a human chest*

![body_plane](./images/body_plane.png "body_plane.png")

*Cross section of tetrahedral mesh of a human chest*

## Challenge
Your task is to utilize ParFEMWARP to warp meshes within two simulations. We have already provided the C++ MPI code and Makefile mesh for each simulation in ParFEMWARP/examples/breathing1 and ParFEMWARP/examples/breathing2. The mesh is located in ParFEMWARP/examples/meshes. You are required to provide specific findings for each simulation in: 1) a report and 2) supplementary documents. Please contact Abir Haque either via Discord or email with any questions.

### Simulation 1: breathing1 - 50 points
Simulation 1 is simulating 16 deformations of a human chest. You are provided code to read and deform the mesh in ParFEMWARP/examples/breathing1. First, perform strong scaling tests on your system on a single node. Second, perform strong scaling tests on your system using multiple nodes. Average runtime across multiple trails is ideal. However, capturing a single runtime from a single trial for each core-configuration is acceptable.


Provide the following items in your report: 1) single node strong scaling speedup plots for each stage of ParFEMWARP (i.e. neighbor list precomputation, global stiffness matrix generation, sum of all user-supplied deformations, and sum of all linear solutions), (8 points) 2) multi-node strong scaling speedup plots for each stage of ParFEMWARP (8 points), 3) single node speedup plot for the entirety of ParFEMWARP (8 points), 4) multi-node speedup plot for the entirety of ParFEMWARP (8 points), 5) the best runtime overall for any core-configuration you choose (10 times the ratio of your team's runtime versus the best runtime across all teams, 10 points total), and 6) comments and conclusions about the scaling pattern for each stage of ParFEMWARP and the overall method (8 points).

Provide the following items in your supplementary item: 1) scripts and/or commands and 2) terminal output from ParFEMWARP for each trial. Failure to provide terminal output for all trials will drop your score to 0 out of 50 points for this simulation.

### ~~Simulation 2: breathing2 - 50 points~~
~~Simulation 2 is simulating 480 deformations of a human chest. You are provided code to read and deform the mesh in ParFEMWARP/examples/breathing2. You are only expected to perform this simulation once using the most optimal configuration you believe your system can provide **with at least 2 nodes**.~~

~~Provide the following item in your report: 1) runtime for the neighbor list generation stage (10 points), 2) runtime for the global stiffness matrix generation stage (5 points), 3) average runtime for each linear solution stage (15/480 points per deformation, 15 points total), 4) total deformations completed (15/480 points per deformation, 15 points total), and 5) runtime of the overall method (5 times the ratio of your team's runtime versus the best runtime across all teams, 5 points total).~~

~~Provide the following item in your supplementary item: 1) scripts and/or commands used to execute ParFEMWARP and 2) terminal output from ParFEMWARP for the simulation. Failure to provide terminal output for the simulation will drop your score to 0 out of 50 points for this simulation.~~

## Rules
1. No modifications to source code are allowed (i.e. any .cpp or .hpp file).
2. Modifications to only Makefiles within ParFEMWARP are allowed.
3. No modifications to input meshes are allowed.
4. Failure to provide terminal output for any simulation will drop your score to 0 out of 50 points for that simulation.
5. Incomplete runs of simulations will grant partial credit based of how many stages and deformations have been completed. 
6. All official runs performed by ParFEMWARP must run locally. This means on your competition hardware. You are free to execute unofficial runs on any device, including your laptop.


![serial_body](./images/serial_body.png "serial_body")

*Example output of performing Simulation 1 via ParFEMWARP with 1 core (i.e. serially)*

![parallel_body](./images/parallel_body.png "parallel_body")

*Example output of performing Simulation 1 via ParFEMWARP with 8 cores on 1 node*
