# University of Kansas / KU SUPERCOMPUTING CLUB

## Diagram

![image](./images/ku.png)
 
## Hardware
| ITEM                          | COST (per unit) | # ITEMS | TOTAL COST | LINK TO PRODUCT                                                                 |
|-------------------------------|-----------------|---------|------------|--------------------------------------------------------------------------------|
| Power Supply                  | $43.95          | 1       | $43.95     | [Link](https://a.co/d/aef7134)                                                  |
| Ethernet Switch               | $89.70          | 1       | $89.70     | [Link](https://a.co/d/80uFMTU)                                                  |
| Power Strip                   | $8.99           | 1       | $8.99      | [Link](https://a.co/d/9DdrLzO)                                                  |
| Power Distribution Board      | $38.00          | 3       | $114.00    | [Link](https://a.co/d/7JitnBU)                                                  |
| Power Monitor                 | $15.99          | 1       | $15.99     | [Link](https://a.co/d/8LErGh1)                                                  |
| 64GB MicroSD Card (30-pack)   | $139.50         | 1       | $139.50    | [Link](https://www.aliexpress.us/item/2251832790078323.html)                    |
| Orange Pi 5+                  | $191.99         | 5       | $959.95    | [Link](https://a.co/d/9byszpf)                                                  |
| Orange Pi 5                   | $139.99         | 23      | $3,219.77  | [Link](https://a.co/d/hcaDbo4)                                                  |
| Ethernet cable (grey, 100ft)  | $60.00          | 1       | $60.00     | [Link](https://www.mcmaster.com/8245K31-8245K14/)                               |
| M4 Hex Head Screws (100 ct.)  | $12.58          | 2       | $25.16     | [Link](https://www.mcmaster.com/91239A148/)                                     |
| 14AWG supply wires (1 black, 1 red, 50ft each) | $23.16 | 2 | $46.32 | [Link](https://www.mcmaster.com/8054T17-8054T378/)                              |
| 24AWG supply wires (orange, 50ft) | $6.15      | 1       | $6.15      | [Link](https://www.mcmaster.com/8054T12/)                                       |
| 24AWG supply wires (black, 50ft)  | $6.15      | 1       | $6.15      | [Link](https://www.mcmaster.com/8054T12/)                                       |
| Ethernet RJ45 crimp-on connector (10-pack) | $9.77 | 10 | $97.70 | [Link](https://www.mcmaster.com/68995K67/)                                      |
| Heatsinks                     | $7.99           | 15      | $119.85    | [Link](https://a.co/d/imQvaOH)                                                  |
| Din Rails 7.5mm depth         | $6.30           | 3       | $18.90     | [Link](https://www.mcmaster.com/8961K45/)                                       |
| Single Clip Mount for DIN 3 Rail | $2.53       | 30      | $75.90     | [Link](https://www.mcmaster.com/8961K28/)                                       |
| Clear Plexiglass 18"x36" (1/4") | $30.28       | 1       | $30.28     | [Link](https://a.co/d/chkxqMH)                                                  |

## Software

| FEATURE              | SOFTWARE USED                          |
|----------------------|----------------------------------------|
| Operating system     | Armbian Linux 24.2.1 Bookworm CLI, Kernel: 5.10 |
| C/C++ compilation    | GNU Compiler Collection                |
| Job scheduling       | Slurm                                  |
| MPI implementation   | MPICH                                  |
| BLAS implementation  | OpenBLAS                               |
| Package management   | Spack                                  |

## Strategy

- **HPL**: Will experiment with several tuning configurations that consider OpenMP support within OpenBLAS, thus reducing intra-node communication overhead.
- **STREAM**: We will explore several MPI+OpenMP configurations to achieve maximum memory bandwidth across the cluster.
- **D-LLAMA 3 8B**: We will compare the performance for different BLAS implementations and determine whether quantization is beneficial given our cluster setup.
- **Hashcat**: Will research and experiment with application, benchmarking with various hash digests (MD5, SHA256, SHA512). We will also explore using a hybrid cracking technique before moving onto a brute force approach.
- **Mystery Application**: Will research into the provided application to ensure completion within the allotted timeframe.

## Team Details
Our team is comprised of five (5) University of Kansas (KU) undergraduate students that are active members of KU’s Supercomputing Club. Below is the team roster and member backgrounds:

| NAME            | BACKGROUND                                                                 |
|-----------------|---------------------------------------------------------------------------|
| Leo Cabezas     | (captain) Junior in Computer Engineering and Mathematics, KU Undergraduate Research Fellow, KU International Excellence Award Scholar. |
| Michael Oliver  | McNair Scholar, Senior in Computer Science, System Administrator at Institute for Information Sciences. |
| Shaan Bawa      | Freshman in Computer Science, Hixson Scholar.                             |
| Wazeen Hoq      | Sophomore in Behavioral Neuroscience and Mathematics.                     |
| Ky Le           | Senior in Computer Science.                                               |
| Hope Wagner           | Freshman in Mechanical Engineering.                                               |
