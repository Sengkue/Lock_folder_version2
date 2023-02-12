@ECHO OFF

title Folder Locker

set "password=secret_password"

if EXIST "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" goto UNLOCK

if NOT EXIST secured goto MDLOCKER

:CONFIRM

echo Are you sure you want to lock the secured folder (Y/N)?

set/p "cho=>"

if /i "%cho%"=="Y" goto LOCK

if /i "%cho%"=="N" goto END

echo Invalid choice.

goto CONFIRM

:LOCK

ren secured "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

attrib +h +s +r +i "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

echo The folder has been locked.

goto END

:UNLOCK

echo Enter the password to unlock the folder:

set/p "input_pass=>"

if NOT "%input_pass%"=="%password%" goto FAIL

attrib -h -s "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}"

ren "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" secured

echo The folder has been unlocked.

goto END

:FAIL

echo Invalid password.

goto UNLOCK

:MDLOCKER

md secured

echo The folder has been created.

goto END

:END
