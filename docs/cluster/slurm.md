
# Table of Contents

* [Definitions](#definitions)
  * [job](#job)
  * [task](#task)
* [Cluster status](#cluster-status)
* [Running jobs](#running-jobs)
  * [Use case without MPI](#use-case-without-mpi)
  * [Use case with MPI](#use-case-with-mpi)
* [Authors](#authors)

## Definitions

### job

Typically what is interesting for a user, will have a corresponding resource allocation and things like an executable, working directory, `stdout` and `stderr` files and so on.

A job may span resources on several nodes. Typically, you submit a job with `sbatch` or `salloc`, but it will also be implicitly submitted if you use `srun`.

### task

One part of a job that has a corresponding sub-allocation, executable, working directory, `stdout`, `stderr` and so on (most typically inherited from the job).

A task can span at most one node.

To launch tasks from within a job, you can use `srun`, `mpirun` will also set up tasks within a job allocation.

The `-c` flag to `sbatch` et al informs slurm how many cores *each* tasks requires (not the *total* number of cores, but cores-per-task).

The `-n` flag informs slurm how many tasks are required.

Actual allocated resources will be the values passed with `-n` and `-c` multiplication, so `-n 4 -c 6` will reserve 24 cores.

## Cluster status

These commands give you information on cluster status and nodes.

    sinfo --Node --long

If you want to include the state of use of the cpu do 

    sinfo -o "%n %.6D %.9P %.8t %.15C %.5a %.10l %.8h %.10g %.11T"

## Running jobs

    -N => number of nodes  
    -n => number of tasks  
    -c => number of threads  

Jobs are generally recommended to be run on cores rather than blocking a whole node with a process that only uses 4 cores. 
It means you should not ask for a certain number of nodes (with `-N`), but only use `-n` to specify cores. And if you want more cores per task also use `-c`.

Note that there is a difference between submitting a job with `sbatch` 
(which will launch a single process no matter what the number of requested tasks is)
and with `srun` (which will launch the requested number of tasks). For those used to the recommended workflow from UPPMAX, one would submit the job with `sbatch` or possibly `salloc` and then use `mpirun` or `srun` if one wanted to launch tasks).

Running a job on multiple CPU

    srun -J jobName -n CPUs <command>

If the cluster has two type of nodes, e.g. 16 and 36 CPUs nodes. When asking for 36 CPU for a single job you must use the following syntax otherwise the job may be sent to a 16 CPU node:  

    srun -J jobName [-N 1] -n 1 -c 36 <command>
 
`-N` is optional because `-c 36` means you need 36 cores in one node, since threads cannot span across nodes. But it doesn't hurt to be explicit and specify all three parameters.

It's possible `-n 1 -c 36` might worked better than using `-n 36`, but in some cases there have been bugs so in practice the other way works better. 

### Use case without MPI

|N|n|c|Description|
| ---- | ---- | ---- | ---- |
||1|36|One task running on 36 threads on one node |
||36||One job with 36 tasks, launches 1 process with `sbatch`, 36 with `srun`, can be spread on multiple nodes|
|1|||Use one node at maximum|
|1|36||One job on one node with 36 tasks allocating 36 cores, will launch 1 process with `sbatch`, 36 with `srun`|
|1||36|One job on one node with 36 cores|
|||36|One job with 36 cores|

### Use case with MPI

|N|n|c|Description|
| ---- | ---- | ---- | ---- |
||1|36|One task running on 36 cores, will be allocated on the same node - mpi?|
||36||36 tasks (each with 1 core), may be spread over multiple nodes|
|1|||Max one node|
|1|36||One job with 36 tasks, use at most one node|
|1||36|One job with one task with 36 cores (mpi?)|
|||36|One job with one task with 36 cores (will be allocated from the same node, mpi?)|


## Authors

Jacques Dainat, Roy Francis, Pontus Freyhult
