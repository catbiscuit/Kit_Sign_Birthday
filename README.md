# BirthDaySign

## 一、Fork 仓库

## 二、添加 Secret

**`Settings`-->`Secrets and variables`-->`Actions`-->`Secrets`-->`New repository secret`，添加以下secrets：**
- `GH_PAT`：
GitHub的token

- `Notify_Bark`：其值如下：
    
	```json
	{
		"Devicekey": "xxx",//Bark推送，不使用的话填空
		"Icon": "https://xxx/logo_2x.png"//Bark推送的icon
	}
    ```
- `Notify_Email`：其值如下：
    
	```json
	{
		"Server": "smtp.qq.com",
		"Port": 587,
		"Sender": "xxx@qq.com",//Email推送，发送者的邮箱，不使用的话填空
		"Password": "xxxx",
		"Receivers": [//Email推送接收者列表，为空时不发送
			"xxx@qq.com"
		]
	}
    ```
- `Config_Birthday`：其值如下：
    
	```json
	{
		"Distance": 2,//距离天数，提前多少天提醒。Distance=2，会提醒今天、明天、后天这3天
		"Peoples": [{//2个Date支持[".","-","/"]分隔。"0.2.23"或"2.23"，年份填0或不填年龄为未知
			"Name": "杨涛",
			"LunarDate": "1990.2.23",//农历生日，过农历生日才填。
			"SolarDate": "1990.3.19"//阳历生日，过阳历生日才填。
		}]
	}
    ```

**`Settings`-->`Secrets and variables`-->`Actions`-->`Variables`-->`New repository variable`，添加以下variables：**
- `CRON_HOURS`：
Cron定时的小时，示例值：8,20。详情参见下面的 任务执行时间

## 三、运行

**`Actions`->`Run`->`Run workflow`**

## 四、查看运行结果

**`Actions`->`Run`->`build`**

