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
