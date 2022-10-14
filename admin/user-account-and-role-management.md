# User Account And Role Management

Currently, there are two tools available in the Management Console: _**User Account Management**_, and _**Permissions**_. The default page is User Account Management, which provides alerts on accounts requiring administrative attention, as well as the default user search link.

## User Roles

Ilios provides for four distinct user roles which determine mode of access for a given user, in two broad categories of NON-STUDENTS (those who are not registered as students with the campus registrar) and STUDENTS (those who are). Any user may be assigned any combination of the roles.

### Non-Students

* _**Course Director:**_ The Course Director role provides for full editorial access to the system for the primary school of the user. It adds the user as an entity in the Course Director and Instructor lists for association. In the `user_role` table of the database, this role is identified with a value of 1.
* _**Instructor:**_ Any Ilios user can be added as an Instructor in Ilios. This association allows the Instructor to maintain their own offerings at a minimum (if they don't have higher access elsewhere). In the `user_role` table of the database, this role is identified with a value of 3.
* _**Developer (aka Administrator):**_ This role provides for full editorial access to the system for the primary school of the user. It does not add the user to any associative lists. Allows for access to the “Admin Console” as well as "Curriculum Inventory" from the Ilios flyout menu. In the `user_role` table of the database, this role is identified with a value of 2.

### Students

* _**Student:**_ The student role allows for the automatic ingestion from an external LDAP directory, and the association to any program cohort. Students may also be assigned additional, non-student roles, but their primary role will remain that of student. In the `user_role` table of the database, this role is identified with a value of 4.

### Former Students

* **Former Student:** The former student role allows for the additional attribute of “former student” to a given user, to identify those users who are graduates, or who were previously (but no longer) enrolled as learners. They remain in the database as students, along with all other assigned roles, but can now be tracked as graduates. In the `user_role` table of the database, this role is identified with a value of 9.

## User Account Management

The **User Account Management** console feature allows for:

* The resolution of conflicts between account data in Ilios, and in the campus directory of record
* The assignment of newly entered student accounts to their correct program cohorts
* The disabling of inactive or invalid accounts
* The management of existing accounts and their role assignments
* The creation of new non-student accounts

Ilios provides a basic LDAP interface to provide for the ingest and update of users into the system. This can be extended and customized as necessary by your institution. If used, this provides the data of record for all user accounts. For more information, please see the installation notes as well as the Ilios GitHub wiki. Users are defined in two broad groups: student records and non-student records.

Student records are those which are identified in the ingested records as currently enrolled individuals, whether active or not. These records are automatically loaded into Ilios if they are not already present. However, since many external directory systems do not always provide consistent program registration information which conforms to the needs of Ilios, once a student record is ingested it must be manually assigned to its correct program cohort.

This assignment is managed from the alert panel shown. Student records may be assigned individually or in bulk; there is no time constraint on assigning them, but until they are assigned and cleared from the alert panel, the students in question will not have access to their information in Ilios, and will not be tracked as part of the educational hours and activities within the curriculum.

Non-student records are those which are valid active records, (i.e. have a valid ID and email), but are not currently noted as enrolled. These records are not automatically ingested, but are reconciled against accounts which have been entered into Ilios already.

When there is a conflict between an Ilios account record and its parent record in the campus directory, this will appear on the Management Console. Each record may either be updated --- replacing the conflicting information with the data found in the external directory --- disabled, or ignored until the next ingest cycle. Any record that is found to be in conflict will remain in the alert panel until action is taken.

To manage existing accounts and their roles, go to the _**Management Console**_ and open the _**Manage User Accounts**_ link. An alert icon will display on the dashboard when there are accounts awaiting attention. Accounts requiring reconciliation will appear in the top alert panel on the Management console landing page, and students requiring cohort assignment in the bottom alert panel. If there are no items requiring attention, the default page will show the user search panel.

**Note:** When using the search panel, the default view of returned records will be from all available records in Ilios, regardless of School affiliation. However, creation of a new record will automatically associate the new record with the primary school affiliation of the current admin user.

### Resolving Account Conflicts

Accounts which appear to have a conflict with the registered data in the external directory will be listed in the alert panel; each will provide details including what points of data are in conflict.

Selecting to _**Disable**_ the account will freeze the account until further action is taken, preventing the user from accessing Ilios and removing them from select lists for further assignment, but will not change the historic Ilios record; selecting to Update will update the account with the information in the external directory; Selecting _**Leave As Is**_ will remove the account from the alert list until the next ingest cycle; not selecting an option will leave the account on the alert list, waiting for reconciliation. You may also set an individual account to be ignored by the reconciliation process; this is done on the individual user account detail page by selecting the option of _**"Exclude From Synch"**_.

### Assigning Student Accounts

For institutions running scheduled updates from an LDAP source, when new student records are found, they are immediately ingested into Ilios. The records must be assigned to their program cohorts manually.

A user will only see those student records for their own primary school affiliation in this list; records for other schools will be ingested, but are only currently manageable by admin users for that specific school. Only student records which have not been entered into Ilios and are unassigned to a specific cohort will appear on this list; if students have been manually entered via the Learner Groups page, the external record will be matched with it.

This assigns students to a “primary” cohort, which will be their parent cohort in the system. Both students and non-students may be assigned into any number of “secondary” cohorts.

### Disabling Accounts

The _**“disabling”**_ of an account is blocking the user’s access to Ilios. This means that a user who has been disabled will no longer be able to log in to the system, and instead will be alerted that their account has been disabled, and to contact the Ilios administrator for assistance. This is the default state for newly ingested student records until they have been assigned to a cohort. For Instructor and Director records, they will also be removed from the current selection lists in the system.

To disable an existing Ilios Account, search for the user account in question, and select them from the results list. From the available actions, choose _**“disable this account”**_ and click _**continue**_. The account is now disabled.

Similarly, for managing existing account roles, simply find the desired account, select the desired active roles for the user in question and click continue.

_\*_Ignoring Accounts for Directory Ingest and Reconciliation

An account may be set to be ignored by the reconciliation with external directory information; this provides for avoiding repeating alerts on accounts that may have information which is unavailable to the campus system, or which are specific to Ilios for any reason. Clicking the box labeled _**“Exclude this account from synchronization process”**_ will set the account to be ignored by the process.

### Account Creation

There are two methods of creating a user in Ilios: via the Management Console, or via csv file upload. To upload a csv list of instructors, go to the Instructor Groups page, create or open a group, and click on the “add new” button. To upload a csv list of students, go to the Learner Groups page, create or open a group, and click on the “add new” button. Please note that inputs must be formatted exactly as described, without any headers, and will not allow the upload of duplicate records. Each row in the csv must be as follows:

`Last Name, First Name, Middle Name, Phone, Email, Campus ID, Other ID`

Once uploaded, the users listed will be added to the instructor group or learner cohort in which you are working.

The other, preferred method of creating users in Ilios is to use the _**Management Console**_ search tool. When a search for a user is run, if no results are found in Ilios, the user is presented with the opportunity to create a new Ilios account.

Selecting _**“Create Account”**_ will bring up the template for entering a new account: The required fields are name, Campus ID, and email. These must match the official records in the directory for accuracy. Note that if internal authentication is not active, the username and password fields are disabled or not visible at all in more recent versions; these are only for use in situations where Ilios native authentication, rather than shibboleth, is in use. Passwords must adhere to a high security standard.

Please note that only non-student accounts may be created here. The account may later be associated with a learner record via external directory reconciliation as described above, but in general student accounts should only be entered into Ilios via external directory feed or via the Learner Groups page. Minimum and maximum lengths of the UC Id field may be set in the configuration file `config/ilios.php` as variable attributes. The default min and max values are each initially set to “9”, but can be modified in the file `web/application/config/[default.]ilios.php`.

There are three basic non-student roles available for assignment in Ilios: Developer, Director, and Instructor.

Assigning Developer privileges allows the user full editorial access to data for their primary school, but does not associate them with the curricular selection lists.

Assigning the role of Director will add the user to the select lists for Course and Program Directors and Instructors, and provide them editorial access to any material to which they are associated.

Assigning the role of Instructor will add the user to the select lists for Instructors, and provide them editorial access to any material to which they are associated.

Leaving a user without a role assignment provides them view access only; this is the default for student users ingested into the system.

If synchronizing with an external directory, user accounts will be checked against that store on a scheduled basis. To remove an individual account from that check, you may check the “Exclude this account from the synchronization process” box. The user account will then be ignored in checking for external changes or updates and the record will no longer appear as an exception.

### Cohort Assignment

Both students and non-students may be assigned into any number of “secondary” cohorts. Students may be assigned to secondary cohorts whether or not they have been assigned to a primary cohort. Secondary cohorts may be selected from any active program in any active school. Once assigned to a secondary cohort, a user may be managed in that cohort’s groups as would any learner.

To assign a user a secondary cohort, click the “edit” button beneath the user cohort information listing on their account information page. Select any available program cohort from the list provided in the picker, and save. The assignment will now be shown on the user’s page.

## Access Control and Permissions

Ilios provides a management interface to allow for the simple control of edit – level permissions for existing users and their access to curricular data. Combined with the option of joint program stewardship, these permissions provide an extremely powerful mechanism for creating and deploying interdisciplinary curricula.

By default, any existing non-student user will automatically have edit privileges to the curriculum for their assigned school. To assign school privileges, or to assign direct course privileges to users, the Management Console should be opened. It is accessed by clicking on the “Open Management Console” link in the Administration section of the Dashboard. Only users assigned admin control for the system (directors, developers) may access the console.

Clicking on the _**Manage Permissions**_ link will bring up a select box of all Ilios users, regardless of school association. You may select one or more users for permissions management.

Selecting one user will return a display of that user’s current access permissions to Schools, Programs and Courses.

**Schools:** This provides access to the curricula for multiple schools in an institutional deployment of Ilios. Roles and access levels are carried over from school to school for any given user.

**Programs:** Provides explicit admin access to the Programs listed, regardless of role or access level.

**Courses:** Provides explicit admin access to the Courses listed, regardless of role or access level.

Selecting the appropriate link will allow for the addition/removal of items from their access list. Assignment is immediate upon display of the course or program in the access lists. You may only modify one category of permissions at a time. To modify additional permissions, save your selection(s) and return to the permissions selection screen.

Only Programs and Courses for the current School being accessed by the admin user will be available for assignment.

Selecting more than one user will allow for the bulk assignment of permissions. When setting permissions for multiple users, please note:

* Only access permission may be granted. In order to remove access permission, you must access an individual user.
* If any permissions exist for any of the selected users in association with the selected Course or Program, they will be overwritten by the new assignment.

Assignment is immediate upon display of the course or program in the access lists.

Clicking the **“Finish”** button returns the user to the main **Management Console** Menu display.
