#后端Long类型 id导致web js数值溢出
## 

# Apache POI
 ## EXCEL导入失败
 原因: 平台采用Apache POI作为Excel的解析组件， POI目前仅支持的 BIFF8 format (from Excel versions 97/2000/XP/2003)。上传的文件为 Excel 5.0/7.0 (BIFF5) 格式， 通俗理解为window office 95， 不在兼容范围之内。 
# Apache Shiro 安全漏洞
## 服务器(含禄口机场)存在安全漏洞。 
### 漏洞名称:Apache Shiro默认密钥致命令执行漏洞(CVE-2-16-4437)。
### 详细描述： Apache Shiro 1.2.4及以前版本中，加密的用户信息序列化后存储在名为remember-me的Cookie中。攻击者可以使用Shiro的默认密钥伪造用户Cookie，触发Java反序列化漏洞，进而在目标机器上执行任意命令。
### 影响版本： Apache Shiro <= 1.2.4
## 修复方案: 升级Apache Shiro 至较高版本。 选择 1.6.0 。
# Java Serializable
## Java Bean 未指定serialVersionUID ,导致反序列化失败. InvalidClassExceptions 。
## 如果没有声明serialVersionUID，JVM将使用自己的算法生成默认的SerialVersionUID，您可以在此处检查算法。
默认的serialVersionUID计算对类详细信息非常敏感，可能因不同的JVM实现而异，并且在反序列化过程中会导致意外的InvalidClassExceptions。
## SUN强烈建议开发人员声明serialVersionUID以避免上面列出的不同JVM问题

# 项目中导入功能性能优化  几分钟优化至10s内。
 ## Excel导入超时  
 ### 原因: 1.nginx设置默认超时为60s。 数据量大时，导入时间会很长，超过60s。
 ### 解决方案: 
    #### 1. 合理利用数据结构和算法， 优化数据校验。 避免查询数据库校验。
    #### 2. 优化更新操作，只有有内容变更的行数据，才会执行update操作。
    #### 3. 更新数据库操作改为批量操作。 手动提交、手动提交事务。 单次提交数据量据环境验证，选择较合适的值。
    #### 4. 新增数据按主键做个排序后，再执行insert操作。
    #### 5. 更新数据按主键做个排序后，再执行update操作，且where只用主键列。

# 图片上传 413 Request Entity Too Large
 ##  大图片上传报错  
 ### 原因: 上传文件请求body超过了nginx设置的上限。 client_max_body_size 10m 
 ### 解决方案: 
    ####  针对文件上传接口，单独设置 nginx中的 client_max_body_size 50m ， 重新nginx即可
  
