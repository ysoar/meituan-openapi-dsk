# PHP SDK 接入指南 & CHANGELOG

## 仿照饿了么openApi编写

## 接入指南

  1. PHP version >= 5.4 & curl extension support
  2. 通过composer安装SDK
  3. 创建Config配置类，填入开发者ID, 业务类型ID， signKey和sandbox参数
  4. 使用sdk提供的接口进行开发调试
  5. 上线前将Config中$sandbox值设为false以及填入正式环境的signkey

## 安装方法
composer require ysoar/meituan-openapi:dev-master
  
### 基本用法

```php
    use MeituanOpenApi\Config\Config;
    use MeituanOpenApi\Api\TakeAway\ProductService;
    
    //实例化一个配置类
    $config = new Config($this->developerId, $this->businessId, $this->signKey, false);
    
    //使用config和token对象，实例化一个服务对象
    $productService = new ProductService($token, $config);
    
    //调用服务方法，获取资源
    $cateList = $productService->queryCateList(12345);

```



