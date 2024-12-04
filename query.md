## Selezionare tutti gli studenti nati nel 1990 (160)
SELECT *
from `students`
where `date_of_birth` > '1990-01-01'
and `date_of_birth` < '1990-12-31';



## Selezionare tutti i corsi che valgono più di 10 crediti (479)
SELECT *
from `courses`
where `cfu` > '10'
;


## Selezionare tutti gli studenti che hanno più di 30 anni


SELECT *
from `students`
where `date_of_birth` > '1994-12-04'
;

## Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

SELECT *
from `courses`
where `period` = 'I semestre'
and `year` = '1'
;

## Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)


SELECT *
from `exams`
where `hour` > '14:00:00'
and `date` = '2020-06-20'
;

## Selezionare tutti i corsi di laurea magistrale (38)

SELECT *
from `degrees`
where `level` = 'Magistrale'
;

## Da quanti dipartimenti è composta l'università? (12)

SELECT *
from `departments`
;


## Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT *
from `teachers`
where `phone` = 'null'
;



## Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo degree_id, inserire un valore casuale)

INSERT INTO `university_db`.`students` (`degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) VALUES ('9999', 'Biagio', 'Antonelli', '1998-03-31', 'asklnsdsdnklfnksdf', '2024-12-05', '69420', 'biagiohd@gmail.com');

## Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

UPDATE `university_db`.`teachers` SET `office_number` = '126' WHERE (`id` = '58');

## Eliminare dalla tabella studenti il record creato precedentemente al punto 9

DELETE FROM `university_db`.`students` WHERE (`id` = '5002');