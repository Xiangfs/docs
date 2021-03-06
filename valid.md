## 校验规则及对应的字段
     本文档仅适用于portal-web工程
    
-------

## 目录

- [必填(require)](#必填require)
- [名称(userName)](#名称username)
- [电话(tel)](#电话tel)
- [邮箱(email)](#邮箱email)
- [微信(wechat)](#微信wechat)
- [手机(mobile)](#手机mobile)
- [密码(pwd)](#密码pwd)
- [法人(legalPerson)](#法人legalperson)
- [地址(address)](#地址address)
- [备注(comment)](#备注comment)
- [组织名称(orgName)](#组织名称orgName)
- [描述(description)](#描述description)
- [潜客跟进天数(followUpDay)](#潜客跟进天数followupday)
- [潜客跟进说明(followUpDescription)](#潜客跟进说明followupdescription)
- [车型名称(modelName)](#车型名称modelname)
- [维修项目名称(repairProjectName)](#维修项目名称repairprojectname)
- [维修项目代码(repairProjectCode)](#维修项目代码repairprojectcode)
- [工时(workingHours)](#工时workinghours)
- [单价(unitPrice)](#单价unitprice)
- [QQ(QQ)](#qqqq)
- [主营业务(mainBusiness)](#主营业务mainbusiness)
- [配件名称(partsName)](#配件名称partsname)
- [配件代码(partsCode)](#配件代码partscode)
- [计量单位(countUnit)](#计量单位countunit)
- [采购价格(purchasePrice)](#采购价格purchaseprice)
- [最少订购(minOrderNum)](#最少订购minordernum)
- [建议售价(suggestPrice)](#建议售价suggestprice)
- [最低售价(minPrice)](#最低售价minprice)
- [最高售价(maxPrice)](#最高售价maxprice)
- [仓库名称(wareHouseName)](#仓库名称warehousename)
- [仓库代码(wareHouseCode)](#仓库代码warehousecode)
- [审核描述(examineDescription)](#审核描述examinedescription)
- [意向颜色(purposeColor)](#意向颜色purposecolor)
- [购车预算(carBudget)](#购车预算carbudget)
- [初次接待(firstFollow)](#初次接待firstfollow)
- [对比车型(compareModel)](#对比车型comparemodel)
- [安全库存(safeStock)](#安全库存safestock)
- [库存数量(stockNum)](#库存数量stocknum)
- [成本单价(costPrice)](#成本单价costprice)

## 模块-正则-规则-错误提示

-------


### <span id="require">必填</span>(require)
 `/\S+/`

* 不允许为空

    无

### <span id="userName">名称</span>(userName)
`/^\S.{1,32}\S$/`

* 必填
* 最大长度为32
* 开头结尾不允许输入空格，中间可以输入任意字符

        1.名称不允许为空，请输入名称
        2.名称不能超过32个字符，请重新输入

### <span id="tel">电话</span>(tel)
`/^[0][1-9][0-9]{1,2}-[0-9]{5,8}$/`

* 不允许输入中文、空格、字母以及除“-”以外的其他符号
* 格式为0开头的3位或4位数的区号 + “-” + 7位或8位的数字(如0571-86981001或010-7788665)

        电话号码格式不正确(正确格式如：0571-8888888)

### <span id="email">邮箱</span>(email)
`/^(?=\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$).{0,32}$/`

* 不允许输入中文、空格
* 最大长度为32
* 格式为：XX@XX.XX或XX@XX.XX.XX

        1.邮箱格式不正确(正确格式如：test@qq.com)
        2.邮箱不能超过32个字符，请重新输入
        
### <span id="wechat">微信</span>(wechat)
`/^[a-zA-Z0-9_-]{5,19}$/`

* 不允许输入中文、空格
* 格式为5-19位的字母、数字、下划线、减号(包含5和19)

        微信格式不正确(正确格式如：test11)

### <span id="mobile">手机</span>(mobile)
`/^1(3[0-9]|4[57]|5[0-35-9]|7[0135678]|8[0-9])\d{8}$/`

* 必填
* 不允许输入中文、字母、符号、空格
* 格式为11位数字(开头为130-139/14[5,7]/150-159/17[0,1,3,7]/18[0,9])

        1.手机号码不允许为空，请输入手机号码
        2.手机号码格式不正确(正确格式如：13010011001)

### <span id="pwd">密码</span>(pwd)
`/[\w-!@#$%^&*]{6,32}/`

* 必填
* 不允许输入中文和空格
* 区分大小写
* 长度为6-32

        1.密码不允许为空，请输入密码
        2.密码格式不正确(不允许输入中文和空格)
        3.密码不能超过32个字符，请重新输入

### <span id="legalPerson">法人</span>(legalPerson)
`/^\S.{0,32}\S$/`

* 最大长度为32

        法人不能超过32个字符，请重新输入

### <span id="address">地址</span>(address)
`/^.{0,32}$/`

* 最大长度为128

        地址不能超过128个字符，请重新输入

### <span id="comment">备注</span>(comment)
`/^.{0,512$}/`

* 最大长度为512

        备注不能超过512个字符，请重新输入

### <span id="orgName">组织名称</span>(orgName)
[同地址](#地址address)

* 最大长度为32

        组织名称不能超过32个字符，请重新输入

### <span id="description">描述</span>(description)
`/^.{0,64}$/`

* 最大长度为64

        描述不能超过64个字符，请重新输入

### <span id="followUpDay">潜客跟进天数</span>(followUpDay)
`/^[1-9][0-9]{0,3}$/`

* 必填
* 不允许输入中文、字母、符号、负数、小数和0
* 只能输入1-10000之间的正整数

        1.跟进天数不允许为空，请输入跟进天数
        2.跟进天数格式不正确，请输入1-10000之间的正整数

### <span id="followUpDescription">潜客跟进说明</span>(followUpDescription)
[同描述](#描述description)

* 最大长度为64

        跟进说明不能超过64个字符，请重新输入

### <span id="modelName">车型名称</span>(modelName)
[同地址](#地址address)

* 必填
* 最大长度为128

        1.车型名称不允许为空，请输入车型名称
        2.车型名称不能超过32个字符，请重新输入

### <span id="repairProjectName">维修项目名称</span>(repairProjectName)
`/^.{1,128}$/`

* 必填
* 最大长度为128

        1.项目名称不允许为空，请输入项目名称
        2.项目名称不能超过128个字符，请重新输入

### <span id="repairProjectCode">维修项目代码</span>(repairProjectCode)
`/^[A-Z]{0,32}$/`

* 最大长度为32(输入的字母默认变为大写)

        项目编码不能超过128个字符，请重新输入

### <span id="workingHours">工时</span>(workingHours)
`/^\d{1,6}(\.\d{1,2})?$/`

* 不允许输入中文、字母、负数和除“.”以外的符号；
* 只能输入0-999999.99之间的数字（可以为小数，最多保留2位）

        工时格式不正确，请输入0-999999.99之间的数字（最多保留2位小数）

### <span id="unitPrice">单价</span>(unitPrice)
`/^\d{1,8}(\.\d{1,2})?$/`

* 不允许输入中文、字母、负数和除“.”以外的符号；
* 只能输入0-99999999.99之间的数字（可以为小数，最多保留2位）

        单价格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）

### <span id="QQ">QQ</span>(QQ)
`/^\d{5,19}$/`

* 不允许输入中文、字母、符号和空格。
* 正确的格式为5-19位的数字

        QQ格式不正确，请输入5-19位数字

### <span id="mainBusiness">主营业务</span>(mainBusiness)
`/^.{0,256}$/`

* 最大长度为256

        主营业务不能超过256个字符，请重新输入

### <span id="partsName">配件名称</span>(partsName)
`/^.{1,32}$/`

* 必填
* 最大长度为32

        1.配件名称不允许为空，请输入配件名称
        2.配件名称不能超过32个字符，请重新输入

### <span id="partsCode">配件代码</span>(partsCode)
`/^[A-Z]{1,32}$/`

* 必填
* 最大长度为32
* 不允许输入中文、空格（输入的字母默认为大写）

        1.配件代码不允许为空，请输入配件代码
        2.配件代码不能超过32个字符，请重新输入
        3.配件代码格式不正确，不允许输入中文和空格

### <span id="countUnit">计量单位</span>(countUnit)
`/^.{0,8}$/`

* 最大长度为8

        计量单位不能超过8个字符，请重新输入

### <span id="purchasePrice">采购价格</span>(purchasePrice)
[同单价](#单价unitprice)

* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-99999999.99之间的数字，最多保留2位小数

        采购价格格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）

### <span id="minOrderNum">最少订购</span>(minOrderNum)
[同工时](#工时workinghours)

* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-999999.99之间的数字，最多保留2位小数

        最少订购格式不正确，请输入0-999999.99之间的数字（最多保留2位小数）

### <span id="suggestPrice">建议售价</span>(suggestPrice)
[同单价](#单价unitprice)

* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-99999999.99之间的数字，最多保留2位小数

        建议售价格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）

### <span id="minPrice">最低售价</span>(minPrice)
[同单价](#单价unitprice)

* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-99999999.99之间的数字，最多保留2位小数

        最低售价格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）

### <span id="maxPrice">最高售价</span>(maxPrice)
[同单价](#单价unitprice)

* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-99999999.99之间的数字，最多保留2位小数

        最高售价格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）

### <span id="wareHouseName">仓库名称</span>(wareHouseName)
`/^[\w-!@#$%^&*]{1,32}$/`

* 必填
* 最大长度为32(可以输入空格)

        1.仓库名称不允许为空，请输入仓库名称
        2.仓库名称不能超过32个字符，请重新输入

### <span id="wareHouseCode">仓库代码</span>(wareHouseCode)
[同配件名称](#配件名称partsname)

* 必填
* 最大长度为32
* 不允许输入中文、空格（输入的字母默认为大写）

        1.仓库代码不允许为空，请输入仓库代码
        2.仓库代码不能超过32个字符，请重新输入
        3.仓库代码格式不正确，不允许输入中文和空格

### <span id="examineDescription">审核描述</span>(examineDescription)
[同地址](#地址address)

* 最大长度为128

        审核描述不能超过128个字符，请重新输入

### <span id="purposeColor">意向颜色</span>(purposeColor)
[同地址](#地址address)

* 最大长度为32

        意向颜色不能超过32个字符，请重新输入

### <span id="carBudget">购车预算</span>(carBudget)
[同地址](#地址address)

* 最大长度为32

        购车预算不能超过32个字符，请重新输入

### <span id="firstFollow">初次接待</span>(firstFollow)
`/^.{0,128}$/`

* 最大长度为128

        初次接待不能超过128个字符，请重新输入

### <span id="compareModel">对比车型</span>(compareModel)
[同地址](#地址address)

* 最大长度为32

        对比车型不能超过32个字符，请重新输入

### <span id="safeStock">安全库存</span>(safeStock)
[同工时](#工时workinghours)

* 必填
* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-999999.99之间的数字，最多保留2位小数

        1.安全库存不允许为空，请输入安全库存
        2.安全库存格式不正确，请输入0-999999.99之间的数字（最多保留2位小数）

### <span id="stockNum">库存数量</span>(stockNum)
[同工时](#工时workinghours)

* 必填
* 不允许输入中文、字母、除“.”以外的符号、负数和空格
* 正确的格式0-999999.99之间的数字，最多保留2位小数

        1.库存数量不允许为空，请输入库存数量
        2.库存数量格式不正确，请输入0-999999.99之间的数字（最多保留2位小数）

### <span id="costPrice">成本单价</span>(costPrice)
[同单价](#单价unitprice)

* 库存数量不允许为空，请输入库存数量
* 库存数量格式不正确，请输入0-999999.99之间的数字（最多保留2位小数）

        1.成本单价不允许为空，请输入成本单价
        2.成本单价格式不正确，请输入0-99999999.99之间的数字（最多保留2位小数）


