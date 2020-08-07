# SQL Queries \(API v2 vs v3\)

This page is here to highlight SQL query syntax differences illustrating the changes made to the Ilios database schema. This happens along with our switching of the API from the old version \(v2\) to the new version \(v3\).

The database schema you know and love will be available until the end of the year. We have made some changes to make retrieving data from Ilios easier, especially regarding Course, Session, and Program Year Objectives. There are other small changes, but the primary changes were made in the realm of Objectives.

The table `objective_x_objective` will be completely removed at the end of 2020. The parental Objective relationships contained therein will be available elsewhere and documented here.

## Course Objectives

#### Sample SQL Query

```text
/** This is for new and old syntaxes for retrieving Objective records 
from Ilios -- going to use a place holder for course_id [course_id]
any valid course ID can be used **/

/** new method - API v3 - retrieve course objectives **/
/** only need to query one table `course_x_objective` **/
SELECT course_objective_id, title 
  FROM course_x_objective 
WHERE course_id = [course_id];

/** old method - API v2 - course objectives **/
SELECT o.objective_id, o.title 
  FROM objective o 
  JOIN course_x_objective cxo 
    ON cxo.objective_id = o.objective_id
WHERE cxo.course_id = [course_id];
```

### Tables Affected - Course Objective Query

In the Course Objective query outlined above, it is important to note the changes that are taking place with the design of the `course_x_objective` table in particular.

**v2 Schema** \(old\) - `course_x_objective`

![](../.gitbook/assets/crs_x_obj_old.png)

**v3 Schema** \(new\) - `course_x_objective`

![](../.gitbook/assets/crs_x_obj_new.png)

Additional fields that are available in `course_x_objective`in the new version of the database schema without having to join to other tables: `ancestor_id`, `title`, and `active`. **Title** is the big win here. Objectives are no longer stored in one location `objectives` and there is now no need to join to that table in order to retrieve Course Objectives.

## Session Objectives

#### Sample SQL Query

```text
/** new method - API v3 - session objectives **/
/** still need to join to session table which contains course ID **/
SELECT sxo.objective_id, sxo.title 
  FROM session_x_objective sxo
  JOIN session s on s.session_id = sxo.session_id 
WHERE s.course_id = [course_id];

/** old method - API v2 - session objectves **/
SELECT o.objective_id, o.title 
  FROM objective o 
  JOIN session_x_objective sxo ON sxo.objective_id = o.objective_id
  JOIN session s ON s.session_id = sxo.session_id
WHERE s.course_id = [course_id];
```

### Tables Affected - Session Objective Query

In the Session Objective query outlined above, it is important to note the changes that are taking place with the design of the `session_x_objective` table in particular. The only reason a join to the `session` table was performed is that we were running our query passed upon the  `course_id` field as a parameter and that field is contained in the `session` table.

**v2 Schema** \(old\) - `session_x_objective`

![](../.gitbook/assets/sess_x_obj_old.png)

**v3 Schema** \(new\) - `session_x_objective`

![](../.gitbook/assets/sess_x_obj_new.png)

Additional fields that are available in `session_x_objective` in the new version of the database schema without having to join to other tables: `ancestor_id`, `title`, and `active`. **Title** is the big win here. Objectives are no longer stored in one location `objectives` and there is now no need to join to that table in order to retrieve Session Objectives.

This also makes it easier to deal with Parent Objectives as we will soon see. 

## Program Year Objectives

#### Sample SQL Query

```text
/** new method - API v3 - program year objectives **/
/** only one table needed in query - no joins required **/
SELECT objective_id, title, competency_id 
  FROM program_year_x_objective 
  WHERE program_year_id = [program_year_id];
/** need to provide program_year_id - [program_year_id] **/

/** old method - API v2 - program year objectives **/
/** two tables needed - one join **/
/** need to get the objective text from the `objective` table
    rather than get it directly from `program_year_x_objective` **/
SELECT o.objective_id, o.title, o.competency_id 
  FROM objective o 
  JOIN program_year_x_objective pyxo 
    ON pyxo.objective_id = o.objective_id
  JOIN program_year py on py.program_year_id = pyxo.program_year_id
WHERE py.program_year_id = [program_year_id];
/** need to provide program_year_id - [program_year_id] **/

```

