Curriculum Reports allow for data sets to be summarized on-screen and downloaded. These are created at run-time for quick access.

Previously, native Ilios reports (`"Subject Reports"`) were course-specific, and would allow the review of data from a single course in the cases where course is the object selected. 

With Curriculum Reports, you may select any number of courses, from any available school, curriculum, and year, to generate a report showing: School, Course, Session, Session Type, Objective, Instructors, First Offering (date of instruction delivery), and Hours (total learner exposure). 

This allows for the creation of reports by phase, theme, or any portion desired of the curriculum, or the entire curriculum, or even multiple curricula if your implementation is tracking more than one. Additionally, these reports can be saved, shared, and replicated to assist in deeper analytics.

# Select Courses 

The first step in generating a report using the new self-service "Curriculum Reports" interface is to select one or more courses to be included in the output.

![curriculum reports - start](../images/reports/curriculum_reports_start.png)

## Courses Chosen

In the screen shot below, two courses have been chosen. 

![courses chosen](../images/reports/courses_chosen.png)

## Options

Currently (as of December 2025), we are offering four options for report output. More will be offered soon. 

1.  Session Objectives 
2.  Session Offerings
3.  Learner Groups
4.  Instructional Time

The available buttons perform the actions of copying a shareable link to a generated report or running the report for the current user.

After the report gets run, a download button appears for the user to export the data (in .csv format) to a location of their choice.

## Buttons Shown

The "copy link" and "run report" buttons are shown below. Hopefully it is obvious in the "courses chosen" image above that these buttons are available at the upper right portion of the screen even though that image does not specifically indicate their existence.

![copy and run buttons](../images/reports/first_two_buttons.png)

# View Results

After clicking the "Run" button, the screen will display a progress bar briefly and then present the user with the "Results Summary" screen where the data gets summarized and becomes available for download.

## Results Summary

The "copy link" button remains in this view, along with a "close" button just to close this screen and return to design view at the root of "Curriculum Reports". The courses are hyperlinked as indicted in the image, along with the download button.

![results summary](../images/reports/results_summary.png)

## Download Results

If the download button is utilized, the user will be prompted like any other downloaded file as to where the .csv output is to be stored.

The files will be downloaded with the following names ("objectives.csv" or "learner-groups.csv"). It is recommended to change the file names after downloading the data in order to keep everything straightened out. The names will download with file names such as "objectives(1).csv" and then "objectives(2)csv" if this is not done. This is for an output of the Objectives reports as an example. 

## Copy Report 

As shown above, there are two buttons available either when viewing the results or before running the report. One of these buttons is used to copy a curriculum report. What is being copied in this case is a URL link to this report. The parameters are all included in the URL so a receiving user (with permissions in the system) can run the report and view / download the data without having to painstakingly choose all of the courses and report type themselves. It can save a lot of time and makes these report shareable.

The URL is copied to the user's clipboard to be distrubted using whatever technique they choose to use - typically email or other message sending application.

# Output Fields 

The Results Summary displays some informational summaries - rolled up data corresponding to the results of running the report. The downloaded .csv files, which can be opened and modified in Excel or other programs contains the detailed information at a much more granular level.

The two types of reports currently available contain the following fields included in the downloaded .csv files. When finished reviewing and / or downloading data, click "Close" to return to Curriculum Reports to run another or navigate elsewhere. You can keep the same selection previously applied as far as courses are concerned or clear all values by clicking "Select All or None" twice (if some are selected) until the check box has been cleared of value.

**NOTE:** One or more courses need to be selected before selecting one of the reports - the outputs of the downlaoded files are detailed below. The screen initially shows a rolled up summary of the information included in more detail in the download file.

The following fields are included in the output on the .csv download file. Each report has its own naming conventions. These will be covered in each report's section below.

## Session Objectives Report

* Course
* Session 
* Session Type
* Objective - session objective - one per row
* Instructors - combined into one field and row per session
* First Offering - date of first offering for any given session
* Hours - duration of offering if applicable
* Web Link - full URL to the session in Ilios

## Session Offeringe Report 

* Course 
* Year - academic year of instruction
* Session
* Offering Date
* Instructors - combined into one field and row per offering
* Learner Groups - combined into one field and row per offering
* Web Link - URL to session in courses and sessions

## Learner Groups Report

* ID - refers to the `course_id` value in the database
* Course 
* Year - academic year of instruction
* Session 
* First Offering - date of first offering for any given session
* Instructors - combined into one field and row per session 
* Learner Group - name / title of attached learner group
* Web Link - full URL to the session in Ilios

## Instructional Time Report

* Course
* Session
* Session Type
* Date (offering date)
* Name (instructor name)
* Minutes (offering duration)
* Web Link (URL to session in courses and sessions)



