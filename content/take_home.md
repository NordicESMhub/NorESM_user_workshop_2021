# Take home messages

- Containers provide a **consistent software environment** (BYOS = Bring Your Own Software)
	- The very same container image runs on different plateforms, from laptop/desktop to cloud and HPC
		- Only requires a container engine (Docker, Singularity, Sarus, etc.) for single node ("inside-out")
		- An **ABI compatible Message Passing Interface (MPI) library** 
		 or Slurm Workload Manager (srun) and a **Process Management Interface (PMI)** for multi-nodes ("outside-in")
	- No need to wait for Sysem Administrators to install particular pieces of software

- Use local and private resources for developments, testing, learning, etc.
	- More confortable and **responsive** (no queue) 
	- Release (very expensive) HPC resources for production runs

- Get the most of **interconnects** when adequate drivers and libraries are included
	- May require some "tuning" for "exotic" infrastructures

- No proprietary compiler
	- Free for everyone to use and **distribute**

- **Performances** close to running directly on bare-metal, often better
- Bit-for-bit **reproducibility** (with the same PES layout and same CPU architecture)
	- Start simulations somewhere and continue them anywhere resources are available

- Can be used as part of **workflows** in which one task is the climate simulation itself
	- Full control over the entire sequence of tasks (no possible loss of information)
	- A *must* for **reproducible research**

## Suggestion

- Accompany every new NorESM release with the container that was used by the development team
	- Guaranted results
	- Much easier for users
		- **Focus on science instead of wasting time to sort-out porting and software dependencies**
