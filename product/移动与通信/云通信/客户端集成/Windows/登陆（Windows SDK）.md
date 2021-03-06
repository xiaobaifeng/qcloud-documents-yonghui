## 1. 登录

用户登录腾讯后台服务器后才能正常收发消息，登录需要用户提供accountType、identifier、userSig等信息，具体含义可参阅帐号文档。

>注意：如果此用户在其他终端被踢，登录将会失败，返回错误码（ERR_IMSDK_KICKED_BY_OTHERS：6208）。开发者必须进行登录错误码ERR_IMSDK_KICKED_BY_OTHERS的判断。关于被踢的详细描述，参见上一篇《初始化》中第6小节“用户状态变更”。

如果用户保存用户票据，可能会存在过期的情况，如果用户票据过期，login将会返回 70001 错误码，开发者可根据错误码进行票据更换。

登录为异步过程，通过回调函数返回是否成功，成功后方能进行后续操作。登录成功或者失败后，有两种回调方式，一种使用闭包，succ和fail两种闭包回调，另一种使用protocol，用户实现TIMCallback接口进行回调。

**注意：只要登录成功以后，用户没有主动登出或者被踢，网络变更会自动重连，无需开发者关心。不过特别需要注意被踢操作，需要注册[用户状态变更回调](/document/product/269/1581#6.-.E7.94.A8.E6.88.B7.E7.8A.B6.E6.80.81.E5.8F.98.E6.9B.B4-.EF.BC.88.E4.BA.92.E8.B8.A2.EF.BC.89)，否则被踢时得不到通知。**

**原型：**
```
int TIMLogin(int sdk_app_id, const TIMUserInfo *tim_user, const char* user_sig, TIMCommCB *callback);
```

**参数说明：**
sdk_app_id - 用于标识接入sdk的应用id
tim_user - 用户账号, 必须填写account_typeidentifierapp_id_at_3rd
user_sig - 用户key
callback - 回调接口

在自有帐号情况下：appidAt3rd字段与sdkAppId相同，其他字段sdkAppId、accountType、identifier、userSig填写相应内容。

**示例：  **
```
void CBCommOnSuccessImp(void* data)
{
    printf("Success\n");
}
 
void CBCommOnErrorImp(int code, const char* desc, void* data)
{
    printf("Error! code = <%d> desc = <%s>", code, desc);
}
 
void Login()
{
    int sdk_app_id = 1104620500;
    TIMUserInfo user;
    user.account_type = "107";
    user.app_id_at_3rd = "1104620500";
    user.identifier = "c9_2";
    const char* user_sig = "pass_word";
 
    TIMCommCB callback;
    callback.OnSuccess = CBCommOnSuccessImp;
    callback.OnError = CBCommOnErrorImp;
    TIMLogin(sdk_app_id, &user, user_sig, &callback);
    SLEEP(1);
}
```

## 2 登出
如用户主动注销或需要进行用户的切换，则需要调用注销操作：

**原型：**
void TIMLogout(TIMCommCB *callback);

**示例：**
```
//注销登录
void Logout()
{
    TIMCommCB callback;
    callback.OnSuccess = CBCommOnSuccessImp;
    callback.OnError = CBCommOnErrorImp;
    TIMLogout(&callback);
    SLEEP(1);
}
```

**注意：**在需要切换帐号时，需要logout回调成功或者失败后才能再次login，否则login可能会失败。
