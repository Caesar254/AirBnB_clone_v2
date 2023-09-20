To create users in MySQL, you can use SQL commands or MySQL's command-line tool. Here's a basic overview of how to create a user with privileges:

1. **Log into MySQL**: You'll need to log in as a user with sufficient privileges to create other users. You can use the `mysql` command-line tool for this:

   ```bash
   mysql -u your_username -p
   ```

   Replace `your_username` with the username you use to connect to MySQL. You'll be prompted to enter the password for this user.

2. **Create a User**: You can create a new user with the `CREATE USER` command. For example, to create a user named 'new_user' with a password 'password':

   ```sql
   CREATE USER 'new_user'@'localhost' IDENTIFIED BY 'password';
   ```

   - `'new_user'` is the username you want to create.
   - `'localhost'` specifies the host from which the user can connect. `'localhost'` means the user can only connect from the same machine where MySQL is running. You can replace it with the IP address or hostname if you want to allow connections from other locations.
   - `'password'` is the password for the user.

3. **Grant Privileges**: After creating the user, you'll typically want to grant them specific privileges on databases or tables. You can use the `GRANT` statement for this purpose. For example, to grant all privileges on a database 'your_database' to 'new_user':

   ```sql
   GRANT ALL PRIVILEGES ON your_database.* TO 'new_user'@'localhost';
   ```

   This gives the user 'new_user' full access to the 'your_database' database.

4. **Flush Privileges**: After granting privileges, you need to flush the privileges to apply the changes immediately:

   ```sql
   FLUSH PRIVILEGES;
   ```

5. **Exit MySQL**: You can exit the MySQL command-line tool by typing:

   ```sql
   EXIT;
   ```

That's it! You've created a new user in MySQL and granted them specific privileges. Remember to use strong passwords for your users and follow security best practices to protect your database.
