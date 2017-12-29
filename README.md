# 交互

* *打开文件*</br>
    **方法名** openFile
    
    参数名|说明
    -|-
    type|类型 1 2
    fileName| 类型为1 是文件名,2是本地路径

    **返回**</br>
        无

* *检查文件是否存在* </br>
    **方法名** checkFile

    参数名|说明
    -|-
    fileName| 文件名

    **返回**

    参数名|说明
    -|-
    status| boolean  存在 true 不存在 false
    path| 存在需要返回

* *下载文件* </br>
    **方法名** downloadFile

    参数名|说明
    -|-
    filePath |七牛地址
    name|  存储的文件名
    funcName| 回调触发的方法名

    **返回**

    参数名|说明
    -|-
    type  |下载中为0  下载完成为1
    progress|   百分比数字
    status|  true

* *选择联系人*</br>
    **方法名** selectMan

    参数名|说明
    -|-
    num | 最大选择人数 为1时是单选模式
    title|  标题

    **返回**</br>
    返回一个JSON数组 [{用户信息}]

* *获取登录用户的个人信息*</br>
    **方法名** queryMy

    参数名|说明
    -|-
    无|无

    **返回** </br>
    返回用户信息JSON类型对象

* *获取某用户信息*</br>
    **方法名** queryUser

    参数名|说明
    -|-
    userId|查询用户的ID

    **返回**</br>
    返回用户信息JSON类型对象

* *添加文件*</br>
    **方法名** addFile

    参数名|说明
    -|-
    无|无

    **返回**

    参数名|说明
    -|-
    status | true or false
    data| **数组**形式,参数如下:</br> name 名字 </br> fileName 七牛路径 </br> fileSize 文件大小 </br> path 文件本地路径

* *添加图片*</br>
    **方法名** 添加图片

    参数名|说明
    -|-
    无|无

    **返回**

    参数名|说明
    -|-
    status | true or false
    data| **数组**形式,参数如下:</br> name 名字 </br> fileName 七牛路径 </br> fileSize 文件大小 </br> path 文件本地路径

* *关闭webView*</br>
    **方法名** finishActivity

    参数名|说明
    -|-
    无|无

    **返回**

    参数名|说明
    -|-
    无|无

## Native调用JS的方法

* *物理回退键(Android)*</br>
    **方法名** backBtnFunc

    参数名|说明
    -|-
    无|无

    **返回**</br>
    返回true则关闭webView

* *跳转到任务或审批页面*</br>
    **方法名** toPage</br>
    **说明** 传 1 跳转到审批页，传2 跳转到任务页