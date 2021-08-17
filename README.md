# 自用教程
准备:Github账号 E5全局账号

1.用全局账号登录https://portal.azure.com/ 并打开Azure Active Directory

2.点击应用注册再点击新注册 Ps:名称随意 选择任何组织目录(任何 Azure AD 目录 - 多租户)中的帐户 重定向Web http://localhost:53682/

3.在应用界面记下应用程序(客户端)ID 点击证书和密码 +新客户端和密码 名称随意 截止日期选最长 记下'值'

4.点击API权限 选择Microsoft Gaph 选择委托的权限

5.勾选以下:Files.Read.All——Files.ReadWrite.All

Sites.Read.All——Sites.ReadWrite.All

User.Read.All——User.ReadWrite.All

Directory.Read.All——Directory.ReadWrite.All

Mail.Read——Mail.ReadWrite

MailboxSettings.Read——MailboxSettings.ReadWrite.

6.确定 点击代表** 同意 等待完成

7.下载Win版Rclone https://rclone.org/downloads/ 在文件目录的地址栏输入CMD

8.按 rclone authorize "onedrive" "应用程序ID" "值ID" 的格式输入 复制'refresh_token:'和'expiry'间Token(不带引号)

9.打开头像旁+号 选择import repository 输入https://github.com/baixiaomo472/E5default 和随意名称 开始输入

10.将Refresh Token替换到1.txt内 保存

11.点击Settings Secrets 创建CONFIG_ID 内容为 id=r'应用程序(客户端)ID' 创建CONFIG_KEY 内容为 secret=r'值'

12.头像Settings 点击Developer settings点击Personal access tokens点击Generate new token Note填写GITHUB_TOKEN

13.勾选repo,admin:repo_hook,workflow点击Generate token

14.点击库的star 在Actions创建第一次的Auto Api Task

# 注意
 # E5部分
  注册时尽量使用新邮箱,不然验证手机号那一步会出错(导致域名只能等一天再注册)

  E5订阅的地区和手机号地区要一致,不然也会导致出错
 # Github Actions部分
   一个Github账号拥有一个2H7G的Linux Github Actions
   
   Github Actions最大支持20个workflow并行
   
   Github Actions每小时最多可以调用1000个API,若按本配置(45Api/h)食用,加上workflow限制一个Github Actions可以支持20个账号的API调用

# 本配置默认设置
 执行API调用5次(45Api/次)
 
 每小时执行一次
