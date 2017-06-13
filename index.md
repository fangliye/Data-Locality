


<h2>22/05- 26/05</h2>
<p>1. Read paper. Delay scheduling a simple technique for achieving locality and fairness in cluster scheduling.pdf. </p>
<p>2. Import Hadoop source code to eclips.</p>
<p>3. Contacted with Euggen asking for some available machines for seting up hadoop cluster.</p>
<h2>29/05- 02/06</h2>
<p> 1. 29/05: set up ubuntu(operating system) in the vmware.  - Done </p>

          Problems:
          
           a. in the ubuntu can not see the shared folder.
           $sudo apt-get install open-vm-tools open-vm-tools-dkms
           $sudo vmhgfs-fuse .host:/ /mnt/hgfs
           b. set the static ip address
           $sudo nano /etc/hosts
           #add this below code in this file
           auto ens33
           iface ens33 inet static
           address 136.XXXX.1
           gateway 136.XXXX.254
           network 136.XXXX.254
                 
<p> 2. 30/05: set up hadoop cluster.  - Done </p>
            - 1 master which includes namenode and sourcemanager;
            - 3 slaves which include datanode and nodemanager;
                       
            Problems: 
            
              a. the namenode could not startup
               $lsof -i:50070
              b. can not see the datanode progress slave3
               restart ubuntu                               
     
<p> 3. 31/05: set up hadoop cluster. - Done</p>

            Problems:
            
             a. change the hadoop version to 2.7.3, but can not start up hadoop, show didn’t set up the jdk
              $nano /usr/local/hadoop/etc/hadoop/hadoop-en.sh
               export JAVA_HOME=/usr/local/jvm/jdk-8-oracle
             b. read the details about the allocation file about fire-scheduler
                   [link]http://han-zw.iteye.com/blog/2322189[/link]
             c. Euggen helps me to solve network problem connecting the master machine using campus wifi. and from master machine                       connect other three slaves
             
<p> 4. 01/06: learn how to set the fair-scheduler in the hadoop and how does it work. the default scheduler is capitably. - Done</p>

<p> 5. 02/06:  try to run simple job using fair scheduler, and try to analysis the whole processes. </p>
  
                     - Don’t know how to see that node requests task log.
 
<h2>06/06-10/06</h2>

<p>1.Importing Hadoop projects to eclipse</p>

    a. Installation
       -Hadoop 2.7.3 source code
       -Install apache maven 3.0.5
       -Install protocolBuffer 2.5.0
       -Install JDK 1.8.121
       -Install CMake
       -FindBugs
       $cd hadoop-maven-plugins     //go to the hadoop-maven-plugins impelement this command
       $mvn install                 //install hadoop-maven-plugins at first
       $cd ..                       //go to the root directory
       $mvn eclipse:eclipse -DskipTests  //Then, generate eclipse project files.
       At last, import to eclipse by specifying the root directory of the project via
       [File] > [Import] > [Existing Projects into Workspace].
       
    b. Problem
      -when I imported the hadoop source code into the eclips there are some errors in some packages. I tried many methods to solve them       but all of them didn't work. But there are no any errors in the yarn package, and I just need to make some change in the yarn           package. So, these errors can be ignored. 
   
<p>2.learn the fair schedule.</p>
   
    - The delay schedule is based on the fair scheduler, so I first try to learn all of the features in the fair schedule. I read the   fair schedule doc downloaded from the hadoop websit.
    - Read the FairSchedule.java code.
<p>3.hava a rugh plan about how to implement coding.</p>
<p>4.How to compile new code. -Done </p>
 
    a. Create binary distributions.
       -Compile the hadoop source code which can be used to set up hadoop cluster.
        $ mvn package -Pdist,native -DskipTests -Dtar
        How to install the compiling enviornment in ubuntu.
        url: [http://blog.csdn.net/blue_it/article/details/54133407]
        
    b. Problems
       -there were some package build failed
        Failed to execute goal org.apache.maven.plugins:maven-antrun-plugin:1.7:
        $ mvn package -Pdist -DskipTests -Dtar   //remove the native, and then build successfule.
        



