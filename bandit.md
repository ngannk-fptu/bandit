# Ngô Kim Ngân

Đây sẽ là toàn bộ writeup về challenge OverTheWire

# level 0 

<img width="948" height="313" alt="image" src="https://github.com/user-attachments/assets/baa58ed7-8c17-48da-a4da-926a53cc2978" />


- kết nối ssh:
```python
 ssh bandit0@bandit.labs.overthewire.org -p 2220
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/19123f2f-cdaa-45f1-aea1-247cc77c5761)

- với level 0 chúng ta sẽ sử dụng lệnh ls (để list các tệp tin) sau đó sẽ xuất hiện 1 file tên là Readme 
và mở lên sử dụng lệnh cat (để xem thông tin trong file )

```python
ls
cat readme
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/ae1eda8f-dbc1-43d4-95b7-3ed7ff5ac6e3)

*Flag0: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL*

# level 1 

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/aba7ae29-2089-4dbe-ac41-923acb23605f)


-tương tự kêt nối ssh đến user:bandit1 và password: flag0, đầu tiên ta cần sử dụng lệnh ls -l 
```python
ls -l 
```
liệt kê kiểu file thuộc dir or f rồi sử dụng cat để check thông tin bên trong 
```python
cat ./- 
```
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/2e23e838-59e8-43b2-8700-db0400932f17)


*Flag1:rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi*

# level 2
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/4b7b35d5-2a26-4a92-ab34-e3c5e49dbb89)

- với level 2 ta kết nối ssh và sử dụng ls -l và check được file spaces in this filename tượng tự với level trên thì ta sử dụng

```python
ls -l 
```
- liệt kê và check file

```python
cat + ( nhấn nút tab ) 
```
- để xem thông tin bên trong thư mục , tab sử dụng để tự động hoàn thành 1 câu hoàn chỉnh

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/86205dca-9bd4-4571-8a49-fd31d12cd268)
*Flag2:aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG*

# level 3: 
<img width="411" alt="image-8" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/302633f7-cd7a-4305-acad-53f5e1edecea">

-  sử dụng lệnh ls  để xem nội dung của thư mục hiện tại và xác định được thư mục inhere/
-  sử dụng lệnh ls -la inhere/ để xem toàn bộ file thư mục bên trong bao gồm .hidden file

```python
ls -la inhere
```
- sử dụng cat để xem nội dung bên trong
  
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/b5f5d280-a499-493b-8c91-1f30315641ce)

*flag3:2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe*
  
# level 4:

<img width="796" alt="image-10" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/a96f3b0e-5191-44f1-9bc7-e53a416008e5">

- để tìm tệp có định dạng xác định có thể đọc được cho con người ta sử dụng lệnh file để check nội dung định dạng của các tệp
- sau khi tìm được định dạng file ta sử dụng cat để check thông tin

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/1692d97a-2483-4f3c-a86c-a6233925875e)
- vậy là ta tìm được 1 tệp ascii text  
*flag4:lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR*

# level 5:

<img width="647" alt="image-13" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/7b534f07-3f74-45a4-821d-a60599372b40">

- trong thư mục inhere có chứa nhiều thư mục chứa file password để tìm file thì dựa trên hint là size và kiểu  type f 
- ta có lệnh find để tìm file cần biết (type f file ) và ( -size 1033c) combine lại ta có 

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/20715d3c-3f9e-4315-b6e4-ef78817ba5fb)

*flag5:P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU*

# level 6:

<img width="539" alt="image-15" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/cc209a28-615b-4d52-86d7-860c99c18d6c">

- với dạng này ta sẽ tìm file dựa vào  gợi ý 33 byte, user bandit7 , group bandit6


```python
find / -type f -user bandit7 -group  bandit6 2>/dev/null 
```
Command Explanation
-  /: tim kiếm toàn bộ server ( / là thư mục root)
-  -type : kiểu đây f ( file)
- user : owned là user bandit7
- group : thuộc group  bandit6
- 2>/dev/null: là bộ lọc loại bỏ những thông báo error

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/8e820065-a655-4ee1-94c6-bcbb6033cc0a)

*flag6:z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S*


# level 7
<img width="443" alt="image-17" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/685ef4a1-06b0-41de-9c34-e7259ce78a63">

