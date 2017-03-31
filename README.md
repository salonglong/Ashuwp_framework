# Ashuwp_framework
##简介

Ashuwp_framework是由阿树工作室发布的一个wordpress后台框架。

最新版本 5.0
更新日期 2017.03.31

使用本框架的要求：你需要具备基础的php语法知识，以及对wordpress主题有基本的了解。

##本框架的功能

* 给wordpress文章添加自定义字段
    * 支持自定义文章类型
* 给wordpress主题后台添加设置页面
    * 支持多个顶级页面及子页面
    * 支持设置选项的导入导出
* 给wordpress的分类添加自定义字段
    * 支持tag等自定义分类法
    
##使用方法

1. 将ashuwp_framework整个文件夹复制到主题中。
2. 将add-functions.php文件的两句加载框架范例代码复制到主题的functions.php文件中。
3. 根据实际需求编辑配置数据。
4. 完成了，去后台看看。


##帮助支持

* [查阅Ashuwp_framework帮助文档](http://www.ashuwp.com/framework/down)
* 邮箱：admin@ashuwp.com

##Introductions

Ashuwp_framework is a framework for wordpress theme, Help developers to add options page/post metabox/term metabox for wordpress theme quickly and easily.

##Usage

1. Upload the folder ashuwp_framework into your theme.
2. Copy the code in add-functions.php into your functions.php.
3. OK,the framework worked.
4. Edit the ashuwp_framework/config-example.php.

##Help

* DOC: (http://www.ashuwp.com/framework/down)
* Email：admin@ashuwp.com


##配置数据

添加文章自定义字段
```php
$meta_conf = array(
  'title' => 'Meta Title',
  'id'=>'example_box',
  'page'=>array('page','post'), //post type
  'context'=>'normal',
  'priority'=>'low'
);

$ashu_meta = array();

$ashu_meta[] = array(
  'name' => 'Input Example',
  'id'   => 'text_example',
  'desc' => 'A text input example, Default content:"Hello ashuwp."',
  'std'  => 'Hello ashuwp.',
  'type' => 'text'
);

/**More config array **/

$new_box = new ashuwp_postmeta_feild($ashu_meta, $meta_conf);
```

添加分类字段
```php
$taxonomy_cof = array('category','post_tag'); // taxonomy

$ashu_feild = array();
$ashu_feild[] = array(
  'name'      => 'Text Example',
  'id'        => 'text_example',
  'desc'      => 'description or notice.Default content:Default content',
  'std'       => 'Default content',
  'edit_only' => false,
  "type"      => "text"
);

/**More config array **/

$ashuwp_termmeta_feild = new ashuwp_termmeta_feild($ashu_feild, $taxonomy_cof);
```

添加设置页面
```php
$page_info = array(
  'full_name' => 'General Options',
  'optionname'=>'general', //
  'child'=>false, 
  'filename' => 'generalpage'
);

$ashu_options = array();

$ashu_options[] = array(
  'name' => 'Input Example',
  'id'   => 'input_example',
  'desc' => 'description or notice',
  'std'  => 'Default content',
  'type' => 'text'
);

/**More config array **/

$option_page = new ashuwp_options_feild($ashu_options, $page_info);
```