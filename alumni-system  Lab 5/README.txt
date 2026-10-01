ALUMNI REGISTRATION SYSTEM — SETUP INSTRUCTIONS
=================================================

1. Copy this whole "alumni-system" folder into:
   C:\xampp\htdocs\alumni-system

2. Start Apache and MySQL from the XAMPP Control Panel.

3. Open http://localhost/phpmyadmin in your browser.
   - Import schema.sql (or run its SQL in the SQL tab) to create the
     `alumni_system` database and the `alumni` table.

4. If your MySQL root user has a password, edit db.php and set the
   $password variable accordingly (it is empty by default, XAMPP default).

5. Open http://localhost/alumni-system/index.html to fill and submit the
   registration form.

6. Open http://localhost/alumni-system/alumni.php to view the alumni
   directory (all registered records).

FILES
-----
index.html    - Registration form (frontend)
style.css     - Styling for the form
register.php  - Backend: validates input, hashes password, inserts record
db.php        - MySQL connection (mysqli)
alumni.php    - Displays all registered alumni in a table
schema.sql    - SQL to create the database and table

NOTES
-----
- Passwords are hashed with password_hash() before storage — never
  stored as plain text.
- register.php uses prepared statements (bind_param) to prevent SQL
  injection.
- Email is UNIQUE in the database; duplicate registrations are rejected.
- Always access PHP files via http://localhost/... — do not double-click
  to open them directly, or PHP will not execute.
