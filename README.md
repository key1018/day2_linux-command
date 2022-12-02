<details>
<summary><h2>리눅스 기본 명령어</h2></summary>
<div markdown="1">

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
## chmod
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

</div>
</details>


<details>
<summary><h2>리눅스 Shell Script</h2></summary>
<div markdown="1">

- Linex Shell이란?
  - 사용자 명령어 해석기
  - 사용자가 프롬프트에 입력한 명령을 해석해서 운영체제에 전달
```
## 사용가능한 shell 리스트 확인하기
eunyoung@BOOK-6MKSS57FS2:~$ cat /etc/shells
# /etc/shells: valid login shells
/bin/sh
/bin/bash
/usr/bin/bash
/bin/rbash
/usr/bin/rbash
/bin/dash
/usr/bin/dash
/usr/bin/tmux
/usr/bin/screen

## 현재 작업 shell 확인
eunyoung@BOOK-6MKSS57FS2:~$ echo $SHELL
/bin/bash
```

# Bash Shell과 변수
- Shell의 변수란?
   - 데이터를 넣는 그릇
   - 선언한 필요없이 사용 가능
   - 변수명 : 문자, 숫자, _(언더바)로 구성될 수 있지만, 시작은 반드시 문자나 _로 시작
```
# 쉘 선언
eunyoung@BOOK-6MKSS57FS2:~$ #!/bin/bash

# 변수 생성
1. 일반변수
사용 구문 : 변수명=변수값
eunyoung@BOOK-6MKSS57FS2:~$ fname=eunyoung
eunyoung@BOOK-6MKSS57FS2:~$ lnamee = kim
lnamee: command not found
→ 변수를 생성할 때 빈칸은 존재하면 안된다.

2. 환경변수
사용 구문 : export 변수명=변수값
→ 환경변수는 전달되는 명령어에 영향을 주는 변수로 일반변수와 내부적으로 다른 구조이다.
eunyoung@BOOK-6MKSS57FS2:~$ export NAME=key

# 변수 확인
사용 구문 : echo $변수명
eunyoung@BOOK-6MKSS57FS2:~$ echo $fname
eunyoung

eunyoung@BOOK-6MKSS57FS2:~$ echo "my name is ${fname}" // {}가 있으나 없으나 $만으로 변수의 값을 넣어줄 수 있으나, 문자열을 붙여서 쓸려면 ${} 를 사용해야 한다.
my name is eunyoung

# 변수 제거
사용 구문 : unset 변수명
eunyoung@BOOK-6MKSS57FS2:~$ unset fname
```
## 매개 변수
➡️ 프로그램에서도 실행할때 인자를 주듯 쉘 스크립트도 역시 그렇게 할 수 있다. <br>
실행한 스크립트 이름은 "${0}" 그 이후는 전달받은 인자 값들이다 (${1}, ${2}, ...)
```
$0	실행된 셸 스크립트명
$1	스크립트에 넘겨진 첫 번째 아규먼트 
$2	스크립트에 넘겨진 두 번째 아규먼트
$3 S4 등등...쭈욱 이후 $숫자	그 이후 해당되는 아규먼트 
$#	아규먼트 개수 
$*	스크립트에 전달된 인자 전체를 하나의 변수에 저장하면 IFS 변수의 첫 번째 문자로 구분
$@	$*와 동일한데 다른 점은 IFS 환경 변수를 사용하지 않는다는 점. 
$!	실행을 위해 백그라운드로 보내진 마지막 프로그램 프로세스 번호 
$$	셸 스크립트의 PID
$?	실행한 뒤의 반환 값 (백그라운드로 실행된 것 제외)

사용 구문
1. echo "script name : ${0}"
2. echo "매개변수 갯수 : ${#}"
3. echo "전체 매개변수 값 : ${*}"
4. echo "전체 매개변수 값2 : ${@}"
5. echo "매개변수 1 : ${1}"
6. echo "매개변수 2 : ${2}"
```

## 예약 변수
➡️ 쉘 스크립트에서 사용자가 정해서 만들 수 없는 이미 정의된 변수가 존재한다. <br>
이 변수명을 피해서 스크립트를 작성해야 한다.

