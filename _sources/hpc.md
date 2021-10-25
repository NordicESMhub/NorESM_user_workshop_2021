# On Betzy

Login on Betzy with your usual Sigma2 *username* (i.e., you are not *ubuntu* any more), and proceed like on the Virtual Machine but use **/cluster/work/users/$USER** (which is equivalent to **\$USERWORK**) instead of **/home/ubuntu** for staging and job data:

```
ssh -i ~/.ssh/YourPrivateSSHkey YourSigma2UserName@betzy.sigma2.no
cd $USERWORK
mkdir work archive
```

:::{note}
All the necessary inputdata being already available on **/cluster/shared/noresm/inputdata** there is no need to download the Zenodo tarball when you are on Betzy (or Fram)
:::

Pull the same container as on the Virtual Machine and extract this time the Slurm batch job script **job_hpc.sh**

We are going to use **srun** for automatically distributing the processes to precisely the resources allocated to the job

## 1-day run with 16 tasks (hands-on exercise)

The existing script can be used to submit the Slurm job which runs NorESM for 1 day on 1x node and 16x CPUs:

```
sbatch job_hpc.sh
```

Now check the timing profile

:::{note}
Short simulations do not necessarily provide the most representative performance figures
:::

## 1-month run with 128 tasks (hands-on exercise)

Edit the script to set nodes=8 and tasks-per-node= 128, delete the line with - - qos (in order to use the *normal* queue) and replace ‘ndays’ by ‘nmonths’, then resubmit the job to get a more precise estimate of the model throughput

## 25-years run with 8x128 tasks (for information only)

**Do not do it now**: the same simulation extended to 25 years provides very similar numbers (the job take about 18 hours)


