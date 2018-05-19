# php一些练习题目

## 数组
1. 有这样的数组 $list = array(1,2,3,3,4,5,6,6,5,3,2,1);输出的这样,用代码实现
	 
	 ```php
		 Array
		(
		    [1] => Array
		        (
		            [0] => 1
		            [1] => 1
		        )
		
		    [2] => Array
		        (
		            [0] => 2
		            [1] => 2
		        )
		
		    [3] => Array
		        (
		            [0] => 3
		            [1] => 3
		            [2] => 3
		        )
		
		    [4] => Array
		        (
		            [0] => 4
		        )
		
		    [5] => Array
		        (
		            [0] => 5
		            [1] => 5
		        )
		
		    [6] => Array
		        (
		            [0] => 6
		            [1] => 6
		        )
		
		)
	 ```
	 
	代码如下
	
	```php
	    $list = array(1,2,3,3,4,5,6,6,5,3,2,1);
        $acit = array_unique($list); //数组去重
        $newarray = array();
        $val_nums = array_count_values($list); //计算数值出现几次
        foreach ($acit as $val) {
            for ($i = 0;$i<$val_nums[$val];$i++) {
                $val_array[$i] = $val;
            }
            $newarray[$val] = $val_array;
            unset($val_array);
        }
        unset($list);unset($acit);unset($val_nums);
        echo "<pre>";print_r($newarray);die;
	```
