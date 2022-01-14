# Timetable Generator
A Genetic Algorithm based Timetable Schedule Generator, that can be used by University and College Management. This allows the faculties to enter the Couse Details, Teacher Details, and Students Registered for examination. The Program runs a Genetic Algorithm to find the timetable of the examination, alongside student seating plans, room allocations, and faculty invigilation allottment.
## Dataset
The dataset used for this problem consists of CSV files for Students, Course, Course Registrations, and Teachers. The dataset provided many clashes in the Course Registrations. The problem is to find the timetable that can minimize all the constraints of the problem.
## Algorithm Details
### Encoding
The GA encodes the problem domain as follows: Each chromosome has a number of genes. Each gene encodes the data [course code, slot, room, teacher, students] in binary. The final individual is an array of such genes
### Population Generation
The GA generates the population by randomly sampling from the dataset, and ensures that a good enough population with diverse chromosome are generated so that the crossovers and mutations may produce good solutions.
### Fitness Functions
The GA uses the fitness function to decode the binary string of each gene, and then assign a score to it depending on the hard and soft constraints, and their appropriate weights. The fitness starts from 10000, and gradually reduces as each rule deducts a score.
### Parent Selection
The GA uses Roulette wheel selection for parent selection. This is done to ensure that a good amount of diversity is introduced in the parents that are selected. The selection is done until the parents selected are equal in number to the population.
### Crossovers
The GA uses 2 types of crossovers, single-point for shuffling genes without changing anything in the binary, and (uniform + selected) crossover, where two genes from parents are selected and only a part of the binary string is crossover. This is to ensure that the offspring generated are not losing the good attributes of their parents. The GA ensures that the crossover is always resulting in a better fitness than its parents, otherwise it keeps doing the crossover and mutation. The crossover probability and the random selection of parents ensures that diversity is included in the GA
### Mutations
The mutation selected is selected mutation, where only a part of the selected gene string is mutated, to ensure that overflow may not occur or that an offspring mutates to get out of the problem domain. The GA also uses random restarts to avoid plateaus and local maxima. This has proven to produce good results.
### Results
We have found that since the problem solution space is almost infinite, a large number of individuals and generations are required in order to reach a feasible solution. The dataset provided and the solution provided was on 100 Individuals with 500 Iterations and it reached a fitness of 9880.
## Usage
Use the Jupyter notebook provided in the `source.ipynb` file. It contains all the codes and cells to execute and use the script. The dataset is given in the `dataset/` folders, that can be tailored according to a particular use case. 
