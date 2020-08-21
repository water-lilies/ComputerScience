## Linux 기본 명령어

> 모든 명령어는 뒤에 --help 옵션을 주면 자세한 사용법이 나온다.

출처 : https://itholic.github.io/linux-basic-command/

### pwd 

>  print working directory

현재 작업중인 디렉토리 정보 출력

```shell
$ pwd
/home/itholic
```



### cd 

>  change directory

경로이동

```shell
$ cd /home/itholic/mydir
$ pwd
/home/itholic/mydir

# 상위 디렉토리로 이동
$ cd ..
# 홈 디렉토리로 이동
$ cd ~
# 이동하기 바로 전의 디렉토리로 이동
$ cd -
```



### ls 

> list segments

디렉토리 목록 확인

```shell
$ ls
testfile1  testfile2  testfile3

# 파일의 상세정보. 최근 업데이트 일자 포함
$ ls -l
total 0
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile1
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile2
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile3

# 숨어있는 파일도 표시
$ ls -a
./  ../  testfile1  testfile2  testfile3


$ ls -al
total 4
drwxr-xr-x 1 itholic 197121 0 11월  6 22:08 ./
drwxr-xr-x 1 itholic 197121 0 11월  6 22:08 ../
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile1
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile2
-rw-r--r-- 1 itholic 197121 0 11월  6 22:08 testfile3

# 파일을 생성된 시간별로(최신순) 표시
$ ls -rt
# 파일을 오래된 시간부터 표시
$ ls -rt
# 마지막에 유형을 나타내는 파일명을 끝에 표시
$ ls -F
```



### cp 

> copy

파일 혹은 디렉토리 복사

```shell
$ ls
testdir/  testfile


$ cp testfile1 testfile_cp
$ ls
testdir/  testfile  testfile_cp

# 디렉토리를 복사할 경우, -r 옵션을 주어야함
$ cp -r testdir testdir_cp
$ ls
testdir/  testdir_cp/  testfile  testfile_cp

# 복사할 때 복사대상이 있으면 지우고 강제로 복사
$ cp -f file cfile
```



### mv

> move

 파일 혹은 디렉토리 이동

이름을 변경하는 용도로도 쓰임

```shell
$ ls
testdir/  testfile


$ mv testfile testfile_mv
$ ls
testdir/  testfile_mv


$ mv testfile_mv testdir/
$ ls
testdir/


$ ls testdir/
testfile_mv
```



### mkdir

> make directory

```shell
$ ls
testfile


$ mkdir testdir
$ ls
testdir/  testfile

# mkdir -p 옵션으로 하위 디렉토리까지 한 번에 생성 가능
$ mkdir -p a/b/c/d/e/
# ls -R 옵션은 하위 디렉토리까지 전부 보여준다
$ ls -R a/     
a/:
b/

a/b:
c/

a/b/c:
d/

a/b/c/d:
e/

a/b/c/d/e:
```



### rm

> remove

```shell
$ ls
testdir/  testfile1  testfile2

# -f옵션을 주면 사용자에게 삭제 여부를 묻지 않고 바로 삭제
$ rm -f testfile1
$ ls
testdir/  testfile2

# 디렉토리 삭제를 할 경우 -r옵션
# 디렉토리 삭제시 하위 디렉토리까지 모두 삭제하므로 유의
$ rm -rf testdir/
$ ls
testfile2
```



###  touch

파일이나 디렉토리의 최근 업데이트 일자를 현재 시간으로 변경

파일이나 디렉토리가 존재하지 않으면 빈 파일을 만든다

```shell
$ touch testfile1
$ ls -l
total 0
-rw-r--r-- 1 itholic 197121 0 11월  6 22:43 testfile1


$ touch testfile2
$ ls -l
total 0
-rw-r--r-- 1 itholic 197121 0 11월  6 22:43 testfile1
-rw-r--r-- 1 itholic 197121 0 11월  6 22:44 testfile2
```



### cat

> concatenate

```shell
$ ls
file1  file2  file3

# 파일내용 출력
$ cat file1
1


$ cat file2
2


$ cat file3
3

# 파일 여러개를 합쳐서 하나의 파일로
$ cat file1 file2 > file1_2
$ ls
file1  file1_2  file2  file3


$ cat file1_2
1
2

# 파일 내용을 다른 파일에 덧붙이기
$ cat file1 >> file2
$ cat file2
2
1

# 새로운 파일 생성
$ cat > file4
hello
world
(작성이 끝나면 ctrl +d 로 파일 저장)


$ cat file4
hello
world
```



### head

파일의 앞부분을 보고싶은 줄 수 만큼 보여준다. 

옵션을 지정하지 않으면 상위 10줄 출력



### tail

파일의 뒷부분을 보고싶은 줄 수 만큼 보여준다.

옵션을 지정하지 않으면 하위 10줄 출력

```shell
$ tail -3 testfile
13
14
15

# -F옵션을 주면 파일 내용을 화면에 계속 띄워주고 파일이 변하게되면 업데이트된 내용을 갱신해줌
# 주로 실시간으로 내용이 추가되는 로그파일을 모니터링할 때 유용하게 사용
$ tail -F testfile
6
7
8
9
10
11
12
13
14
15
(명령어가 종료되지 않고 계속 해당 화면을 출력하며, 파일 내용 변경시 자동으로 갱신해준다)
```



### find

특정 파일이나 디렉토리 검색

find [검색경로] -name [파일명]

```shell
$ ls
dir1/  dir3/  file1  file3  picture1.jpg  picture3.jpg
dir2/  dir4/  file2  file4  picture2.jpg  picture4.jpg

# 풀네임으로 검색 가능
$ find ./ -name 'file1'
./file1

# 조건 지정하여 검색 가능
$ find ./ -name "*.jpg"
./picture1.jpg
./picture2.jpg
./picture3.jpg
./picture4.jpg

# -exec 옵션
# 조건 지정하여 바로 삭제 가능
$ find ./ -name "*.jpg" -exec rm {} \;
$ ls
dir1/  dir2/  dir3/  dir4/  file1  file2  file3  file4

# type 옵션
# 디렉토리나 파일만 지정해서 검색 가능
$ find ./ -type d
./
./dir1
./dir2
./dir3
./dir4


$ find ./ -type f
./file1
./file2
./file3
./file4

# wc -l 옵션
# find 조건에 맞는 결과 값이 몇개 존재하는지 숫자로 알려줌
$ find ./ -type f | wc -l
4

# sed 명령어
# 특정 조건에 해당하는 파일들의 내용을 전부 찾아서 바꿔줌
find ./ -name "*.txt" -exec sed -i 's/hi/hello/g' {} \;
```



