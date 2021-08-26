Hi! Jerry here. This code is meant for Velo by Wix. This code here is for the Velo by Wix certification project where I was asked to create a Contact Holder website. 
The users should login using the built in wix-users system and should be able to access only the contacts they created. There should also be a built-in feature where the website
should send a birthday email to every single contact.

To start, I tried to tackle the birthday email. So, I first had to find an external API in which I could send an email, so I chose SendGrid API. I got an api key and put it into 
the built-in secrets manager. Then, I had to write the code for sending the email and put it in the file birthdayEmail,jsw in the backend. Then, I had to use the job scheduler, 
jobs.config, to schedule a cron expression that triggers everyday at 9am UTC. After I tested it and it worked, I then changed the code in birthdayEmail.jsw to check if any of the
contacts were celebrating a birthday in the collection I made, Contacts.

To allow people to create contacts, I created a create contact page as well as a dynamic page called "Contacts (All)" and "Contacts (ID)." On the create contact page, I made a 
form as well as a dataset on the page so that I could connect the input elements on the page to the "Contacts" content collection. THis allowed me to store the user's input data 
and to display it onto the Contacts (All) page. I also made it so that people had to be logged in in order to view the "Contacts (All)" page as well as creating a contact.

After that, on the Contacts (ID) page, I created a place where you could send an email to the contact. I created to input fields, the email subject and the email body, and a send 
email button that when clicked, would open the "Message" lightbox. it would also trigger the backend file, sendEmail.jsw, and would send an email using the values of the input 
fields to send an email to the contact.

Finally, I created a remove contact button on the Contacts (ID) page. When clicked, it would trigger the "Remove" lightbox which would have two buttons, a yes and cancel button. 
If the yes button was clicked, it would remove the current item of the collection, then it would redirect you to the Contacts (All) page. If the cancel button was pressed, then it
would just close the lightbox. 
