# Team Kent Ridge

## National University of Singapore

<img src="./logos/nus.png" alt="Team Kent Ridge Logo" height="200"/>

## Diagram

![NUS Hardware Diagram](./diagrams/nus-diagram.svg)

## Hardware

Our cluster comprises of ARM64-based compute nodes (Orange Pi 5 Max), with these key hardware specifications:

| Category          | Specification                                         |
| ----------------- | -------------------------------------------------------------------------------------------------|
| Master Chip       | Rockchip RK3588 (8nm LP process)                      |
| CPU               | 8-core 64-bit; 4× Cortex-A76 @ 2.4GHz + 4× Cortex-A55 @ 1.8GHz with independent NEON coprocessor |
| GPU               | Integrated ARM Mali-G610; OpenGL ES 1.1/2.0/3.2, OpenCL 2.2, Vulkan 1.2|
| NPU               | 6 TOPS; supports INT4/INT8/INT16/FP16 hybrid computing|
| PMU               | RK806-1​                                               |
| RAM               | 16 GB LPDDR5   |
| Storage           | MicroSD card slot; M.2 M-Key (PCIe 3.0 ×4, NVMe SSD) ​ |
| USB               | 2× USB 3.0, 2× USB 2.0 ​                               |
| Ethernet          | 1× 2.5 GbE LAN via PCIe (RTL8125BG) ​                  |
| Power Input       | USB Type-C, 5V @ 5A ​                                  |
| PCB Dimensions    | 89 mm × 57 mm × 1.6 mm ​                               |
| Weight            | 62 g ​                                                 |
| Power Consumption | 12.5W (expected)                                      |

All SBCs will communicate over the NICGIGA 24-port switch and connect to each other via SSH. 

Two Raspberry Pi 3Bs will be used (not included in the budget) for:
  1.  a DHCP Server + DNS
  2.  a Gateway / Firewall (required to access our university network, incoming connections disabled during the competition)

### Power monitoring

The system will be connected to a Server Technology Sentry CW-8H2A413 Switched PDU for accurate power monitoring.
The PDU will send power usage statistics to a Grafana dashboard, and a view of this will be shared live with the committee. 
The setup (including PDU) will also be livestreamed via video. We are happy to provide further verification of the power draw values. 

### Hardware Table 

| Category | Item | Amount | Description | Expected Power Draw (W) | Cost per unit (USD) | Total Price (USD) |
| ------- |-------- | ------- |------- |------- |------- |------- |
| Compute | Orange Pi 5 Max 16GB  | Single-Board Computer (SBC) | 16 | 200 | 249.00 | 3984.00 |
| Storage | Crucial T500 PCIe Gen4x4 NVMe M.2 SSD (1TB) | NFS Drive | 3 | 10 | 214.00 | 642.00 |
| Network | NICGIGA 24-Port 2.5G Ethernet Switch (S25-2400) | Network Switch | 1 | 15 | 249.99 | 249.99 |
| Storage | Kioxia Exceria MicroSDHC U1 32GB | Operating System Drive | 16 | NA | 11.77 | 188.33 |
| Storage | Crucial P310 PCIe Gen4x4 NVMe M.2 2280 SSD (1TB) | NFS Drive | 1 | 3.33 | 164.00 | 164.00 |
| Power | DC5.5 x 2.1mm Female Jack to USB Type-C | Power Adapter | 16 | NA | 3.08 | 49.42 |
| Cooling | ARCTIC P14 Pro PST, 5 Pack | Fans | 1 | 20 | 44.99 | 44.99 |
| Power | DC Power Fuse Distribution Strip | Power Distribution | 3 | NA | 13.99 | 41.97 |
| Power | Meanwell LRS-300-5V w UK Plug | Power source | 1 | NA | 36.34 | 36.34|
| Power | 14AWG 100ft Electrical Wire | Power Cable | 2 | NA | 15.00 | 30.00 |
| Network | Cat5E + Cat6 Cables (Various Lengths) | Network Cables | 16 | NA | 1.56 | 25 |
| Cooling | 14x14x6mm and 22x22x10mm Heatsinks | Heatsinks | 16 | NA | 0.56 | 9.05 |
| Power | DC5.5 x 2.1mm Male Jack | Power Adapter | 16 | NA | 0.28 | 4.55 |
| Totals | | | | 248.33 | | 5469.64  |

## Software

- **Operating System**
  - Armbian Linux: Best support for Orange Pi
- **Cluster Orchestration and Management**
  - Ansible: Orchestration tool, eliminating the need to manually set up individual SBCs
  - SLURM: Job scheduler and workload manager. Chosen for team familiarity due to being used in university's cluster.
  - Grafana: Dashboard for system monitoring. Chosen for team familiarity.
  - Prometheus: Used to collect and store real-time metrics such as power usage and temperature.
- **Storage**
  - BeeGFS: Parallel file system for higher IO throughput.
- **MPI** 
  - OpenMPI: For multi-node runs,
- **Linear Algebra Libraries**
  - OpenBLAS: Linear algebra operations. 

## Strategy

### Benchmarks / Applications


1. **High Performance Linpack (HPL)**
    - HPL is installed and compiled with OpenBLAS.
    - We will experiment with several parameters (such as problem size `N` and block size `NB`) and tune them for our system.
    - Tune to maximize TFLOPS.
2. **D-LLAMA**
    - Compiled from source following the official repository documentation.
    - Implementation of weight quantization and exploration of NPU-offloaded computation.
3. **MDTest**
    - Compiled from the MDTest source utilizing OpenMPI.
    - Test different storage methods like BeeGFS.
    - Optimise with MPI rank placement and network tuning.
4. **IQ-TREE**
    - Compiled from source.
    - Tune with OpenMP and MPI for ranks and threads per node.
5. **Mystery Application**
    - Assign team members based on the mystery application and members' individual interests.  

## Team Details

| Name                            | Interests!                                                      | Responsibilities                                              |
| ------------------------------- | --------------------------------------------------------------  | ------------------------------------------------------------- |
| Muhammad Asyraf Bin Abdul Rahim | Motorsport / tinkering  / gaming                                | Hardware design, network management, thermal management       |
| Lau Zhe Wen                     | Photography                                                     | Hardware procurement, optimizing IQ-TREE                      |
| Tan Yong Xiang                  | Likes climbing things                                           | Hardware procurement, power system design, optimizing IQ-TREE |
| Mande Neil Ashvinikumar         | Networking (the ethernet kind) enthusiast                       | Network setup, optimising MDTest                              |
| Gabra Shubhan                   | Playing chess, playing cricket, travelling                      | Hardware procurement, power system design, optimizing D-LLAMA |
| Chan Dong Jun                   | Stargazing                                                      | Ansible system administration, optimizing D-LLAMA             |
| Joel Chong                      | Low latency systems, C++ enthusiast (very enthusiastic)         | Optimizing HPL, general software optimizations                |
| Koh Tze Rui                     | Also likes climbing things                                      | Hardware procurement, optimizing HPL                          |
