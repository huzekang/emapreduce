# Step 2 : Prerequisites {#concept_cms_hxn_y2b .concept}

Make sure that the following prerequisites are met before you create an E-MapReduce cluster:

1.  Create an Alibaba Cloud account

    To create an E-MapReduce cluster, you must have an Alibaba Cloud account, which is used to uniquely identify you in the Alibaba Cloud ecosystem. You can use this account to create E-MapReduce clusters and activate other Alibaba Cloud services, including [Object Storage Service \(OSS\)](https://www.alibabacloud.com/product/oss) and [ApsaraDB for RDS \(RDS\)](https://www.alibabacloud.com/product/rds).

    For more information about creating an Alibaba Cloud account, see [Sign up with Alibaba Cloud](https://partners-intl.aliyun.com/help/doc-detail/50482.htm).

2.  Create an AccessKey \(optional\)

    To use E-MapReduce, you must create a minimum of one AccessKey. Follow these steps to create an AccessKey:

    1.  Log on to the [Alibaba Cloud website](https://partners-intl.aliyun.com/login-required).

    2.  Go to the Alibaba Cloud console.
    3.  Hover over your profile picture and then click **AccessKeys**.

        **Note:** If the following dialog box appears, click **Continue to manage AccessKey**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17837/155927274510452_en-US.png)

    4.  Click **Create AccessKey**.
    5.  The AccessKey has been created.
3.  Authorize default system role to the E-MapReduce service account.

    When you activate the E-MapReduce service, a default system role named AliyunEMRDefaultRole must be granted to the E-MapReduce service account. Once assigned, E-MapReduce can call the relevant services \(such as ECS and OSS\), create clusters, save logs, and perform other related tasks.For more information, see [Role authorization](../../../../reseller.en-US/Cluster Planning and Configurations/Cluster planning/Role authorization.md#).

4.  Activate Alibaba Cloud OSS

    E-MapReduce stores job and execution logs on Alibaba Cloud OSS. Therefore, you must activate Alibaba Cloud OSS. For more information, see [Sign up for OSS](https://partners-intl.aliyun.com/help/doc-detail/31884.htm?). Create OSS buckets in the same region as the EMR cluster that you need to create. For more information, see [Create a bucket](https://partners-intl.aliyun.com/help/doc-detail/31885.htm?).

5.  Create high-configuration instances \(optional\)

    If you need to create instances with eight or more cores for a Pay-As-You-Go-based cluster, log on to your Alibaba Cloud account and submit a ticket for application. For more information, see [Support and Services](https://workorder.console.aliyun.com/console.htm).


