# 敏感词过滤

## 安装
```php
composer require quansitech/qs-sensitive
```

## 用法
```php
$sensitive = new Senstive();
$txt = "你是不是傻&吊。。。";
$words = $sensitive->filter($txt);

echo $words; // 你是不是***。。。
```

自定义干扰因子和敏感词库
```php
$disturbList = ['!', '(', ')'];
$words = './words.txt';
$sensitive = new Senstive($disturbList, $words);
$txt = "你是不是傻(!)吊。。。";
$words = $sensitive->filter($txt);

echo $words; //你是不是*****。。。
```
