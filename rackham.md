# Rackham

Rackham is a high performance computer cluster at UPPMAX (Uppsala Multidisciplinary Center for Advanced Computational Science).
UPPMAX is Uppsala University's resource of high-performance computers, large-scale storage and know-how of high-performance computing (HPC).

  * [UPPMAX github repo](https://github.com/UPPMAX?utf8=✓&q=&type=&language=)
  * [UPPMAX official Cheat Sheet](https://www.uppmax.uu.se/support/getting-started/uppmax-cheat-sheet/)
  * [Rackham User Guide](https://uppmax.uu.se/support/user-guides/rackham-user-guide/)
  

### UPPMAX modules

| Command | Comment
| --- | --- 
| module avail   | List available modules
| module load ***modulename***   | Load the module ***modulename***
| module unload ***modulename***   | Load the module ***modulename***
| module list  | List all modules loaded
| module spider ***searchword***  | Search all module containing ***searchword***

### Running jobs with the Slurm ressource manager

| Command | Comment
| --- | --- 
| interactive -A projectID   | Start interactive job using 1 core for 1 hour
| interactive -A projectID -t 8:00:0 -p core -n 2   | Start interactive job using 2 cores for 8 hours
| sbatch -A projectID -t d-hh:mm:ss -n cores -p partition my_jobscript_file  | Start batch job
| sbatch -A projectID -t 7-00:00:00 -p node my_jobscript_file  | Running for 7 days on all 20 cores one one node
| sbatch -A projectID -t 48:00:00 -p core -n 4 my_jobscript_file  | Running for 2 days on only 4 cores on a node
| scancel ***jobId***   | Cancel a single job
| scancel -i -u user | Interactively cancel all jobs for user

### Showing user, job and project info

| Command | Comment | Full documentation
| --- | --- | ---
| jobinfo   | Show all running and waiting jobs in the queue | [jobinfo](https://www.uppmax.uu.se/support/user-guides/jobstats-user-guide/)
| jobinfo -u ***user***   | Show jobs for specific user | [jobinfo](https://www.uppmax.uu.se/support/user-guides/jobstats-user-guide/)
| jobstats -p -A ***projectID***   | generate plots for resource usage for recent jobs in a project | [jobstats](https://www.uppmax.uu.se/support/user-guides/jobstats-user-guide/)
| uquota | Show disk usage of projects you are a member of|
| projinfo    | Show used core hours of projects you are a member of |
| finishedjobinfo    | Telling you about finished jobs on Rackham |
| projmembers    | List members of a project |
| projsummary  ***projectID***  | Summarizes some useful information about projects |
| squeue -u ***user*** | Information about ***user***'s jobs |


**/!\\** Most of the commands use the cluster you are logged into as default cluster, if you wish to apply the command to another cluster you have to specify is using:  
   **-M** ***clusterName*** 
  
**/!\\** Most of the commands have plenty of parameters and have an help. So don't forget to check it using:  
   ***command --help***