- check list file ta thấy file data.txt có từ khóa là millionth sau đó ta sẽ dùng câu lệnh 

```python
 cat data.txt | grep millionth 
```
Command Explanation
- grep: bộ lọc trỏ đến vị trí cụ thể 
- | : hoặc câu lệnh kép

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/43e18c02-f4bf-42d8-98be-1f7d5a8fdb82)

*flag7:TESKZC0XvTetK0S9xNwm25STk5iWrBvP*


# level 8
<img width="556" alt="image-19" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/eff1f089-5b75-4ca3-be03-e6a7a12d23ca">
- ls check ta được file data.txt với yêu cầu tìm ra dòng văn bản duy nhất xuất hiện một :
- sử dụng cat check được các kí tự của các text đang bị đảo => sắp xếp để tìm ra dòng password duy nhất :

```python
 sort data.txt | uniq -u 
```
Command Explanation
- sort : sử dụng để sắp xếp các kí tự theo trình tự
- uniq -u : uniq và -u (unique) chọn ra line khác biệt duy nhất 

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/d3d1c55d-504e-4237-9d14-10fb09aca15b)

*flag8:EN632PlfYiZbn3PhVK3XOGSlNInNE00t*

# level 9
<img width="697" alt="image-21" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/a8e29451-3bfb-4678-a74d-8f1d4da99b24">

- The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

```python
 strings data.txt | grep =
```
- strings : lọc kí tự có thể đọc
- grep : lọc các kí tự đã được filter "=" theo đề 

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/b4d77740-6bba-4e08-865a-bf0273e6a083)


*flag9:G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s*




# level 10
<img width="502" alt="image-23" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/5855f0ca-140c-4b95-85ac-1eb442c01ec5">

- The password for the next level is stored in the file data.txt, which contains base64 encoded data


```python
 cat data.txt | base64 -d
```
- theo đề ta thấy đã bị encode the phương thức base64

base64 -d : decrypt giải mã 

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/9e3ca7bc-fc85-4a04-99e7-c685b7ac909f)


*flag10:6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM*


# level 11
<img width="752" alt="image-25" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/ce07fbf9-c609-4ed6-b023-e95737d4c431">

-The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

-đề bài said các kí tự đã bị rotated 13 positions có nghĩa ROT13 

```python
  cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
- tr: dịch chuyển các kí tự theo phép ROT13

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/4d585687-c540-4d88-a0ff-0e2f51d45361)

*flag11:JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv*

# level 12

<img width="1042" alt="image-27" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/d9b01dab-c79e-4e4a-be81-7d5174b3cf00">

- The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

- data.txt là hexadump file ta sẽ phân tích và tìm ra phương pháp nén của file

- dịch chuyển đến thư mục /tmp có quyền chung cho phép tạo và chỉnh sửa file

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/485b1dea-cf2d-41ea-8828-763215adec3d)

- qua search thì file data2 đã được nén theo gzip --> revert về origin file nén 

```python
  xxd -r data.txt > com_data.gz
```
- vert xong search thì file3 đã được nén theo bz --> liên tục đến file tar và bz cuối cùng

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/cae70a5b-0ba3-4adf-b230-b852e5d14d93)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/c252d30a-9f85-4698-a933-0147a3ac0cfb)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/f3a99c2b-3b1c-42e6-8424-71ea27dc865e)


*flag12:wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw*

# level 13

<img width="1042" alt="image-31" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/1f050c6a-4a02-42b4-a676-e6fa99f36473">

-sử dụng ssh kết nối với file sshkey.private  

```python
  ssh -i sshkey.private  bandit14@bandit.labs.overthewire.org -p 2220
```

```python
  cat /etc/bandit_pass/bandit14
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/beed2774-b518-4321-be94-c634c48d6873)


*flag13:fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq*


# level 14
<img width="647" alt="image-33" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/12c36edc-f55d-4bac-9c85-286cc1310bd9">

- sử dụng netcat kết nối localhost với -p 30000 , provide mật khẩu trước 

```python
  nc localhost 30000
```
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/3b83495f-2af2-4a70-87cd-a4fb205783b6)


*flag14:jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt*


