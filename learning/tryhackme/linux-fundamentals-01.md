#Tryhackme - Linux Foundamentals 01

## What I learned
- How to use Linux terminal
- Basic command for navogation

## Command Used
- echo
- Whoami

Interacting With the Filesystem
- ls
- cd
- cat
- pwd
  
Searching
- Find
- Grep

Shell Operator
- `&`
- `&&`
- `>`
- `>>`

#What I did 

Interacting With the Filesystem
- echo = Output any text that we provide
- Whoami =  check user
- ls = list file in directory if directory contains a file will show list 
- cd = change current directory to we  cd + path
- cat = read content in file
- pwd = print our current directory path 

 Searching
 - `Find` = if we already know file name we can use find -name filename.text
   `find -name passwords.txt` in case dont know file name we can construct a command such as
   `find -name *.txt`  we can get any name in txt file type with file directory path

- `grep`
  `wc` More I have learn some trip, In the case that I want to know how many line ? error ? in example access.log file we can use command like this  `wc -l access.log`

  Grep Word from file : I want to search word in file , We can use command grep "error" access.log
  Grep word from all file in folder : -R = --recursive ค้นหาแบบวนซ้ำเข้าไปในทุกโฟลเดอร์ย่อย  `grep -R`

```bash
  grep -R "ข้อความที่ต้องการค้นหา" /path/to/directory
  grep -R  "Hello" /etc/  `
```

Shell Operator
- & This operator allows you to run commands in the background of your terminal. ใช้รันคำสั่งให้ทำงานอยู่เบื้องหลัง (background) ทำให้เราสามารถใช้ terminal ต่อได้ทันที โดยไม่ต้องรอคำสั่งนั้นเสร็จ
 ` รันคำสั่ง → ได้ prompt ทันที → ทำงานอื่นต่อได้ `
- && This operator allows you to combine multiple commands together in one line of your terminal. it will run command1 success first and then next command2. The command2 not run if Command1 not success. คำสั่งถัดไปจะทำงานก็ต่อเมื่อคำสั่งก่อนหน้าทำงานสำเร็จเท่านั้น

```bash  
command1 && command2
    ↓
command1 สำเร็จ? 
    ↓ YES → รัน command2
    ↓ NO  → หยุด ไม่รัน command2

# สร้างโฟลเดอร์ แล้วเข้าไปในโฟลเดอร์นั้น
mkdir myfolder && cd myfolder

# อัปเดตแล้วติดตั้งโปรแกรม
sudo apt update && sudo apt install nginx
```

- `>` (Output Redirector) This operator is what's known as an output redirector. ส่งออกไปที่ไฟล์ (แทนที่)
```bash 
# สร้างไฟล์ welcome ด้วยข้อความ "hey"
echo hey > welcome

# ตรวจสอบไฟล์
cat welcome
# ผลลัพธ์: hey

# ถ้าใช้ > อีกครั้ง เนื้อหาเดิมจะหายไป
echo hello > welcome
cat welcome
# ผลลัพธ์: hello (hey หายไปแล้ว)
```
⚠️ Caution:
If the file already exists, all of its original content will be replaced! ถ้าไฟล์มีอยู่แล้ว เนื้อหาเดิมจะ ถูกแทนที่ทั้งหมด!

- `>>` (Append Redirector) - ต่อท้ายไฟล์  it instead just puts the output at the end.
เหมือน > แต่ ไม่ลบเนื้อหาเดิม จะนำข้อความใหม่ไป ต่อท้าย (append) ข้างล่างแทน

```bash 
echo hey > welcome

# ต่อท้ายด้วย "hello"
echo hello >> welcome

# ตรวจสอบไฟล์
cat welcome
# ผลลัพธ์:
# hey
# hello
```
More example
```bash 
# 1. รันสแกนเน็ตเวิร์กในพื้นหลัง
nmap -sV 192.168.1.0/24 > scan_result.txt &

# 2. อัปเดตและอัปเกรดแบบมีเงื่อนไข
sudo apt update && sudo apt upgrade -y

# 3. บันทึก log แบบต่อท้าย
echo "[$(date)] Server started" >> /var/log/myserver.log

# 4. รวมหลายคำสั่ง
mkdir backup && cp -r important/* backup/ && echo "Backup complete!" >> backup.log
```

`nmap`	โปรแกรมสแกนเครือข่าย (Network Mapper)

`-sV`	สแกนเวอร์ชันของบริการ (version detection) บนพอร์ตที่เปิดอยู่

`192.168.1.0/24`	เป้าหมาย - เครือข่ายทั้งหมดตั้งแต่ 192.168.1.1 - 192.168.1.254

`>	redirector` - ส่งผลลัพธ์ไปเก็บในไฟล์ (แทนที่เนื้อหาเดิม)

`scan_result.txt`	ไฟล์ที่ใช้เก็บผลลัพธ์

`&`	รันคำสั่งในพื้นหลัง (background)

** ใช้ nohup - ถ้าต้องการให้รันต่อแม้ปิด terminal: If we want to close terminal but want job continue , we can use `nohup`
```bash
nohup nmap -sV 192.168.1.0/24 > scan_result.txt &
```
