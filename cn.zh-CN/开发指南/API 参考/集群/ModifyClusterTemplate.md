# ModifyClusterTemplate {#concept_shb_s2y_dgb .concept}

修改集群模版参数以及示例。

## 请求参数 {#section_pdw_lv4_dgb .section}

|参数|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|BizId|String|是|CT-4A6799A79D73385B|集群模版 ID|
|ClusterType|String|是|HADOOP|集群类型|
|EmrVer|String|是|EMR-3.15.0|EMR 版本|
|RegionId|String|是|cn-hangzhou|区域|
|TemplateName|String|是|new\_template\_name|集群模版名|
|AccessKeyId|String|否|LTAI8ljWyu7y\*\*\*\*|AccessKeyId|
|AutoRenew|Boolean|否|false|包年包月集群是否自动续费|
|BootstrapAction.N.Arg|String|否|--a|引导操作参数|
|BootstrapAction.N.Name|String|否|action\_name|引导操作名|
|BootstrapAction.N.Path|String|否|oss://bucket/path|引导操作脚本路径|
|ChargeType|String|否|PostPaid|付费类型|
|Config.N.ConfigKey|String|否|fs.trash.interval|自定义配置项的 key|
|Config.N.ConfigValue|String|否|60|自定义配置项的值|
|Config.N.Encrypt|String|否|0|保留字段，无需设置|
|Config.N.FileName|String|否|yarn-site|自定义配置项所属文件名|
|Config.N.Replace|String|否|0|保留字段，无需设置|
|Config.N.ServiceName|String|否|YARN|自定义配置项服务名（大写）|
|Configurations|String|否|\[\{"classification": "core-site","properties": \{"fs.trash.interval": "61"\}\},\{"classification": "hadoop-log4j","properties": \{"hadoop.log.file": "hadoop1.log","hadoop.root.logger": "INFO","a.b.c": "ABC"\}\}\]|软件自定义配置。（集群启动前，可以指定一个 json 文件修改软件配置。）|
|DepositType|String|否|HALF\_MANAGED|托管类型|
|EasEnable|Boolean|否|true|是否高安全集群|
|HighAvailabilityEnable|Boolean|否|true|是否高可用集群|
|HostGroup.N.AutoRenew|Boolean|否|true|机器组机器是否自动续费|
|HostGroup.N.ChargeType|String|否|PostPaid|付费方式|
|HostGroup.N.ClusterId|String|否|0|保留字段|
|HostGroup.N.Comment|String|否|comment|保留字段|
|HostGroup.N.CreateType|String|否|ON\_DEMAND|保留字段|
|HostGroup.N.DiskCapacity|Integer|否|80|机器组的数据盘容量|
|HostGroup.N.DiskCount|Integer|否|4|机器组的数据盘数量|
|HostGroup.N.DiskType|String|否|CLOUD\_SSD|机器组的数据盘类型|
|HostGroup.N.HostGroupId|String|否|0|保留字段|
|HostGroup.N.HostGroupName|String|否|主实例组|机器组名字|
|HostGroup.N.HostGroupType|String|否|MASTER|机器组类型|
|HostGroup.N.InstanceType|String|否|ecs.mn4.2xlarge|机器组型号|
|HostGroup.N.MultiInstanceTypes|String|否|ecs.sn1.xlarge,ecs.sn2.xlarge|多规格机器型号列表，逗号隔开|
|HostGroup.N.NodeCount|Integer|否|4|机器组节点数|
|HostGroup.N.Period|Integer|否|36|包年包月时间（天）|
|HostGroup.N.SysDiskCapacity|Integer|否|80|机器组的系统盘容量|
|HostGroup.N.SysDiskType|String|否|CLOUD\_SSD|机器组的系统盘类型|
|HostGroup.N.VSwitchId|String|否|vsw-bp10tvjyc77psy0z5h0ni|交换机 ID|
|InitCustomHiveMetaDb|Boolean|否|false|保留字段，无需填写|
|InstanceGeneration|String|否|ecs-3|ECS 实例分代|
|IoOptimized|Boolean|否|true|是否 IO 优化|
|IsOpenPublicIp|Boolean|否|true|是否使用公网 IP|
|LogPath|String|否|oss//bucketname/path|OSS 日志路径|
|MachineType|String|否|ECS|机器类型|
|MasterPwd|String|否|pwd|Master 节点SSH 访问密码|
|NetType|String|否|vpc|网络类型|
|OptionSoftWareList|RepeatList|否|\["ZOOKEEPER","LIVY"\]|可选软件列表|
|Period|Integer|否|36|包年包月时间（天）|
|SecurityGroupId|String|否|sg-bp1id7ajv83kmqwq2isx|安全组 ID|
|SecurityGroupName|String|否|emr\_sg|安全组名字|
|SshEnable|Boolean|否|true|是否打开 SSH 访问|
|UseCustomHiveMetaDb|Boolean|否|false|false|
|UseLocalMetaDb|Boolean|否|true|是否使用本地 Hive 元数据库|
|UserDefinedEmrEcsRole|String|否|AliyunEmrEcsDefaultRole|用于 ECS 调用的 EMR 权限名|
|VSwitchId|String|否|vsw-bp10tvjyc77psy0z5h0ni|交换机 ID|
|VpcId|String|否|vpc-bp1l4urd87xlh7i4bju4h|VPC ID|
|ZoneId|String|否|cn-hangzhou-b|区域 ID|

