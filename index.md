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
 
<h2>06/06-10/06 (Plan)</h2>

<p>1.install the hadoop source code in my eclipse.</p>
<p>2.learn the yarn framework of hadoop.</p>
<p>3.hava a rugh plan about how to implement coding.</p>
<p>4.How to compile new code. </p>

