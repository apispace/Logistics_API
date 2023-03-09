# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=kuaidiwuliu) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 全国快递物流查询
目前已支持600+快递公司的快递信息查询。自动识别快递公司及单号，服务器毫秒响应，数据及时准确。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/wlgj1/introduction](https://www.apispace.com/eolink/api/wlgj1/introduction?utm_source=github&utm_term=kuaidiwuliu) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/wlgj1/guidence/](https://www.apispace.com/eolink/api/wlgj1/guidence/?utm_source=github&utm_term=kuaidiwuliu)

**该产品拥有以下APIs：**
1. 实时快递查询
2. 快递批量实时查询
3. 智能识别电子面单号

### 功能亮点

1.  全国快递物流查询服务，支持快递公司600+家，接口稳定，时效性高。
1.  主动发起查询请求返回最新物流详情，输入一个单号即可一键查询全程的物流轨迹信息。
1.  根据用户提交的快递单号，智能判断该单号所属快递公司。
1.  基于快递公司单号规则和千万级快递单号大数据，单号识别率超过98%。


### 应用场景

#### 1. 网购收货

用户在网上购买商品，并选择快递物流公司进行配送，物流公司会将商品从卖家处取货，然后送达用户手中，方便快捷。

#### 2. 企业运输

企业需要将货物从工厂或仓库运往全国各地的顾客手中，通过快递物流可以实现快速、安全、高效的运输服务。

#### 3. 文件传递

个人或企业需要将文件或合同等文件快速传递给合作伙伴、客户或同事，通过快递物流可以实现快速而安全的传递服务。

#### 4. 食品配送

餐饮企业需要将食品从生产地或仓库运往各个门店，通过快递物流可以确保食品安全、卫生，为用户提供优质的用餐服务。

#### 5. 医药配送

医院、医药企业需要将药品、医疗器械等物品送达到全国各地的病人或客户手中，通过快递物流可以实现安全、快速的送达服务，为患者提供及时的医疗服务。


### 相关附件

-   [快递公司编码表](https://easy-open-link.feishu.cn/wiki/wikcn2OczVpSCxXt9EBGwQ1gzQd)
-   [物流状态编码对照表](https://easy-open-link.feishu.cn/wiki/wikcnaTBVBONVTPpxXAgGR4TWgc)


### 返回示例

以实时快递查询为例

```
{
    "traceId":"932737509700083170",
    "success":true,
    "logisticsTrace":{
        "cpCode":"DBKD",
        "mailNo":"DPK366013054101",
        "theLastTime":"2021-11-05 18:57:34",
        "theLastMessage":"已签收，签收人类型：本人",
        "logisticsCompanyName":"德邦快递",
        "courier":"彭瑞元",
        "takeTime":"4天1小时56分",
        "logisticsStatusDesc":"已签收",
        "courierPhone":"16626323347",
        "logisticsStatus":"SIGN",
        "cpMobile":"95353",
        "cpUrl":"http://www.deppon.com",
        "logisticsTraceDetailList":[
            {
                "areaCode":"CN131081000000",
                "areaName":"河北省,廊坊市,霸州市",
                "subLogisticsStatus":"ACCEPT",
                "time":1635757268000,
                "logisticsStatus":"ACCEPT",
                "desc":"您的订单已被收件员揽收,【廊坊霸州市煎茶铺镇营业部】库存中"
            },
            {
                "areaCode":"CN131081000000",
                "areaName":"河北省,廊坊市,霸州市",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635769013000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【廊坊霸州市煎茶铺镇营业部】，下一部门【西青转运场装卸车一部】"
            },
            {
                "areaCode":"CN131081000000",
                "areaName":"河北省,廊坊市,霸州市",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635770139000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【廊坊霸州市煎茶铺镇营业部】，下一部门【西青转运场装卸车一部】"
            },
            {
                "areaCode":"CN131081000000",
                "areaName":"河北省,廊坊市,霸州市",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635770140000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【廊坊霸州市煎茶铺镇营业部】，下一部门【西青转运场装卸车一部】"
            },
            {
                "areaCode":"CN120111000000",
                "areaName":"天津,天津市,西青区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635774298000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，到达西青转运场装卸车一部"
            },
            {
                "areaCode":"CN120111000000",
                "areaName":"天津,天津市,西青区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635796203000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【西青转运场装卸车一部】，下一部门【顺德枢纽中心】"
            },
            {
                "areaCode":"CN120111000000",
                "areaName":"天津,天津市,西青区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635796300000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【西青转运场装卸车一部】，下一部门【顺德枢纽中心】"
            },
            {
                "areaCode":"CN440606000000",
                "areaName":"广东省,佛山市,顺德区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1635910458000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，到达顺德枢纽中心"
            },
            {
                "areaCode":"CN440606000000",
                "areaName":"广东省,佛山市,顺德区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636051232000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【顺德枢纽中心】，下一部门【深圳龙华集配站】"
            },
            {
                "areaCode":"CN440606000000",
                "areaName":"广东省,佛山市,顺德区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636051919000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【顺德枢纽中心】，下一部门【深圳龙华集配站】"
            },
            {
                "areaCode":"CN440309000000",
                "areaName":"广东省,深圳市,龙华区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636059242000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，到达深圳龙华集配站"
            },
            {
                "areaCode":"CN440309000000",
                "areaName":"广东省,深圳市,龙华区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636082553000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【深圳龙华集配站】，下一部门【深圳罗湖区老街经营分部】"
            },
            {
                "areaCode":"CN440309000000",
                "areaName":"广东省,深圳市,龙华区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636082609000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，离开【深圳龙华集配站】，下一部门【深圳罗湖区老街经营分部】"
            },
            {
                "areaCode":"CN440303000000",
                "areaName":"广东省,深圳市,罗湖区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636085468000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，到达深圳罗湖区老街经营分部，部门电话：0755-33114117"
            },
            {
                "areaCode":"CN440303000000",
                "areaName":"广东省,深圳市,罗湖区",
                "subLogisticsStatus":"ON_THE_WAY",
                "time":1636087098000,
                "logisticsStatus":"TRANSPORT",
                "desc":"运输中，到达深圳罗湖区老街经营分部，部门电话：0755-33114117"
            },
            {
                "areaCode":"CN440300000000",
                "areaName":"广东省,深圳市",
                "subLogisticsStatus":"DELIVERING",
                "time":1636098210000,
                "logisticsStatus":"DELIVERING",
                "desc":"派送中，德邦已开启”安全呼叫“，保护您的电话隐私，小哥今日体温正常，将佩戴口罩为您配送，也可联系小哥将包裹放置指定地点，祝您身体健康。,派送人：彭瑞元,电话:16626323347"
            },
            {
                "areaCode":"CN440300000000",
                "areaName":"广东省,深圳市",
                "subLogisticsStatus":"SIGN",
                "time":1636109854000,
                "logisticsStatus":"SIGN",
                "desc":"已签收，签收人类型：本人"
            }
        ]
    }
}
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223953145-0366dc65-f6b1-42c1-a988-ea9371f8cf90.png)

### Python(Requests) 调用代码示例
这里以 实时快递查询API 为例
```
import requests

url = "https://eolink.o.apispace.com/wlgj1/paidtobuy_api/trace_search"

payload = {"cpCode":"YTO","mailNo":"YTO1111111111","tel":"13000000000或0000","orderType":"asc"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```

