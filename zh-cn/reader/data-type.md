# 按数据类型读取文件

* 读取文件暂不支持 `windows` 系统；
* 扩展版本大于等于 `1.2.7`；

## 编译

编译时需添加 `--enable-reader`

```bash
./configure --enable-reader
```

## 示例

```bash
$config   = ['path' => './tests'];
$excel    = new \Vtiful\Kernel\Excel($config);

$filePath = $excel->fileName('tutorial.xlsx')
    ->header(['Item', 'Cost'])
    ->output();

$excel->openFile('tutorial.xlsx')
    ->openSheet();

// 读取每行单元格数据时，可指定每个单元格数据类型进行读取
var_dump($excel->nextRow([
    \Vtiful\Kernel\Excel::TYPE_STRING, \Vtiful\Kernel\Excel::TYPE_STRING
]));
```