# level 15
<img width="1007" alt="image-36" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/69730adc-83c3-4103-967a-e0483537f5eb">

- The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

- sử dụng openssl connect đến localhost p 30001

```python
  openssl s_client  -connect localhost:30001
```
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/26788939-6e7b-4a09-98e6-1454f8be25eb)


*flag15:JQttfApK4SeyHwDlI9SXGR50qclOAil1*


# level 16
<img width="1057" alt="image-37" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/c2992ae6-540a-48e8-88a9-493d31427bc0">

- The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
- dựa theo range 31000 to 32000 ta có thể sử dụng nmap để quét cổng và checking service port

```python
  nmap -sV localhost -p 31000-32000
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/a981ea7d-677d-4740-9c0b-ca1df4ef66db)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/48939f32-4132-402b-a17b-104a96837495)

- tạo sshkey chứa key ssh đến bandit17 giống như level 14

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/a28d78f8-bfdc-4326-bc85-d5a4f3bdd895)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e8c4335f-72bf-4187-8ae6-e5ac1b9e4ffd)


*flag16:VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e*

# level 17

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/dafb838a-0a78-4b1a-bf8c-e550087491d6)

- sử dụng diff dể tìm ra sự thay đổi giữa pass new và old => lấy pass new và các line còn lại là giống nhau nên có thể loại trừ 

```python
  diff [file1] [file2]
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/16e7a396-bc1c-4c58-bcf8-79c89c7c1503)


*flag17:hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg*

# level 18
<img width="857" alt="image-41" src="https://github.com/j10nelop/ehc_challenge/assets/152776722/b699f303-3ec1-4cce-83c1-ec99519529d3">

- kết nối ssh với bandit18

```python
  ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh  
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/661a2b67-78ed-4a30-9c9e-da30761a103f)

*flag18:awhqfNnAbc1naukrpqDYcF95h7HoMTrC*

# level 19

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/add9ce07-f040-4d92-bc1f-e97a97070beb)

- Đề bài yêu cầu chúng ta chạy file *bandit20-do* nhưng lưu ý ở đây là phải sử dụng setuid. Khi sử dụng setuid để thực thi file, chúng ta sẽ trở thành chủ sở hữu tạm thời của file đó

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/0e14995b-4f0e-4cbc-888d-2422f2f70624)


*flag19:VxCazJaVykI6W36BkBU0mJTCM8rR95XT*

# level 20

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e195c86a-af12-4749-a45a-3693c00597b5)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/967b1651-1eb4-48d7-90d2-17f1d8dd5d89)

- connect nc to the suconnect on p 2000 pair the password and let the process run in the background with &

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/a63ff655-9c0d-42ba-ba6a-450079949ea6)

*flag20:NvEJF7oVjkddltPSrdKEFOllh9V1IBcq*

# level 21

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/99b2723d-90a5-4375-9462-a4a0cc55f53a)

- Cronjob này chạy tệp /usr/bin/cronjob_bandit22.sh với tư cách là người dùng bandit22. Năm ngôi sao cho biết nó được chạy mỗi phút, mỗi ngày. Để biết chính xác những gì được thực thi, chúng ta cần xem tệp bash.

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e938ec09-8943-4667-b01f-c2beb08cdd80)


*flag21:WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff*


# level 22
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/b047fff9-50a1-485c-b710-bfdc699bdd4e)

- làm giống level 21
- ta có tên tệp được tạo bởi dòng echo Tôi là người dùng $myname | md5sum | cut -d ' ' -f 1. Chúng ta chỉ cần thay thế $myname bằng bandit23

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/12453afc-4d99-4845-8a86-72f483d0ee3e)

*flag22:QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G*


# level 23
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/7323d82f-c11b-455f-b2a0-55f4820fe9d5)

- giống level trước
  
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/d26d3d8c-3e9a-4e03-990b-9b2368dc2cfe)

- tạo một tệp trong thư mục 'tmp'. Điều này ngăn chặn việc xóa tệp sớm và một bản sao trong trường hợp có sự cố. Sau đó di chuyển tệp vào thư mục ‘/var/spool/bandit24’ và nó sẽ được thực thi.

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/af370afc-b493-4d81-b931-ec307dc6a3c2)

*flag23:VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar*


# level 24

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/35b66d12-7513-4fb3-9928-c07557102c2d)

- brute forcing giải quyết yêu cầu đề bài

- tạo script trên /tmp

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/fe2ece41-2af7-4f9d-a6e0-235bafa2a768)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/ebd5e294-7741-4526-9bf4-da1a72b9bd46)

*flag24:p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d*


# level 25
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/00b8cf77-3539-4d08-a39b-7820b8d00048)

- theo đề bài ta thấy The shell for user bandit26 is not /bin/bash nó /usr/bin/showtext
- cat lên thì có hint ta sẽ ssh và thu nhỏ login để hiện more

```
ssh -i bandit26.sshkey -p 2220 -l bandit26 bandit.labs.overthewire.org
```

Ấn v chuyển sang vim sau đó nhập lệnh

```
:set shell =/bin/bash 
:shell
```

Dùng lệnh cat để đọc flag trong file text.txt

```
cat /etc/bandit_pass/bandit26
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/eab4bf80-eac2-4652-bc5a-8929b2f2fdab)


