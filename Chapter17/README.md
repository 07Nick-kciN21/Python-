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

 檔案或目錄    | 說明   
 ------       | -----    
 manage.py    | python命令檔，用來建立app、啟動server
 __init.py__  | 一個空檔，使該資料夾(這裡指下層myproject資料夾)成為一個python package 
 settings.py  | 設定檔
 url.py       | 路徑頁面的配置


## 建立Application 應用程式
建立應用程式語法
`python manage.py startapp "應用程式名稱"`
在最上層目錄建立一個myapp應用程式
`python manage.py startapp myapp`
完成後還須建立templates和static資料夾
`md templates`
`md static`

名稱      | 用途 
---       | ---    
templates | 用來存放顯示的模板(.html檔)
static    | 用來存放圖片、CSS和JavaScript檔
注意:這兩個檔案要與myapp應用程式平行

## setting.py 環境設定

###除錯模式設定(26行)

設定為除錯模式，執行時輸出錯誤訊息以利除錯，但在真正上線時要改為FALSE。
```
DEBUG = TRUE
```
### 加入App應用程式(40行)
把 myapp 加入 INSSTALLED_APPS 串列中
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp',  #新增的app
]

```

### 設定Template路徑(58行)
```
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],#加上templates路徑
        'APP_DIRS': True,
        'OPTIONS': {
    ...
```

### 設定語系和時區(107到109行)
```
LANGUAGE_CODE = 'zh-hant' #改成繁體中文

TIME_ZONE = 'Asia/Taipei' #改成台北時區

```

### 設定靜態路徑檔(121行)
```
STATIC_URL = '/static/'
STATIC_FILES_DIRS = [               #加入 static 路徑檔
    os.path.join(BASE_DIR, 'static'),
]

```

## 以伺服器瀏覽
用 manager.py 啟動Server
` python manager.py runserver `

打開瀏覽器輸入http://127.0.0.1:8000 就能看見網頁
