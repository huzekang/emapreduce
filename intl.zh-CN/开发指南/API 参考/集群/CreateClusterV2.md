# CreateClusterV2 {#concept_ahy_wy1_kfb .concept}

调用 CreateClusterV2 接口创建一个 E-MapReduce 集群

## 请求参数 {#section_wbp_dz1_kfb .section}

|字段|类型|是否必须|示例值|描述|
|--|--|----|---|--|
|ClusterType|String|是|HADOOP|集群类型|
|EmrVer|String|是|EMR-3.15.0|EMR 版本|
|Name|String|是|bi\_hadoop|集群的名字。长度限制为 1-64 个字符，只允许包含中文、字母、数字、-、\_。|
|RegionId|String|是|cn-hangzhou|区域 ID。目前支持华东 1，华东 2，华南 1，华北 2，华北 3，美西，新加坡，德国|
|ZoneId|String|是|cn-hangzhou-e|可用区 ID。华东 1（杭州）支持：cn-hangzhou-b。 华北 2（北京）支持：cn-beijing-a,cn-beijing-b,cn-beijing-c|
|AccessKeyId|String|是|LTAI8ljWyu7y\*\*\*\*|AccessKeyId|
|AuthorizeContent|String|否|0|暂时无需填写|
|AutoRenew|Boolean|否|false|包年包月集群是否自动续费|
|BootstrapAction.N.Arg|String|否|--a=b|引导操作参数|
|BootstrapAction.N.Name|String|否|name|引导操作名字|
|BootstrapAction.N.Path|String|否|oss://bucket/path|引导操作脚本路径|
|Config.N.ConfigKey|String|否|fs.trash.interval|自定义配置项的 key|
|Config.N.ConfigValue|String|否|60|自定义配置项的值|
|Config.N.Encrypt|String|否|0|保留字段|
|Config.N.FileName|String|否|yarn-site|自定义配置项所属文件名|
|Config.N.Replace|String|否|0|保留字段|
|Config.N.ServiceName|String|否|YARN|自定义配置项服务名（大写）|
|DepositType|String|否|HALF\_MANAGED|托管类型|
|EasEnable|Boolean|否|false|是否高安全集群|
|HighAvailabilityEnable|Boolean|否|false|是否高可用集群，用，若开启高可用，需要 2 台 Master 节点|
|HostGroup.N.AutoRenew|Boolean|否|false|机器组机器是否自动续费|
|HostGroup.N.ChargeType|String|是|PostPaid|机器组机器付费类型|
|HostGroup.N.ClusterId|String|否|0|保留字段，无需填写|
|HostGroup.N.Comment|String|否|0|保留字段，无需填写|
|HostGroup.N.CreateType|String|否|0|保留字段，无需填写|
|HostGroup.N.DiskCapacity|Integer|是|80|机器组的数据盘容量|
|HostGroup.N.DiskCount|Integer|是|4|机器组的数据盘数量|
|HostGroup.N.DiskType|String|是|CLOUD\_SSD|机器组的数据盘类型|
|HostGroup.N.GpuDriver|String|否|cuda9|GPU 驱动|
|HostGroup.N.HostGroupId|String|否|0|保留字段|
|HostGroup.N.HostGroupName|String|是|主实例组|机器组名字|
|HostGroup.N.HostGroupType|String|是|MASTER|机器组类型，枚举值：MASTER、CORE、TASK。目前MASTER 和CORE 均只支持设置一个组。|
|HostGroup.N.InstanceType|String|是|ecs.mn4.2xlarge|机器组型号|
|HostGroup.N.NodeCount|Integer|是|1|机器组节点数|
|HostGroup.N.Period|Integer|否|1|包年包月时间（月，1，2，3，4，5，6，7，8，9，12，24，36），HostGroup.n.ChargeType=PrePaid 时，必填。|
|HostGroup.N.SysDiskCapacity|Integer|是|80|机器组的系统盘容量|
|HostGroup.N.SysDiskType|String|是|CLOUD\_SSD|机器组的系统盘类型|
|HostGroup.N.VSwitchId|String|否|vsw-bp10tvjyc77psy0z5\*\*\*\*|虚拟交换机 ID，NetType=vpc 时，必填。|
|InitCustomHiveMetaDB|Boolean|否|false|保留字段，无需填写|
|InstanceGeneration|String|否|ecs-3|ECS 实例分代|
|IoOptimized|Boolean|否|true|是否开启 IO 优化，默认 true|
|IsOpenPublicIp|Boolean|否|true|是否开启公网 IP。若开启，默认会带有 8 MB 的带宽。|
|KeyPairName|String|否|test\_pair|密钥对|
|LogPath|String|否|oss//bucketname/path|OSS 日志路径|
|MachineType|String|否|ECS|机器类型|
|OptionSoftWareList.N|RepeatList|否|\["ZOOKEEPER","LIVY"\]|可选软件列表|
|SecurityGroupId|String|否|sg-bp1id7ajv83kmqwq\*\*\*\*|安全组 ID。可以在 ECS 中创建一个然后使用。需要确认的是，若使用已有的安全组，会被增加上默认安全组策略：入只开放 22 端口，出开放所有端口。SecurityGroupId 和 SecurityGroupName 必须选填一个。|
|SecurityGroupName|String|否|emr-sg|需要新建的安全组名称。如果不指定安全组 ID，那么将使用这个名字创建一个新的安全组。当集群创建完成以后，可以在集群详情中看到创建的安全组 ID。这个安全组将会有带有默认的安全组策略：入只开放 22 端口，出开放所有端口。SecurityGroupId 和 SecurityGroupName 必须选填一个。|
|SshEnable|Boolean|否|false|是否开启 SSH|
|UseCustomHiveMetaDB|Boolean|否|false|保留字段，无需填写|
|UseLocalMetaDb|Boolean|否|true|是否使用本地 Hive 元数据库|
|UserDefinedEmrEcsRole|String|否|AliyunEmrEcsDefaultRole|用于 ECS 调用的 EMR 权限名|
|UserInfo.N.Password|String|否|pwd|集群密码|
|UserInfo.N.UserId|String|否|12345|knox 账号的 aliyun 用户 ID|
|UserInfo.N.UserName|String|否|tom|knox 账号用户名|
|MasterPwd|String|否|pwd|Master 节点 SSH 访问密码。需要满足 ECS 的密码规则：8 - 30 个字符，且同时包含任意三项（大、小写字母，数字和特殊符号）|
|ChargeType|String|是|PostPaid|付费类型，PostPaid：按量付费，PrePaid：包年包月|
|Period|Integer|否|1|包年包月时间（月，1，2，3，4，5，6，7，8，9，12，24，36），ChargeType=PrePaid 时，必填。|
|RelatedClusterId|String|否|C-D7958B72E59B\*\*\*\*|当前集群是 gateway 时，其关联的主集群 ID|
|Configurations|String|否|0|无需填写|
|VpcId|String|否|vpc-bp1l4urd87xlh7i4b\*\*\*\*|Vpc ID，NetType=vpc 时，必填。|
|VSwitchId|String|否|vsw-bp10tvjyc77psy0z5\*\*\*\*|交换机 ID，NetType=vpc 时，必填。|
|WhiteListType|String|否|""|暂时无需填写|
|NetType|String|是|vpc|网络类型|

