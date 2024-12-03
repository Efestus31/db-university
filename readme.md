# ttable name
- university
 ## Table Structure

 * Dipartimento
  * id_diaprtimeto | (PK INT AI)
  * nome | CHAR(30) NOT NULL
  * descrizione |  VARCHAR(200) NULL 

* Corso di Laurea
  * id_corso_laurea | (PK INT AI)
  * nome | CHAR(30) NOT NULL
  * id_dipartimento | INT
  * descrizione | VARCHAR(200) NULL

* Corso
  * id_corso | (PK INT AI)
  * nome | VARCHAR(20) NOT NULL
  * id_corso_laurea | INT
  * descrizione | VARCHAR(200) NULL
  * credito_formativo TINYINT

* Insegnante
   * id_insegnante | (PK INT AI)
   * nome | VARCHAR(20) NOT NULL
   * cognome | VARCHAR(20) NOT NULL
   * email | VARCHAR(20) NOT NULL
   * telefono | VARCHAR(15) NOT NULL

* Appello d'Esame
   * id_appello | (PK INT AI)
   * data | DATE
   * id_corso | INT
   * descrizione | VARCHAR(200) NULL

* Studente
   * id_studente | (PK INT AI)
   * nome | VARCHAR(20) NOT NULL
   * cognome | VARCHAR(20) NOT NULL
   * email | VARCHAR(20) NOT NULL
   * telefono | VARCHAR(15) NOT NULL
   * id_corso_laurea | INT




