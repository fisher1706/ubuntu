# https://www.youtube.com/watch?v=K8W4VUJQdX4&list=PLYl91BhaOf-kkXWweBzgOw555he6S7SUs&index=2

# additional lick -> more about bash
# https://www.youtube.com/watch?v=ZVHx6zKXGc0&list=PLisqB92_b4TnsWzfIHTTqkso-rXQIkPFv&index=2


# ELF - executable file
# /etc/fstab - data about connected devices
# /dev - all devices
# /dev/sda... - hard disks
# "dpkg" - install hard -> "apt" - install soft 
# "install" file - *.deb
# /din - *.deb files

# -----------------------------COMMAND LINE-----------------------------------------------------------------------------

# name of so system
```shell
uname -a
```

# name of current user
```shell
whoami
```

# where I am
```shell
pwd
```

# read first n str of file or folder(file)
```shell
cat 1.txt | head -2
```

# read end n str of file or folder(file)
```shell
cat 1.txt | tail -10
```

# read big file by part (found "a" /a in file)
```shell
less 1.txt
```

# read big file by part (found "a" /a in file) quit - "q"
```shell
ls --help | more
```

# instruction about command or "ls --help" or "info ls" -> number in help - number of section
```shell
man ls
```

# use cat for create file with input from command line - input data - "Control" + D -> exit
```shell
cat > 2.txt
```

# write data from first file to second file - update data in file
```shell
cat 2.txt > 3.txt
```

# write data from first file to second file - add data in file
```shell
cat 2.txt >> 3.txt
```

# write data to file
```shell
ls -la > helper.txt
cat helper.txt
```

# find some data from file -> find "total" in 1.txt
```shell
grep total 1.txt
```

# IF-THEN
```shell
cat 1.txt && echo "READ!"
```

# IF-NOT-THEN
```shell
cat 6.txt || echo "FAIL!"
```

# see history of actions -> history 10 -> show past 10 commands -> !10 - run command 10 -> !! - run last command
```shell
history
```

# data about file
```shell
file 1.txt
```

# create file with certain date
```shell
touch -t 202002111215 new_file.txt
```

# create file with certain date from file
```shell
touch -r 1.txt new_file.txt
```

# create new dir
```shell
mkdir new_dir
ls -la
```

# create new dir in dir
```shell
mkdir -p new_dir_second/docs/diploma
ls -la
```

# delete dir/file -> r - recursively -> possible use -> f - force: rm -rf
```shell
rm -r new_dir_second
ls -la
```

# delete not empty dir with "rmdir"
```shell
rmdir -p new_dir_second/docs/diploma
ls -la
```

# copy file/folder -> r - recursively: cp -r - "-u" -> check time data of file: cp -u
```shell
cp 1.txt 4.txt
```

# copy all files/dirs from dir "hdd" to dir "new_dir"
```shell
cp -r hdd/* newdir
```

# rename file/folder
```shell
mv 2.txt 10.txt
```

# symbolic link -> cat "link_to_file" - see data of file
```shell
ln -s 1.txt link_to_file
cat link_to_file
```

# create hard link
```shell
cp passwd passwd_link
```

# switch to root
```shell
sudo -i
```

# cancel root
```shell
exit
```

# data about all dir
```shell
man hier
```

# to see free place on disks
```shell
df -h
```


# -----------------------------INPUT/OUTPUT-----------------------------------------------------------------------------
# 1. stdin - input <
# 2. stdout - output >
# 3. stderr - error 2>

# stdout - to "grep_file.txt" -> stderr - to "error_grep_file.xtx"
```shell
grep -rl bash /etc/ > grep_file.txt 2> error_grep_file.xtx
```

# stdout and stderr - to "all_data.xtx"
```shell
ls 1.txt 2.txt 20.txt &> all_data.xtx
```

# -----------------------------MOUNT DISKS------------------------------------------------------------------------------

