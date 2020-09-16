# 徐仁鴻的Python學習筆記

------

> * 這篇筆記的內容主要是整理我學習python的內容
> * 本文參考自 Python自學聖經:從程式素人到開發強者的技術與實戰大全!
> * 後續會慢慢更新
## 章節目錄
Chapter17: Django網站開發

------

## 什么是 Django


## Django安裝
`pip install django == 2.2.6`

## 建立Django專案
使用命令提示字元執行以下指令
建立專案語法
`django-admin startproject 專案名稱`
建立一個myproject專案
`django-admin startproject myproject`
建立後會在當前路徑生成一個myproject資料夾
專案內各檔案說明:

| 檔案或目錄   | 說明   
| ------       | -----   :  
| manage.py    | python命令檔，用來建立app、啟動server
| __init.py__  | 一個空檔，使該資料夾(這裡指下層myproject資料夾)成為一個python package 
| settings.py  | 設定檔
| url.py       | 路徑頁面的配置
| wsgi.py      | 

## 建立Application 應用程式
建立應用程式語法
`python manage.py startapp "應用程式名稱"`
在最上層目錄建立一個myapp應用程式
`python manage.py startapp myapp`
完成後還須建立templates和static資料夾
`md templates`
`md static`
|名稱      | 用途
| ---      | ---    :
|templates | 用來存放顯示的模板(.html檔)
|static    | 用來存放圖片、CSS和JavaScript檔
注意:這兩個檔案要與myapp應用程式平行