## 返回参数 {#section_xxl_hz1_kfb .section}

|字段|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BF4FBAC6-B03E-4BFB-B6DB-EB53C34F2E22|请求 ID|
|ClusterId|String|C-D7958B72E59BAB88|集群 ID|

## 示例 {#section_yr3_jz1_kfb .section}

-   请求示例

    ```
    /?ClusterType=HADOOP
    &EmrVer=EMR-3.15.0
    &Name=bi_hadoop
    &RegionId=cn-hangzhou
    &AccessKeyId=LTAI8ljWyu7y****
    &AutoRenew=false
    &ChargeType=PostPaid
    &DepositType=HALF_MANAGED
    &HighAvailabilityEnable=true
    &InstanceGeneration=ecs-3
    &IoOptimized=true
    &IsOpenPublicIp=true
    &KeyPairName=
    &LogPath=oss//bucketname/path
    &MachineType=ECS
    &MasterPwd=pwd
    &NetType=vpc
    &OptionSoftWareList.1=["ZOOKEEPER","LIVY"]
    &Period=30
    &SecurityGroupId=sg-bp1id7ajv83kmqwq****
    &SecurityGroupName=emr-sg
    &SshEnable=
    &UseLocalMetaDb=
    &UserDefinedEmrEcsRole=AliyunEmrEcsDefaultRole
    &VpcId=vpc-bp1l4urd87xlh7i4b****
    &VSwitchId=vsw-bp10tvjyc77psy0z5****
    &ZoneId=cn-hangzhou-e
    &BootstrapAction.1.Arg=--a=b
    &BootstrapAction.1.1ame=name
    &BootstrapAction.1.Path=oss://bucket/path
    &Config.1.ConfigKey=
    &Config.1.ConfigValue=
    &Config.1.Encrypt=
    &Config.1.FileName=
    &Config.1.Replace=
    &Config.1.ServiceName=
    &HostGroup.1.AutoRenew=false
    &HostGroup.1.ChargeType=PostPaid
    &HostGroup.1.ClusterId=
    &HostGroup.1.Comment=
    &HostGroup.1.CreateType=
    &HostGroup.1.DiskCapacity=80
    &HostGroup.1.DiskCount=4
    &HostGroup.1.DiskType=CLOUD_SSD
    &HostGroup.1.GpuDriver=
    &HostGroup.1.HostGroupId=
    &HostGroup.1.HostGroupName=主实例组
    &HostGroup.1.HostGroupType=MASTER
    &HostGroup.1.InstanceType=ecs.mn4.2xlarge
    &HostGroup.1.1odeCount=1
    &HostGroup.1.Period=30
    &HostGroup.1.SysDiskCapacity=80
    &HostGroup.1.SysDiskType=CLOUD_SSD
    &HostGroup.1.VSwitchId=vsw-bp10tvjyc77psy0z5****
    &UserInfo.1.Password=pwd
    &UserInfo.1.UserId=12345
    &UserInfo.1.UserName=
    &AuthorizeContent=
    &Configurations=
    &EasEnable=false
    &InitCustomHiveMetaDB=
    &RelatedClusterId=
    &UseCustomHiveMetaDB=
    &WhiteListType=
    &<公共请求参数>
    ```

-   正常返回示例

    JSON 格式

    ```
    {
    	"ClusterId":"C-4DE6DA872B0E0D58",
    	"RequestId":"F4DE89FB-7054-475C-B7E2-B9A38152DA7E"
    }
    ```

-   异常返回示例

    JSON 格式

    ```
    {
    	"code":"RAM.Permission.NotAllow",
    	"message":"It is not allow to execute this operation,please use RAM to authorize!",
    	"requestId":"9AEDC439-1F63-491D-B8C6-9737C372BF3A",
    	"successResponse":false
    }
    ```


## 错误码 {#section_img_my5_cgb .section}

[查看本产品错误码](https://error-center.alibabacloud.com/status/product/Emr)