## 返回参数 {#section_vdw_lv4_dgb .section}

|字段|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|BF4FBAC6-B03E-4BFB-B6DB-EB53C34F2E22|请求 ID|
|ClusterTemplateId|String|CT-4A6799A79D73385B|集群模版 ID|

## 示例 {#section_ydw_lv4_dgb .section}

-   请求示例

    ```
    /?BizId=CT-4A6799A79D73385B
    &ClusterType=HADOOP
    &EmrVer=EMR-3.15.0
    &RegionId=cn-hangzhou
    &TemplateName=new_template_name
    &AccessKeyId=LTAI8ljWyu7y****
    &AutoRenew=false
    &ChargeType=PostPaid
    &Configurations=
    &DepositType=HALF_MANAGED
    &EasEnable=true
    &HighAvailabilityEnable=true
    &InitCustomHiveMetaDb=
    &InstanceGeneration=
    &IoOptimized=true
    &IsOpenPublicIp=true
    &LogPath=oss//bucketname/path
    &MachineType=ECS
    &MasterPwd=pwd
    &NetType=vpc
    &OptionSoftWareList.1=["ZOOKEEPER","LIVY"]
    &Period=36
    &SecurityGroupId=sg-bp1id7ajv83kmqwq2isx
    &SecurityGroupName=emr_sg
    &SshEnable=true
    &UseCustomHiveMetaDb=
    &UseLocalMetaDb=true
    &UserDefinedEmrEcsRole=AliyunEmrEcsDefaultRole
    &VpcId=vpc-bp1l4urd87xlh7i4bju4h
    &VSwitchId=vsw-bp10tvjyc77psy0z5h0ni
    &ZoneId=cn-hangzhou-b
    &BootstrapAction.1.Arg=
    &BootstrapAction.1.1ame=
    &BootstrapAction.1.Path=
    &Config.1.ConfigKey=
    &Config.1.ConfigValue=
    &Config.1.Encrypt=
    &Config.1.FileName=
    &Config.1.Replace=
    &Config.1.ServiceName=
    &HostGroup.1.AutoRenew=true
    &HostGroup.1.ChargeType=PostPaid
    &HostGroup.1.ClusterId=
    &HostGroup.1.Comment=
    &HostGroup.1.CreateType=
    &HostGroup.1.DiskCapacity=80
    &HostGroup.1.DiskCount=4
    &HostGroup.1.DiskType=CLOUD_SSD
    &HostGroup.1.HostGroupId=
    &HostGroup.1.HostGroupName=主实例组
    &HostGroup.1.HostGroupType=MASTER
    &HostGroup.1.InstanceType=ecs.mn4.2xlarge
    &HostGroup.1.MultiInstanceTypes=
    &HostGroup.1.1odeCount=4
    &HostGroup.1.Period=36
    &HostGroup.1.SysDiskCapacity=80
    &HostGroup.1.SysDiskType=CLOUD_SSD
    &HostGroup.1.VSwitchId=vsw-bp10tvjyc77psy0z5h0ni
    &<公共请求参数>
    ```

-   正常返回示例

    JSON 格式

    ```
    {
    	"RequestId":"5EDD1207-5DAB-42F9-9BF9-7591286A8F3F"
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


## 错误码 {#section_a2w_lv4_dgb .section}

[查看本产品错误码](https://error-center.alibabacloud.com/status/product/Emr)

