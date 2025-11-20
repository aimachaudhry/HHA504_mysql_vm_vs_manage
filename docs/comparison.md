# MySQL on a VM vs on a Manged Service: A Comparison

Both MySQL on a VM and on a manged service allows the creation and interaction of databases. However, they differ in setup and flexibility. Due to this, there are different approaches that makes one option more preferable than the other depending on the workload. 


## Small Student App:

For a small student app, I would choose to use MySQL on a virtual machine. Although there were more steps to create the instance, create the firewall rules, and install the server packages, there is more control over the database. There are more options for storage configuration and memory allocation, which can allow for more experimentation when building a student app. I also believe that using MySQL on a virtal machine is a good introduction on creating databases. The cost was also lower and for a smaller project, I think using a VM would be best.

## Departmental Analytics Database:

For a departmental analytics database, I would use a managed service as opposed to a virtual machine. For a larger database such as this one, it is important to have a platform that manages the updates and security feautures, which is what Cloud SQL provides. The managed server can reduce administrative workload, making it a more practical option for an analytics department. 

## HIPAA-Aligned Workload:

For a HIPAA-aligned workload, I would choose the managed service especially because it prioritizes compliance. For a virtual machine, there are options to manually configure these feautures, but it could come with risks such as compliance violations or data breaches. To ensure confidentiality and privacy, Cloud SQL would lead to less risk. 
