# 欢迎来到优家售后助手

## 内部结构

### version
- 说明：版本升级配置json文件
- 字段解释：
  1. retCode：成功返回码(通用设置，对于该项目没有实质意义，下面一样)
  2. retInfo: 成功消息说明（通用设置，对于该项目没有实质意义，下面一样）
  3. data:需要解析的消息内容
     - desc(字符串内容)：需要显示的消息内容，注意换行使用"\r\n"代替键盘回车键
	 - versionCode(字符串内容):app版本号，现在app取的是发版那天的年月日时（19071115：代表19年7月11日15时），用于版本升级版本号比较
	 - versionName(字符串内容):app版本名称，比如V2.4.1
	 - isForce(整数内容):0代表强制升级，1代表强制升级
### img_version.png
- 生成二维码下载app图片替换原来的图片，注意不能修改名字，要保持一致

### question
- 说明：app常见问题配置
  - question_category：配置常见问题标题
    - 字段解释：
	data：需要解析的内容
	categories：分类列表内容（增加条目必须添加到第一个列表上面，不能加到最后一个列表，而且code不能一样、要累加）
	 1. categoryCode：分类code
	 2. categoryName：分类名字
	 3. categoryUrl： 拉去内容数据url，跟category_1.....保持一致，具体配置看实际配置代码
  - category_1/2/3/4....:配置question_category列表中categoryUrl的具体实现内容
    data：需要解析的内容
	questions:问题具体的内容，注意：如果需要将新加的显示在前面就必须添加到列表的最上面一条
	1. questionCode：问题code
	2. questionName：设置要显示的内容
	3. questionUrl：设置要跳转的url
	
### message
- 说明：消息内容配置（content.json）
- 字段解释：
  data：需要解析的内容
  contents:分类列表（倒叙排列需要将数据放到列表的最上面一条，注意：contentId是唯一的，递增展示）
  1. contentId：内容id，唯一识别消息，不能重复，递增显示
  2. contentName：需要显示的内容
  3. contentTime：需要显示的时间
  4. contentUrl：需要跳转的内容
     
	 