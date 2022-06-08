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

<h1 class="gap">Tasks</h1>


 
 <div class="panel-heading panel-heading-actions">
    <h2 class="panel-title">
      0. Hello World
    </h2>
 
    
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [0-hello_world](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/0-hello_world)

  
  <h2 class="panel-title">
      1. Confused smiley
    </h2>
   <p>Write a script that displays a confused smiley <code>&quot;(Ôo)&#39;</code>.</p>
  
  <pre><code>julien@ubuntu:/tmp/h$ ./1-confused_smiley 
&quot;(Ôo)&#39;
julien@ubuntu:/tmp/h$ 
</code></pre>
  
 
   ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [1-confused_smiley](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/1-confused_smiley)
 
 <h2 class="panel-title">
      2. Let&#39;s display a file
    </h2>
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [2-hellofile](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/2-hellofile)

<h2 class="panel-title">
      3. What about 2?
</h2>
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [3-twofiles](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/3-twofiles)
  
   <h2 class="panel-title">
      4. Last lines of a file
    </h2>
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [4-lastlines](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/4-lastlines)
  
  
  <h2 class="panel-title">
      5. I&#39;d prefer the first ones actually
    </h2>
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [5-firstlines](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/5-firstlines)
  
  
  <h2 class="panel-title">
      6. Line #2
    </h2>

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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [6-third_line](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/6-third_line)
  
  <h2 class="panel-title">
      7. It is a good file that cuts iron without making a noise
    </h2>
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [7-file](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/7-file)
 
 <h2 class="panel-title">
      8. Save current state of directory
    </h2>
 
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [8-cwd_state](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/8-cwd_state)
 
 <h2 class="panel-title">
      9. Duplicate last line
    </h2>
 
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
</code></pre>

### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [9-duplicate_last_line](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/9-duplicate_last_line)    
    
 <h2 class="panel-title">
      10. No more javascript
    </h2>
 
 ### Reference i used:
