 <h1 class="gap">0x02. Shell, I/O Redirections and filters</h1>
<h2>Resources</h2>

<p><strong>Read or watch</strong>:</p>

<ul>
<li><a href="http://linuxcommand.org/lc3_lts0070.php" title="Shell, I/O Redirection" target="_blank">Shell, I/O Redirection</a> </li>
<li><a href="http://mywiki.wooledge.org/BashGuide/SpecialCharacters" title="Special Characters" target="_blank">Special Characters</a> </li>
</ul>

<p><strong>man or help</strong>:</p>

<ul>
<li><code>echo</code></li>
<li><code>cat</code></li>
<li><code>head</code></li>
<li><code>tail</code></li>
<li><code>find</code></li>
<li><code>wc</code></li>
<li><code>sort</code></li>
<li><code>uniq</code></li>
<li><code>grep</code></li>
<li><code>tr</code></li>
<li><code>rev</code></li>
<li><code>cut</code></li>
<li><code>passwd (5)</code> (<em>i.e. <code>man 5 passwd</code></em>)</li>
</ul>

<h2>Learning Objectives</h2>

<p>At the end of this project, you are expected to be able to <a href="https://fs.blog/feynman-learning-technique/?fbclid=IwAR2K5_BGPVo0QjJXkOIIqNsqcXK4lTskPWJvA0asKQIGtCPWaQBdKmj1Ztg" title="explain to anyone" target="_blank">explain to anyone</a>, <strong>without the help of Google</strong>:</p>

<h3>Shell, I/O Redirection</h3>

<ul>
<li>What do the commands <code>head</code>, <code>tail</code>, <code>find</code>, <code>wc</code>, <code>sort</code>, <code>uniq</code>, <code>grep</code>, <code>tr</code> do</li>
<li>How to redirect standard output to a file</li>
<li>How to get standard input from a file instead of the keyboard</li>
<li>How to send the output from one program to the input of another program</li>
<li>How to combine commands and filters with redirections</li>
</ul>

<h3>Special Characters</h3>

<ul>
<li>What are special characters</li>
<li>Understand what do the white spaces, single quotes, double quotes, backslash, comment, pipe, command separator, tilde and how and when to use them</li>
</ul>

<h3>Other Man Pages</h3>

<ul>
<li>How to display a line of text</li>
<li>How to concatenate files and print on the standard output</li>
<li>How to reverse a string</li>
<li>How to remove sections from each line of files</li>
<li>What is the <code>/etc/passwd</code> file and what is its format</li>
<li>What is the <code>/etc/shadow</code> file and what is its format</li>
</ul>

<h3>Copyright - Plagiarism</h3>

<ul>
<li>You are tasked to come up with solutions for the tasks below yourself to meet with the above learning objectives.</li>
<li>You will not be able to meet the objectives of this or any following project by copying and pasting someone else&rsquo;s work. </li>
<li>You are not allowed to publish any content of this project.</li>
<li>Any form of plagiarism is strictly forbidden and will result in removal from the program.</li>
</ul>

<h2>Requirements</h2>

<h3>General</h3>

<ul>
<li>Allowed editors: <code>vi</code>, <code>vim</code>, <code>emacs</code></li>
<li>All your scripts will be tested on Ubuntu 20.04 LTS</li>
<li>All your scripts should be exactly two lines long (<code>$ wc -l file</code> should print 2)</li>
<li>All your files should end with a new line (<a href="http://unix.stackexchange.com/questions/18743/whats-the-point-in-adding-a-new-line-to-the-end-of-a-file/18789">why?</a>)</li>
<li>The first line of all your files should be exactly <code>#!/bin/bash</code></li>
<li>A <code>README.md</code> file, at the root of the folder of the project, describing what each script is doing</li>
<li>You are not allowed to use backticks, <code>&amp;&amp;</code>, <code>||</code> or <code>;</code></li>
<li>All your files must be executable</li>
<li>You are not allowed to use <code>sed</code> or <code>awk</code></li>
</ul>

<h2>More Info</h2>

<p>Read your <code>/etc/passwd</code> and <code>/etc/shadow</code> files.</p>

<p>Note: You do not have to learn about <code>fmt</code>, <code>pr</code>, <code>du</code>, <code>gzip</code>, <code>tar</code>, <code>lpr</code>, <code>sed</code> and <code>awk</code> yet.</p>

  </div>
