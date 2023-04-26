Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia SELECT * FROM students JOIN degrees ON degrees.id = students.degree_id WHERE degrees.name = 'Corso di Laurea in Economia';

Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze SELECT * FROM departments JOIN degrees ON degrees.department_id = departments.id WHERE degrees.name LIKE '%magistrale%' AND departments.name LIKE '%neuroscienze%';

Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44) SELECT * FROM courses JOIN course_teacher ON courses.id = course_teacher.teacher_id JOIN teachers ON teachers.id = course_teacher.course_id WHERE teachers.name LIKE 'Fulvio' AND teachers.surname LIKE 'Amato';

Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome SELECT degrees.name AS 'Corso di Laurea', departments.name AS 'Nome dipartimento', students.* FROM students JOIN degrees ON degrees.id = students.id JOIN departments ON departments.id = students.id ORDER BY students.surname

Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti SELECT * FROM degrees JOIN courses ON courses.degree_id = degrees.id JOIN course_teacher ON course_teacher.course_id = courses.id JOIN teachers ON course_teacher.teacher_id = teachers.id;

Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54) SELECT departments.*, teachers.name, teachers.surname FROM teachers JOIN course_teacher ON course_teacher.teacher_id = teachers.id JOIN courses ON course_teacher.course_id = courses.id JOIN degrees ON courses.degree_id = degrees.id JOIN departments ON degrees.department_id = departments.id WHERE departments.name = 'Dipartimento di Matematica'