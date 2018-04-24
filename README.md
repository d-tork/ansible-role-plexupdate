# wilmardo.plexupdate

[![Build Status](https://travis-ci.org/wilmardo/ansible-role-domoticz.svg?branch=master)](https://travis-ci.org/wilmardo/ansible-role-plexupdate)
[![Galaxy](https://img.shields.io/badge/galaxy-wilmardo.plexupdate-blue.svg)](https://galaxy.ansible.com/wilmardo/plexupdate/)

Keep your Plex server automagically up to date with [Plexupdate](https://github.com/mrworf/plexupdate)!

## Requirements

None but when plexupdate_notify is enabled a working crontab email configuration is required to be able to receive notifications.

## Role Variables

### Default usage

As default plexupdate is installed and running.
If you want to adapt this to your needs look at the [Advanced usage](#advanced-usage) section.

### Advanced usage

For more advanced usage the following variables are available:
```yaml
# Version of Tautulli to install, gets passed to git module
plexupdate_version: master
# Plexupdate install location
plexupdate_install_location: /opt/plexupdate/
# Plexupdate config location
plexupdate_config_location: /etc/plexupdate.conf
# Plexupdate cronwrapper location, change cron.daily to interval (cron.hourly, cron.daily, cron.weekly, cron.monthly)
plexupdate_cronwrapper: /etc/cron.daily/plexupdate

# Cron options for plexupdate
# If Plexupdate will automatically install newly downloaded version
plexupdate_autoinstall: true
# If Plexupdate will delete the downloaded package after installation to conserve disk space
plexupdate_autoupdate: true
# If Plexupdate will download the public release (set to no to download PlexPass releases)
plexupdate_public: true
# If Plexupdate will notify by mail after cron error
plexupdate_notify: false
```

## Dependencies

None

## Example Playbook

Install plexupdate with the default settings
```yaml
- hosts: all
  roles:
     - role: wilmardo.plexupdate
```

## License

BSD-3-Clause-Clear

## Author Information

This role was created in 2018 by [Wilmar den Ouden](https://wilmardenouden.nl).
