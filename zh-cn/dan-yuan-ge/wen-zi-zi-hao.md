# 文字字号

## **函数原型**

```php
fontSize(double $size);
```

### **double $size**

> 单元格字体大小

## 示例

```php
$config = [
    'path' => './tests'
];

$fileObject = new \Vtiful\Kernel\Excel($config);
$fileObject = $fileObject->fileName('tutorial.xlsx');
$fileHandle = $fileObject->getHandle();

$format = new \Vtiful\Kernel\Format($fileHandle);
$style  = $format->fontSize(30)->toResource();

$filePath = $fileObject->header(['name', 'age'])
    ->data([
        ['viest', 21],
        ['wjx',   21]
    ])
    ->setRow('A1', 50, $style)
    ->setRow('A2:A3', 50, $style)
    ->output();

var_dump($filePath);
```

