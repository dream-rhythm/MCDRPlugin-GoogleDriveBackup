# MCDRPlugin-GoogleDriveBackup
This is a minecraft MCDR server plugin, it can backup Minecraft world to Google Drive.

## 簡介
![Image/Intro.PNG](https://raw.githubusercontent.com/fcu-d0441320/MCDRPlugin-GoogleDriveBackup/master/Image/Intro.PNG)
這是一個依賴[minecraft MCDR](https://github.com/Fallen-Breath/MCDReforged)的插件  
部分原始碼由[QuickBackupM](https://github.com/TISUnion/QuickBackupM)改寫而來  
他可以讓Minecraft擁有備份地圖到Google雲端的能力

## 指令
|指令|需求權限|作用|
|:--|:--:|:--:|
|`!!gdb help`|guest|列出所有指令|
|`!!gdb getAuth`|owner|獲取GoogleDrive認證網址|
|`!!gdb setToken <token>`|owner|將GoogleDrive認證給的金鑰填入|
|`!!gdb setFolder <folderId>`|owner|設定要上傳的目的資料夾|
|`!!gdb make`|user|建立備份檔並上傳到GoogleDrive|

## 安裝
1. 將`GoogleDriveBackup.py`放到`plugins`資料夾內
2. 在`plugins`資料夾內新增一個名為`GoogleDriveBackup`的資料夾
3. 到[Google Drive Api](https://developers.google.com/drive/api/v3/quickstart/python)申請API金鑰  
  3.1 點選`Quick start`  
  3.2 類型選`Desktop app`，並點`create`  
  3.3 點`Download client configuration`下載設定檔`credentials.json`  
  3.4 將`credentials.json`更名為`client_secrets.json`放到第二步的`GoogleDriveBackup`資料夾內  
4. 安裝依賴套件
  - 方案1:使用`requirements.txt`  
    4.1 下載`requirements.txt`  
    4.2 在命令提示字元/終端機輸入`pip3 install -r requirements.txt`進行安裝  
  - 方案2:自己一個一個安裝  
    4.1 在命令提示字元/終端機輸入以下指令進行安裝  
      ```shell
      pip install pydrive
      pip install threading  
      pip install google-api-python-client
      pip install google-auth-httplib2
      pip install google-auth-oauthlib    
      ```  
5. 設定驗證金鑰及上傳目的資料夾  
  5.1 到Minecraft中輸入`!!MCDR plugin load GoogleDriveBackup`載入插件    
  5.2 輸入`!!gdb getAuth`，這時他會產生一個驗證連結，請登入以進行驗證並記下最後的驗證金鑰  
  5.3 輸入`!!gdb setToken <剛剛的金鑰>`進行金鑰設定  
  5.4 到你的Google雲端新增一個資料夾，並複製網址列folder/之後的那串亂碼(FolderId)  
  5.5 輸入`!!gdb setFolder <剛剛的folderId>`進行金鑰設定  
