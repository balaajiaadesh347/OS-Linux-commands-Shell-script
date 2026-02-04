# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
sha
shyam
vicky
```
^d
cat > file2
```
naga
rahul
suresh
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
sha
shyam
vicky
```
cat < file2
## OUTPUT
```
naga
rahul
suresh
```
# Comparing Files
cmp file1 file2
## OUTPUT
 ```
file1 file2 differ: byte 2, line 1
```
comm file1 file2
 ## OUTPUT
```
sha
	shyam
vicky
	naga
	rahul
suresh
```
diff file1 file2
## OUTPUT
```
1,4c1,4
< sha
< shyam
< vicky

---
> naga
> rahul
> suresh
```
#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
```
Hel
Thi
```
cut -d "|" -f 1 file22
## OUTPUT

```
1001 
1002 
1003 
```
cut -d "|" -f 2 file22
## OUTPUT
```
 Ram 
 tom 
 Jeo 
```
cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT


<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/1b6e8051-aa25-4fc7-a124-d835287b8a30" />


grep hello newfile 
## OUTPUT


<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/6d857122-3047-421a-9c66-81def85b09dd" />


grep -v hello newfile 
## OUTPUT
```
Hello world

```
cat newfile | grep -i "hello"
## OUTPUT

<img width="140" height="50" alt="image" src="https://github.com/user-attachments/assets/449340e5-869a-47d1-ba65-46b024a11e6c" />


cat newfile | grep -i -c "hello"
## OUTPUT
```
2
```
grep -R ubuntu /etc
## OUTPUT


<img width="1283" height="623" alt="image" src="https://github.com/user-attachments/assets/24559432-8b0d-4493-b8d3-4c7c4a8fb6b9" />


grep -w -n world newfile   
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/f71ca3bf-7718-443c-a6fb-554dcbad408e" />

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT


<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/d9bc2690-e300-4266-89fb-671f4448a78d" />


egrep -w '(H|h)ello' newfile 
## OUTPUT


<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/1c9162b8-9692-49f5-aff3-f63141649027" />


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT


<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/90c6f4a4-22ec-4e50-8ce9-32f79a0c131a" />



egrep '(^hello)' newfile 
## OUTPUT


<img width="161" height="28" alt="image" src="https://github.com/user-attachments/assets/8a2f88b2-5cf2-489b-bf0b-1e6f03d216f7" />


egrep '(world$)' newfile 
## OUTPUT


<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/aeb2718a-a83d-4e0a-9fd5-3b5808fa80e6" />


egrep '(World$)' newfile 
## OUTPUT


<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/ebe364bf-36e5-4eb9-8419-352abb4080ee" />


egrep '((W|w)orld$)' newfile 
## OUTPUT


<img width="316" height="69" alt="image" src="https://github.com/user-attachments/assets/d31fc1c7-61af-46e2-bd55-65fff5356798" />


egrep '[1-9]' newfile 
## OUTPUT


<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/028c6447-97a8-486d-8860-5c8cb7404d0b" />


egrep 'Linux.*world' newfile 
## OUTPUT


<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/c38209cd-ee89-475c-8293-9c6bd5004eb8" />



## OUTPUT


<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/91852719-28de-4586-97a5-3b0e504908ce" />


egrep 's{1,2}' newfile
## OUTPUT 

<img width="315" height="48" alt="image" src="https://github.com/user-attachments/assets/1a6743c2-e2e3-469b-a7df-d84688687d06" />


cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```
sed -n -e '$p' file23
## OUTPUT
```
1002 | tom |  5000 | Admin
```
sed  -e 's/Ram/Sita/' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
```
sed  -e '2s/Ram/Sita/' file23
## OUTPUT
```
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR
```
sed  '/tom/s/5000/6000/' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```
sed -n -e '1,5p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```
sed -n -e '2,/Joe/p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```
seq 10 
## OUTPUT
```
1
2
3
4
5
6
7
8
9
10
```
seq 10 | sed -n '4,6p'
## OUTPUT
```
4
5
6
```
seq 10 | sed -n '2,~4p'
## OUTPUT
```
2
3
4
```
seq 3 | sed '2a hello'
## OUTPUT
```
1
2
hello
3
```
seq 2 | sed '2i hello'
## OUTPUT
```
1
hello
2
```
seq 10 | sed '2,9c hello'
## OUTPUT
```
1
hello
10
```
sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
$1001 | Ram | 10000 | HR
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
```
sed -n '2,4{s/$/*/;p}' file23
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR
```
cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
```
1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR
```
cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
```
www.yahoo.com
www.google.com
www.mrcet.com
 ```
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT


<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/3123ea0e-96b3-49b5-99fe-03481fba766a" />


#Backup commands
tar -cvf backup.tar *
mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT

<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/42788c80-14c8-47c7-a08a-33c78613a103" />


tar -xvf backup.tar
## OUTPUT

<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/884c5e79-6a56-4c10-adf6-8c0bb6e3066b" />


 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
```
 echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT

<img width="471" height="89" alt="image" src="https://github.com/user-attachments/assets/a4d3db20-583d-4008-bcba-069c4e6d4bbc" />


cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT

<img width="650" height="418" alt="image" src="https://github.com/user-attachments/assets/21aedcb5-003c-427e-83c2-de3c8dc616ec" />

 
ls file1
## OUTPUT
```
file1
```
echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
 ```
