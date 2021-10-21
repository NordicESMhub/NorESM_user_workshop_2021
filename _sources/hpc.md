# On Betzy

Login on Betzy with your usual Sigma2 *username* (i.e., you are not *ubuntu* any more), and proceed like on the Virtual Machine but use **/cluster/work/users/$USER** (which is equivalent to **\$USERWORK**) instead of **/home/ubuntu** for staging and job data:

```
ssh -i ~/.ssh/YourPrivateSSHkey YourSigma2UserName@betzy.sigma2.no
cd $USERWORK
mkdir -p work archive
```

:::{note}
All the necessary inputdata being already available on **/cluster/shared/noresm/inputdata** there is no need to download the Zenodo tarball when you are on Betzy (or Fram)
:::

Pull the same container as on the Virtual Machine and extract this time the Slurm batch job script **job_hpc.sh**