| 변수 |	설명 |
| :-: | :-: |
| HOME |	사용자 홈 디렉토리 |
| PATH |	실행 파일의 경로 |
| LANG |	프로그램 실행 시 지원되는 언어 |
| UID	 | 사용자의 UID |
| SHELL |	사용자가 로그인시 실행되는 쉘 |
| USER |	사용자의 계정 이름 |
| FUNCNAME |	현재 실행되고 있는 함수 이름 |
| TERM |	로그인 터미널 |

```
이 외의 변수 명령어

set : 셸 변수를 출력하는 명령어
env : 환경 변수를 출력하는 명령어
export : 특정 변수의 범위를 환경 변수의 데이터 공간으로 전송하여 자식 프로세스에서도 특정 변수를 사용 가능하게 한다. 전역 변수의 개념
unset : 선언된 변수를 제거한다.
```
## 셀 산술 연산
➡️ Bash 변수는 본질적으로 문자열이라 별도의 특수한 문법을 사용해 연산을 해야 한다. <br>
```
# Bash에서 계산 처리하는 3가지 문법
1. expr
2. let
3. $(())

1. expr 연산자
- expr는 역따옴표를 반드시 감싸준다. 역따옴표 대신 $(( )) 해줘도 동작은 한다.
- expr을 사용할 때 피연산자와 연산자 사이에 공백이 필요하다.
- 산술 연산할때 우선순위를 지정하기위해 괄호를 사용하려면 \처리를 해줘야 한다.
- 곱셈 문자 *는 \처리를 해주어야 한다.

eunyoung@BOOK-6MKSS57FS2:~$ plus=`expr $number1 + $number2`
eunyoung@BOOK-6MKSS57FS2:~$ minus=`expr $number1 - $number2`
eunyoung@BOOK-6MKSS57FS2:~$ mul=`expr $number1 \* $number2`  
→ 곱셈에는 \* 를 이용한다.
→ 연산자 *와 괄호() 앞에는 역슬래시와 같이 사용
eunyoung@BOOK-6MKSS57FS2:~$ div=`expr $number1 / $number2`
eunyoung@BOOK-6MKSS57FS2:~$ rem=`expr $number1 % $number2`

2. let 연산자
eunyoung@BOOK-6MKSS57FS2:~$ let re=number1+number2
eunyoung@BOOK-6MKSS57FS2:~$ let re=number1-number2
eunyoung@BOOK-6MKSS57FS2:~$ let re=number1*number2
eunyoung@BOOK-6MKSS57FS2:~$ let re=number1/number2
eunyoung@BOOK-6MKSS57FS2:~$ let re=number1%number2

3. $(( )) 연산자
eunyoung@BOOK-6MKSS57FS2:~$ echo add:$((number1+number2))
add:30
eunyoung@BOOK-6MKSS57FS2:~$ echo sub:$((number1-number2))
sub:-10
eunyoung@BOOK-6MKSS57FS2:~$ echo mul:$((number1*number2))
mul:200
eunyoung@BOOK-6MKSS57FS2:~$ echo div:$((number1/number2))
div:0
eunyoung@BOOK-6MKSS57FS2:~$ echo mod:$((number1%number2))
mod:10
```

## 셀 조건문

### if문
➡️ if문의 특징은 fi 와 대괄호[ ] 이다. <br>
여타 언어와 달리 중괄호를 안쓰기 떄문에 fi로 if문의 끝을 알려주어야 하며, <br>
주의해야할 점은 if문 뒤에 나오는 대괄호 [ ] 와 조건식 사이에는 반드시 공백이 존재해야 한다. <br>

사용 구문 :  <br>
if [ 값1 조건식 값2 ]
then
    수행1
else
    수행2
fi
<br>

if [ 값1 조건식 값2 ]; then
    수행1
else
    수행2
fi <br>
→ then을 if [] 와 붙여쓰려면 반드시 세미콜론 ; 을 써야한다.

