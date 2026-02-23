# San Diego Super Computing Center / University of California, San Diego - Team 1

## Diagram

![image](./images/ucsd1.png)

## Hardware

- 16 Rock 5Bs
    - Each is connected to Unifi2Standard 48 ethernet switch via a cat6 ethernet cable
    - Each is connected to an extension cord by USB-C power supply
        - Extension cords will be connected to PSU+PDU
    - For oMPI compatibility, every Rock 5B will be able to SSH into each other before we get to the competition, saving us competition time
- 2x MV-V7E500 500GB SSDs (1 TB total)
    - 1 SSD will be on the login node, while the other will be on a different node (we may call this the secondary login node)
- Cluster compute structure: Primary access through a login node structure, which will have important storage/accessories locally connected (vs. virtual access)

| Part                  | Units | Wattage/Unit | Cost per unit | Tax/Shipping | Anticipated Tariff | Total Price |
|-----------------------|-------|--------------|---------------|--------------|--------------------|-------------|
| RADXA Rock Pi 5B (16 Gb RAM) | 16    | 12           | 117.90        | 148.00       | 0.25               | $2,506.00   |
| Unifi Switch 48       | 1     | 40           | 400.00        |              |                    | $400.00     |
| MV-V7E500 500GB SSD   | 2     |              | 150.00        |              |                    | $300.00     |
| Enclosure (DIY)       | 1     |              |  79.92        |              |                    | $79.92      |
| Power supply          | 16    |          |  11.2        |  20.72            | 0.25               | $244.72     |
| Fan                   | 4     | 1.56         | 6.99          |              |                    | $27.96      |
| **TOTAL COST**        |       |              |               |              |                    | **$3,558.60**|



## Software

Filesystem & Storage
- SSDs will be configured with RAID0 for better read/write speeds
- Ceph will be used a network file system since members of the team have past experience working with it and setting it up on clusters
    - This will allow every node to efficiently access data without bottlenecking the applications, and provide the bandwidth we need for I/O libraries required in our applications and benchmarks
    - Ceph is a POSIX-compliant file system notable for how it splits metadata and
    data into separate data stores, allowing more efficient writes and collaboration
    between users. We believe this will be especially helpful for I/O focused
    applications and benchmarks like STREAM, allowing us to maximize performance
    - Ceph is widely used in industry, is an open-source platform, and has large
    amounts of documentation and research available for our team to make use of.

Networking
- Networking will be set up with IPMI/BMC
- We will use the pre-configured network settings on the switch

Sysadmin, OS, and Setup
- The cluster will run on Debian, using an official image from Radxa.
- We will set up users and privileges through Ansible:
    - Standardize our setup process, including building on playbooks developed for club hardware and projects.
    - A convenient way to set up the preliminary software stack.
    - This will allow us to easily reset any system without repercussion if we need to reset a system.
- We will try strongly to set up Slurm on the cluster so that we can schedule tasks overnight when we’re away from the machines:
    - Since we are a large team, it will be easier to manage resources with Slurm as well.
- We will follow standard processes, like disabling password-based logins (among other choices), to ensure cluster security.
- If time permits, we’ll look into setting up a logger and optimizing CPU clock speeds.
- GCC compiler.
- Spack to manage and install dependencies for all users.
- Grafana dashboard to profile cluster.
- Prometheus and Docker to query data from the provided PDU.

Application and Benchmark Specific Dependencies
- **STREAM**: stream_mpi in Fortran or C, ssh config, mpicc, mpirun
- **Hashcat**: libOpenCL.so on POCL
- **D-LLAMA**: git, Python 3
- **HPL**: Standard BLAS implementation, as there are no vendor-optimized versions of this library


## Team Details

**Aarush Mehrotra**: Aarush Mehrotra is this year’s SBCC team captain. He is a double-major in
Mathematics-Computer Science and Economics. He is currently an HPC Intern at SDSC. With
prior SBCC and SCC experience, he brings institutional knowledge and real-world experience to
the team. Aarush has experience working with machine learning benchmarks, scientific
applications, and various other HPC tools. He looks forward to competing and making friends at
SBCC25.

**Gauri Renjith**: Gauri has prior experience using high performance computing to perform
genome-wide association analyses of genetic information. As a computer science major
specializing in bioinformatics, she provides a unique perspective on HPC applications and is
excited to explore supercomputing and its usage to understand biological problems.

**Ferrari Guan**: Ferrari has prior experience in high-performance computing (HPC) as a network
specialist and system administrator for the SCC team. As a computer engineering major, he has
experience working on the hardware, the software, and everything in between. He is enthusiastic
about building HPC cyberinfrastructure and solving real-world problems.

**Luiz Gurrola**: Luiz Gurrola has prior experience in high performance computing through SBCC
as well as experience in system administration. He is interested in all fields relating to computer
science and computation and is eager to improve and apply his skills.


**Ryan Estanislao**: Ryan has prior experience in high performance computing through last year’s
SCC Home Team, analyzing runtimes on the ICON application. As a computer science major, he
is interested in further understanding how to make various applications more efficient.

**Shing Hung**: Shing has prior experience constructing a Raspberry PI-based CPU cluster with
Ceph, and conducting read/write and video streaming benchmarks through her past internship.
She is excited to explore more on embedded system programming, hardware coding, and
firmware design.

**William Wu**: William has prior experience working with hardware like Arduinos and Raspberry
Pi when automating tasks for lab work. He has also competed nationally in cyber competitions
and can transfer many of his skills into working on Hashcat.

**Minh Quach**: Minh has prior experience working with system optimization and embedded
systems. She has worked on Jetson Nano-based projects, optimizing real-time computer vision
applications and managing resource-constrained devices. As a computer engineering student, she
is eager to apply her knowledge to building and optimizing single-board computer clusters and
tackling real-world HPC challenges.
