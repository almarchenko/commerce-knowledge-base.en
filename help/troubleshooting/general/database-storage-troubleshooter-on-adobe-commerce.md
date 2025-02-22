---
description: This article is a troubleshooter tool for customers on Adobe Commerce having issues with databases. Click on each question to reveal the answer in each step of the troubleshooter. Depending on your symptoms and configuration, the troubleshooter will explain how to troubleshoot space and configuration issues with databases.
labels: Adobe Commerce,on-premises,cloud infrastructure,database,troubleshooting,MySQL,error,space,disk space,disk,database,storage,site down,connection,queries, troubleshooting,connection
title: Database storage troubleshooter on Adobe Commerce
---

# Database storage troubleshooter on Adobe Commerce

This article is a troubleshooter tool for customers on Adobe Commerce who are having issues with databases. Click on each question to reveal the answer in each step of the troubleshooter. Depending on your symptoms and configuration, the troubleshooter will explain how to troubleshoot space and configuration issues with databases.

+++**Step 1 - Do you have a `/tmp` issue caused by a lack of space?**

This can be indicated by a range of symptoms including the `/tmp` mount being full, site down, or not being able to SSH into a node. You may also be experiencing errors like _No space left on device (28)_. For a list of errors resulting from /tmp being full, review [/tmp mount full](https://support.magento.com/hc/en-us/articles/4403572246285).  
  
Or do you have a `/data/mysql` issue caused by a lack of space? This can also be indicated by a variety of symptoms including site outage, customers unable to add products to cart, connection failure to database, and Galeria errors like _SQLSTATE\[08S01\]: Communication link failure: 1047 WSREP_. For a list of errors resulting from low MySQL disk space, refer to [MySQL disk space is low on Adobe Commerce on cloud infrastructure](https://support.magento.com/hc/en-us/articles/360037591972).  
  
If you are unsure if you have a disk space issue and you have a New Relic account, go to the [New Relic Infrastructure monitoring Hosts page](https://docs.newrelic.com/docs/infrastructure/infrastructure-ui-pages/infrastructure-ui/infrastructure-hosts-page/). From there, click on the **Storage** tab, change the **Chart Shows** drop down from 5 to 20 results, and look in the table for high disk use in the Disk Used % chart or table. For more detailed steps, refer to [New Relic Infrastructure Monitoring > Storage tab](https://docs.newrelic.com/docs/infrastructure/infrastructure-ui-pages/infrastructure-ui/infrastructure-hosts-page/#storage-tab).  
  
If you have any of the symptoms described above, check the state of your inodes to make sure this is not being caused by a file number issues. To do so run the following command in the CLI/Terminal:  
`df -ih`

**Is IUse percentage greater than 90%?**

a. **YES** – This is caused by having too many files. Review the steps to remove files safely in [Safely delete files when out of disk space, Adobe Commerce on cloud infrastructure](https://support.magento.com/hc/en-us/articles/4406832353677-Safely-delete-files-when-out-of-disk-space-Adobe-Commerce-on-our-cloud-infrastructure). Proceed to [Step 2](#step-2) after you have completed these steps. If you want to request more space, [submit a support ticket](https://support.magento.com/hc/en-us/articles/360019088251).  
b. **NO** – Check space. Run `df -h | grep mysql` and then `df -h | grep tmp` in the CLI/Terminal to check disk space usage in the `/tmp` and `/data/mysql` directories. Proceed to [Step 3](#step-3).

+++

+++**Step 2 - Is greater than 70% used for `/tmp` or `/data/mysql`?**

Once you have reduced the number of files, run `df -h | grep mysql` and then `df -h | grep tmp` in the CLI/Terminal to check disk space usage in `/tmp` and `/data/mysql`. 

a. YES – Proceed to [Step 3](#step-3).   
b. NO – Queries may be exhausting the available storage. This may crash the node, killing the query and removing the `tmp` files. Examine the output of the `SHOW PROCESSLIST;` in the MySQL CLI for queries that may be the cause of the problem. [Submit a support ticket](https://support.magento.com/hc/en-us/articles/360019088251), requesting more space.

+++

+++**Step 3 - Which directory has greater than 70% used?**

Which directory has > 70% used? `/tmp` or `/data/mysql`?  
Note: By default database tmpdir writes to `/tmp`. To check your database configuration is still on this default, run the following command in MySQL CLI: `SHOW VARIABLES LIKE "TMPDIR";` If the database tmpdir is still writing to `/tmp`, you will see `/tmp` in the Value column.

a. `/tmp` – Proceed to [Step 4](#step-4).   
b. `/data/mysql` – Proceed to [Step 5](#step-5).

+++

+++**Step 4 - Troubleshooting `tmp` mount full**

[Troubleshoot /tmp mount full for Adobe Commerce](https://support.magento.com/hc/en-us/articles/4403572246285), scroll down the article and try the solutions and best practices. Then run `df -h | grep mysql` and then `df -h | grep tmp` in the CLI/Terminal to check disk space usage in `/tmp` and `/data/mysql` directories.

>[!NOTE]
>
>The solutions in [Troubleshoot /tmp mount full for Adobe Commerce](https://support.magento.com/hc/en-us/articles/4403572246285) are designed for merchants who have not changed the variables for database tmpdir, which by default writes to `/tmp`. If you have changed the tmpdir value, the instructions in [Troubleshoot /tmp mount full for Adobe Commerce](https://support.magento.com/hc/en-us/articles/4403572246285) will not help.

**Is less than 70% used?**

a. YES – You have solved the issue.   
b. NO – [Submit a support ticket](https://support.magento.com/hc/en-us/articles/360019088251), requesting more space.

+++

+++**Step 5 - Additional troubleshooting**

Your database configuration may no longer be at the original default. Find the database tmpdir config by running in the MySQL CLI: `SELECT @@DATADIR;`. If `/data/mysql/` is outputted, the database tmpdir is now writing to `/data/mysql/`. Try to increase space in this directory by following the steps in [MySQL disk space is low on Adobe Commerce on our cloud infrastructure](https://support.magento.com/hc/en-us/articles/360037591972). Then run `df -h | grep mysql` and then `df -h | grep tmp` in the CLI/Terminal to check disk space usage in `/data/mysql` and `/tmp`.  

**Is less than 70% used?**

a. YES – You have solved the issue.   
b. NO – [Submit a support ticket](https://support.magento.com/hc/en-us/articles/360019088251), requesting more space.

+++
 
