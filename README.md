# **University Course Scheduling Genetic Algorithm**

This project presents a genetic algorithm solution for generating schedules for university courses while satisfying various constraints and criteria. The implementation involves data loading, initial population generation, fitness calculation, selection, crossover, mutation, and iterations to evolve schedules that adhere to specified constraints and optimize additional criteria.

## Table of Contents
- [Problem Statement](#problem-statement)
    - [Constraints](#constraints)
- [Implementation](#implementation)
    - [Initial Population Generation](#initial-population-generation)
    - [Fitness Calculation](#fitness-calculation)
    - [Selection](#selection)
    - [Crossover](#crossover)
    - [Mutation](#mutation)
    - [Iterations](#iterations)
    - [Results Visualization](#results-visualization)
- [Conclusion](#conclusion)

## Problem Statement

The task is to develop a generic solution for generating schedules for university courses using a Genetic Algorithm. The algorithm must read data from provided files, adhere to specified constraints, and optimize additional criteria.

### Constraints
### Libraries Used

- Pandas: For data manipulation.
- NumPy: For array operations.
- Matplotlib: For data visualization.

#### Hard Constraints

- An exam must be scheduled for each course.
- Each student is enrolled in at least 3 courses. A student cannot give more than 1 exam at a time.
- Exams cannot be held on weekends.
- Exams must be held between 9 am and 5 pm.
- Each exam must be invigilated by a teacher. A teacher cannot invigilate two exams at the same time.
- A teacher cannot invigilate two exams in a row.

#### Soft Constraints

- All students and teachers shall have a break on Friday from 1-2.
- A student shall not give more than 1 exam consecutively.
- Prefer MG course exams before CS course exams.
- Optimize faculty break time.

## Implementation

### 1. Data Loading

The provided CSV files are loaded using Pandas:

```python
import pandas as pd

courses = pd.read_csv('courses.csv')
students_courses = pd.read_csv('studentCourse.csv')
teachers_names = pd.read_csv('teachers.csv')
```

### 2. Initial Population Generation

The initial population of schedules is generated randomly using a function `generate_random_schedule`. This function randomly assigns courses to teachers, classrooms, and time slots while ensuring that hard constraints are not violated.

### 3. Fitness Calculation

The fitness of each schedule is calculated based on constraints and criteria using the function `calculate_fitness`. This function evaluates the schedule's adherence to both hard constraints (such as ensuring an exam is scheduled for each course) and soft constraints (such as faculty break time optimization).

### 4. Selection

Roulette wheel selection is used to select the best schedules based on their fitness values. This method assigns a probability of selection to each schedule based on its fitness, and schedules with higher fitness have a higher chance of being selected as parents for crossover.

### 5. Crossover

Single-point crossover is applied to generate offspring from selected parent schedules. This process involves selecting a random crossover point and combining genetic material from two parent schedules to create two new offspring schedules.

### 6. Mutation

Mutation is optionally applied to introduce diversity into the population. This process involves randomly altering one or more elements of a schedule to explore new solutions and prevent premature convergence.

### 7. Iterations

The genetic algorithm iterates for a specified number of iterations, updating the population at each iteration. During each iteration, selection, crossover, and mutation are performed to evolve the population towards better solutions.

### 8. Results Visualization

The best schedule and its details are displayed in a table format. Additionally, fitness scores of all schedules are visualized using a line plot to track the optimization progress over iterations.

## 9. Conclusion

This implementation provides a robust solution for university course scheduling using a genetic algorithm, effectively satisfying constraints and optimizing criteria. The genetic algorithm approach offers flexibility and scalability, making it suitable for complex scheduling problems in educational institutions.

## Contributors
- [Abdul Ahad](https://github.com/AbdulahadIltaf)
- [Shahzaib Ali](https://github.com/Gamer997)

## Want to learn more about Genetic Algorithms

- [What are Genetic Algorithms](https://www.youtube.com/watch?v=XP2sFzp2Rig&ab_channel=argonaut)
- [Genetic Algorithms From Scratch in Python](https://machinelearningmastery.com/simple-genetic-algorithm-from-scratch-in-python/)
- [Genetic Algorithm Implementation in Python](https://towardsdatascience.com/introduction-to-genetic-algorithm-and-python-implementation-for-function-optimization-fd36bad58277)