* [linuxhint.com](https://linuxhint.com/remove-all-files-with-extension-linux-command-line/)

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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [10-no_more_js](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/10-no_more_js)
 

 <h2 class="panel-title">
      11. Don&#39;t just count your directories, make your directories count
    </h2>
 <p>Write a script that counts the number of directories and sub-directories in the current directory.</p>

<ul>
<li>The current and parent directories should not be taken into account<br></li>
<li>Hidden directories should be counted<br></li>
</ul>

### Reference i used:
* [www.baeldung.com](https://www.baeldung.com/linux/count-directories)
 
<pre><code>julien@production-503e7013:~/shell/fun_with_the_shell$ ls -lRa
.:
total 32
drwxrwxr-x 3 julien julien 4096 Jan 20 03:53 .
drwxrwxr-x 3 julien julien 4096 Jan 20 02:58 ..
-rwxr--r-- 1 julien julien 43 Jan 20 02:59 0-commas
-rwxr--r-- 1 julien julien 47 Jan 20 02:50 1-empty_casks
-rwxrw-r-- 1 julien julien 68 Jan 20 03:35 2-gifs
-rwxrw-r-- 1 julien julien 47 Jan 20 03:53 3-directories
-rw-rw-r-- 1 julien julien 14 Jan 20 03:35 Makefile
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 test_dir

./test_dir:
total 16
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 .
drwxrwxr-x 3 julien julien 4096 Jan 20 03:53 ..
-rw-rw-r-- 1 julien julien 0 Jan 20 03:40 .horrible_selfie.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 README.md
-rw-rw-r-- 1 julien julien 0 Jan 20 03:17 docker.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:17 file.sh
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 photos
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 rep.gif

./test_dir/photos:
total 8
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 cat.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:22 index.html
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 main.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 rudy_rigot.gif

./test_dir/rep.gif:
total 8
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
julien@production-503e7013:~/shell/fun_with_the_shell$ ./11-directories
3
julien@production-503e7013:~/shell/fun_with_the_shell$
</code></pre>

 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [11-directories](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/11-directories)
  
 
  <h2 class="panel-title">
      12. What’s new
    </h2>
  
 <p>Create a script that displays the 10 newest files in the current directory.</p>

<p>Requirements:</p>

<ul>
<li>One file per line</li>
<li>Sorted from the newest to the oldest</li>
</ul>
 
### Reference i used:
* [www.baeldung.com](https://www.baeldung.com/linux/get-recent-file-in-directory)


<pre><code>alex@ubuntu:/tmp$ ls -l
total 7
-rwxr-xr-x 1 501 dialout  32 Sep 27 23:51 0-hello_world
-rwxr-xr-x 1 501 dialout  46 Sep 28 11:09 10-no_more_js
-rwxr-xr-x 1 501 dialout  43 Sep 28 11:19 11-directories
-rwxr-xr-x 1 501 dialout  30 Sep 29 13:43 12-newest_files
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:54 1-confused_smiley
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:58 2-hellofile
-rwxr-xr-x 1 501 dialout  39 Sep 27 23:58 3-twofiles
-rwxr-xr-x 1 501 dialout  33 Sep 27 23:59 4-lastlines
-rwxr-xr-x 1 501 dialout  33 Sep 28 00:00 5-firstlines
-rwxr-xr-x 1 501 dialout  28 Sep 28 00:25 6-third_line
-rwxr-xr-x 1 501 dialout 110 Sep 28 00:34 7-file
-rwxr-xr-x 1 501 dialout  36 Sep 28 00:34 8-cwd_state
-rwxr-xr-x 1 501 dialout  35 Sep 28 00:35 9-duplicate_last_line
-rw-r--r-- 1 501 dialout  19 Sep 27 23:51 README.md
alex@ubuntu:/tmp$ ./12-newest_files 
12-newest_files
11-directories
10-no_more_js
9-duplicate_last_line
7-file
8-cwd_state
6-third_line
5-firstlines
4-lastlines
3-twofiles
alex@ubuntu:/tmp$
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [12-newest_files](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/12-newest_files)

 
 <h2 class="panel-title">
      13. Being unique is better than being perfect
    </h2>
 <p>Create a script that takes a list of words as input and prints only words that appear exactly once.</p>

<ul>
<li>Input format: One line, one word</li>
<li>Output format: One line, one word</li>
<li>Words should be sorted</li>
</ul>

<pre><code>julien@ubuntu:/tmp/0x02$ cat list 
C#
C
Javascript
Perl
PHP
PHP
ASP
R
Go
C#
C++
R
Perl
Javascript
Javascript
Python
Javascript
Javascript
Javascript
Java
Java
Python
Javascript
Javascript
Javascript
ASP
julien@ubuntu:/tmp/0x02$ cat list | ./13-unique 
C
C++
Go
julien@ubuntu:/tmp/0x02$ 
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [13-unique](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/13-unique)
  
 
 <h2 class="panel-title">
      14. It must be in that file
    </h2>
 <p>Display lines containing the pattern &ldquo;root&rdquo; from the file <code>/etc/passwd</code></p>

<pre><code>$ ./14-findthatword
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
$
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [14-findthatword](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/14-findthatword)

 
 
 <h2 class="panel-title">
      15. Count that word
    </h2>
 <p>Display the number of lines that contain the pattern &ldquo;bin&rdquo; in the file <code>/etc/passwd</code></p>

<pre><code>$ ./15-countthatword
81
$ 
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [15-countthatword](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/15-countthatword)
 
 
 <h2 class="panel-title">
      16. What&#39;s next?
    </h2>
<p>Display lines containing the pattern &ldquo;root&rdquo; and 3 lines after them in the file <code>/etc/passwd</code>.</p>

<pre><code>$ ./16-whatsnext
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
--
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
_usbmuxd:*:213:213:iPhone OS Device Helper:/var/db/lockdown:/usr/bin/false
_dovecot:*:214:6:Dovecot Administrator:/var/empty:/usr/bin/false
_dpaudio:*:215:215:DP Audio:/var/empty:/usr/bin/false
$
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [16-whatsnext](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/16-whatsnext)
 
 
 <h2 class="panel-title">
      17. I hate bins
    </h2>
 <p>Display all the lines in the file <code>/etc/passwd</code> that do not contain the pattern &ldquo;bin&rdquo;.</p>

<pre><code>$ ./17-hidethisword
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
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [17-hidethisword](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/17-hidethisword)
  
 
  <h2 class="panel-title">
      18. Letters only please
    </h2>
 
 <p>Display all lines of the file <code>/etc/ssh/sshd_config</code> starting with a letter.</p>

<ul>
<li>include capital letters as well</li>
</ul>

<pre><code>$ ./18-letteronly
SyslogFacility AUTHPRIV
AuthorizedKeysFile  .ssh/authorized_keys
UsePrivilegeSeparation sandbox # Default for new installations.
AcceptEnv LANG LC_*
Subsystem   sftp    /usr/libexec/sftp-server
$
</code></pre>

 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [18-letteronly](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/18-letteronly)
  
 
 <h2 class="panel-title">
      19. A to Z
    </h2>
  <p>Replace all characters <code>A</code> and <code>c</code> from input to <code>Z</code> and <code>e</code> respectively.</p>

<pre><code>julien@ubuntu:/tmp/0x02$ echo &#39;Replace all characters `A` and `c` from input to `Z` and `e`.&#39; | ./19-AZ 
Replaee all eharaeters `Z` and `e` from input to `Z` and `e`.
julien@ubuntu:/tmp/0x02$ 
</code></pre>

 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [19-AZ](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/19-AZ)
  
 
 <h2 class="panel-title">
      20. Without C, you would live in hiago
    </h2>
 
 <p>Create a script that removes all letters <code>c</code> and <code>C</code> from input.</p>

<pre><code>julien@ubuntu:/tmp/0x02$ echo Chicago | ./20-hiago 
hiago
julien@ubuntu:/tmp/0x02$ 
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [20-hiago](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/20-hiago)
   
 
 <h2 class="panel-title">
      21. esreveR
    </h2>
  <p>Write a script that reverse its input.</p>

<pre><code>julien@ubuntu:/tmp/0x02$ echo &quot;Reverse&quot; | ./21-reverse 
esreveR
julien@ubuntu:/tmp/0x02$ 
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [21-reverse](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/21-reverse)
 
 <h2 class="panel-title">
      22. DJ Cut Killer
    </h2>
 
 <p>Write a script that displays all users and their home directories, sorted by users.</p>

<ul>
<li>Based on the the <code>/etc/passwd</code> file</li>
</ul>

<pre><code>julien@ubuntu:/tmp/0x02$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false
systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false
systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false
systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false
syslog:x:104:108::/home/syslog:/bin/false
_apt:x:105:65534::/nonexistent:/bin/false
messagebus:x:106:110::/var/run/dbus:/bin/false
uuidd:x:107:111::/run/uuidd:/bin/false
lightdm:x:108:114:Light Display Manager:/var/lib/lightdm:/bin/false
whoopsie:x:109:116::/nonexistent:/bin/false
avahi-autoipd:x:110:119:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/bin/false
avahi:x:111:120:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/bin/false
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/bin/false
colord:x:113:123:colord colour management daemon,,,:/var/lib/colord:/bin/false
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/var/run/speech-dispatcher:/bin/false
hplip:x:115:7:HPLIP system user,,,:/var/run/hplip:/bin/false
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/bin/false
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
julien:x:1000:1000:Julien Barbier,,,:/home/julien:/bin/bash
guillaume:x:1001:1001:,,,:/home/guillaume:/bin/bash
betty:x:1002:1002::/home/betty:
julien@ubuntu:/tmp/0x02$
julien@ubuntu:/tmp/0x02$ ./22-users_and_homes 
_apt:/nonexistent
avahi-autoipd:/var/lib/avahi-autoipd
avahi:/var/run/avahi-daemon
backup:/var/backups
betty:/home/betty
bin:/bin
colord:/var/lib/colord
daemon:/usr/sbin
dnsmasq:/var/lib/misc
games:/usr/games
gnats:/var/lib/gnats
guillaume:/home/guillaume
hplip:/var/run/hplip
irc:/var/run/ircd
julien:/home/julien
kernoops:/
lightdm:/var/lib/lightdm
list:/var/list
lp:/var/spool/lpd
mail:/var/mail
man:/var/cache/man
messagebus:/var/run/dbus
news:/var/spool/news
nobody:/nonexistent
proxy:/bin
pulse:/var/run/pulse
root:/root
rtkit:/proc
saned:/var/lib/saned
speech-dispatcher:/var/run/speech-dispatcher
sync:/bin
sys:/dev
syslog:/home/syslog
systemd-bus-proxy:/run/systemd
systemd-network:/run/systemd/netif
systemd-resolve:/run/systemd/resolve
systemd-timesync:/run/systemd
usbmux:/var/lib/usbmux
uucp:/var/spool/uucp
uuidd:/run/uuidd
whoopsie:/nonexistent
www-data:/var/www
julien@ubuntu:/tmp/0x02$ 
</code></pre>
 
 ### Repo:
 * Github repository: alx-system_engineering-devops
 * Directory: 0x02-shell_redirections
 * File: [22-users_and_homes](https://github.com/musfeed/alx-system_engineering-devops/tree/master/0x02-shell_redirections/22-users_and_homes)
   