| 문자1 = 문자2 | 문자1 과 문자2가 일치 (sql같이 = 하나만 써도 일치로 인식) | 
| :-: | :-: |
| 문자1 == 문자2 | 문자1 과 문자2가 일치 | 
| 문자1 != 문자2 | 문자1 과 문자2가 일치하지 않음 | 
| -z 문자 | 문자가 null 이면 참 | 
| -n 문자 | 문자가 null 이 아니면 참 | 
| 문자 == 패턴 | 문자열이 패턴과 일치 | 
| 문자 != 패턴 | 문자열이 패턴과 일치하지 않음 | 
| 값1 -eq 값2 | 값이 같음(equal) | 
| 값1 -ne 값2 | 값이 같지 않음(not equal) | 
| 값1 -lt 값2 | 값1이 값2보다 작음(less than) | 
| 값1 -le 값2 | 값1이 값2보다 작거나 같음(less or equal) | 
| 값1 -gt 값2 | 값1이 값2보다 큼(greater than) | 
 값1 -ge 값2 | 값1이 값2보다 크거나 같음(greater or equal) | 

### 이중 괄호 ((expression))
→ expression 에는 수식이나 비교 표현식이 들어갈 수 있다.

| ! | 논리 부정 | 
| :-: | :-: |
| ~ | 비트 부정 | 
| ** | 지수화 | 
| << | 비트 왼쪽 쉬프트 | 
| >> | 비트 오른쪽 쉬프트 | 
| & | 비트 단위AND | 
| | | 비트 단위 OR | 
| && | 논리 AND | 
| || | 논리 OR | 
| num++ | 후위증가 | 
| num-- | 후위감소++ | 
| num | 전위증가 | 
| --num | 전위감소 | 
```
#!/bin/bash
function func(){

a=10
b=5

if [ ${a} -eq ${b} ]; then
        echo "a와 b는 같다."
fi

if [ ${a} -ne ${b} ]; then
        echo "a와 b는 같지않다."
fi

}

#함수 호출
func
```

### 파일 검사


| if [ -d ${변수} ]; then | ${변수}의 디렉토리가 존재하면 참 | 
| :-: | :-: |
| if [ ! -d ${변수} ]; then	| ${변수}의 디렉토리가 존재하지 않으면 참 | 
| if [ -e ${변수} ]; then | ${변수}라는 파일이 존재하면 참 |  
| if [ ! -e ${변수} ]; then | ${변수}라는 파일이 존재하지 않으면 참 | 
| if [ -r ${변수} ]; then | 파일을 읽을 수 있으면 참 | 
| if [ -w ${변수} ]; then | 파일을 쓸 수 있으면 참 | 
| if [ -x ${변수} ]; then | 파일을 실행할 수 있으면 참 | 
| if [ -s ${변수} ]; then | 파일의 크기가 0보다 크면 참 | 
| if [ -L ${변수} ]; then | 파일이 symbolic link이면 참 | 
| if [ -S ${변수} ]; then | 파일 타입이 소켓이면 참 | 
| if [ -f ${변수} ]; then | 파일이 정규 파일이면 참 | 
| if [ -c ${변수} ]; then | 파일이 문자 장치이면 참 | 
| if [ ${변수1} -nt ${변수2}]; then | 변수1의 파일이 변수2의 파일보다 최신 파일이면 참 | 
| if [ ${변수1} -ot ${변수2}]; then | 변수1의 파일이 변수2의 파일보다 최신이 아니면 참 | 
| if [ ${변수1} -ef ${변수2}]; then | 변수1의 파일과 변수2의 파일이 동일하면 참 | 
```
eunyoung@BOOK-6MKSS57FS2:~/script$ chmod +x backup // 파일이 실행가능하도록 '실행'기능 추가
#!/bin/bash
if ! [ -d bak ]; then #현재 디렉토리에 bak라는 디렉토리가 존재하지 않는다면
        mkdir bak #bak라는 디렉토리를 생성한다.
fi
cp *.log bak
```

### 논리 연산

| 조건1 -a 조건2 | AND | 
| :-: | :-: |
| 조건1 -o 조건2 | OR | 
| 조건1 && 조건2 | 양쪽 다 성립 |  
| 조건1 || 조건2 | 한쪽 또는 양쪽다 성립 | 
| !조건 | 조건이 성립하지 않음 | 
| true | 조건이 언제나 성립 | 
| false | 조건이 언제나 성립하지 않음 | 

