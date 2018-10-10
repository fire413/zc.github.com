# 天气预报软件说明书 #


 ## 项目介绍 ##


> 摘要：本设计使用Android设计技术开发了一种运用在Android系统上的手机天气预报软件，通过该软件可选择地区来获得天气，温度等信息。
> 功能介绍：
1. 遍历全国省市县数据
2. 显示天气信息
3. 手动切换城市
4. 后台自动更新天气

## 我的模块 ##
### 遍历全国省市县数据 ###
将从服务器获取的全国省市县数据存储到本地。建立3张表：province、city、county，分别用于存放省、市、县的数据信息。获取并解析和处理全国所有的省市县数据，并且编写界面将数据显示出来。
通过与服务器的交互获得全国所有省市县的数据，调用sendOkHttpRequest()方法，传入请求地址，注册一个回调来处理服务器响应。通过Utility类中的handleProvinceResponse()，handleCityResponse()，handleCountyResponse()方法来解析和处理数据，再组装成实体类对象，再调用save()将数据存储到数据库当中。通过ChooseAreaFragment类中的onCreateView()方法获取一些控件的实例，然后初始化ArrayAdapter，设置为ListView的适配器。接着在onActivityCreated()方法中给ListView和Button设置点击事件。
