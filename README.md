# 리눅스  명령어

## --help
➡️ 명령어 뒤에 --help를 붙이면 명령어의 사용설명서가 출력된다.
## ls
➡️ "list"의 약자로, 현재 디렉토리(폴더) 파일 목록을 출력하는 명령어이다. 
## la -a / --all
➡️ 감춰진 파일을 조회하는 명령어이다.
## ls -al
➡️ 현재 머물고 있는 디렉토리에 있는 파일들(감춰진 파일 함)의 목록을 보여준다. 중요한 것은 ls가 아닌 문자를 입력해서 명령을 한다는 것이다. <br>
즉, 디렉터리 내부의 파일 소유자 파일 크기 생성(수정)날짜 등 모든 정보 표시
## ls -l
➡️ 현재 머물고 있는 디렉토리에 있는 파일과 디렉토리를 자세히 보여주는 명령어이다.
즉, 퍼미션(권한), 포함된 파일수, 소유자, 그룹, 파일크기, 수정일자, 파일이름 정보 표시
## ls -h -al
➡️ -h를 붙이면 K, M, G 단위의 파일 크기를 사용하여 표시된다.
## ls -S
➡️ 파일 사이즈를 기준으로 파일목록을 정렬해서 보여주는 명령어이다.

*우리가 linux에서 명령을 실행할 때 명령어 뒤애 '-'를 삽입한 뒤 추가 옵션을 삽입하는 것을 parameter라고 부른다.*
```
eunyoung@BOOK-6MKSS57FS2:~$ ls

eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 24
drwxr-xr-x 3 eunyoung eunyoung 4096 Nov 29 01:54 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile

eunyoung@BOOK-6MKSS57FS2:~$ ls -h -al
total 24K
drwxr-xr-x 3 eunyoung eunyoung 4.0K Dec  1 14:52 .
drwxr-xr-x 3 root     root     4.0K Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3.7K Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4.0K Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile

eunyoung@BOOK-6MKSS57FS2:~$ ls -alS
total 24
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:22 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
```
## pwd
➡️ "print working directory"의 약자로, 현재 위치하고 있는 디렉토리를 알려주는 명령어이다.
```
eunyoung@BOOK-6MKSS57FS2:~$ pwd
/home/eunyoung

-> 컴퓨터의 최상위 디렉토리 밑에있는 home안의 eunyoung이라는 디렉토리에 현재 머물고있다 라는 의미이다.
```
## mkdir
➡️ "make directory"의 약자로 새로운 디렉토리를 만들 수 있는 명령어이다.
```
사용 구문 : mkdir 새로운 디렉토리명 / mkdir -p 새로운 디렉토리명 +"/" + 새로운 하위 디렉토리명

eunyoung@BOOK-6MKSS57FS2:~$ mkdir hello_linux // mkdir뒤에는 내가 만들고 싶은 디렉토리의 이름을 적는다.
eunyoung@BOOK-6MKSS57FS2:~$ pwd
/home/eunyoung
eunyoung@BOOK-6MKSS57FS2:~$ ls
hello_linux // 현재 내가 만든 디렉토리

eunyoung@BOOK-6MKSS57FS2:~$ mkdir -p dir1/dir2/dir3/dir4
eunyoung@BOOK-6MKSS57FS2:~$ cd dir1/dir2/dir3/dir4
eunyoung@BOOK-6MKSS57FS2:~/dir1/dir2/dir3/dir4$ pwd
/home/eunyoung/dir1/dir2/dir3/dir4    // 현재 내가 만든 디렉토리
```
## touch
➡️ 빈 파일을 생성하는 명령어이다. <br>
```
사용 구문 : touch [옵션] [파일명]

eunyoung@BOOK-6MKSS57FS2:~$ touch empty_file.txt
eunyoung@BOOK-6MKSS57FS2:~$ ls
empty_file.txt  hello_linux

eunyoung@BOOK-6MKSS57FS2:~$ ls -l
total 4
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 14:06 empty_file.txt // 권한 앞에 'd'가 없는 경우, 파일이라는 의미이다.
drwxr-xr-x 2 eunyoung eunyoung 4096 Dec  1 13:54 hello_linux // 권한 앞에 'd'가 붙어있는 경우, directory(폴더)이라는 의미이다.
```
<details>
<summary>리눅스의 타임스탬프</summary>
<div markdown="1">

 1. atime : 최종 접근 시간(access time) <br>
 2. ctime : 최종 상태 변경 시간(change time) <br>
 3. mtime : 최종 수정 시간(modify time)

