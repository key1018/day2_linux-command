# 리눅스 명령어

## ls
➡️ "list"의 약자로, 현재 디렉토리(폴더) 파일 목록을 출력하는 명령어이다. 
## ls -al
➡️ 현재 머물고 있는 디렉토리에 있는 파일들의 목록을 보여준다. 중요한 것은 ls가 아닌 문자를 입력해서 명령을 한다는 것이다. <br>
즉, 디렉터리 내부의 파일 소유자 파일 크기 생성(수정)날짜 등 모든 정보 표시
## ls -l
➡️ 현재 머물고 있는 디렉토리에 있는 파일과 디렉토리를 자세히 보여주는 명령어이다.
즉, 퍼미션(권한), 포함된 파일수, 소유자, 그룹, 파일크기, 수정일자, 파일이름 정보 표시

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
eunyoung@BOOK-6MKSS57FS2:~$ mkdir hello_linux // mkdir뒤에는 내가 만들고 싶은 디렉토리의 이름을 적는다.
eunyoung@BOOK-6MKSS57FS2:~$ pwd
/home/eunyoung
eunyoung@BOOK-6MKSS57FS2:~$ ls
hello_linux // 현재 내가 만든 디렉토리
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


