# On the Virtual Machine

Login on your own Virtual Machine with the **private SSH key** corresponding to the public key that you provided the Organizers of this Workshop (it does not grant you access to any other Virtual Machine anyway):

```
ssh -i ~/.ssh/YourPrivateSSHkey ubuntu@158.39.48.xxx
```

Each Virtual Machine features 16 VCPUs + 64GB RAM + 80GB root disk, and comes with:

- an Operating System (OS) with the default C/C++/FORTRAN compilers
- a Message Passing Interface (MPI) library, required for the hands-on exercise on "outside-in" interaction with the container (but not for "inside-out")
- Singularity

already installed, nothing else

:::{note}
Replace *158.39.48.xxx* by the IP address that you have been allocated (please check your email and let us know if you have not got it), and all use same user name (*ubuntu*)
:::
