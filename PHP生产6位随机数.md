# PHP生产6位随机数，要求的大写字母和数字
1. 方法一

```php
 function getRandCode_1($len = 6)  
	{  
	    $charts = "ABCDEFGHJKLMNPQRSTUVWXYZ";  
		$noncestr = substr(str_shuffle($charts),5,2);
		for ( $i = 0; $i < 2; $i++ ) 
		{ 
		   $noncestr .= $chars[ mt_rand(0, strlen($chars) - 1) ]; 
		} 

		$noncestr = str_shuffle($noncestr.mt_rand(1000, 9999));
	    return  $noncestr;  
	}  
所有的时间
第一次：php sjishu.php  0.12s user 0.08s system 80% cpu 0.256 total
第二次：php sjishu.php  0.13s user 0.03s system 65% cpu 0.240 total
第三次：php sjishu.php  0.13s user 0.03s system 65% cpu 0.240 total
```
2. 方法二

```php
 function getRandCode($len = 6)  
	{  
	    $charts = "ABCDEFGHJKLMNPQRSTUVWXYZ";  
		$noncestr = substr(str_shuffle($charts),5,2);
		$noncestr = str_shuffle($noncestr.mt_rand(1000, 9999));
	    return  $noncestr;  
	}  
所有的时间
第一次：php sjishu.php  0.10s user 0.09s system 75% cpu 0.256 total
第二次：php sjishu.php  0.10s user 0.08s system 84% cpu 0.211 total
第三次：php sjishu.php  0.10s user 0.07s system 85% cpu 0.206 total
```



假设我们现在一共有1w次使用的时间
```php
for($i=0;$i<10000;$i++) {
		$code = getRandCode();

		echo $code."\n";

}

```
我使用的固体硬盘数据不是很明显



