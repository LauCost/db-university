Query con Join

1- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

SELECT * FROM students INNER JOIN degrees ON degrees.name = 'Corso di Laurea in Economia';

2- Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze

SELECT * FROM courses INNER JOIN departments ON departments.name = 'Dipartimento di Neuroscienze';

3- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

SELECT * FROM courses INNER JOIN teachers ON teachers.id = 44;

4- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

SELECT `students`.`name`,`students`.`surname`, `degrees`.`name`,`departments`.`name` FROM `students` INNER JOIN `degrees` ON `degree_id` = `degrees`.`id` INNER JOIN `departments` ON `degrees`.`department_id`= `departments`.`id` ORDER BY `students`.`surname` , `students`.`name`;

5- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
