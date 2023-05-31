# Attach Learning Materials

Learning Materials can be attached at either the Course or Session level. Session level Learning Materials are those relevant to the subject matter being covered in that particular Session.

The first step is to select a Course and Session. These steps are covered in other parts of the guide.

### Attach Existing Learning Material to a Session

Before uploading a potential duplicate Learning Material file, link, or citation, you should search to if it already exists in the system. The key thing to remember here is that with Learning Materials, the relationship between the Learning Material and the Session is what is being created here. The same Learning Material can be attached to any number of Courses or Sessions.

#### Search for Learning Material (LM)

In this example, a search was performed for "Anatomy". Any of the resulting LM's can be attached to the Session by clicking anywhere in the area corresponding to the LM. 

![Search for "Anatomy"](../../images/attach_session_learning_material/search_for_session_lm.jpg)

After selecting the one as indicated above, it has now become attached to this Session as shown below.

**NOTE:** Now that there are multiple Learning Materials attached to the Session, the `Sort Materials` button is available and activated. This is covered later.

![LM now attached](../../images/attach_session_learning_material/attach_session_lm.jpg)

**See Results of Action and Modify Available Meta-Data**

As seen above, the file has now been attached to this Session. Click on the Display Name as shown by the green arrow to view more details and to modify some information about the attachment of this file to the Course. Many attributes of the file itself cannot be modified.

Refer to the screen shot below for details.

![Details shown](../../images/attach_session_learning_material/session_lm_details.jpg)

### Add New Learning Material to a Session

If a search has been performed and / or you know there is a newer version of a file or a new file, link, or citation to be uploaded, a new (not already in the system) Learning Material can be attached to any Session.

As listed below, there are three types of Learning Materials that can be uploaded and associated with any Session. This refers specifically to new files or links being uploaded.

* File
* Web Link
* Citation

![Select LM type](../../images/attach_session_learning_material/select_type.jpg)

!["File" selected](../../images/attach_session_learning_material/file_type_selected.jpg)

## Field Descriptions

* **Display Name:**  Free-text entry field of up to 60 characters. This name is what will display for users of the system to identify the Learning Materials.
* **Status:** Defaults to Final so it will be displayed to Learners.  Other options are "Draft" or "Revised".  Select from Draft, Revised, or Final. Only learning material with Final status will appear to learners in the system.  Final is the default for this Status.
* **Owner:** Defaults to the logged-in User. This is the user who has uploaded the Learning Materials. Non-editable. Provided by system.
* **Content Author:** The name of the person who created the content.  Free-text entry field of up to 80 characters to capture the actual author (if known) of the Learning Materials content.
* **User Role:** The role of the logged in user.  Defaults to Author - other options:  "Co-Author" or "Instructional Designer".
* **Description:** Free-text entry field to allow brief description of the Learning Material. For each unique use of a learning material, additional attributes may be added specific to that particular usage in the curriculum.
* **Copyright Permission:** Check that box after reading the description provided or write a rationale for using the file.  Checking of this box validates that you have permission to use the file being uploaded / attached to the Course.
* **Copyright Rationale:** If the Copyright Permission check box is not selected, this free text area is provided to add the logic behind the file's usage.
* **Choose File:** Launches a common file dialog box to attach any file obtainable on the user's computer.
* **File/Web Link/Citation:** For files: the physical or actual name of the uploaded file; for web links, the literal URL; for citations, the specific cite content.
* _**\[file size]:**_ For uploaded files, the size in KB. Non-editable. Provided by system.
* _**\[file type]:**_ - For uploaded files, the file mime-type / extension. Non-editable. Provided by system.  Allowed file types include:  aiff, avi, csv, doc, docx, gif, gz, html, jpeg, jpg, mov, mp3, mp4, mpg, pdf, png, ppt, pptx, rtf, swf, tar, tiff, txt, wav, word, wmv,  xls, xlsx, xml, zip.
* _**\[Upload date]:**_ Non-editable. Provided by system.

### Description

Learning Materials may be attached to courses or sessions. In order to be used with Ilios, materials must be tagged with certain additional information: a display name, owner and copyright information, MeSH vocabulary, etc. These elements are available for the user to input and edit when Learning Materials are loaded into the system.

Learning Materials are currently stored in an Ilios-specific file directory system. Items in the file directory may be attached to the curriculum directly by searching the repositories from the search interface for Learning Materials; if a desired item is not found, it may be uploaded directly to the server from the same interface.

**Protected information (eg. PII, ePHI etc.) should not be stored in Ilios.**

If there is a need to associate PHI with an Ilios session or course, it should be stored as a link to a secure location or citation, not added to the file system or entered directly.

Learning Materials may be physical objects (digital files) such as presentations, images, documents, video and sound recordings; they may be specific links to external data (websites, streaming media, or documents with a qualified URL); or they may be a citation for a 3rd party document, journal or reference.

Learning Materials may be given the status of “draft”, “final”, or “revised”. Only items stored with a status of “final” will be visible and accessible to learners; file owners may modify the status of their Learning Materials at any time. Only the owner of a file may modify its status.

Once Learning Materials are loaded to the system, their associated metadata attributes will be provided for review when they are selected.

In order to save a learning material in connection with a session or course, that session or course must first be saved to the database. Attempting to load learning materials to an unsaved session will generate an error alert.

**The current default size limit for learning material upload in Ilios is 100 MB.**

For lectures and other similar media, where the likely method of delivery is streaming/viewing from the server, rather than downloading, materials should be stored elsewhere, and the links to them should be the resources saved in Ilios.

#### Additional Fields (modified once the inital upload has been completed)

* _**Status:**_ Options for this are Final (appears to students as long there is no start or end date), Revised (same as Final for display purposes), and Draft (will not be displayed to students even if the current date lies between the start and end date (if it exists)).
* _**Required:**_ Identifies required vs. recommended materials in the context of use. Requirement is unique to a given instance of use for any Learning Materials.
* _**Instructional Notes:**_ Free-text entry field to allow commentary and instruction for the Learning Materials. Notes may be set to be visible to all users, or set as visible only to instructional faculty/staff. Notes provided are unique to a given instance of use for any Learning Materials.
* _**Show Notes to Students:**_ Indicates whether or not the optional notes entered in the Instructional Notes field (described above) are displayed to students or not.
* _**Timed Release**_ (Add Start Date / Add End Date): This allows for Learning Materials to be displayed to students for a specified range of dates. This can be either Start Date or End Date or both. The Learning Materials must be in a Final or Revised state to be displayed.
* _**MeSH Terms (Select MeSH for:):**_ Selected by searching the MeSH database. MeSH terms selected are unique to a given instance of use for any Learning Materials.
