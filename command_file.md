1- Switch to the postgres Linux user:

sudo su - postgres

2- Connect to the PostgreSQL (Odoo’s database) shell to modify the database.

psql


3- If you don't remember the name of your Odoo database (you set it when you created your Admin user), use the following command to list all the databases and accociated users. 

\l


4- Search for the odoo user and the associated database name. The latter is the name you need.


5- Once you know the database name, connect to the Odoo database:

\c test


Note: change test to the actual name of your Odoo database.

 

6 - Now we need to change the password of the Admin user. If you don’t remember the user’s email value (which is used as the login), execute the following command to get a list of all user logins.

select login from res_users;


Find your email in that list.

 

7- Finally, change the password value of the Admin user to the newly generated one:

update res_users set password = 'new_hashed_password' where login = 'your@email.com';

Note: change your@email.com to your actual email value. Change new_hashed_password to that long string of text that you copied/wrote down earlier. Both values should remain wrapped in single quotation marks.

 

Exit the database:

\q
 

Congratulations! You will now be able to log in to your Admin account with the new password. 
