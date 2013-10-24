### What is this

Cup was made to solve a simple problem...making sure services/processes stay running. You can cron this to run at any interval you want and tell it what to check on.
Cup will try once to launch a service if its not running. If it has problems, it emails/notifies you...and of course it logs.

### Requirements

Bash, awk, find, pgrep, date, curl (you should probably have these already)

### How to use it

Clone this repo, edit the conf file (which is pretty self-explanatory), and place this in cron. I recommend every minute or 5 minutes using something like ```*/5 * * * * /home/user/cup/cup```

Want to run it like a daemon? Check out the daemon command most linux distros have. I do something like this:

```daemon -D /scripts/cup -r --attempts=1 --delay=10 --name=cup /scripts/cup/cup```

^which will actually run it every 10 seconds...dont worry, it doesn't fork, it just runs it again when the previous instance finishes!

#### Notes

Cup was meant to be run as root so it can start services if they are down.
Keep in mind that process name is the name the of the service in top/ps etc... where program name is the init script for the service e.g.  /etc/init.d/ssh