</div>
</details>

## cd
➡️ "change directory"의 약자로 특정 디렉토리로 이동하고 싶을 때 사용한다.
```
eunyoung@BOOK-6MKSS57FS2:~$ cd hello_linux/
eunyoung@BOOK-6MKSS57FS2:~/hello_linux$ pwd
/home/eunyoung/hello_linux

만약! hello_linux의 부모폴더인 /home/eunyoung/로 되돌아가고 싶다면

방법1. 최상위 디렉터리부터 가고자하는 폴더로 이동하는 방법
-> 즉, 최상위 디렉토리를 기준으로 경로를 표현하는 것으로 '절대경로'라고 부른다.
eunyoung@BOOK-6MKSS57FS2:~/hello_linux$ cd /home/eunyoung
eunyoung@BOOK-6MKSS57FS2:~$ pwd
/home/eunyoung

방법2. 현재 머물고있는 디렉토리의 부모 디렉토리를 의미하는 '..'을 사용하여 이동하는 방법
-> 즉, 현재 디렉토리를 기준으로 부모 디렉토리가 변경되므로 '상대경로'라고 부른다.
eunyoung@BOOK-6MKSS57FS2:~/hello_linux$ cd ..
eunyoung@BOOK-6MKSS57FS2:~$ pwd
/home/eunyoung
```

## rm
➡️ "remove"의 약자로 파일을 삭제하는 명령어이다.
## rm -r
➡️ 디렉토리를 삭제하는 명령어이다.
-r, -R, --recursive   remove directories and their contents recursively
``` 
사용 구문 : rm 파일명 / *(전체 파일 삭제)
rm -r 폴더명

eunyoung@BOOK-6MKSS57FS2:~$ rm hello_linux/
rm: cannot remove 'hello_linux/': Is a directory 
eunyoung@BOOK-6MKSS57FS2:~$ rm empty_file.txt
eunyoung@BOOK-6MKSS57FS2:~$ ls
hello_linux
eunyoung@BOOK-6MKSS57FS2:~$ rm -r hello_linux/
```

## cp
➡️ "copy"의 약자로 파일이나 디렉토리를 원하는 곳에 원하는 이름으로 복사할 수 있는 명령어이다.
```
사용구문 : cp [옵션] [복사 할 디렉토리/파일] [복사 될 디렉토리/파일] / cp -r [복사할 디렉토리명] [복사될 디렉토리명]

eunyoung@BOOK-6MKSS57FS2:~$ cp cp.txt dir1/cp.txt
eunyoung@BOOK-6MKSS57FS2:~$ cd dir1
eunyoung@BOOK-6MKSS57FS2:~/dir1$ ls -al
total 12
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:34 .
drwxr-xr-x 4 eunyoung eunyoung 4096 Dec  1 15:34 ..
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:34 cp.txt
drwxr-xr-x 2 eunyoung eunyoung 4096 Dec  1 15:34 dir2

현재 위치에 있는 dir1 디렉토리를 dir4 디렉토리라는 이름으로 복사
eunyoung@BOOK-6MKSS57FS2:~$ cp -r dir1 dir4
eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 36
drwxr-xr-x 6 eunyoung eunyoung 4096 Dec  1 15:43 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:33 cp.txt
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:35 dir1
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:40 dir3
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:43 dir4
```
<details>
<summary>옵션</summary>
<div markdown="1">
 
