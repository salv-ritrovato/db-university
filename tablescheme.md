## Table: departments

- id INT PK AI NN UQ
- name VARCHAR NN
- head_of_department VARCHAR
- email VARCHAR
- phone VARCHAR

## Table: degrees

- id BIGINT PK AI NN UQ
- department_id FK INT NN
- name VARCHAR NN
- website VARCHAR

## Table: courses

- id BIGINT PK AI NN UQ
- degree_id FK INT NN
- name VARCHAR NN
- website VARCHAR

## Table: teachers

- id BIGINT PK AI NN UQ
- name VARCHAR NN
- email VARCHAR

## Table: course_teacher

- course_id FK INT
- teacher_id FK INT

## Table: students

- id BIGINT PK AI NN UQ
- name VARCHAR NN
- email VARCHAR
- degree_id FK INT NN

## Table: exams

- id BIGINT PK AI NN UQ
- course_id FK INT NN
- date DATE NN

## Table: exam_registrations

- student_id FK INT
- exam_id FK INT
- grade INT

# DEPARTMENTS -- DEGREES (ONE-TO-MANY)
# DEGREES -- COURSES (ONE-TO-MANY)
# COURSES -- TEACHERS (MANY-TO-MANY)
# STUDENTS -- DEGREES (MANY-TO-ONE)
# COURSES -- EXAMS (ONE-TO-MANY)
# STUDENTS -- EXAMS (MANY-TO-MANY)