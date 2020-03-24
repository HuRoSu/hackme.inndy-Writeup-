# Hackme Inndy Writeups
# Misc
## 1.flag
Description
All flags are in this format:
FLAG{This is flag's format}

## 2.corgi can fly
下載圖片後 Description得知(Maybe you can try stegsolve)
使用stegsolve.jar後掃QRCode取得flag

## 3.television
Windows使用IDA等逆向工程程式
Unix系統用Hexdump或是直接使用strings
`hexdump -C` (a470附近)可得Flag

## 5.where is flag
解壓縮後出現flag
用正規表示式配合cat grep去排除後取得Flag
`cat flag|grep -o "FLAG{[a-Z0-9]*}"`

# Web
## 15.hide and seek
點開後會到首頁
直接看原始碼就能找到Flag

