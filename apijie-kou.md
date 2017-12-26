# API接口

### 1、登录

[http://169.254.1.0/CACHEDIR434810813/cgi-bin/login.xml?username=123456&password=123456&t=0](http://169.254.1.0/CACHEDIR434810813/cgi-bin/login.xml?username=123456&password=123456&t=0)

* 请求头

  | key | value |
  | :--- | :--- |
  | Accept | \*_/_\* |
  | User-Agent | Mozilla/5.0 |
  | Host | 169.254.1.0 |
  | Accept-Encoding | gzip, deflate |
  | Accept-Language | zh-CN,zh;q=0.8 |
  | Cookie | quickStart=yes; lang=zh; menuState=locked |

* 请求参数

  | 参数 | 必选 | 类型 | 说明 |
  | :--- | :--- | :--- | :--- |
  | username | Y | String | admin |
  | password | Y | string | password |
  | t | N | String | 1190706696 |

* 返回参数

  * 请求成功：

    | 参数 | 类型 | 说明 |
    | :--- | :--- | :--- |
    | cookie | String | user=admin&t=-4200&digest=F84779D61CA51088EACCD86F43A75BAE |

  * 请求失败 ：`<FAIL>1</FAIL>`

    | 错误码 | 说明 |
    | :--- | :--- |
    | 1 | 名称有误 无效密码 |

* 记录cookie=user=admin&t=-4200&digest=F84779D61CA51088EACCD86F43A75BAE

### 2、merge

[http://169.254.1.0/xml/dynamic/merge.xml?sysData=&options=](http://169.254.1.0/xml/dynamic/merge.xml?sysData=&options=)

* 请求头

  | key | value |
  | :--- | :--- |
  | Accept | \*_/_\* |
  | User-Agent | Mozilla/5.0 |
  | Host | 169.254.1.0 |
  | Accept-Encoding | gzip, deflate |
  | Accept-Language | zh-CN,zh;q=0.8 |
  | Cookie | quickStart=yes; lang=zh; menuState=locked |

* 请求参数

  | 参数 | 必选 | 类型 | 说明 |
  | :--- | :--- | :--- | :--- |
  | sysData | Y | String | “” |
  | options | Y | string | “” |

* 返回参数点击看附件：[merge.xml](resources/EB19A60A58EF45D46AA6C873649BB479.xml)

  | 参数 | 说明 |
  | :--- | :--- |
  | serial | 5631C01071 |

* 记录serial=5631C01071

* 之后所有的请求头Cookie:‘Auth’+serial+'='+URLEncoder.encode\(cookie\)+‘; lang=zh; menuState=locked;’

* 效果：Auth5631C01071=user%3Dadmin%26t%3D1190608431%26digest%3DF2C58E77E07620B1560AFFC790329FBC; lang=zh; menuState=locked;

### 3、获取配置信息

[http://169.254.1.0/CACHEDIR434810813/xml/dynamic/configData.xml](http://169.254.1.0/CACHEDIR434810813/xml/dynamic/configData.xml)

* 请求头

  | key | value |
  | :--- | :--- |
  | Accept | \*_/_\* |
  | User-Agent | Mozilla/5.0 |
  | Host | 169.254.1.0 |
  | Accept-Encoding | gzip, deflate |
  | Accept-Language | zh-CN,zh;q=0.8 |
  | Cookie | Auth5631C01071=user%3Dadmin%26t%3D1190608431%26digest%3DF2C58E77E07620B1560AFFC790329FBC; lang=zh; menuState=locked; |

* 返回参数点击看附件：[ConfigData.xml](resources/469528A0A2B04F779D8D017C395B5308.xml)

  | 参数 | 类型 | 说明 |
  | :--- | :--- | :--- |
  | CMRID | - | 5用 |
  | RTCMID | - | 5用 |
  | RTCM3ID | - | 5用 |
  | StationName | - | 5用 |
  | StationCode | - | 5用 |
  | refLat | double | 参考纬度 |
  | refLon | double | 参考经度 |
  | refHgt | double | 参考高度 |

### 4.获取当前位置\(300毫秒调用一次，循环调用5次\)

[http://169.254.1.0/CACHEDIR434810813/xml/dynamic/posData.xml](http://169.254.1.0/CACHEDIR434810813/xml/dynamic/posData.xml)

* 请求头

  | key | value |
  | :--- | :--- |
  | Accept | \*_/_\* |
  | User-Agent | Mozilla/5.0 |
  | Host | 169.254.1.0 |
  | Accept-Encoding | gzip, deflate |
  | Accept-Language | zh-CN,zh;q=0.8 |
  | Cookie | Auth5631C01071=user%3Dadmin%26t%3D1190608431%26digest%3DF2C58E77E07620B1560AFFC790329FBC; lang=zh; menuState=locked; |

* 返回参数点击看附件：[posData.xml](resources/D6050F704F41397546CE59A39727E147.xml)

  | 参数 | 类型 | 说明 |
  | :--- | :--- | :--- |
  | lat | double | here纬度 |
  | lon | double | here经度 |
  | hgt | double | here高度 |
  | avgLat | double | avg纬度 |
  | avgLon | double | avg经度 |
  | avgHt | double | avg高度 |

### 5.提交

[http://169.254.1.0/CACHEDIR434810813/cgi-bin/refPosPage.xml?CMRID=0&RTCMID=0&RTCM3ID=0&StationName=CREF0001&StationCode=&coordSystem=Geographical&refLatDeg=0&refLatMin=0&refLatSec=0.00000&refLatSign=1&refLonDeg=0&refLonMin=0&refLonSec=0.00000&refLonSign=1&refHgt=0.000&refX=0.0000&refY=0.0000&refZ=0.0000&herePositionUsed=1&hereLat=0&hereLon=0&hereHgt=0.000&refLat=0&refLon=0&hereX=0.0000&hereY=0.0000&hereZ=0.0000&AutoAvgTime=120](http://169.254.1.0/CACHEDIR434810813/cgi-bin/refPosPage.xml?CMRID=0&RTCMID=0&RTCM3ID=0&StationName=CREF0001&StationCode=&coordSystem=Geographical&refLatDeg=0&refLatMin=0&refLatSec=0.00000&refLatSign=1&refLonDeg=0&refLonMin=0&refLonSec=0.00000&refLonSign=1&refHgt=0.000&refX=0.0000&refY=0.0000&refZ=0.0000&herePositionUsed=1&hereLat=0&hereLon=0&hereHgt=0.000&refLat=0&refLon=0&hereX=0.0000&hereY=0.0000&hereZ=0.0000&AutoAvgTime=120)

* 请求头

  | key | value |
  | :--- | :--- |
  | Accept | \*_/_\* |
  | User-Agent | Mozilla/5.0 |
  | Host | 169.254.1.0 |
  | Accept-Encoding | gzip, deflate |
  | Accept-Language | zh-CN,zh;q=0.8 |
  | Cookie | Auth5631C01071=user%3Dadmin%26t%3D1190608431%26digest%3DF2C58E77E07620B1560AFFC790329FBC; lang=zh; menuState=locked; |

* 请求参数

  | 参数 | 必选 | 类型 | 说明 |
  | :--- | :--- | :--- | :--- |
  | CMRID | - | - | 3返回 |
  | RTCMID | - | - | 3返回 |
  | RTCM3ID | - | - | 3返回 |
  | StationName | - | - | 3返回 |
  | StationCode | - | - | 3返回 |
  | coordSystem | - | - | Geographical |
  | refLatDeg | - | - | Avg纬度 度 |
  | refLatMin | - | - | Avg纬度 分 |
  | refLatSec | - | - | Avg纬度 秒 |
  | refLatSign | - | - | 1 |
  | refLonDeg | - | - | Avg经度 度 |
  | refLonMin | - | - | Avg经度 分 |
  | refLonSec | - | - | Avg经度 秒 |
  | refLonSign | - | - | 1 |
  | refHgt | - | - | Avg高度 |
  | refX | - | - | Avg X |
  | refY | - | - | Avg Y |
  | refZ | - | - | Avg Z |
  | herePositionUsed | - | - | 0 |
  | hereLat | - | - | here 纬度 |
  | hereLon | - | - | here 经度 |
  | hereHgt | - | - | here 高度 |
  | refLat | - | - | here 纬度 |
  | refLon | - | - | here 经度 |
  | hereX | - | - | here X |
  | hereY | - | - | here Y |
  | hereZ | - | - | here Z |
  | AutoAvgTime | - | - | 120 |

* 返回参数

  * 请求成功
    `<OK>1</OK>`
  * 请求失败



