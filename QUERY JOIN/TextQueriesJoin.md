# 1

```sql

SELECT * 
FROM `students`
INNER JOIN `degrees` ON  `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name`= "Corso di Laurea in Economia";

```
---

# 2

```sql

SELECT * 
FROM `degrees`
INNER JOIN `departments` ON  `degrees`.`department_id` = `departments`.`id`
WHERE `departments`.`name`= "Dipartimento di Neuroscienze"
AND `departments`.`level` = "magistrale";

```
---

# 3

```sql

SELECT * 
FROM `course_teacher`
INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
WHERE `course_teacher`.`teacher_id` = 44;

```
---

# 4

```sql

SELECT * 
FROM `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname` ASC, 
`students`.`name` ASC;

```
---

# 5

```sql

SELECT * 
FROM `degrees`
INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
ORDER BY `degrees`.`name` ASC;

```
---

# 6

```sql

SELECT * 
FROM `departments`
INNER JOIN `degrees` ON `departments`.`id` = `degrees`.`department_id`
INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `departments`.`name` = "Dipartimento di Matematica";

```
---

# 6

```sql

SELECT COUNT(*) AS esami_sostenuti, `exam_student`.`student_id`, `exam_student`.`exam_id`  
FROM `students`
INNER JOIN `exam_student` ON `students`.`id` = `exam_student`.`student_id`
WHERE `exam_student`.`vote` < 18
GROUP BY `exam_student`.`student_id` , `exam_student`.`exam_id`;

```