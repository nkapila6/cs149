# cs149

|| processin'

## About

Stanford CS149 (Fall 2023) is a deep dive into parallel computing: why modern hardware is parallel, how to program it, and how to make parallel code actually fast. The course covers multi-core CPUs, SIMD, GPUs, distributed systems, and specialized accelerators, with heavy emphasis on measuring and reasoning about performance.

Lore: Prof. Kayvon Fatahalian used to teach CMU 15-418, then moved to Stanford and created CS149. The 15-418 version is more comprehensive and has lecture recordings, but CS149's programming assignments are more modern and fashionable. A common path is to watch the 15-418 recordings but do the CS149 assignments. (Note: for Fall 2023, CS149 has its own recordings too - linked in the Lectures table.)

Course meta:

- Offered by: Stanford (sibling course: CMU 15-418)
- Instructors: Kayvon Fatahalian and Kunle Olukotun
- Prerequisites: Computer Architecture, C++
- Languages/tools: C++, ISPC, CUDA, Spark, OpenMP
- Difficulty: 5/5
- Class hours: ~150 hours
- YouTube playlist: https://youtube.com/playlist?list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp
- Reference walkthrough repo: https://github.com/PKUFlyingPig/CS149-parallel-computing

## Study Plan

Work top to bottom. Start each row after finishing the lecture in the first column.

| After | Type | Assignment | Prereq | Link | Local |
| --- | --- | --- | --- | --- | --- |
| Lec 4 | Prog | 1 - Analyzing Parallel Program Performance on a Quad-Core CPU | Lec 2, 3, 4 | https://github.com/stanford-cs149/asst1 | `assignments/asst1/` |
| Lec 4 | Written | 1 | - | https://gfxcourses.stanford.edu/cs149/fall23content/static/pdfs/written_asst1.pdf | `assignments/written/written_asst1.pdf` |
| Lec 6 | Prog | 2 - Scheduling Task Graphs on a Multi-Core CPU | Lec 5, 6 | https://github.com/stanford-cs149/asst2 | `assignments/asst2/` |
| Lec 7 | Prog | 3 - A Simple Renderer in CUDA (warmups from Lec 7, main from Lec 8) | Lec 7, 8 | https://github.com/stanford-cs149/asst3 | `assignments/asst3/` |
| Lec 8 | Written | 2 | - | https://gfxcourses.stanford.edu/cs149/fall23content/static/pdfs/written_asst2.pdf | `assignments/written/written_asst2.pdf` |
| Lec 10 | Prog | 4 - Chat149 - A Flash Attention Transformer DNN | Lec 7, 10 | https://github.com/stanford-cs149/cs149gpt | `assignments/asst4/` |
| Lec 11 | Written | 3 | - | https://gfxcourses.stanford.edu/cs149/fall23content/static/pdfs/written_asst3.pdf | `assignments/written/written_asst3.pdf` |
| Lec 13 | Prog | 5 (EC) - Big Graph Processing in OpenMP | Lec 6, 13 | https://github.com/stanford-cs149/biggraphs-ec | `assignments/asst5/` |
| Lec 13 | Written | 4 | - | https://gfxcourses.stanford.edu/cs149/fall23content/static/pdfs/written_asst4.pdf | `assignments/written/written_asst4.pdf` |
| Lec 16 | Written | 5 | - | https://gfxcourses.stanford.edu/cs149/fall23content/static/pdfs/written_asst5.pdf | `assignments/written/written_asst5.pdf` |

Finish any remaining lectures (17-18) while wrapping up open programming assignments. Assignments 1, 2, 3, and 5 use the same starter repos across years; only Assignment 4 differs (Fall 2023 is Chat149, Fall 2024 is a Trainium accelerator assignment).

## Lectures