*flag25:c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1*


# level 26
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e2b100c8-1e0c-49a2-aacc-1b31fe4aaef0)

-tương tự level 25 kết nối ssh r thu nhỏ terminal 

```
ssh -i bandit26.sshkey -p 2220 -l bandit26 bandit.labs.overthewire.org
```

Ấn v chuyển sang vim sau đó nhập lệnh

```
:set shell =/bin/bash 
:shell
```

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/36642029-9a5b-48a1-aa8a-3403494d15fa)


*flag26:YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS*

# level 27
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e4029ee3-6913-46c3-b017-a795de60393f)

- download clone git resporitory bandit27
  
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/f71b537c-376b-4135-96c1-9f35ad3e4c36)

- cd repo cat readme dể xem flag

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/d338c405-c6e6-4433-b6f9-e6a4702ce9f4)

*flag27:AVanL161y9rsbcJIsFHuw35rjaOM19nR*

# level 28

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/0531342f-11ed-4edb-92ae-2f0a1d22c91e)

- download git repo cat readme.md
  
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/65669dc1-2441-4aa8-ae75-bc781c92754a)

- check git log

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/db8b7fd6-27db-4780-99fd-00e043dce052)

- 'fix info leak' có vẻ khác biệt show commit
![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/e02944ba-8ebe-4ecc-b92b-81eb2546648f)

*flag28:tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S*

# level 29

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/463879ab-6b64-4a44-94fd-40fce89a78db)
- tương tự như bước trên

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/062b2ec5-fc2f-41f1-bf28-4523d48bb95c)

- ta sẽ tiếp tục check các branch

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/30c629cd-6eec-4f20-8f7b-9be9749f9492)


*flag29:xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS*

# level 30

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/b61d2a63-0a62-4ea7-a8c1-23d05abc4ca7)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/6d08a3a3-c0eb-4536-a9e4-af6f6097b0e8)

- ta có thể xem chi tiết bằng git tag

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/b94d0128-27ea-4f88-bffb-f9823618eff8)


*flag30:OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt*

# level 31

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/17bf3b6c-c8ff-4e4f-a2dd-e398550d8c1b)

-'README' nói rằng phải đẩy tệp vào kho lưu trữ

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/73bfddfc-231d-486f-add1-5ecb95fb9682)



*flag31:rmCBvG56y58BXzv98yZGdO7ATVL5dW8y*

# level 32

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/abdd58b7-eada-4f0b-a008-c28e7c265fc9)

- ta có $0 là biến tham chiếu tới shell

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/0116c6fc-b6be-4021-9f55-66b114c958f6)

- whoami thì ta thấy đang có tên là bandit33 => cat /etc/bandit_pass/bandit33

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/684dd891-0653-4bdc-a48a-e4bb8f92e185)


*flag32:odHo63fHiFqcWWJG9rLiLDtPm45KzUKy*

# level 33  

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/fe06c342-bce6-468f-82c3-473537d0a069)

![image](https://github.com/j10nelop/ehc_challenge/assets/152776722/f84cee93-c255-4672-a53b-5455edfc72b6)

# thanks








 




  
















