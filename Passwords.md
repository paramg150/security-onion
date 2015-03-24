# OS root account #

Like other Ubuntu-based distributions, there is no root password. Your default user account has been given sudo permissions. Graphical utilities requesting administrative access should prompt for password; enter your user password. Command-line utilities that require administrative access can be prefixed with "sudo". For example, to add a user:
```
sudo adduser mynewuseraccount
```

# MySQL #
The MySQL root password is null to allow the NSMnow administration scripts to add/delete sensors properly. MySQL only allows connections from localhost.  If you need to look at the database manually, you can do so like this:
```
mysql -uroot
```

# Xplico #
We use the default Xplico credentials as listed here:
http://wiki.xplico.org/doku.php?id=interface

# Sguil #
Log into Sguil using the username/password you created in the Setup wizard.  Add accounts with "sudo nsm\_server\_user-add" and change passwords with "sudo nsm\_server\_user-passwd".

# Squert #
Squert authenticates against the Sguil user database, so you should be able to login to Squert using the same username/password you use to login to Sguil.

# ELSA #
ELSA authenticates against the Sguil user database, so you should be able to login to ELSA using the same username/password you use to login to Sguil.

# Snorby #
Snorby does not authenticate against the Sguil user database.  Log into Snorby using the EMAIL ADDRESS and password you specified in Setup.

## Reset Snorby Password ##
To reset your Snorby password, first open the Rails console:
```
cd /opt/snorby/
sudo RAILS_ENV=production bundle exec rails c
```
In the Rails console, reset your Snorby password as follows:
```
u = User.find_by_email("foo@bar.com")
u.password="NewUnencryptedPassword123"
u.password_confirmation="NewUnencryptedPassword123"
u.save
quit
```