# 安徽大学校园网自动登录脚本
本脚本仅适用于安徽大学的校园网登录(支持有线/无线)

## 准备工作

1. 在release中下载最新版本的zip包并解压
2. 在"login_config.ini"文件中写入以下内容并保存:

```ini
[info]
account = 这里是平常登录校园网的账号(即学号)
password = 这里是平常登录校园网的密码(初始为身份证后六位)
```

下面是样例:

```ini
[info]
account = WZ1237844
password = 123456
```

3. 此时就可以双击exe运行了, 脚本会自动登录校园网


## 配置开机自动运行
1. 以管理员身份运行 计划任务自动生成与导入器.exe
2. (可选)设置主板BIOS AC断电自启
## 注意事项

1. 在ini中填写的必须是英文符号!!!!!!
2. 如果你配置了开机自启动, 则不可以再移动文件
3. 请不要随意修改文件名


## todo_list

- [x] 为即会使用带后缀的有线宽带和无线宽带的安大人提供自动选择(有线/无线网络连接)
- [x] 提供异常情况处理


## 如果你想本地构建的话
1. pip install -r requirements.txt
2. playwright install chromium ~~(安装成功后会显示安装路径, 请记住它)~~
3. 可以愉快的运行了
4. 打包指令(请找到你自己的chrome-win路径以替换以下指令中的path_to_chrome-win)

for 安徽大学校园网自动登录.exe
```shell
pyinstaller --onefile --noconsole --add-data "path_to_chrome-win\chrome-win;chrome-win" --hidden-import=plyer.platforms.win.notification --name=安徽大学校园网自动登录 --version-file .\the_version_info.txt .\auto_login.py
```
演示路径
```shell
pyinstaller --onefile --noconsole --add-data "C:\Users\admin\AppData\Local\ms-playwright\chromium-1067\chrome-win;chrome-win" --hidden-import=plyer.platforms.win.notification --name=安徽大学校园网自动登录 --version-file .\the_version_info.txt .\auto_login.py
```

for update.exe
```shell
pyinstaller --onefile --name=update .\update.py
```
for 计划任务自动生成与导入.exe
```shell
pyinstaller --onefile --name=计划任务自动生成与导入 .\计划任务自动生成与导入.py
```
引用来源:https://github.com/Natural-selection1/AHU_auto_login

代码修改自用，如有侵权，请告知删除