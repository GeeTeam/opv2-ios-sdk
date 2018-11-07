# Protocol

## GOPManagerDelegate

`GOPManager` 相关操作, 操作验证过程中的请求行为

### gtOnePass:errorHandler:

OnePass 失败回调, 返回网络层面或者业务层面的错误

**Declaration**

```objc
- (void)gtOnePass:(GOPManager *)manager errorHandler:(GOPError *)error;
```

**Parameters**

Param		|Description	
----------|------------	
manager 	|验证管理器
error     |错误对象

### gtOnePass:didReceiveDataToVerify:

处理 OnePass 校验

**Declaration**

```objc
- (void)gtOnePass:(GOPManager *)manager didReceiveDataToVerify:(NSDictionary *)data;
```

**Parameters**

Param		|Description	
----------|------------	
manager 	|验证管理器
data		|用于校验的参数

- 参数示例
	
```
{
    "accesscode" = "92b94bd3310c46ceb5bb8df9987c97e9", // 运营商token
    "accesscode_time" = "379", // 取token耗时
    "phone" = "cad76d7a25684f2d79aae1781a61ca67528c5ae05c714d6306862675a0aea37d", // 手机号（加密后）
    "process_id" = "9fa312ba0f622ee9dd638a515a5ed222", // 流水号
    "clienttype" = "0",
    "sdk" = "0.6.1",
}
```

# GOPManager

OnePass 的主要外部调用接口

## Property

### delegate

OnePass 代理

**Declaration**

```objc
@property (nonatomic, weak) id<GOPManagerDelegate> delegate;
```

### diagnosisStatus

诊断当前网络 OnePass 是否可用。如果可用返回 `YES` ,否则 `NO`。

**Declaration**

```objc
@property (nonatomic, readonly, assign) BOOL diagnosisStatus;
```

### currentPhoneNum

当前的手机号。如果加密, 返回加密后的。

**Declaration**

```objc
@property (nonatomic, readonly, copy) NSString *currentPhoneNum;
```

## Method

### initWithCustomID:timeout:

初始化并返回一个新的`GOPManager`实例对象

**Declaration**

```objc
- (instancetype)initWithCustomID:(NSString *)customID timeout:(NSTimeInterval)timeout;
```

**Parameters**

Param		|Description
----------|---------------	
customID 	|产品id, 请在官网注册获取
timeout	|本地各请求的超时时间

**Return Value**

一个新的 `GOPManager` 实例对象

### verifyPhoneNum:

开始 OnePass 验证

**Declaration**

```objc
- (void)verifyPhoneNumber:(NSString *)phoneNum;
```

**Parameters**

Param		|Description
----------|---------------	
phoneNum 	|手机号码, 11位字符串, 仅支持大陆三大运营商的手机号

**Discussion**

OnePass需要设备的数据网络支持。如果OnePass失败, 会使用短信进行补充当前的场景。极验提供默认的短信服务, 开发者也可通过接口关闭默认的短信行为, 切换为自己的短信系统。

目前仅支持大陆地区的手机号。SDK内部默认正则规则为 `'^1([3-9])\\d{9}$'`。
