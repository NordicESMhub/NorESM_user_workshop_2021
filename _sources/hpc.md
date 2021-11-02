# On Betzy

Login on Betzy with your usual Sigma2 *username* (i.e., you are not *ubuntu* any more), and proceed like on the Virtual Machine but use **/cluster/work/users/$USER** (which is equivalent to **\$USERWORK**) instead of **/home/ubuntu** for staging and job data:

```
$ ssh -i ~/.ssh/YourPrivateSSHkey YourSigma2UserName@betzy.sigma2.no
$ cd $USERWORK
$ mkdir work archive
```

:::{note}
All the necessary inputdata being already available on **/cluster/shared/noresm/inputdata** there is no need to download the Zenodo tarball when you are on Betzy (or Fram)
:::

Pull the same container image as on the Virtual Machine, and extract this time the Slurm batch job script **job_hpc.sh**

On many systems it is common to use an alternative launcher to start parallel applications, for instance Slurm’s **srun** rather than the **mpirun** *wrapper* provided by a particular MPI installation (as we did on the Virtual Machine for the "outside-in" exercise)

This approach is supported with Singularity as long as the MPI version installed in the container supports the same Process Management Interface (PMI) and version as that used by the launcher (which is the case with our container)

In the frame of this workshop we are therefore going to use **srun** for automatically distributing the processes to precisely the resources allocated to the job, without loading any module with MPI

```{exercise} 
:label: 1Day-Betzy
Using the existing script *as it is* submit the Slurm job which runs NorESM for **1 day** on **1x node** and **16x CPUs**, then monitor the run and once the simulation has finished check the timing profile
```

````{solution} 1Day-Betzy
:class: dropdown
```{code-block} bash
$ sbatch job_hpc.sh
```
````

:::{note}
Short simulations do not necessarily provide the most representative performance figures therefore, for the purpose of benchmarking, longer simulations are normally performed (typically 1 month or more) 
:::


```{exercise} 
:label: 1Month-Betzy
Edit the script to set **nodes=8** and **tasks-per-node=128**, delete the line with **\- \- qos** (in order to use the *normal* queue) and replace ‘ndays’ by **‘nmonths’**, then resubmit the job to get a more precise estimate of the model throughput
```
````