```
#!/bin/bash

if [ -f ${myfile1} -a -f ${myfile2} ]; then  # myfile1과 myfile2는 모두 정규 파일이다.
        echo "myfile1과 myfile2는 모두 파일입니다."
else
        echo "myfile1과 myfile2는 모두 파일인 것은 아닙니다."
fi
-----------------------------------------------------------------------------------------------
value=10

if [ ${value} -gt 5 -a ${value} -lt 15 ]; then
        echo "value의 값은 5보다 크고 15보다 작다."
fi

# 위의 문장과 동일한 문장이다.
if [ ${value} -gt 5 ] && [ ${value} -lt 15 ]; then
        echo "value의 값은 5보다 크고 15보다 작다."
fi

# 대괄호 두개를 써서 표현할 수 있다.
if [[ ${value} -gt 5 && ${value} -lt 15 ]]; then
        echo "value의 값은 5보다 크고 15보다 작다."
fi
```
### if elif else 문

```
#!/bin/bash
 
num1="10"
num2="10"
 
if [ ${num1} -lt ${num2} ]; then # "-lt", A가 B보다 작으면 True
    echo "yes"
elif [ ${num1} -eq ${num2} ]; then # "-eq", A와 B가 서로 같으면 True
    echo "bbb"
else
    echo "no"
fi
```
### case 문
➡️ 각 case의 끝을 보면 세미콜론 2개로 종료한다. <br>
case 문자열 in
 경우1) 
    명령 명령 명령
    ;;
 경우2)
    명령 명령 명령
    ;;
 * )
    명령 명령 명령
    ;;
esac
```
#!/bin/bash

value="linux"

case ${value} in
        "linux") echo "리눅스" ;;
        "java") echo "자바" ;;
        "oracle") echo "오라클" ;;
        "windows") echo "윈도우" ;;
        *) echo "아무것도아님" ;;
esac

COUNTRY=korea
 
case $COUNTRY in
  "korea"|"japan"|"china") # or 연산도 가능하다
    echo "$COUNTRY is Asia"
    ;;
  "USA"|"Canada"|"Mexico")
    echo "$COUNTRY is Ameria"
    ;;
  * )
    echo "I don't know where is $COUNTRY"
    ;;
esac
```
## 쉘 반복문

### for문
```
#!/bin/bash

# 초기값; 조건값; 증가값을 사용한 전통적인 for문
for ((i=1; i<5; i++)); do
        echo $i
done
```
### for in문
```
# 변수를 사용한 반복문
value="1 2 3 4 5 6"
for x in ${value}
do
        echo ${x}
done

# 배열을 사용한 반복문
arr=(10 20 30 40 50)
for a in ${arr[@]}
do
        echo ${a}
done
```
### while문
```
#!/bin/bash

count=0
while [ ${count} -le 5 ]; # count가 5보다 작을때까지
do
        echo ${count}
        count=$(( ${count}+1 )) # count에 1씩 추가
done

val=0
while (( ${val} <= 5 )); # 이중괄호 (()) 사용하면 논리연산자 사용 가능
do
        echo ${val}
        val=$(( ${val}+1 ))
done
```

### until문
➡️ 수행 조건이 false 일때 실행되는 루프문이다. 즉, while의 반대버젼이라고 보면 된다. (while은 조건이 true 면 루프)
```
count=20

until [ ${count} -le 5 ]; do # count값이 5보다 작다.
        echo ${count}
        count=$(( ${count}-1 ))
done
```

