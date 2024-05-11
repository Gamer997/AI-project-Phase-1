# Genetic Algorithm for University Course Scheduling

This project implements a genetic algorithm to generate schedules for university courses while satisfying various constraints and criteria.

## Problem Statement

The task is to develop a generic solution for generating schedules for university courses using a Genetic Algorithm. The algorithm must read data from provided files, adhere to specified constraints, and optimize additional criteria.

### Constraints

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

### Libraries Used

- Pandas: For data manipulation.
- NumPy: For array operations.
- Matplotlib: For data visualization.

### Data Loading

The provided CSV files are loaded using Pandas:

```python
import pandas as pd

courses = pd.read_csv('courses.csv')
students_courses = pd.read_csv('studentCourse.csv')
teachers_names = pd.read_csv('teachers.csv')
