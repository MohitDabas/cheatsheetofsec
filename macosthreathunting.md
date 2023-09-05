### How to do threat hunting on MacOS.

Get a list of user who has logged in
```
$l ast
```
Persistence Mechanism
```
# check /Library/Launchdaemon and .plist files content under /Library/Launchdaemon folder
# Cron Persistence under crontab
# check /etc/periodic folder
# check AppleScript
$ grep -A1 "AppleScript" <any .plist file>
# Check LoginHooks and LogoutHooks
$ sudo default read com.apple.loginwindow
#check /var/at folder for periodic jobs running
```

Network Connection and Process
```
$ netstat -na | egrep 'LISTEN|ESTABLISH'
$ lsof  -i
$ ps -p <pid>
# check for applications
$ lsappinfo list
# Investigate open files
$ lsof -i
# check proxy
$ scutil --proxy
```
System diagnose
```
$ sysdiagnose

```
