# Hackme Inndy Writeups
# Misc
## 1.flag
Description<br>
All flags are in this format:<br>
FLAG{This is flag's format}<br>

## 2.corgi can fly
下載圖片後 Description得知(Maybe you can try stegsolve)<br>
使用stegsolve.jar後掃QRCode取得flag<br>

## 3.television
Windows使用IDA等逆向工程程式<br>
Unix系統用Hexdump或是直接使用strings<br>
`hexdump -C` (a470附近)可得Flag<br>

## 5.where is flag
解壓縮後出現flag<br>
用正規表示式配合cat grep去排除後取得Flag<br>
`cat flag|grep -o "FLAG{[a-Z0-9]*}"`<br>

# Web
## 15.hide and seek
點開後會到首頁<br>
直接看原始碼就能找到Flag<br>

## 19.ping
一個command injection<br>
從黑名單知道沒有擋`` ` ``<br>
先正常ls查看`` `ls` ``<br>
出現<br>
`ping: flag.php`<br>
`index.php: Name or service not known`<br>
發現flag<br>
所以去嘗試cat flag.php<br>
不過cat被禁用 只要cat以外的讀取文件都能用<br>
像是more less等<br>
還需要考慮到的是flag也被禁<br>
所以需要用``*``來省略字母<br>
因此輸入`` `more f*` ``來取得Falg<br>

## 20.scoreboard
對Scoreboard這個Web做caching<br>
會發現在response header的地方有個HTTP header fields的名子為x-flag<br>

## 31.dafuq-manager 1
可以知道guest登入後cookie會多出一個show_hidden<br>
而show_hidden的值為no<br>
可以猜把值改yes可以顯示隱藏的資料<br>
所以就利用Edit Cookie的程式將show_hidden的值改為yes<br>
第一題的Flag就在good.job.here.is.your.hidden.flag-1.txt<br>

# Reversing
## 41.helloworld
下載後先上`chmod +x helloworld`使檔案可執行<br>
如果是64bit的Unix系統 可能無法跑<br>
用`file helloworld`檢查檔案發現是32bit的<br>
可以`apt install lib32ncurses5`去下載讓64能跑32<br>
接著一樣反組譯 這邊是用objdump<br>
Windows一樣能用IDA<br>
下objdump指令`objdump -M intel -d ./helloworld`<br>
objdump指令說明<br>
-M disassembler options 並選用intel語法<br>
-d disassemble<br>
會發現在80484D8有`cmp eax,0x12b9b0a1`<br>
cmp為比較指令 得知它要比較是否為0x12b9b0a1<br>
將hex轉dec後得知為314159265<br>
接著跑./helloworld輸入數字 得到Flag<br>

# Pwn
## 57.catflag
基本題 nc連上去後就可以直接下ls  
就能cat到flag了  

## 59.ROP
利用ROPGadge來生成shell
用`ROPgadge --binary rop --ropchain`來生成
ROPgadge binary來指定檔案
ropchain來生成code
再用vim或nano等編輯改成pwntools格式



# Crypto