| Lec | Topic | Description | Video |
| --- | --- | --- | --- |
| 1 | Why Parallelism? Why Efficiency? | Challenges of parallelizing code, motivations for parallel chips, processor basics | [Watch](https://www.youtube.com/watch?v=V1tINV2-9p4&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 2 | A Modern Multi-Core Processor | Forms of parallelism: multi-core, SIMD, and multi-threading | [Watch](https://www.youtube.com/watch?v=CKmNpAO5rS4&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 3 | Multi-core Arch Part II + ISPC Programming Abstractions | Finish multi-threaded, latency vs bandwidth, ISPC, abstraction vs implementation | [Watch](https://www.youtube.com/watch?v=F4bVSyz_jxo&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 4 | Parallel Programming Basics | Structuring parallel programs; data-parallel and shared address space models | [Watch](https://www.youtube.com/watch?v=0-ztm8SKq70&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 5 | Performance Optimization I: Work Distribution and Scheduling | Work distribution, overhead, Cilk work stealing | [Watch](https://www.youtube.com/watch?v=mmO2Ri_dJkk&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 6 | Performance Optimization II: Locality, Communication, and Contention | Message passing, async vs blocking, pipelining, arithmetic intensity, contention | [Watch](https://www.youtube.com/watch?v=Mhdny2JNhmc&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 7 | GPU Architecture and CUDA Programming | CUDA abstractions on modern GPUs | [Watch](https://www.youtube.com/watch?v=qQTDF0CBoxE&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 8 | Data-Parallel Thinking | map, reduce, scan, prefix sum, groupByKey | [Watch](https://www.youtube.com/watch?v=Ba3TqxSgnTk&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 9 | Distributed Data-Parallel Computing Using Spark | Producer-consumer locality, RDDs, Spark scheduling | [Watch](https://www.youtube.com/watch?v=jaMWmLq422U&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 10 | Efficiently Evaluating DNNs on GPUs | Scheduling DNN layers, mapping convs to matmul, transformers, layer fusion | [Watch](https://www.youtube.com/watch?v=qbKtU0X6-WU&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 11 | Cache Coherence | Memory coherence, MSI/MESI, false sharing | [Watch](https://www.youtube.com/watch?v=lrCfG2CPDEw&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 12 | Memory Consistency | Relaxed consistency models, acquire/release semantics | [Watch](https://www.youtube.com/watch?v=nFXWmo9MFiY&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 13 | Fine-Grained Synchronization and Lock-Free Programming | Fine-grained sync, lock-free queues/stacks, ABA problem, hazard pointers | [Watch](https://www.youtube.com/watch?v=GA1ObImqaMo&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 14 | Domain Specific Programming Languages | DSL motivation, case studies | [Watch](https://www.youtube.com/watch?v=sRuyBNxCkGQ&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 15 | Transactional Memory 1 | Motivation for transactions, design space | [Watch](https://www.youtube.com/watch?v=rFFf3WIJ7BA&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 16 | Transactional Memory 2 | STM and HTM implementations | [Watch](https://www.youtube.com/watch?v=Tbk1vnYLQqI&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 17 | Hardware Specialization | Energy-efficient computing, fixed-function, FPGAs, mobile SoCs | [Watch](https://www.youtube.com/watch?v=2tAb3EgyjNw&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |
| 18 | Accessing Memory + Course Wrap Up | How DRAM works, post-CS149 topic suggestions | [Watch](https://www.youtube.com/watch?v=J7v_ubArrno&list=PLoROMvodv4rMp7MTFr4hQsDEcX7Bx6Odp) |

The playlist also has a Midterm Review video (playlist video 14) between lecture 13 and 14, not listed above.

## Apple Silicon / Local Setup

Can you run the assignments on an Apple Silicon Mac (M-series)? Summary:

| Asst | Apple Silicon? | What you need |
| --- | --- | --- |
| 1 | Yes | macOS ISPC binary, Makefile tweaks (see `assignments/asst1/README_aarch64.md`). Missing: kmeans `data.dat` is on Stanford AFS, not public. |
| 2 | Yes | Nothing special, pure C++ with std::thread. Fully portable. |
| 3 | No | CUDA required. No Apple Silicon path. Use a cloud GPU box (Google Colab free T4, AWS g4dn, etc). |
| 4 | Maybe | ISPC Makefile tweaks like asst1, plus recompile `module_ref.so` from source (the shipped .so is x86 only). |
| 5 | Yes | `brew install libomp` and add libomp include/lib flags to the Makefile. Graph dataset is publicly downloadable (3GB). |

asst1 has a full ARM handout at `assignments/asst1/README_aarch64.md`. For asst1 programs 3 and 4, change `avx2-i32x8` to `neon-i32x8` and `x86-64` to `aarch64` in the Makefiles. ISPC emits 8-wide NEON instead of 8-wide AVX2 (same width, different ISA).
