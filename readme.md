[![Latest Stable Version](https://poser.pugx.org/zoujingli/think-library/v/stable)](https://packagist.org/packages/zoujingli/think-library) 
[![Latest Unstable Version](https://poser.pugx.org/zoujingli/think-library/v/unstable)](https://packagist.org/packages/zoujingli/think-library) 
[![Total Downloads](https://poser.pugx.org/zoujingli/think-library/downloads)](https://packagist.org/packages/zoujingli/think-library) 
[![License](https://poser.pugx.org/zoujingli/think-library/license)](https://packagist.org/packages/zoujingli/think-library)

# ThinkLibrary for ThinkPHP5.1
ThinkLibrary 是针对ThinkPHP5.1版本封装的一套工具类库，方便快速构建WEB应用。

## ThinkLibrary 使用
控制器需要继续 `library\Controller`，然后`$this`就可能使用全部功能。
```php
// 定义 MyController 控制器
class MyController extend \library\Controller{
    
    // 显示数据列表
    public function index(){
    
        return $this->_page('MyTableName');
        
    }
    
}
```

## 列表处理
```php
// 列表展示
return $this->_page($dbQuery, $isPage, $isDisplay, $total);
```

## 表单处理
```php
// 表单显示及数据更新
return $this->_form($dbQuery, $tplFile, $pkField , $where, $data);
```

## 文件存储
```php
// 保存内容到文件
\library\File::save($filename,$content);

// 获取文件内容
\library\File::get($filename)

// 生成文件名称
\library\File::name($url,$ext,$prv,$fun);

//指定存储类型，调用方法
\library\File::instance('oss')->save($filename,$content);
\library\File::instance('local')->save($filename,$content);
\library\File::instance('qiuniu')->save($filename,$content);

\library\File::instance('oss')->get($filename);
\library\File::instance('local')->get($filename);
\library\File::instance('qiuniu')->get($filename);
```