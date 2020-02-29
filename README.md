# Nagios/NREP Checks

Collection of various custom check scripts for Nagios/NREP.  In some cases
similar checks existed but didn't exactly do what I needed.

# Checks

## check_cert_age

Checks the age of a TLS certificate using OpenSSL.  This check relies on a
BSD style date(1) command.  Supports checking HTTPS, IMPAS and SMTP via StartTLS
connections.

~~~
usage:  check_cert_age [options]

options:
  -v	Show version.
  -h	Show this help message.
  -p	Port number if other than default for the protocol.
  -H	Hostname to monitor. Defaults to localhost.
  -m	Protocol to check.  Valid options are HTTPS, IMAPS and
    	SMTP_TLS.  Default is HTTPS.
  -c	Critical alert if certificate has less than this number of
    	days before expiration. Defaults to 7 days.
  -w	Warning alert if certificate has less than this number of
    	days before expiration. Defaults to 7 days.
~~~

## check_zool_status

Check the status of a zpool using the `zpool status` command.  A pool should
be specified and any result other than ONLINE results in a critical alert.

~~~
usage:  check_zpool_status [options]

options:
  -v	Show version.
  -h	Show this help message.
  -p	Pool name.
~~~
