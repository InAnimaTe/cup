### What is this

Cup was made to solve a simple problem...making sure services/processes stay running. You can cron this to run at any interval you want and tell it what to check on.
Cup will try once to launch a service if its not running. If it has problems, it emails you...and of course it logs.

### How to use it

Clone this repo, edit the conf file (which is pretty self-explanatory), and place this in cron. I recommend every minute or 5 minutes using something like ```*/5 * * * * /home/user/cup/cup```

#### Notes

Keep in mind that process name is the name the of the service in top/ps etc... where program name is the init script for the service e.g.  /etc/init.d/ssh
