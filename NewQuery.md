# Contare quanti iscritti ci sono stati ogni anno

```sql
SELECT YEAR(`enrolment_date`) AS `year`, Count(*) AS `num_students`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY `year`;
```

# Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```sql
SELECT `office_address` AS `address`, Count(*) AS `num_teachers`
FROM `teachers`
GROUP BY `office_address`
ORDER BY `address`;

```

# Calcolare la media dei voti di ogni appello d'esame

```sql
SELECT AVG(`vote`) AS `media_voto`, `exam_id`AS `id_esame`
FROM `exam_student`
GROUP BY `exam_id`
```


# Contare quanti corsi di laurea ci sono per ogni dipartimento
```sql
SELECT count(*) `corsi`, `degree_id` AS `dipartimenti`
FROM `courses`
GROUP BY `degree_id`
```

# Joins:
# Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
```sql
SELECT `students`.*
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```
# Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
```sql
SELECT `degrees`.*
FROM `degrees`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `degrees`.`level` = 'Magistrale'
AND `departments`.`name` = 'Dipartimento di Neuroscienze'
```

# Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
```sql
SELECT `courses`.`name` AS `Nome Corso`
FROM `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = '44'
```


# Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
```sql
SELECT `students`.*, `departments`.`name` AS `nome_dipartimento`, `degrees`.`name` AS `corsi di larurea`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` 
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname` ASC
```