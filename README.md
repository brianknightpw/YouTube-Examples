# YouTube-Examples
Examples from Brian on YouTube

Learn with the Nerds Events

•	Power Apps Cheat Sheet: https://pragmaticworks.com/resources/cheat-sheets/power-apps-cheat-sheet-page/
•	Free Developer License: https://powerapps.microsoft.com/en-us/developerplan/ 
Crib Notes
Dataverse
•	Go to https://make.powerapps.com
•	Go to Solutions and create a new solution called “University Honors Program”
•	Create a Publisher called LWTN. Display Name, Name and Prefix of LWTN
•	Create Application table (with attachments)
1.	Application Number (Auto Number)
2.	SAT Score – Whole Number
3.	ACT Score – Whole Number
4.	GPA – Decimal
5.	Applicant – Lookup (Contact)
6.	Parent Alumni – Yes/No
7.	Parent Graduation Year – Whole Number
8.	Parent Name - Text
9.	Application Status – Choice (Pending, Rejected, Approved)
•	Create Mentor table (with attachments)
1.	Mentor Name – Text 
2.	Relationship – Choice (Parent, Friend, Teacher, Co-Worker, Other)
3.	Application – Lookup (Application)
•	Create the forms/views for Mentor
1.	Clone Mentor form to Portal Mentor Form 
	Remove Application
•	Create the forms/views for Application
1.	Create a new tab for Mentor Info (Subgrid: Mentor) 
2.	Create a new tab for Alumni Info (Parent Graduation Year, Parent Name
3.	Clone the Main form to a new form called Portal Application Form
	Remove Application Status
	Remove Applicant
•	Create a Model-Driven app (Modern Mode) with the Contact, Mentor and Application table
Portal
•	Back at https://make.powerapps.com. 
•	Open the Portal Management app, Edit the Portal you created earlier and open the Model-Driven Application you created earlier 
•	Create a new page Applications and change the template to Page with Title. Set the role to Authenticated Users
•	Add a List named Application List to page and point it to Applications and Active Application view. 
•	Create a new subpage under Applications called New Application
1.	Turn off Captcha
•	Go to Portal Management
1.	Basic Forms  New Application
	Additional Settings 
•	Check Associate Current Portal User and select Applicant for Portal User Lookup Column
•	Check Attach File
•	Attach File Storage Location: Notes
•	Attach File Option: Notes
•	Label: Upload Your Government ID
•	Try the app
•	Why is the Upload not there?
1.	Add Child Permission under Application to Notes

Advanced Form
•	Create in Portal Management
1.	Step 1 – 
	Source Type : Current Portal User
	Check Associate Current Portal User on Insert as before
	Additional Functionality – Check Attach File as before
2.	2 - Mentor Info
	Source Type: Result from a Previous Step
3.	Remove form from New Application and replace with: 
{% webform name:'Application Advanced Form'%} 
4.	Create a Basic Form for Mentor
5.	Go back to Advanced Form Step 2
	Go to Related  Metadata
	Type: Subgrid
	Click Create and link it to the new Mentor form
6.	If time allows
	Create a new Web Form Step (tab for the alumni info)
	Create a new Web Form Step (Conditional)
	lwtn_parentalumni = true (may vary if you have a different prefix)

