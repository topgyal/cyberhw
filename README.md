# codepath_homework

See branches for assignments.

# Honeypot Assignment

**Time spent:** **10** hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)

**Summary:** How did you deploy it? I used GCP to deploy it.

<img src="mhn-admin.gif">

### Dionaea Honeypot Deployment (Required)

**Summary:** Dionaea is a honeypot used to trap malware samples.

<img src="dionaea-honeypot.gif">

### Database Backup (Required) 

**Summary:** The MHN server is supported on Ubuntu 18.04, Ubuntu 16.04, and Centos 6.9. The exported JSON file record oid, protocol, date, source_ip, source_port, destination_port etc.


## Notes

One challenge i faced was to deploy dionaea. Instead of deploying command in honeypot-1, i started in mhn-admin. And i was lost for few minutes why there no attacks coming in. 
Also setting up billing and compute AI was little confusing in the beginning, but following the link from command made it easy.
