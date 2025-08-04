# File-Permissions-in-Linux
File permissions in Linux are defined for three types of users:

Owner (User)

Group

Others (World)

Each of these can have the following permissions:

r = read (4)

w = write (2)

x = execute (1)

Permissions are displayed as:

rwxrwxr-x

Where:

- rwx (first three) = owner permissions

- rwx (middle three) = group permissions

- r-x (last three) = others permissions

| User Type | Permission | Octal |
| --------- | ----------  -----  |
| Owner     | rwx        | 7     |
| Group     | rwx        | 7     |
| Others    | r-x        | 5     |

So the numeric (octal) representation is: 775

Flowchart for Understanding Permissions

START
  ↓
Who is accessing the file?
  ↓
┌────────────────────────────┐
│ Is it the Owner?           │───Yes───> Check Owner's permissions
│                            │
│             No             ↓
│ Is it a Group Member?      │───Yes───> Check Group's permissions
│                            │
│             No             ↓
│ Is it Others?              │───Yes───> Check Others' permissions
└────────────────────────────┘

Then:

If r → can read

If w → can write

If x → can execute

Apply chmod in a Python Script:

- import os
- file_path = "your_file.py"
- os.chmod(file_path, 0o775)

Replace "your_file.py" with the actual filename or path.


