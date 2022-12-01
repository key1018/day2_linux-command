# 리눅스 명령어

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
 
1. -i : 복사될 파일이 이름이 이미 존재할 경우, 사용자에게 덮어 쓰기 여부를 묻습니다.
2. -b : 복사될 파일이 이름이 이미 존재할 경우, 백업파일을 생성합니다.
3. -f : 복사 될 파일이 이름이 이미 존재 할 경우, 강제로 덮어쓰기 합니다.
4. -r : 하위 디렉토리 까지 모두 복사합니다.
5. -a : 원본 파일의 속성, 링크 정보까지 모두 복사합니다.
6. -p : 원본 파일의 소유자, 그룹, 권한 등의 정보까지 모두 복사합니다.
7. -v : 복사 진행 상태를 출력합니다.

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
