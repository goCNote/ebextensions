# AWS Elastic Beanstalk Extensions
These are a collection of useful [EB Extensions](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/ebextensions.html) that CNote uses. They may have been modified slightly from our Production usage for security reasons.

# DISCLAIMER: USE AT YOUR OWN RISK
These extensions are shared WITHOUT WARRANTY OF ANY KIND. CNote accepts no
liability for any issues that arise from using these extensions. We suggest
thoroughly testing them yourselves before employing in any production
application.

# Inventory

## DNS Query Logs
Captures all DNS queries made on the machine. Useful for forensics in the event
of a breach.

[dnsquerylogs.config](dnsquerylogs.config)

* SysV wrapper around [tcpdump](https://www.tcpdump.org/)
* Writes to `/var/log/dnsqueries.log`
* Rotates hourly or at 10MB increments using [logrotate](https://linux.die.net/man/8/logrotate)
* Streams DNS query logs to Cloudwatch using [awslogs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/QuickStartEC2Instance.html)
