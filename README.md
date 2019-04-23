# 阿里云Green内容安全扩展
PhalApi 2.x扩展类库，基于Aliyun的内容安全扩展。

## 安装和配置
修改项目下的composer.json文件，并添加：  
```
    "vivlong/phalapi-aliyun-green":"dev-master"
```
然后执行```composer update```。  

安装成功后，添加以下配置到/path/to/phalapi/config/app.php文件：  
```php
    /**
     * 阿里云Green相关配置
     */
    'AliyunGreen' =>  array(
        'accessKeyId'       => '<yourAccessKeyId>',
        'accessKeySecret'   => '<yourAccessKeySecret>',
        'regionId'          => 'cn-hangzhou',
    ),
```
并根据自己的情况修改填充。  

## 注册
在/path/to/phalapi/config/di.php文件中，注册：  
```php
$di->aliyunGreen = function() {
    return new \PhalApi\AliyunGreen\Lite();
};
```

## 使用
使用方式：
```php
  \PhalApi\DI()->aliyunGreen->textScan('测试内容');
```  

