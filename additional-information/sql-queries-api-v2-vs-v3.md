# SQL Queries \(API v2 vs v3\)

This page is here to highlight SQL query syntax differences illustrating the changes made to the Ilios database schema. This happens along with our switching of the API from the old version \(v2\) to the new version \(v3\).

The database schema you know and love will be available until the end of the year. We have made some changes to make retrieving data from Ilios easier, especially regarding Course, Session, and Program Year Objectives. There are other small changes, but the primary changes were made in the realm of Objectives.

```text
/** This is for new and old syntaxes for retrieving Objective records 
from Ilios -- going to use a place holder for course_id [course_id]
any valid course ID can be used **/

/** new method - retrieve course objectives **/
/** only need to query one table `course_x_objective` **/
SELECT course_objective_id, 
title FROM course_x_objective WHERE course_id = [course_id];

/** old method - course objectives **/
SELECT o.objective_id, o.title FROM objective o 
JOIN course_x_objective cxo ON cxo.objective_id = o.objective_id
WHERE cxo.course_id = [course_id];
```

#### Tables Affected - Course Objective Query



