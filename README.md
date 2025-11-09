# Operational-Performance-Analysis-of-a-Cinema-Ticketing-System
This project models a cinema's single-server queueing system to analyze its performance and its a part of my ie306 (System Simulation) class

The core simulation engine, including the Linear Congruential Generator (LCG) for random number generation and the event-scheduling algorithm, was built entirely from scratch using only standard Python libraries, demonstrating a deep understanding of the underlying analytical mechanics.

1. Project Context & Business Problem
Academic Context
This analysis was developed for my IE 306: Systems Simulation course at Boğaziçi University with my friend Miray Köse. The objective was to apply theoretical simulation concepts to a realistic business problem. The original academic assignment file (IE306_Assignment2_2025.pdf) is included in this repository for reference.


2. Methodology & "From-Scratch" Engine
I developed a discrete-event simulation (DES) model in Python to mirror the client's operations. The system was modeled as a single-server queue (M/G/1) and run for 4 independent replications of a 7-day period to ensure statistically stable results.

A key challenge of this project was the requirement to build the entire simulation engine from the ground up, proving a fundamental understanding of the statistical models.

Core Engine (No external libraries):

Linear Congruential Generator (LCG): Implemented from scratch to generate uniform random numbers (U(0, 1)).

Random Variate Generation: Used the Inverse Transform Method (ITM) to generate stochastic inputs from the LCG's output (e.g., Exponential for inter-arrival times, Uniform for service times).

Event-Scheduling Algorithm: Managed the Future Event List (FEL) manually using Python lists, handling all core event logic (arrival, service completion, end-of-day).

3. Phase 1: Performance Analytics & Key Findings
The "Grand Average" results from the 7-day, 4-replication simulation run provide a clear, data-driven picture of the system's baseline performance.

<img width="1271" height="244" alt="image" src="https://github.com/user-attachments/assets/18181525-1234-45c7-854e-dbca92876cb1" />

| Metric | Grand Average (1-Server Baseline) | Business Implication |
| :--- | :--- | :--- |
| **Server Utilization** | `42.82%` | ** The server is idle for over 57% of the time. |
| **Avg. Wait Time (Lucky)** | `1.19 minutes` | Extremely low. Customers are not waiting in long queues. |
| **Avg. Queue Length** | `0.16 customers` | The queue is almost always empty. |
| **Avg. Tickets Sold** | `140.89 / 250` | The cinema is failing to sell ~44% of its capacity. |
| **Avg. Unlucky Customers** | `0.18 per day` | Virtually zero customers are turned away due to a sell-out. |




