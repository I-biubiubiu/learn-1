PK
    �q<Na�[�     & composer实现自动加载.mdup" 2%composer实现自动加载.md#<p align=center>composer实现自动加载 </p>
##### 准备工作：提前安装好composer
##### 1.创建一个项目目录，eg： learn
##### 2.在项目目录下，创建一个空的composer.json文件。

    {
	
	}

##### 3.从控制台进入项目的根目录，执行命令

    composer install

##### 4.会自动生成composer目录
##### 5.自动生成目录结构后，在composer.json文件中新增代码，实现自动加载，代码如下：

    { "autoload": {
	    "psr-4": {
	      "Learn\\":""
		    }  
			   }
	  }
##### 6.在根目录创建一个文件person.php，代码如下：

    <?php
    namespace Learn;
    class person{
    public function save(){
        echo 123123;
	    }
    }
	  

##### 7.使用类文件。在OOP目录下新建index.php文件，代码如下

    <?php
    use Learn\person;
    require 'vendor/autoload.php';
    $tao = new person();
    $tao->save();
##### 8.在控制器运行如下composer命令：
`composer dump-autoload`
##### 9.打开Vendor/autoload_psr4.php,自动生成如下代码：

    <?php
    // autoload_psr4.php @generated by Composer
    $vendorDir = dirname(dirname(__FILE__));
    $baseDir = dirname($vendorDir);
    return array(
    'Learn\\' => array($baseDir . ''),
    );

##### 10.运行代码
`123123`
PK 
    �q<Na�[�     &               composer实现自动加载.mdup" 2%composer实现自动加载.mdPK      q   l    