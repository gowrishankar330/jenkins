if we forgot username and password for jenkins.
Do the following:

Stop Jenkins: sudo systemctl stop jenkins

Edit the config.xml: sudo nano /var/lib/jenkins/config.xml

Look for the line: <useSecurity>true</useSecurity>
Now, it will make you log in with user authentication, which basically allows everyone to get in and do whaterver they want.

Change it to: <useSecurity>false</useSecurity>

Save the file and restart Jenkins: sudo systemctl start jenkins

Now Jenkins will start without authentication.
Open it in your browser → go to Manage Jenkins → Security → Configure Global Security and create a new admin user.

Don’t forget to re-enable security: Edit /var/lib/jenkins/config.xml
Set <useSecurity>true</useSecurity> ,  Restart Jenkins again: sudo systemctl restart jenkins


