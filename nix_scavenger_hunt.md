# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*  /home/luish/wats1030-intro-to-unix/challenge_files

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*

challenge_files             nix_scavenger_hunt_stretch.md
LICENSE                     README.md
nix_scavenger_hunt.md       super_scavengers.md
nix_scavenger_hunt.md.save

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?

-a shows you the hidden folders (the ones that begin with '.'
-l shows the permissions of the file
-l when used with flags such as -l or -s shows the size in a human-readable way.

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?

-a, --all
              do not ignore entries starting with .

-l     use a long listing format

-h, --human-readable
              with -l and -s, print sizes like 1K  234M  2G etc.

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here: /

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here: /home/luish

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?* 3

2015_special_stuff.demo  cloaked-wookie.demo  scooter-dou ble-mamba.demo


* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?* /home/luish/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?* it showed the previous command that I used, in this case pwd.

* Press the up arrow a few more times. *What do you see?* The previous command I've used.

* Run the `history` command. *What do you see?* It shows me the commands I've used.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?* luish

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

luish    tty1         2019-01-17 11:45 (:0)
luish    pts/0        2019-01-17 11:47 (:0)
luish    pts/1        2019-01-17 11:45 (:0)
luish    pts/2        2019-01-17 12:41 (:0)
luish    pts/3        2019-01-17 11:55 (:0)
luish    pts/4        2019-01-17 12:41 (:0)

* How long has your system been running? Use `uptime` to see, and *paste the result here:*  13:25:10 up  1:40,  4 users,  load average: 1.27, 0.92, 0.79

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*  It shows the processes running on the system. The manual of ps further explains that the flags allows to refine the output of it.

a shows the processes for all users
u displays the process of the current user
x displays the processes not attached to the terminal.

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?* I see top as the terminal counterpart of the task manager. AS it shows you in real-time the current processes of the running system. It shows the usage of the cpu, ram of each process.

### Finding and Viewing Files


* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* two
credit_cards2.txt  credit_cards.txt
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?* 01-15-2015

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

### Finding and Viewing Files

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?* ./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* two files

Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

./serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* the content of the challenge_files folder

    * Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* It shows the output of the ls -alh command, but it allows the user to actually give a look of the


* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

root       875  0.0  0.1 104096 15548 ?        S    19:17   0:00 /usr/lib/sddm/sddm-helper --socket /tmp/sddm-auth4f2deb57-6de9-4918-8524-d7e67ee6fc4f --id 1 --start /usr/bin/startkde --user luish
luish      879  0.0  0.0  36508  7800 ?        Ss   19:17   0:00 /usr/lib/systemd/systemd --user
luish      880  0.0  0.0 227964  2384 ?        S    19:17   0:00 (sd-pam)
luish      887  0.0  0.4 316320 39832 ?        Sl   19:17   0:01 /usr/bin/kwalletd5 --pam-login 7 3
luish      888  0.0  0.0   9100  3372 ?        S    19:17   0:00 /bin/sh /usr/bin/startkde
luish      895  0.0  0.0  10956  4444 ?        Ss   19:17   0:01 /usr/bin/dbus-daemon --session --address=systemd: --nofork --nopidfile --systemd-activation --syslog-only
luish      923  0.0  0.0   2204    88 ?        S    19:17   0:00 /usr/lib/kf5/start_kdeinit --kded +kcminit_startup
luish      924  0.0  0.2 117072 19688 ?        Ss   19:17   0:00 kdeinit5: Running...
luish      925  0.0  0.4 311276 39416 ?        Sl   19:17   0:01 /usr/lib/kf5/klauncher --fd=9
luish      928  0.1  0.7 1161016 58212 ?       Sl   19:17   0:08 kded5 [kdeinit5]
luish      943  0.0  0.4 311008 38432 ?        Sl   19:17   0:02 /usr/bin/kglobalaccel5
luish      946  0.0  0.5 326412 40428 ?        Sl   19:17   0:01 /usr/bin/kaccess
luish      948  0.0  0.0  53004  7080 ?        S    19:17   0:00 kwrapper5 /usr/bin/ksmserver
luish      950  0.0  0.5 405284 47592 ?        Sl   19:17   0:03 /usr/bin/ksmserver
luish      954  0.0  0.2 248656 19188 ?        Sl   19:17   0:02 /usr/lib/kf5/kscreen_backend_launcher
luish      966  0.0  0.0 158912  5124 ?        Sl   19:17   0:00 /usr/lib/dconf-service
luish      969  9.3  1.8 3076568 147504 ?      Sl   19:17  12:21 /usr/bin/kwin_x11 -session 10116d3dddd000154773437900000009200010_1547749621_276459
luish      971  0.0  0.3 268677268 25640 ?     SNl  19:17   0:00 /usr/bin/baloo_file
luish      973  0.0  0.8 537788 71476 ?        Sl   19:17   0:04 /usr/bin/krunner
luish      975  3.6  3.0 2743560 245604 ?      Sl   19:17   4:49 /usr/bin/plasmashell
luish      979  0.0  0.5 465820 41652 ?        Sl   19:17   0:01 /usr/lib/polkit-kde-authentication-agent-1
luish      983  0.0  0.2 255420 20952 ?        Sl   19:17   0:01 /usr/bin/xembedsniproxy
luish      987  0.0  0.2 256300 22332 ?        Sl   19:17   0:01 /usr/bin/gmenudbusmenuproxy
luish      997  0.0  0.6 408876 48780 ?        Sl   19:17   0:02 /usr/lib/kdeconnectd -session 10116d3dddd000154774924600000009320004_1547749606_557899
luish      998  1.8  0.1 1375132 13388 ?       S<sl 19:17   2:26 /usr/bin/pulseaudio --daemonize=no
luish     1012  0.0  0.5 331624 46216 ?        Sl   19:17   0:03 /usr/bin/msm_kde_notifier -session 10116d3dddd000154773437900000009200009_1547749606_557912
luish     1031  0.0  0.4 573200 32556 ?        Sl   19:17   0:01 /usr/bin/kactivitymanagerd start-daemon
luish     1035  0.0  0.4 435468 39252 ?        Sl   19:17   0:03 /usr/lib/org_kde_powerdevil -session 10116d3dddd000154773437900000009200011_1547749606_558089
luish     1042  0.0  0.6 359280 49424 ?        Sl   19:17   0:02 /usr/bin/octopi-notifier -session 10116d3dddd000154773438000000009200013_1547749606_558093
luish     1052  0.0  0.0 253752  6712 ?        Sl   19:17   0:00 /usr/lib/pulse/gsettings-helper
luish     1055  0.0  0.8 450436 67076 ?        Sl   19:17   0:06 /usr/bin/yakuake -session 10116d3dddd000154774924900000009320010_1547749606_558067
luish     1086  0.0  0.0 237336  4988 ?        Sl   19:17   0:00 /usr/lib/geoclue-2.0/demos/agent
luish     1115  0.0  0.0   9424  4000 pts/1    Ss+  19:17   0:00 /bin/bash
luish     1130  0.0  0.0  46632  6716 ?        Ss   19:17   0:00 /usr/lib/bluetooth/obexd
luish     1137  0.0  0.4 315144 38872 ?        Sl   19:17   0:01 /usr/bin/kuiserver5
luish     1180  0.0  0.0 241892  6980 ?        Ssl  19:17   0:00 /usr/lib/gvfsd
luish     1185  0.0  0.0 383160  5880 ?        Sl   19:17   0:00 /usr/lib/gvfsd-fuse /run/user/1000/gvfs -f -o big_writes
luish     1657  0.0  0.2 117472 17336 ?        S    19:18   0:00 file.so [kdeinit5] file local:/run/user/1000/klauncherfgXVrS.1.slave-socket local:/run/user/1000/kded5lCSUXo.1.slave-socket
luish     2226  0.0  0.5 268752496 41128 ?     Sl   19:23   0:01 /usr/lib/baloorunner
luish     6345  4.0  2.7 1076604 219020 ?      Sl   20:38   2:05 /usr/lib/opera/opera
luish     6348  0.0  0.0   2724   860 ?        S    20:38   0:00 /usr/lib/opera/opera_sandbox /usr/lib/opera/opera --type=zygote --enable-proprietary-media-types-playback
luish     6349  0.0  0.3 270340 30380 ?        S    20:38   0:00 /usr/lib/opera/opera --type=zygote --enable-proprietary-media-types-playback
luish     6352  0.0  0.0 270340  6724 ?        S    20:38   0:00 /usr/lib/opera/opera --type=zygote --enable-proprietary-media-types-playback
luish     6373  2.1  1.2 376828 101112 ?       Sl   20:38   1:07 /usr/lib/opera/opera --type=gpu-process --field-trial-handle=9392875974278401074,14626738447476436429,131072 --enable-proprietary-media-types-playback --gpu-preferences=KAAAAAAAAACAAABAAQAAAAAAAAAAAGAAAAAAAAAAAAAIAAAAAAAAAAgAAAAAAAAA --enable-proprietary-media-types-playback --service-request-channel-token=12064589404075820002
luish     6431  0.0  0.9 573488 76136 ?        Sl   20:38   0:00 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=6370166559705719217 --lang=en-US --enable-proprietary-media-types-playback --extension-process --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=6370166559705719217 --renderer-client-id=3 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     6503  0.2  1.2 593936 103700 ?       Sl   20:38   0:07 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=4170627098435872029 --lang=en-US --enable-proprietary-media-types-playback --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=4170627098435872029 --renderer-client-id=13 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     6540  0.0  0.8 539172 70328 ?        Sl   20:38   0:00 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=3543636747215368350 --lang=en-US --enable-proprietary-media-types-playback --extension-process --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=3543636747215368350 --renderer-client-id=4 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     6627  0.0  1.0 568944 84180 ?        Sl   20:38   0:00 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=17472680774183224638 --lang=en-US --enable-proprietary-media-types-playback --extension-process --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=17472680774183224638 --renderer-client-id=15 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     6825  3.6  3.6 874292 293508 ?       Sl   20:38   1:54 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=234240967959323352 --lang=en-US --enable-proprietary-media-types-playback --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=234240967959323352 --renderer-client-id=9 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     6862  0.1  1.5 638992 127596 ?       Sl   20:38   0:04 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=15950923553629216102 --lang=en-US --enable-proprietary-media-types-playback --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=15950923553629216102 --renderer-client-id=5 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     7256  3.6  3.3 1022984 267776 ?      Sl   20:56   1:13 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=3617427873245856058 --lang=en-US --enable-proprietary-media-types-playback --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=3617427873245856058 --renderer-client-id=16 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish     8323  0.0  0.0 312148  6128 ?        Ssl  21:02   0:00 /usr/lib/at-spi-bus-launcher
luish     8329  0.0  0.0  10556  4116 ?        S    21:02   0:00 /usr/bin/dbus-daemon --config-file=/usr/share/defaults/at-spi2/accessibility.conf --nofork --print-address 3
luish     8331  0.0  0.0 171676  7240 ?        Sl   21:02   0:00 /usr/lib/at-spi2-registryd --use-gnome-session
luish    18700  0.3  0.8 448044 65008 ?        Sl   21:18   0:02 /usr/bin/konsole
luish    18743  0.0  0.0   9424  4188 pts/2    Ss   21:18   0:00 /bin/bash
luish    18840  0.0  0.0   9100  1856 ?        S    21:19   0:00 /bin/bash /usr/bin/atom
luish    18842  5.1  2.5 1621592 202668 ?      Sl   21:19   0:30 /usr/lib/electron/electron --executed-from=/home/luish --pid=18838 /usr/lib/atom/atom
luish    18844  0.0  0.6 363700 52360 ?        S    21:19   0:00 /usr/lib/electron/electron --type=zygote --no-sandbox
luish    18911  2.4  1.0 479096 81204 ?        Sl   21:20   0:14 /usr/lib/electron/electron --type=gpu-process --no-sandbox --gpu-preferences=KAAAAAAAAACAAACAAQAAAAAAAAAAAGAAEAAAAAAAAAAAAAAAAAAAAAgAAAAAAAAA --service-request-channel-token=29C6206900911D91F60238788A2E1DBD
luish    18928 18.0  3.6 1398528 289728 ?      Sl   21:20   1:45 /usr/lib/electron/electron --type=renderer --enable-experimental-web-platform-features --no-sandbox --service-pipe-token=A8EE0716790358CCB3B2EF21308C9499 --lang=en-US --app-path=/usr/lib/atom --node-integration=true --webview-tag=true --no-sandbox --background-color=#fff --disable-blink-features=Auxclick --num-raster-threads=4 --enable-main-frame-before-activation --enable-compositor-image-animations --service-request-channel-token=A8EE0716790358CCB3B2EF21308C9499 --renderer-client-id=4 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish    18989  0.1  1.0 1083096 83544 ?       Sl   21:20   0:00 /usr/lib/electron/electron --type=renderer --enable-experimental-web-platform-features --no-sandbox --service-pipe-token=0423C84657BFC520122F17048E89272F --lang=en-US --app-path=/usr/lib/atom --node-integration=true --webview-tag=true --no-sandbox --background-color=#fff --num-raster-threads=4 --enable-main-frame-before-activation --enable-compositor-image-animations --service-request-channel-token=0423C84657BFC520122F17048E89272F --renderer-client-id=6 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish    19360  4.3  1.5 654512 122616 ?       Sl   21:24   0:12 /usr/lib/opera/opera --type=renderer --field-trial-handle=9392875974278401074,14626738447476436429,131072 --service-pipe-token=10733637425892285575 --lang=en-US --enable-proprietary-media-types-playback --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=4 --enable-main-frame-before-activation --service-request-channel-token=10733637425892285575 --renderer-client-id=29 --shared-files=v8_context_snapshot_data:100,v8_natives_data:101
luish    19491  0.0  0.0  13932  4408 pts/2    T    21:27   0:00 man top
luish    19501  0.0  0.0   8512  1064 pts/2    T    21:27   0:00 less
luish    19553  0.0  0.0  13260  3488 pts/2    R+   21:29   0:00 ps aux
luish    19554  0.0  0.0   8316  2220 pts/2    S+   21:29   0:00 grep --colour=auto luish
