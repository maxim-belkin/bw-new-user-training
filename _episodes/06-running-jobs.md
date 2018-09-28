---
title: "Running jobs"
teaching: 30
exercises: 0
questions:
- "How do I run jobs on Blue Waters?"
objectives:
- "Learn about the MOM and compute nodes"
- "Learn how to submit, delete, and control jobs"
- "Learn how to execute software on compute nodes"
keypoints:
- "FIXME"
---

_**This episode is a stub and is beeing actively developed.**_
_Please feel free to share your ideas and/or contribute._

## A Closer Look at the Blue Waters nodes

Before we learn how to launch jobs on Blue Waters,
let's take a closer look at its structure.

![Blue Waters nodes](../fig/BW-nodes.png)


As you already know, when we connect to Blue Waters _via_ `ssh` command we land on one
of three login nodes. Here we can take care of all input data and compile our application.
However, we can not simply execute our science  application there. Instead, we have to:

1. Prepare the so-called _job batch script_ that sets up the execution environment
2. Submit the job to the queue
3. From within that script, send the application for execution on the compute nodes

## Job script

Blue Waters uses **Portable Batch System** (**PBS**) to handle scheduling on jobs.
A job script is a simple Shell script that you want to be executed by the system on
the MOM nodes.
It contains special instructions for the queuing system about the requested resources,
account to be charged, job name, and _etc._
The script must have an `aprun` command that sends an
application for the execution on the compute nodes.

Please copy the following directory to your home folder: `~mbelkin/new-user-training`.
This directory contains two simple batch scripts (`*.pbs`) and a `src` directory with
a few programs.

# Backfill

~~~
$ showbf -f xk
~~~
{: .language-bash}

# Submitting job to the queue
~~~
$ qsub jobscript.sh
$ qstat
$ qstat -f
$ qhold
$ qdel
$ checkjob
~~~
{: .language-bash}
