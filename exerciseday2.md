# JOIN
1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT *
FROM students
JOIN degrees 
ON students.degree_id = degrees.id
WHERE degrees.name = "Corso di Laurea in Economia"

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

SELECT *
FROM degrees
JOIN departments 
ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Neuroscienze'
AND degrees.level = 'magistrale';

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT *
FROM courses
JOIN course_teacher 
ON courses.id = course_teacher.course_id
JOIN teachers 
ON course_teacher.teacher_id = teachers.id
WHERE teachers.id = 44;

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome

SELECT *
FROM students
JOIN degrees ON students.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
ORDER BY students.surname, students.name;

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT *
FROM degrees
JOIN courses ON degrees.id = courses.degree_id
JOIN course_teacher ON courses.id = course_teacher.course_id
JOIN teachers ON course_teacher.teacher_id = teachers.id;

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)

SELECT DISTINCT teachers.name, teachers.surname
FROM departments
JOIN degrees ON degrees.department_id = departments.id
JOIN courses ON courses.degree_id = degrees.id
JOIN course_teacher ON course_teacher.course_id = courses.id
JOIN teachers ON course_teacher.teacher_id = teachers.id
WHERE departments.name = 'Dipartimento di Matematica';

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.

# SELECT
1. Selezionare tutti gli studenti nati nel 1990 (160)

SELECT *
FROM students
WHERE YEAR(date_of_birth) = 1990;

2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

SELECT *
FROM courses
WHERE cfu > 10;

3. Selezionare tutti gli studenti che hanno più di 30 anni

4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
laurea (286)

SELECT *
FROM courses
WHERE period = 'I semestre'
AND year = 1;

5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)

6. Selezionare tutti i corsi di laurea magistrale (38)

SELECT *
FROM degrees
WHERE level = 'magistrale';

7. Da quanti dipartimenti è composta l'università? (12)

SELECT COUNT(*)
FROM departments;

8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT COUNT(*)
FROM teachers
WHERE phone IS NULL;