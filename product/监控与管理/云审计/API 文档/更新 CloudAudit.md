# 更新 CloudAudit
## 接口描述
UpdateAudit 用于更新云审计（CloudAudit）。
> **注意：**  
> 更新指定日志文件传递的设置。对路径的更改不需要停止 CloudAudit 服务。使用此操作指定用于日志传送的现有存储桶。如果现有的存储桶以前是 CloudAudit 日志文件的目标，则可以更改成功。否则需要手动授权 COS 存储桶，使得 CloudAudit 具有写权限才行。CloudAudit 的名称是不能修改的。


## 请求参数
以下请求参数列表仅列出了接口请求参数。

|参数名称|必选|类型|描述|
|---------|---------|---------|--------|
|IsMultiRegionAudit	|否|	number	|是否开启多地域采集(0 不开启，1 开启)|
|KmsKeyId	|否|	string	| KMS 的 scretId 用于数据加密|
|Name	|是|	string	|CloudAudit 的名字，3-128 字节，只能包含 ASCII 编码字母（a-z,A-Z），数字（0-9），下划线（_）|
|CosBucketName	|是|	string	|要投递的 COSBUCKET 的名称（命名规范参照 COS 的命名要求）|
|CosKeyPrefix	|否|	string	|cos 存储桶的前缀（命名规范参照 COS）|
|CmqTopicName	|否|	string	|Cmq 的名字，如果开启消息队列请填写（命名规范参照 CMQ 要求）|


## 实际案例
### 请求

```
{
   "IsMultiRegionTrail": number,
   "KmsKeyId": "string",
   "Name": "string",
   "CosBucketName": "string",
   "CosKeyPrefix": "string",
   "CosTopicName": "string"
}
```
### 响应

```
{
   "IsMultiRegionTrail": number,
   "KmsKeyId": "string",
   "Name": "string",
   "CosBucketName": "string",
   "CosKeyPrefix": "string",
   "CmqTopicResource": "string",
   "CmqTopicName": "string",
}
```

