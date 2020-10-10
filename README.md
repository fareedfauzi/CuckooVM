# CuckooVM explain
Cuckoo running in a nested hypervisor!

If you've ever wanted to run Cuckoo but couldn't afford dedicating a full workstation/server/PC for it? Then, here is a solution for that by running Cuckoo in a nested Hypervisor. The VM has been configured to run on VMWare and Cuckoo within this VM will be running VirtualBox to test your samples.

**Download:**
The VM could be found [here](https://archive.org/details/CuckooVM).

**Installation:**
Just import into VMWare (tested), add a Windows System (preferably Windows 7) and run. Or read the blog post found [here](http://bit.ly/HowtoUseCuckooVM2).

If you are using an INTEL based Architecture, then please download this Windows 7 VM from [here](http://bit.ly/2w9Sih5).

Was announced [here](https://twitter.com/binaryz0ne/status/1239988679692738561).
Enjoy!

# Steps
1. Download from here https://archive.org/details/CuckooVM
2. Import the ovf to VMware
3. Open the Ubuntu Virtual Machine
4. Open Virtualbox in the Ubuntu and setup vm analysis for cuckoo in Virtualbox.
  - If you're using AMD, run the pre-setup "win7" vm in virtual box and restore to the base2 snapshot.
  - If you're using Intel, copy the `CuckooVM/Win7_Intel.tar` into the ubuntu and import it. Run the `Win7_intel` and restore to the base2 snapshot.
5. Configure `/home/cuckoo/.cuckoo/conf/virtualbox.conf` for vm name. If using amd, just leave it. If using intel, change from "win7" to "Win7_intel"
6. To start.
  - 1st terminal. Run `cuckoo -d`
  - 2nd terminal. Run `cuckoo web runserver 0.0.0.0:8000`
7. Here we go! -> http://<IP>:8000/dashboard/
8. Give a thank to https://twitter.com/binaryz0ne!