1. -i : 복사될 파일이 이름이 이미 존재할 경우, 사용자에게 덮어 쓰기 여부 
2. -b : 복사될 파일이 이름이 이미 존재할 경우, 백업파일을 생성
3. -f : 복사 될 파일이 이름이 이미 존재 할 경우, 강제로 덮어쓰기
4. -r : 하위 디렉토리 까지 모두 복사
5. -a : 원본 파일의 속성, 링크 정보까지 모두 복사
6. -p : 원본 파일의 소유자, 그룹, 권한 등의 정보까지 모두 복사
7. -v : 복사 진행 상태를 출력

</div>
</details>

## mv 
➡️ "move"의 약자로 파일이나 디렉토리를 원하는 곳으로 옮기거나, 이름을 변경할 때 사용할 수 있는 명령어이다.
```
1. 이동
사용 구문 : mv [이동할 파일/디렉토리] [이동될 파일/디렉토리]
eunyoung@BOOK-6MKSS57FS2:~$ touch mv.txt
eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 28
drwxr-xr-x 4 eunyoung eunyoung 4096 Dec  1 15:47 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:33 cp.txt
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:47 dir1
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:47 mv.txt   // mv.txt라는 파일이 존재
eunyoung@BOOK-6MKSS57FS2:~$ mv mv.txt dir1/mv.txt  // 파일 이동
eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 28
drwxr-xr-x 4 eunyoung eunyoung 4096 Dec  1 15:48 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:33 cp.txt
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:48 dir1    // mv.txt라는 파일이 존재X
eunyoung@BOOK-6MKSS57FS2:~$ ls -al dir1
total 12
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:48 .
drwxr-xr-x 4 eunyoung eunyoung 4096 Dec  1 15:48 ..
drwxr-xr-x 2 eunyoung eunyoung 4096 Dec  1 15:34 dir2
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:47 mv.txt // 파일이 dir1으로 이동된 것을 확인

2. 이름 변경
사용구문 : mv [변경할 파일/디렉토리] [변경될이름이 담긴 파일/디렉토리]
eunyoung@BOOK-6MKSS57FS2:~$ touch rename.txt
eunyoung@BOOK-6MKSS57FS2:~$ mv rename.txt rename2.txt
eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 28
drwxr-xr-x 4 eunyoung eunyoung 4096 Dec  1 15:52 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 13:37 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:33 cp.txt
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:48 dir1
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:48 rename2.txt  // 변경된 이름 확인
```
## nano
➡️ 파일을 만들고 편집하거나 파일에 정보를 저장하는 명령어이다.
![image](https://user-images.githubusercontent.com/103404357/205115241-a483d770-98f5-44a5-91ff-7568bd910b3f.png)
```
eunyoung@BOOK-6MKSS57FS2:~$ nano
eunyoung@BOOK-6MKSS57FS2:~$ ls -al
total 40
drwxr-xr-x 5 eunyoung eunyoung 4096 Dec  2 02:06 .
drwxr-xr-x 3 root     root     4096 Nov 29 01:54 ..
-rw------- 1 eunyoung eunyoung 1189 Dec  1 15:55 .bash_history
-rw-r--r-- 1 eunyoung eunyoung  220 Nov 29 01:54 .bash_logout
-rw-r--r-- 1 eunyoung eunyoung 3771 Nov 29 01:54 .bashrc
drwxr-xr-x 2 eunyoung eunyoung 4096 Nov 29 01:54 .landscape
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  2 02:02 .local
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  2 01:49 .motd_shown
-rw-r--r-- 1 eunyoung eunyoung  807 Nov 29 01:54 .profile
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:33 cp.txt
drwxr-xr-x 3 eunyoung eunyoung 4096 Dec  1 15:48 dir1
-rw-r--r-- 1 eunyoung eunyoung   16 Dec  2 02:06 hello.html  // 파일이 생성된 것을 볼 수 있다.
-rw-r--r-- 1 eunyoung eunyoung    0 Dec  1 15:48 rename2.txt
```
파일을 수정하고자 할 때
```
사용구문 : nano [편집하고자하는 파일명]

eunyoung@BOOK-6MKSS57FS2:~$ nano hello.html
```
![image](https://user-images.githubusercontent.com/103404357/205117260-902df936-6df9-4db9-ae95-77a0900067bb.png)

## cat
➡️ "concatenate"의 약자로 두 개 이상의 파일을 연결해서 출력하거나 파일의 내용을 볼 때 사용하는 명령어이다.
```
1. 한 개의 파일을 출력

eunyoung@BOOK-6MKSS57FS2:~$ cat hello.html
<html>
        <body>
                hello
                nano nano nano nano
        </body>
</html>

2. 여러개의 파일을 출력
eunyoung@BOOK-6MKSS57FS2:~$ cat hello.html rename2.txt
<html>
        <body>
                hello
                nano nano nano nano
        </body>
</html>
wow good~~

3. > 을 활용하여 파일내용을 복사/생성/합치기

# rename2의 내용을 new_file라는 이름으로 생성
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt > new_file
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt new_file
wow good~~
wow good~~

# rename2 + cp 내용을 new_file라는 이름으로 생성
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt cp.txt > new_file
eunyoung@BOOK-6MKSS57FS2:~$ cat new_file
wow good~~
hello nano and linux!!!!!

4. >>을 활용하여 기존 파일의 내용을 지우지 않고 대상 파일의 내용을 아래에 추가하기
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt >> cp.txt
eunyoung@BOOK-6MKSS57FS2:~$ cat cp.txt
hello nano and linux!!!!!
wow good~~

# rename2 파일에 새로운 내용 입력 후 저장
eunyoung@BOOK-6MKSS57FS2:~$ cat > rename2.txt
show me the money
^C
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt
show me the money

# rename2 파일에 새로운 내용 추가 후 저장
eunyoung@BOOK-6MKSS57FS2:~$ cat >> rename2.txt
ok bye
^C
eunyoung@BOOK-6MKSS57FS2:~$ cat rename2.txt
show me the money
ok bye
```
## less
➡️ 파일 내용을 확인하는 명령어들 중 하나로 해당 창에서 위아래로 움직이며 파일 내용을 확인할 때 용이하다. 하지만, 파일 수정은 불가능하다.
```
사용 구문 : less [파일명]
eunyoung@BOOK-6MKSS57FS2:~$ less rename2.txt
```
<details>
<summary>옵션</summary>
<div markdown="1">
 
1. q: 종료 후 쉘창으로 복귀
2. enter: 1행 아래로 이동
3. space bar 또는 f: 아래로 1페이지 이동
4. 숫자+n : 원하는 페이지만큼 뒤로 이동
5. PageUp: 위로 1페이지 이동
6. PageDown: 아래로 1페이지 이동

</div>
</details>

## tail
➡️ 파일의 뒷 부분을 출력하는 명령어이다.
```
# 사용 구문 : tail [파일명]
기본적으로 마지막 행을 기준으로 10개의 행이 출력된다.
eunyoung@BOOK-6MKSS57FS2:~$ tail  rename2.txt

# 사용 구문 : tail -n [라인번호] [파일명]
마지막 행부터 지정한 라인번호까지 출력한다.
eunyoung@BOOK-6MKSS57FS2:~$ tail -n 3 rename2.txt

# 사용 구문 : tail +[라인번호] [파일명]
지정한 라인번호부터 마지막 행까지 출력된다.
eunyoung@BOOK-6MKSS57FS2:~$ tail +4 rename2.txt

# 사용 구문 : tail -f [파일명]
파일에 데이터가 추가될 때까지 대기하면서 추가되면 계속 출력한다. ctrl + c로 종료한다.
eunyoung@BOOK-6MKSS57FS2:~$ tail -f rename2.txt
```
## chown
➡️ 파일 또는 디렉토리의 소유권자 및 그룹식별자룰 정하는 명령어이다.

```
# 사용구문 : chown [소유자]:[그룹식별자] [파일명]
eunyoung@BOOK-6MKSS57FS2:~$ chown key:eunyoung hello.html

# 사용구문 : chown [소유자] [파일명]
eunyoung@BOOK-6MKSS57FS2:~$ chown key hello.html

# 사용구문 : chown :[그룹식별자] [파일명]
eunyoung@BOOK-6MKSS57FS2:~$ chown :kim hello.html
```
# chmod
➡️ "change mod"의 약자로, 파일의 권한을 변경하 수 있는 명령어이다.
```
사용 구문 : chmod [옵션] [모드] [파일명]

"r" : 읽기 권한 (r == 4)
"w" : 쓰기 권한 (w == 2)
"x" : 실행 권한 (x == 1)
"-" : 권한 없음

첫 3자리 : 소유자
중간 3자리 : 그룹
마지막 3자리 : 모든 사용자

# hello.txt 파일의 권한 : 사용자(권한없음), 그룹(권한없음), 그외 사용자(권한없음)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 000 hello.html
---------- 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html

# hello.txt 파일의 권한 : 사용자(읽기), 그룹(읽기), 그외 사용자(읽기)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 444 hello.html
-r--r--r-- 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html

# hello.txt 파일의 권한 : 사용자(읽기+실행), 그룹(읽기+실행), 그외 사용자(읽기+실행)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 555 hello.html
-r-xr-xr-x 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html

# hello.txt 파일의 권한 : 사용자(읽기+쓰기), 그룹(읽기+쓰기), 그외 사용자(읽기+쓰기)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 666 hello.html
-rw-rw-rw- 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html

# hello.txt 파일의 권한 : 사용자(읽기+쓰기+실행), 그룹(읽기+쓰기+실행), 그외 사용자(읽기+쓰기+실행)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 777 hello.html
-rwxrwxrwx 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html

# hello.txt 파일의 권한 : 사용자(읽기+쓰기+실행), 그룹(읽기+쓰기), 그외 사용자(읽기)
eunyoung@BOOK-6MKSS57FS2:~$ chmod 764 hello.html
-rwxrw-r-- 1 eunyoung eunyoung   69 Dec  2 02:15 hello.html
```
## grep
➡️ 파앨 내에서 특정 문자열을 찾아 해당 문자열을 출력하는 명령어이다.
```
사용 구문 : grep [옵션] [패턴] [파일]

# rename2.txt의 내용에서 "the"라는 문자열을 검색하고, 문자열이 존재하는 라인을 출력
eunyoung@BOOK-6MKSS57FS2:~$ grep "the" rename2.txt
show me the money
the name
the Mona Lisa

# 현재 디렉토리에 있는 모든 파일에서 "the"라는 문자열을 검색해서 출력
eunyoung@BOOK-6MKSS57FS2:~$ grep "the" *
grep: dir1: Is a directory
new_file:what is the the driver of the car
rename2.txt:show me the money
rename2.txt:the name
rename2.txt:the Mona Lisa

# 대소문자 구분없이 문자열 검색해서 출력
eunyoung@BOOK-6MKSS57FS2:~$ grep -i "the" rename2.txt
show me the money
the name
the Mona Lisa
The end? The end?

# "the" 문자열이 포함된 라인 번호 출력
eunyoung@BOOK-6MKSS57FS2:~$ grep -n "the" rename2.txt
1:show me the money
10:the name
12:the Mona Lisa

# "the" 문자열이 초함된 결과를 지정 숫자까지만 출력
사용 구문 : grep -m [지정숫자] [파일명]
eunyoung@BOOK-6MKSS57FS2:~$ grep -m 2 "the" rename2.txt
show me the money
the name

# 현재 디렉토리에서 "the" 문자열이 포함되지 않은 라인 출력
eunyoung@BOOK-6MKSS57FS2:~$ grep -n -v "the" rename2.txt
2:ok bye
3:1
4:2
5:3
6:4
7:5
8:6
9:7
11:new file
13:The end? The end?
14:ok let's go!
```
## history
➡️ 현재까지 쳤던 모든 명령어 리스트를 행 넘버와 함께 출력하는 명령어이다.
```
eunyoung@BOOK-6MKSS57FS2:~$ history
    1  ls
    2  ls -al
    3  pwd
    4  mkdir hello_linux
    5  pwd
    6  ls
    7  touch empty_file.txt
    8  ls
    9  pwd
    ...
    
# history 리스트 지우기
eunyoung@BOOK-6MKSS57FS2:~$ history -c
```
## ps
➡️ "process status"의 약자로 현재 실행중인 프로세스 목록을 확인하는 명령어이다.
```
사용 구문 : ps [옵션]

-a : 전체 사용자의 프로세스 출력
-u : 각 프로세스 사용자 및 사용시간 출력
-x : 제어 터미널이 없는 프로세스 출력
-l : 자세한 형태의 정보 출력
-e : 모든 프로세스 상태 출력
 
eunyoung@BOOK-6MKSS57FS2:~$ ps
  PID TTY          TIME CMD
  102 pts/0    00:00:01 bash
  448 pts/0    00:00:00 ps
eunyoung@BOOK-6MKSS57FS2:~$ ps -e
  PID TTY          TIME CMD
    1 ?        00:00:00 init
  100 ?        00:00:00 init
  101 ?        00:00:01 init
  102 pts/0    00:00:01 bash
  449 pts/0    00:00:00 ps
  
# 모든 프로세스를 풀 포맷으로 출력, more 명령어를 이용하여 페이지 단위로 출력
eunyoung@BOOK-6MKSS57FS2:~$ ps -ef | more
UID        PID  PPID  C STIME TTY          TIME CMD
root         1     0  0 01:49 ?        00:00:00 /init
root       100     1  0 02:24 ?        00:00:00 /init
root       101   100  0 02:24 ?        00:00:01 /init
eunyoung   102   101  0 02:24 pts/0    00:00:01 -bash
eunyoung   454   102  0 03:58 pts/0    00:00:00 ps -ef
eunyoung   455   102  0 03:58 pts/0    00:00:00 more
# 
```
## man
➡️ "manual"의 약자로, 명령어의 설명서를 출력하는 명령어이다.
```
사용 구문 : man [명령어]

-q : 설명서 종료
-h : 도움말 출력
-↑키/↓키 : 한 줄 위/아래로 이동
-Page Up 키/Page Down 키 : 한 페이지 위/아래로 이동
-/ : 단어 검색
-n : 검색한 단어의 다음 언어로 이동

eunyoung@BOOK-6MKSS57FS2:~$ man grep
```
## nohup
➡️ "no hang up"의 약자로 프로세스를 실행한 터미널의 세션 연결이 끊기더라도 지금 실행시킨 프로그램을 종료시키지 않도록 하는 명령어이다.
```
* nohub으로 실행시킬 파일은 반드시 755 권한을 가지고 있어야 한다.
# nohup 포어그라운드 실행
# nohup을 포어그라운드에서 사용하면 명령이 종료될 때까지 셸과 상호 작용을 할 수 없으므로 유용하지 않다.
사용 구문 : nohup [명령어]

# nohup 백그라운드 실행
# 기본적으로 어떤 프로그램을 종료없이 백그라운드에서 실행시키기 위해 사용하기 때문에 nohup + & 조합으로 많이 사용된다.
사용 구문 : nohup [명령어] &

# nohup 종료
사용 구문 : ps -ef | grep [파일명] # nohup으로 실행한 데몬 PID 확인
사용 구문 : kill -9 [PID번호]
```

