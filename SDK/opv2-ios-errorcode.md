# ErrorCode

## OnePass

`OnePass`产品的业务错误代码

ErrorCode	|Description	
----------|------------	
-20301 | `GOPErrorInvalidPhoneNumber` 手机号码不可用
-20302 | `GOPErrorUnsupportedNetwork` 网络不支持
-20303 | `OPErrorUnsupportedOperator` 运营商不支持
-20304 | `GOPErrorEmptyOperatorURL` 服务端返回运营商URL为空
-39900 | `GOPErrorGenericNetworkError` 网络错误，原始错误见userInfo 中的 GOPErrorOriginalErrorKey
-39901 | `GOPErrorSocketError` Socket 错误
-39902 | `GOPErrorReceiveEmptyDataError` 服务器返回数据为空
-40101 | `GOPErrorCMGetTokenFail` 移动获取 token 失败
-40104 | `GOPErrorCMUnsupportedNetwork` 移动不支持的网络
-40201 | `GOPErrorCUGetTokenFail` 联通获取 token 失败
-40204 | `GOPErrorCUUnsupportedNetwork` 联通不支持的网络
-40301 | `GOPErrorCTGetTokenFail` 电信获取 token 失败
-40302 | `GOPErrorCTResultParseError` 电信返回结果解析失败
-40304 | `GOPErrorCTUnsupportedNetwork` 电信不支持的网络
-49900 | `GOPErrorOperatorUnknownError` 未知的运营商错误
-50100 | `GOPErrorInvalidPreGatewayReturns` pregateway 返回结果有误

## Cocoa Error

可能遇见的有

### NSURLErrorDomain

ErrorCode	|Description	
----------|------------	
-999		|`NSURLErrorCancelled`用户操作导致的请求中断, 一般忽略处理
-1000		|`NSURLErrorBadURL`URL异常
-1001 		|`NSURLErrorTimedOut`请求超时	
-1002		|`NSURLErrorUnsupportedURL `不支持的URL
-1003		|`NSURLErrorCannotFindHost `无法找到主机
-1004		|`NSURLErrorCannotConnectToHost `无法连接到服务器
-1005		|`NSURLErrorNetworkConnectionLost `网络丢失, 一般弱网或者网络突然中断导致
-1006		|`NSURLErrorDNSLookupFailed `DNS查询失败
-1007		|`NSURLErrorHTTPTooManyRedirects `过多的请求跳转, 服务器返回过多的302
-1008		|`NSURLErrorResourceUnavailable `访问的资源不可用
-1009		|`NSURLErrorNotConnectedToInternet `未连接到互联网
-1010		|`NSURLErrorRedirectToNonExistentLocation `重定向到不存在的地址
-1011		|`NSURLErrorBadServerResponse `服务器无响应
-1012		|`NSURLErrorUserCancelledAuthentication `客户端取消了安全认证, 或者证书不匹配或服务端不支持ssl和tls
-1013		|`NSURLErrorUserAuthenticationRequired `客户端要求安全认证, 服务端不支持ssl或tls
-1014		|`NSURLErrorZeroByteResource `返回字节流为空
-1015		|`NSURLErrorCannotDecodeRawData `无法解析的原始数据
-1016		|`NSURLErrorCannotDecodeContentData `解析返回内容错误
-1017		|`NSURLErrorCannotParseResponse `无法解析响应体
-1102		|`NSURLErrorNoPermissionsToReadFile `无资源访问权限, 一般为`challenge`等参数有误, `challenge`只可被用来请求一次, 失效后可能会遇到该问题
-1200		|`NSURLErrorSecureConnectionFailed `创建安全连接失败
-1201		|`NSURLErrorServerCertificateHasBadDate `服务端证书异常
-1202		|`NSURLErrorServerCertificateUntrusted `服务端证书不可信
-1203		|`NSURLErrorServerCertificateHasUnknownRoot `服务端使用未知的根证书

>更多详情请访问[URL Loading System Error Codes](https://developer.apple.com/documentation/foundation/1508628-url_loading_system_error_codes)文档及相关苹果官方文档