# mount disk to dir "ubuntu" - on "root" user -> mount -r -> "read only"
```shell
mount /dev/sta1 /home/ubuntu/
```

# umount disk from dir "ubuntu" - on "root" user
```shell
umount /home/ubuntu/
```
# "target is busy" -> go out from current dir


# -----------------------------INSTALL PACKAGES-----------------------------

# dpkg - data about all installed packages - dpkg --list apt -> data about "apt" - dpkg --status apt -> see status "apt"
```shell
dpkg --list
```

# data about all files "apt"
```shell
dpkg --listfiles apt
```

# search data about "python"
```shell
dpkg --search python*
```

# install by dpkg "sudo": -install or -i -> work with "*.deb" files
```shell
apt dowload sudo
cd /bin
ls *.deb
dpkg -i sudo_1.9.9-1ubuntu2.4_amd64.deb
```

# delete packages "sudo" by dpkg - "remove" - delete package -> "perch" - delete dependencies
```shell
dpkg --remove sudo
dpkg --purge sudo
```

# install "sudo" by apt -> try to find data in: /etc/apt/sources.list
```shell
apt install sudo 
```

# search data about package -> for example "sudo"
```shell
apt search sudo
```

# get all data about package -> for example "sudo"
```shell
apt show sudo
```

# apt -get == apt

# get data about possibility update packages -> to see detail information -> apt list --upgradable
```shell 
apt list --upgradable 
```

# update packages -> update packages within the version of package
```shell
apt upgrate
```

# update packages -> install new versions of packages
```shell
apt full-upgrate
```

# delete package and dependencies
```shell
apt remove sudo
apt purge sudo
```

# "Have you mooed today"
```shell
apt moo
```

# ------------------------------------USERS-----------------------------------------------------------------------------

# get data about all users
```shell
cat /etc/passwd
```

# get data about one user -> for example "ubuntu"
```shell
getent passwd ubuntu 
```

# to show where data is found about user, group ...
```shell
cat /etc/nsswitch.conf
```

# add user "alex"
```shell
useradd alex
```

# set password for "alex" -> enter password
```shell
passwd alex
```

# create home dir for "alex"
```shell
mldir /home/alex
```

# switch to user "alex"
```shell
su - alex
```

# add user "alex_two" with parameters
```shell
useradd alex_to -m -d /home/alex_to -k /home/ubuntu -s /bin/bash
```

# create user "fisher" (like apt):
```shell
adduser fisher
```

# update user -> -d - change home dir -> -m move home dir -> -l -> set new user_name -> -s /bin/bash  
```shell
usermood fisher -l vova
```

# delete user "fisher" and all data about "fisher"
```shell
userdell -r fisher
```

# ----------------------------------------GROUP-------------------------------------------------------------------------

# to see all data about group
```shell
cat /etc/group
```

# to all data about group "ubuntu"
```shell
groups ubuntu
```

# add group "fisher"
```shell
addgropu fisher
```

# switch user "fisher" to other group "ubuntu"
```shell
usermod fisher -g ubuntu
```

# add second groups for user "fisher" -> G - "cdrom", "audio"
```shell
usermod fisher -G cdrom, audio
```

# add groups for user "fisher" to "second" ("test", "zapel") groups -> [-a -G]
```shell
usermod fisher -a -G test, zapel
```

# delete group "cdrom" -> if main group has same user -> can not delete group
```shell
dellgroup cdrom
```

# -----------------------------USER CONFIGURATIONS----------------------------------------------------------------------

# user configuration "fisher" -> user "fisher" can not login
```shell
usermod fisher -s /bin/false
# OR
usermod fisher -s /sbin/nologin
```

# block user "fisher"
```shell
usermod -L fisher
```

# unblock user "fisher"
```shell
usermod -U fisher
```

# set expire data for user "fisher"
```shell
usermod fisher -e 2022-12-20
```

# get data about user "fisher"
```shell
chage -l fisher
```