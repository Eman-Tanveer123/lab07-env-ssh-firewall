# Challenge: Environment Audit and Ping Block

## Job 1: System Variables Audit
Commands Used:
printenv | grep '^PATH='
printenv | grep '^LANG='
printenv | grep '^PWD='

Values:
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/eman-tanveer123
LANG=en_US.UTF-8
PWD=/home/eman-tanveer123/lab07-env-ssh-firewall

## Job 2: Temporary Student Variables
Commands Used:
export STUDENT_NAME="Eman Tanveer"
export STUDENT_ROLL_NUMBER="FA24B1-SE-053"
export STUDENT_SEMESTER="5th"
printenv | grep '^STUDENT_'

Output:
STUDENT_NAME=Eman Tanveer
STUDENT_ROLL_NUMBER=FA24B1-SE-053
STUDENT_SEMESTER=5th

Proof after exit: After logging out and logging in back, 'printenv | grep ^STUDENT_' returned nothing because export only sets temporary variables for the current session.

## Job 3: Permanent Student Variables
Commands Used:
echo -e 'export STUDENT_NAME="Eman Tanveer"\nexport STUDENT_ROLL_NUMBER="FA24B1-SE-053"\nexport STUDENT_SEMESTER="5th"' >> ~/.bashrc
source ~/.bashrc
printenv | grep '^STUDENT_'

Proof after new login: The variables remain active in new sessions because they are loaded automatically from ~/.bashrc upon shell startup.

## Job 4: Ping Block and Allow
