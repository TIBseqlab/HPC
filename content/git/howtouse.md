## 使用方法
#### 登录
Windows用户，请首先下载Putty或者Mobaxterm之类的ssh客户端；Linux用户，请确认SSH工具能正常使用。

首先用户必须要有可用的账号和密码，没有账号的用户请参考[上机流程](Procedure.md)。
1. Windows用户请按照客户端的指示进行登录，登录节点,172.16.25.8，然后输入用户名和密码。
2. Linux 用户，请打开Terminal，并输入如下命令：
```bash
ssh username@172.16.25.8
```
然后输入自己的密码即可成功登陆超算管理节点。如果想不用每次都输入密码，可以参见[ssh without password](http://www.thegeekstuff.com/2008/11/3-steps-to-perform-ssh-login-without-password-using-ssh-keygen-ssh-copy-id)来设置

#### 软件安装
1. 安装软件之前，请首先查看[Software](software.md)看是否已经安装。如果必须安装，请尽量安装在自己的home文件夹上，这样能保证在一个节点上能用，所有节点都能用。现在几乎所有的软件都有办法安装在自己的home文件夹上，一般搜索“install XXX without root access” 就能找到解决办法。
2. 登录节点没有外网，无法连接外部网络。

#### 测试
登陆节点禁止做任何计算程序的测试，请登陆到其它节点进行测试，比如node10, 然后top看看机器的使用情况，如果空闲，可以做小规模测试。
```bash
ssh node10
top 
```

#### PBS队列（试用）
TORQUE已经部署在集群上，现在不强求大家使用，但会在适当时机推行。关于如何使用qsub来提交作业，详细文档可以参考[qsub提交作业](https://www.westgrid.ca/support/running_jobs).

这里我们给出几个简单的例子来说明怎么使用qsub，具体的命令请参考[qsub 命令](PBS_Script.pdf)：
####### 案例1： 
Submitting Batch Jobs with qsub
A batch job script is a text file of commands for a specified UNIX shell (typically bash or tcsh) to interpret, similar to what you could execute by typing directly at a keyboard. The job is submitted to an input queue using the qsub command. A job will wait in the input queue for a longer or shorter time, depending on factors such as system load and the priority assigned to the job. When appropriate resources become available to run a job, it is removed from the input queue and started on one or more assigned processors. A job will be terminated if it exceeds its allotted time limit, or, on some systems, if it exceeds memory limits. By default, the standard output and error streams from the job are directed to files in the directory from which the job was submitted.

In the simplest case, a batch job file called batch.pbs could be submitted with:

qsub batch.pbs

The batch job system needs a description of the job requirements. These can be specified using qsub command-line options or by using special directive lines in the batch job script itself.  The most commonly-used qsub flag, -l (letter ell), is used to specify various resources required by the job, such as the maximum run time, the number of processors needed and the amount of memory required. For a full list of qsub options one can use man qsub. However, the qsub manual page just gives a generic description that doesn't take into account some of the specific hardware and policies at the various WestGrid sites. By choosing combinations of resource requests that cannot be satisified, it is quite possible to submit jobs that will sit in the input "forever", without a warning message. This can happen, for example, if you try to use the ncpus parameter, instead of nodes, to request processors on one of the distributed clusters, or in some situations if you request more memory than is physically available.

Explanations for the resource-related parameters used above and other qsub options are given in a later section.

If the qsub command successfully processes the script and has queued a job for execution, it will return a JOBID in the form of a number followed by the name of a server. Generally, the server portion of the JOBID can be ignored. The JOBID number can be used in other commands involved in monitoring or deleting the job.

If no UNIX shell is explicitly specified in the job script, the user's login shell will be used to interpret the script when it is run on a compute node assigned by the batch system. When the script is executed, the program runs as a child process of the script. When the program finishes, execution returns to the next line of the script. When the last line of the script has been completed, the job terminates. Jobs can be aborted using the qdel command, which is discussed later in these notes.

Summary of Job Commands
CLICK HERE for a handout of common pbs script commands, environment variables, job monitoring commands, cluster and group information. 