127
```
 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT


<img width="646" height="250" alt="image" src="https://github.com/user-attachments/assets/2978621e-5303-49e5-b86d-6dc71c53f21f" />


chmod 755 strcomp.sh
 
./strcomp.sh 

# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT

<img width="450" height="35" alt="image" src="https://github.com/user-attachments/assets/f8626e1a-83bc-4c7a-855e-7e7d4f88c5d4" />

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT


<img width="449" height="69" alt="image" src="https://github.com/user-attachments/assets/4770aba7-fc6c-428a-adf5-544380474c3b" />


# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
##OUTPUT

<img width="449" height="69" alt="image" src="https://github.com/user-attachments/assets/e8e4727c-0d5e-4a25-886b-7eb8f582c5a1" />

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT

<img width="359" height="63" alt="image" src="https://github.com/user-attachments/assets/cff506ad-bfd6-479c-855f-04f4e8d5200a" />

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT

<img width="459" height="45" alt="image" src="https://github.com/user-attachments/assets/db23f0a1-17a1-4e6a-8fd7-b94bf3645db6" />


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT

<img width="301" height="35" alt="image" src="https://github.com/user-attachments/assets/4626f95b-cb72-4828-9bcd-d8ce8644e1d4" />

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
## output:

<img width="457" height="45" alt="image" src="https://github.com/user-attachments/assets/3dc2f34b-01ef-4128-95b6-404bb745d2ac" />

 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
 
 ## output:

 <img width="458" height="244" alt="image" src="https://github.com/user-attachments/assets/fc477e19-2d41-4d05-a357-e0f5b832626d" />

cat > untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
  $ ./untiltest.sh
 
 ## output:

 <img width="554" height="141" alt="image" src="https://github.com/user-attachments/assets/b74333d5-c3e9-4e3a-96bd-f5db3f014b5e" />

cat > forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh

$ ./forin1.sh
 ## output:

 <img width="629" height="198" alt="image" src="https://github.com/user-attachments/assets/b51b9c69-fb69-4692-8009-cdea12c3ba07" />

 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat > forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
## output:

<img width="633" height="134" alt="image" src="https://github.com/user-attachments/assets/64d20122-4441-4ba6-a36f-4180de99a9c9" />

 
cat > forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 

 $ ./forin3.sh
 ## output:

<img width="639" height="204" alt="image" src="https://github.com/user-attachments/assets/000ca390-7981-4e1e-87cb-3e052d026e98" />


cat > forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

$ ./forin2.sh

## OUTPUT

<img width="637" height="161" alt="image" src="https://github.com/user-attachments/assets/6d49c915-d30b-49e3-8758-6a8f7edbfa55" />


cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT

<img width="636" height="178" alt="image" src="https://github.com/user-attachments/assets/e79a1ba4-f04e-4330-83f4-7f6e41113871" />


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT

<img width="626" height="138" alt="image" src="https://github.com/user-attachments/assets/169fab7b-cd93-47f8-bea1-5f7718122880" />

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT

<img width="626" height="138" alt="image" src="https://github.com/user-attachments/assets/b9dc3cfb-c190-40d8-858a-6a86919ffb76" />

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT


 <img width="629" height="288" alt="image" src="https://github.com/user-attachments/assets/a2272364-d99d-4858-bff1-87eeeb5f3a96" />

cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
## OUTPUT

<img width="656" height="78" alt="image" src="https://github.com/user-attachments/assets/61783a16-3250-4a6c-954a-25126d5b5e2b" />

 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT

 	<img width="656" height="115" alt="image" src="https://github.com/user-attachments/assets/4acec7de-1782-4bb4-8c05-debc3e38c664" />

cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
<img width="653" height="70" alt="image" src="https://github.com/user-attachments/assets/97554697-826f-4449-9aae-21922d02c589" />


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT



$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 

 <img width="653" height="49" alt="image" src="https://github.com/user-attachments/assets/03ac87bb-d2da-4efb-9d72-b7fe45291795" />

 ./funcex.sh 1 2

 <img width="653" height="49" alt="image" src="https://github.com/user-attachments/assets/f4f332ce-79bf-4a8b-9477-bab6852eeb5b" />

cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 <img width="656" height="90" alt="image" src="https://github.com/user-attachments/assets/e4b773cf-d606-4e1f-ac2b-e13a3be807c5" />

 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
<img width="656" height="90" alt="image" src="https://github.com/user-attachments/assets/0752b901-99a0-4ca8-a91f-f33b8788d714" />

$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 <img width="656" height="330" alt="image" src="https://github.com/user-attachments/assets/27146c15-01da-490d-8779-3105ea7756a8" />

 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 <img width="654" height="315" alt="image" src="https://github.com/user-attachments/assets/9328944b-1898-47ea-84ce-7e3d14ac78b9" />

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 

<img width="655" height="93" alt="image" src="https://github.com/user-attachments/assets/18036e2b-566e-4971-8785-d604fa276b4e" />

# RESULT:
The Commands are executed successfully.
