OpenShift Enterprise 2 - Extras
===

Overview
---
This Ansible project accomplishes five things.

1. Configure rsyslog to send logs to remote server over two-way TLS.

2. Configure auditd to log rsyslog, and as a result, to a remote server.

3. Update the web console so that the summary screen directs the app owner to "https" instead of http.

4. Enable app owners to use private SSL certificates by default.

5. Configure Broker to send logs to rsyslog

Remote rsyslog
---
This project assumes that you have generated certificates (and keys) for each broker and node, as well as the central logger.  These certificates must be signed by a CA in the trust chain.  Communications is forced over TLS (no SSL).  Furthermore, peers are "white listed" to control which hosts may send logs to the aggregator.

Underneath the "group_vars" folder, you will find two files containing variables pointing to the SSL Cert information.  Double check that these are accurate.

"production" is the inventory file.  Adjust the hosts as you see fit.  

Future Work
---
Log rotation needs to be improved.  I'll add options to send it to some repository.