</div>

<h2 class="gap">Tasks</h2>

  <div class="panel-heading panel-heading-actions">
    <h3 class="panel-title">
      0. Hello World
    </h3>

    
  </div>
<!-- Task Body -->
    <p>Write a script that prints “Hello, World”, followed by a new line to the standard output.</p> 
<pre><code>julien@ubuntu:/tmp/h$ ./0-hello_world 
Hello, World
julien@ubuntu:/tmp/h$ ./0-hello_world | cat -e
Hello, World$
julien@ubuntu:/tmp/h$ 
</code></pre>

  </div>

  <div class="list-group">
    <!-- Task URLs -->

  ### Repo:

    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 0-hello_world
  
  <h3 class="panel-title">
      1. Confused smiley
    </h3>
   <p>Write a script that displays a confused smiley <code>&quot;(Ôo)&#39;</code>.</p>
  
  <pre><code>julien@ubuntu:/tmp/h$ ./1-confused_smiley 
&quot;(Ôo)&#39;
julien@ubuntu:/tmp/h$ 
</code></pre>
  
  ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 1-confused_smiley
  
   <h3 class="panel-title">
      2. Let&#39;s display a file
    </h3>
  <p>Display the content of the <code>/etc/passwd</code> file.</p>

<p>Example:</p>

<pre><code>$ ./2-hellofile
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
_installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
_lp:*:26:26:Printing Services:/var/spool/cups:/usr/bin/false
_postfix:*:27:27:Postfix Mail Server:/var/spool/postfix:/usr/bin/false
_scsd:*:31:31:Service Configuration Service:/var/empty:/usr/bin/false
_ces:*:32:32:Certificate Enrollment Service:/var/empty:/usr/bin/false
_mcxalr:*:54:54:MCX AppLaunch:/var/empty:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
$
</code></pre>
 
  ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 2-hellofile
 

<h3 class="panel-title">
      3. What about 2?
</h3>
<p>Display the content of <code>/etc/passwd</code> and <code>/etc/hosts</code></p>
<p>Example:</p>

<pre><code>$ ./3-twofiles
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting. Do not change this entry.
##
127.0.0.1   localhost
255.255.255.255 broadcasthost
::1 localhost
$
</code></pre>
  ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 3-twofiles
  
   <h3 class="panel-title">
      4. Last lines of a file
    </h3>
   <p>Display the last 10 lines of <code>/etc/passwd</code></p>

<p>Example:</p>

<pre><code>$ ./4-lastlines
_assetcache:*:235:235:Asset Cache Service:/var/empty:/usr/bin/false
_coremediaiod:*:236:236:Core Media IO Daemon:/var/empty:/usr/bin/false
_launchservicesd:*:239:239:_launchservicesd:/var/empty:/usr/bin/false
_iconservices:*:240:240:IconServices:/var/empty:/usr/bin/false
_distnote:*:241:241:DistNote:/var/empty:/usr/bin/false
_nsurlsessiond:*:242:242:NSURLSession Daemon:/var/db/nsurlsessiond:/usr/bin/false
_nsurlstoraged:*:243:243:NSURLStorage Daemon:/var/empty:/usr/bin/false
_displaypolicyd:*:244:244:Display Policy Daemon:/var/empty:/usr/bin/false
_astris:*:245:245:Astris Services:/var/db/astris:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false

</code></pre>

<p>Tips: &ldquo;Thinks of it as a cat, what is at the end of it?&rdquo;</p>
  
  ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 4-lastlines
  
  
  <h3 class="panel-title">
      5. I&#39;d prefer the first ones actually
    </h3>
  <p>Display the first 10 lines of <code>/etc/passwd</code></p>
  
  <p>Example:</p>

<pre><code>$ ./5-firstlines
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
</code></pre>
  
   ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 5-firstlines
  
  <h3 class="panel-title">
      6. Line #2
    </h3>

  <p>Write a script that displays the third line of the file <code>iacta</code>.</p>

<p>The file <code>iacta</code> will be in the working directory</p>

<ul>
<li>You&rsquo;re not allowed to use <code>sed</code></li>
</ul>

<pre><code>julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est (&quot;The die is cast&quot;) is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ ./6-third_line 
Alea iacta est (&quot;The die is cast&quot;) is a Latin phrase attributed by Suetonius
julien@ubuntu:/tmp/h$ 
</code></pre>

