# 1
```sql

SELECT COUNT(*) AS num_studenti, YEAR(`enrolment_date`) AS anno_iscrizione
FROM `students`
GROUP BY YEAR(`enrolment_date`);

```
---

# 2
```sql

SELECT COUNT(*) AS num_insegnanti, `office_address` AS indirizzo_ufficio
FROM `teachers`
GROUP BY `office_address`;

```
---

# 3
```sql

SELECT ROUND(AVG(`vote`)) AS media_voti, `exam_id` AS num_appello
FROM `exam_student`
GROUP BY `exam_id`;

```
---

# 4
```sql

SELECT COUNT(*) AS num_corsi, `department_id` AS id_dipartimento
FROM `degrees`
GROUP BY `department_id`;

```