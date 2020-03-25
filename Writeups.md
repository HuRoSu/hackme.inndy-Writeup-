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
一個command injection
從黑名單知道沒有擋`` ` ``
先正常ls查看


