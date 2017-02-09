# ansible-ubuntu-common
An ansible script that bootstraps an ubuntu server

The overall steps are:

- Lock down ssh

- Lock down sudoers

- Set up hostname

- NTP for time synchronization

- Locale configuration

- Firewall setup with fail2ban to block ssh bruteforce attempts

- Unattended security upgrades

- Useful tools/packages from default ubuntu repo e.g. emacs :)

## Required Variables

- `short_name` - system name

- `ip_address` - Static IP address of the server

- `etc_hosts_entry` - An entry in /etc/hosts mapping your static ip to your fqdn

- `locale` - Your default system locale e.g. en_US.UTF-8

- `timezone` - Timezone as appears in tzdata e.g. 'Africa/Nairobi'

- `allowed_tcp_ports` - Allowed iptables INPUT TCP ports (including ssh)

- `additional_iptables_rules` - A list of additional iptables rules

- `fail2ban_mail_recipient` - Mail recepient for fail2ban notifications (default root@localhost)

- `reboot_on_upgrade` - whether to reboot when unattended upgrades require it (default "no")

- `reboot_time` - What time to reboot in format HH:MM (default "now")

- `additional_packages` - Additional packages from default repo that should be present (default: emacs-nox)

## TODO

- Add tests

- add to galaxy