## 쉘 배열문
### 배열 생성/추가
```
#!/bin/bash

# 배열의 크기 지정없이 배열 변수 선언
# 굳이 'declare -a' 명령으로 선언하지 않아도 바로 배열 변수 사용 가능함
declare -a array

arr=("test1" "test2" "test3") # 배열 선언 및 지정

echo ${arr[0]}  # test1


# 기존 배열에 1개의 배열 값 추가 3가지 방법
arr[3]="test4"
arr+=("test5")
arr[${#arr[@]}]="test6" # 배열 길이를 인덱스로 사용해 push
arr[${#arr[@]}]="test7"

echo ${arr[@]}  # arr의 모든 데이터 출력
echo ${arr[*]}  # arr의 모든 데이터 출력
echo ${#arr[@]} # arr 배열 길이 출력

echo ${arr[@]:2:3} # 인덱스 2부터 3개의 요소 출력
```
### 배열 원소 삭제
➡️ /를 사용해 해당 문자열 부분이 있으면 삭제 할 수 있다. 다만, unset을 이용해 삭제를 권고하는 편이다.
```
  GNU nano 4.8                                          if                                          Modified  #!/bin/bash

arr=(1 2 3)
remove=(3)

arr=( "${arr[@]/$remove}" )
echo ${arr[@]}

arr2=("abc" "bbb" "efg")
unset arr2[0] # arr2의 0번 인덱스 값 삭제
echo ${arr2[@]}
unset array # 배열 전체 삭제
```
### 연관 배열 MAP
➡️ key와 value 타입으로 저장된 배열을 말한다. 
```
#!/bin/bash

# 연관배열 생성
declare -A map=([key1]="hello" [key2]="linux" [what is it]=12345 [key3]="good")

declare -p map # 연관배열 정보 출력

echo "map[key1]=${map[key1]}"
# 값 : map[key1]=hello

key=key1
echo "map[key]=${map=[${key}]}"
# 값 : map[key]=[key1]

# 연관배열 value 값 모두 출력 (MAP은 순서를 보장하지않는다)
echo "배열전체=${map[@]}"
# 값 : 배열전체=12345 linux good hello [key1]

# 연관배열 key 인덱스 모두 출력 (MAP은 순서를 보장하지않는다)
echo "key,인덱스=${!map[@]}"
#값 : key,인덱스=what is it key2 key3 key1 0

# 연관배열 길이 출력
echo "길이:${#map[@]}"
#값 : 길이:5

# 배열 원소 추가
map+=([linux]=hi)
map+=([linux2]=a [linux2]=b)

echo ${map[@]}
# 값 : 12345 linux good hello [key1] hi b

# 배열 원소 삭제
unset 'map[key1]' # key로 삭제

echo ${map[@]}
# 값 : 12345 linux good [key1] hi b
# key1의 값인 hello가 사라진 것을 확인할 수 있다.
```
## 쉘 함수
➡️ 쉘 스크립트에서는 함수명 앞 function은 써주지 않아도 알아서 인식된다. <br>
또한, 함수를 호출할때는 괄호를 써주지 않고 호출해야한다는 점이 다르다. 그리고 함수 호출 코드는 함수 코드보다 반드시 뒤에 있어야 된다. <br>
함수 코드 보다 앞에서 호출 시 오류가 발생하기 때문이다.
```
#!/bin/bash

func(){
        echo "함수실행!"
}

# 함수실행
func
# 값 : 함수실행!

function string_test(){
        echo "string test"
        echo "인자값=${@}"
}

#함수에 인자값 전달하기(공백으로 뛰어서 2개의 인자값을 넘김)
string_test "hello" "linux"
# 값 : string_test
# 값 : 인자값=hello linux
```

## 명령어 종료 상태 코드
➡️ 종료 코드란, exit 명령으로 프로그램을 종료시키면서 사용자에게 ***프로그램 종료의 이유***를 알리기 위하여 반환하는 값이다. <br>
쉘 스크립트 내에서 exit 명령어가 실행되면 스크립트가 종료되며 부모 프로세스에 종료 상태를 전달할 수 있는데 이 값은 프로그램 내에서 임의로 지정할 수도 있다.  <br>
일반적으로 종료 코드가 0이면 명령이 성공적으로 완료되었음을 나타내고 0이 아니면 오류가 발생했음을 나타낸다. 

| 종료 코드 | 설명 | 
| :-: | :-: |
| 0 | 성공 |
| 1 | 일반적인 오류 | 
| 2 | 셸 내장 명령의 틀린 사용 |
| 126 | 파일이 실행되지 않음 |
| 127 | 명령어를 찾을 수 없음 |
| 128 | 종료할 때 잘못된 인수 적용 |
| 128+n | 치명적인 시그널 n 에러 |
| 130 | ctrl + n 키 조합에 의한 종료 |
```
exit 16 # 강제 종료
echo "hello linux" # 실행 안됨

date &> /dev/null
echo $?
# 값 : 0 반환
```

</div>
</details>