<p>Note: The output will differ, depending on the content of the file <code>iacta</code>.</p>

### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 6-third_line
  
  <h3 class="panel-title">
      7. It is a good file that cuts iron without making a noise
    </h3>
  <p>Write a shell script that creates a file named exactly <code>\*\\&#39;&quot;Best School&quot;\&#39;\\*$\?\*\*\*\*\*:)</code> containing the text <code>Best School</code>  ending by a new line.</p>

<pre><code>julien@ubuntu:~/shell$ ls &amp;&amp; ./7-file &amp;&amp; ls -l &amp;&amp; cat -e \\*
0-mac_and_cheese 7-file 7-file~ Makefile
total 20
-rwxrw-r-- 1 julien julien 79 Jan 20 06:24 0-mac_and_cheese
-rwxrw-r-- 1 julien julien 90 Jan 20 06:40 7-file
-rwxrw-r-- 1 julien julien 69 Jan 20 06:37 7-file~
-rw-rw-r-- 1 julien julien 14 Jan 20 06:38 Makefile
-rw-rw-r-- 1 julien julien 17 Jan 20 06:40 &#39;\*\\&#39;&quot;Best School&quot;\&#39;\\*$\?\*\*\*\*\*:)&#39;
Best School$
julien@ubuntu:~/shell$
</code></pre>

 ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 7-file
 
 <h3 class="panel-title">
      8. Save current state of directory
    </h3>
 
 <p>Write a script that writes into the file <code>ls_cwd_content</code> the result of the command <code>ls -la</code>. If the file <code>ls_cwd_content</code> already exists, it should be overwritten. If the file <code>ls_cwd_content</code> does not exist, create it.</p>
 
 <pre><code>julien@ubuntu:/tmp/h$ ls -la
total 20
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
julien@ubuntu:/tmp/h$ ./8-cwd_state 
julien@ubuntu:/tmp/h$ ls -la
total 24
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
-rw-rw-r--  1 julien julien  329 Sep 20 18:18 ls_cwd_content
julien@ubuntu:/tmp/h$ cat ls_cwd_content 
total 20
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
-rw-rw-r--  1 julien julien    0 Sep 20 18:18 ls_cwd_content
julien@ubuntu:/tmp/h$ 
</code></pre>
 
 
  ### Repo:
    * GitHub repository: alx-system_engineering-devops
    * Directory: 0x02-shell_redirections
    * File: 8-cwd_state
 
 <h3 class="panel-title">
      9. Duplicate last line
    </h3>
 
 <p>Write a script that duplicates the last line of the file <code>iacta</code></p>

<ul>
<li>The file <code>iacta</code> will be in the working directory</li>
</ul>

<pre><code>julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est (&quot;The die is cast&quot;) is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ ./9-duplicate_last_line 
julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est (&quot;The die is cast&quot;) is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ 



  ### Repo:
      * GitHub repository: alx-system_engineering-devops
      * Directory: 0x02-shell_redirections
      * File: 9-duplicate_last_line
    
    
    
 <h3 class="panel-title">
      10. No more javascript
    </h3>

<p>Write a script that deletes all the regular files (not the directories) with a <code>.js</code> extension that are present in the current directory and all its subfolders.</p>

<pre><code>julien@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 julien julien   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 julien julien 4096 Sep 20 18:23 dir1
drwxrwxr-x 2 julien julien 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 julien julien  329 Sep 20 18:18 ls_cwd_content
-rw-rw-r-- 1 julien julien    0 Sep 20 18:23 main.js

./dir1:
total 0
-rw-rw-r-- 1 julien julien 0 Sep 20 18:23 code.js

./dir.js:
total 0
julien@ubuntu:/tmp/h$ ./10-no_more_js 
julien@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 julien julien   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 julien julien 4096 Sep 20 18:29 dir1
drwxrwxr-x 2 julien julien 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 julien julien  329 Sep 20 18:18 ls_cwd_content

./dir1:
total 0

./dir.js:
total 0
julien@ubuntu:/tmp/h$ 
</code></pre>

### Repo:
      * GitHub repository: alx-system_engineering-devops
      * Directory: 0x02-shell_redirections
      * File: 10-no_more_js
 
