# DLLAMA

Source code: [https://github.com/b4rtaz/distributed-llama](https://github.com/b4rtaz/distributed-llama)

## General Guidelines
For each task, teams will run a short, long, and leadboard prompt and report the tokens/s throughput (exact guidelines will be sent out once determined). The performance on short and long prompts will be evaluated internally, while the performance on the leaderboard prompt will be evaluated in comparison to the leaderboard consisting of all the teams that submit. If you have any questions, please ask in the Q&A section of the competition Discord!

## Task 1: Llama 3.1 8B Instruct Q40 (base model)
Teams will benchmark the Llama 3.1 8B Instruct Q40 model on provided prompts using the `dllama inference` mode, with 3 worker nodes (4 nodes total), 2 threads per node and a maximum sequence length of 4096. For this task, teams must use the Llama 3.1 8B Instruct Q40 model and tokenizer provided in the Distributed Llama repository with no changes to the source code. The results from this task will also serve as a baseline for Task 3.

## Task 2: Qwen 3 8B Q40 (base model)
Teams will benchmark the Qwen 3 8B Q40 model on provided prompts using the `dllama inference` mode, with 3 worker nodes (4 nodes total). For this task, teams must use the Qwen 3 8B Q40 model and tokenizer provided in the Distributed Llama repository with no changes to the source code; however, teams are allowed to change thread count, maximum sequence length, and other runtime parameters as long as the model, tokenizer, and source code remain unchanged. 

## Task 3: Llama 3.1 8B Instruct Q40 (optimized)
Teams will benchmark the Llama 3.1 8B Instruct Q40 model on provided prompts. For this task, teams are encouraged to explore possible optimization (such as modifications to the DLLAMA source code, alternative inference engines, or software/hardware advantages). Model throughput in this task will be evaluated in comparison to the teams' results in Task 1. For the leaderboard results, multinode runs are preferred and will be weighted accordingly. 

Teams will be required to submit code for this task (ex. a fork of the source code repository) with **well-documented** changes and explanations of the optimizations made. The teams' effort and approach to optimization will be taken into account during scoring. Code submissions must be made before benchmarking begins (detailed guidance to come). 

## Competition Instructions
Here is the full document: [https://single-board-cluster-competition.github.io/sbcc26-competition-site/files/SBCC26_D-LLAMA_Instructions.pdf](https://single-board-cluster-competition.github.io/sbcc26-competition-site/files/SBCC26_D-LLAMA_Instructions.pdf)