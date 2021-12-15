Query con Group by

1- Contare quanti iscritti ci sono stati ogni anno

SELECT COUNT(id), YEAR(enrolment_date) FROM students GROUP BY YEAR(enrolment_date);

2- Contare gli insegnanti che hanno l'ufficio nello stesso edificio

SELECT COUNT(id), office_address FROM teachers GROUP BY office_address;

3- Calcolare la media dei voti di ogni appello d'esame

SELECT exam_id, AVG(vote) FROM exam_student GROUP BY exam_id;

4- Contare quanti corsi di laurea ci sono per ogni dipartimento

SELECT COUNT(id), department_id FROM degrees GROUP BY department_id;






Query con Join

1- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT * FROM students INNER JOIN degrees ON degrees.name = 'Corso di Laurea in Economia';

2- Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze

SELECT * FROM courses INNER JOIN departments ON departments.name = 'Dipartimento di Neuroscienze';

3- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT * FROM courses INNER JOIN teachers ON teachers.id = 44;

4- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT students.name,students.surname, degrees.name,departments.name FROM students INNER JOIN degrees ON degree_id = degrees.id INNER JOIN departments ON `degrees.department_id = departments.id ORDER BY students.surname , students.name;

5- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

SELECT degrees.name, courses.name, teachers.name, teachers.surname FROM degrees
INNER JOIN courses ON degrees.id = courses.degree_id INNER JOIN course_teacher ON courses.id = course_teacher course_id INNER JOIN teachers ON teachers.id = course_teacher.teacher_id;

6- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

SELECT teachers.name, teachers.surname, departments.name FROM course_teacher INNER JOIN teachers ON course_teacher.teacher_id = teachers.id INNER JOIN courses ON course_teacher.course_id = courses.id INNER JOIN degrees ON courses.degree_id= degrees.id INNER JOIN departments ON degrees.department_id = departments.id WHERE departments.name = 'Dipartimento di matematica';