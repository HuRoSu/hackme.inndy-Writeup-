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
`ping: flag.php
index.php: Name or service not known`
所以要去cat flag.php<br>
不過cat被禁用 只要cat以外的讀取文件都能用<br>
像是more less等<br>
還需要考慮到的是flag也被禁<br>
所以需要用``*``來省略字母<br>
因此輸入```more f*```來取得Falg<br>

