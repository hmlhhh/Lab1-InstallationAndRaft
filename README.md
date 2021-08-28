**95-702 Distributed Systems Lab 1**

In this lab, you will install Open JDK, IntelliJ, and TomEE Plus. These
tools will be used throughout much of the course. You will also solve
some Raft puzzles and answer a question about proof of work and SHA256.

For those using a Windows operating system, you will need to show your
TA that you are using a "Pro" version of Windows (not a "Home" version).

**Part 1. Installation of Open JDK**

Visit <https://adoptopenjdk.net/archive.html>.

Do **not** choose the defaults, rather be sure to choose Open JDK12 and
Open J9.

Download and run the JDK installer for jdk-12.0.2+10.2_openj9-0.15.1

Download and run the JRE installer for jdk-12.0.2+10.2_openj9-0.15.1

Set your JAVA_HOME environment variable.

On a MAC, JAVA_HOME is set within the .bash_profile of your home
directory.

exportJAVA_HOME=/Library/Java/JavaVirtualMachines/adoptopenjdk-12-openj9.jdk/Contents/Home

From the command line, javac -version and java -version should both
report the version number as 12.

Show your TA that your command line java commands are correct.

**Part 2. Installation of IntelliJ IDEA Ultimate**

Establish your student credentials with JetBrains for the free version
of IntelliJ for educational use:
[[https://www.jetbrains.com/student/]{.ul}](https://www.jetbrains.com/student/).
Download and install the latest IntelliJ IDEA Ultimate.

Write a Java program that displays "Hello World".

Show this running program to your TA.

**Part 3. Installation of TomEE+**

Visit
[[http://tomee.apache.org/download-ng.html]{.ul}](http://tomee.apache.org/download-ng.html)
and download the TomEE 8.x.x (e.g 8.0.4) version of **TomEE Plus**
(Note: "Plus", not "Plume".)

Copy the TomEE directory to an appropriate directory on your file
system. The directory path should contain no spaces. Do not change the
name of the TomEE Plus directory.

1.  Open IntelliJ and create a new project.

2.  Under Java/ Java EE /select Web Application

3.  Select Next and name your project TestWebApp

4.  Right click src and create a new servlet

5.  Give it the name TestServlet in the package
    edu.cmu.andrew.yourAndrewID

6.  Select OK

7.  In the web.xml file, after the servlet element, create a servlet
    mapping element as shown here:

\<servlet-mapping>

\<servlet-name>TestServlet\</servlet-name>

\<url-pattern>/\*\</url-pattern>

\</servlet-mapping>

8.  Open the TestServlet in the src directory. Within the doGet method,
    add this line of code:

response.getWriter().append(\"Hello from TestServlet \");

9.  Select Run/Edit Configurations/+/TomEE Server/Local

10. Name the server MyTomEE

11. Select Configure

12. In TomEE text box, select the folder on the far right.

13. Select open after browsing to the apache-tomee-plus directory.
    Select OK.

14. Select Deployment and click Fix in the bottom right and then OK.

15. Select File/Project Structure/Project Settings/Libraries/+/Java

16. Navigate to TomEE plus directory and select lib/apply/OK

17. Select the green Run triangle.

> 18\. A browser runs and you should see Hello from TestServlet.

Show your TA your browser visiting the TestServlet.

This is the checkmark for this lab.

While testing, leave the following settings alone. You should just work
from

the defaults provided.

You can set the URL with:

Run/Edit Configurations/Deployment/Application Context

The test browser visits the location specified at:

Run/Edit Configurations/Server/Open browser/URL

**Part 4. Working with Raft**

1)  Visit
    [[https://raft.github.io/raftscope/index.html]{.ul}](https://raft.github.io/raftscope/index.html)
    and play with the Raft simulator.

2)  Show your TA that you were able to get the Raft simulator to show
    the following replicated logs. Note, the final server need not be
    S1. The only requirement is that each log is identical to the one
    shown in Figure 1.

> ![](media/image1.png){width="3.165790682414698in"
> height="2.7038899825021874in"}
>
> Figure 1: Answer to question 7

3)  Working with a fresh copy of the Raft simulator, do the following:

```{=html}
<!-- -->
```
A.  Send two requests from the leader to all followers.

B.  Stop one of the followers.

C.  Send four requests from the leader to the remaining followers.

D.  Resume the stopped follower. Explain to your TA what happened.

4)  Working with a fresh copy of the Raft simulator, do the following:

```{=html}
<!-- -->
```
A.  Wait until a single leader is established.

B.  Stop three of the four followers.

C.  Send three requests from the leader, one after the other.

D.  Explain to your TA what happened.

**Part 5. Working with hashes**

In the slides on Nakamoto consensus, see
[1_Blockchain_Raft_and_Nakamoto.pdf](https://canvas.cmu.edu/courses/19194/files/5122183/download?wrap=1),
there is a quiz question that asks:

Quiz: Which of the blocks on the right can be\
the next block in the chain of length 2?\
Format: Nonce, Difficulty, id, Tx1, Tx2, HashPointer

Use the SHA256 calculator at this URL:

<https://www.xorbin.com/tools/sha256-hash-calculator>,

Show your TA, by referring to the hash, that you have chosen the correct
answer.

Note: There are no newlines or return characters in the correct answer.