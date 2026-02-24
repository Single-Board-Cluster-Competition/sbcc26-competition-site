# Not So Slow Slugs

## University of California, Santa Cruz

<img src="./logos/ucsc.png" alt="UCSC Logo" height="200"/>

## Diagram

![Not So Slow Slugs Hardware Diagram](./diagrams/ucsc-diagram.png)

## Hardware

We originally expected to recieve \$6k in funding instead of having a \$6k budget cap. Because of this, we had to scale back our original plans and use more of what we already had. Our Faculty advisor has a 10 RPi5-node picocluster worth $3k that we are using. This will be great for general worker nodes but we still needed some specialized boards for acceleration of the tasks. MDTest is dependent more on I/O speed which doesn't benefit from the compute capabilities of the 10 RPis. The raspberry Pis only expose a single lane of PCIe 2.0, which is quite slow compared to today's standards. To solve this, we needed something wth at least PCIe Gen3 x4. Thankfully, the Jetson Orins have this, so they can double as the GPU nodes and the fast storage nodes. Additionally, we may acquire 1 or 2 LattePanda IOTA though sponsorships, which will be supporting our CPU compute.

### Power monitoring

For power monitoring, we will likely use a KASA python api, and create our own visualization. 

### Hardware Table 

| Item | Amount | Purpose | Expected Power Draw | Price|
| -------- | ------- |------- |------- |------- |
| Raspberry Pi 5 (PicoCluster 10T) | 10 | CPU Compute | 120W (12W) | $3000 |
| Jetson Orin Nano | 2 | GPU Compute | 50W (25W) | $300 |
| LattePanda Iota (Intel N150, 8GB RAM / 64GB eMMC) | 2  | CPU Compute| 48W (24W) | $260 |

## Software

We will be using Ubuntu on all our devices due to it's familiarity and support. On top of that we will use Slurm scheduler to run the benchmarks on our cluster. 

## Strategy

### Benchmarks

We will begin by collecting as much data as possible, to gain some insight to model performance. Each team member will study the algorithms. Once better understood, we will find the best parameters for each of the benchmarks, and submit. 

### Applications

We will start by running the applications on a single node, then expanding to as far as we can. We will monitor network traffic, compute usage, and power usage, making sure each is optimal.

## Team Details

Caleb - Robotics Engineering & Computer Engineering

Brock - Electrical Engineering

Indira - Computer Engineering & Applied Mathematics

Shiloh - Computer Science Game Design

Julien - Computer Engineering & Applied Mathematics

Jason - Computer Engineering

Holden - Robotics Engineering

Myles - Computer Science & Scientific Computing and Applied Mathematics