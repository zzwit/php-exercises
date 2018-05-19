
PHP一些常用的算法
===
- 杨辉三角

``` php
/**
 * 杨辉三角 * 首尾都是1 
     	1
	 1  1
	 1  2  1
	 1  3  3  1 
	 1  4  6  4  1 
*/
 function setLa($n)
{
    $arr = [];
    for ($i=0;$i<$n;$i++) {
      for($j = 0;$j<=$i;$j++) {
         if($j == 0 || $i == $j) {
                $arr[$i][$j] = 1;
	      } else {
	      $arr[$i][$j] = $arr[$i-1][$j-1] + $arr[$i-1][$j];
	      }
	      echo $arr[$i][$j]."\t";
	  }
        echo "</br>";
   }
}

```
- 九九乘法表
``` PHP
 function juju() {
    for ($i =1; $i<=9;$i++) {
        for($j=1;$j<=$i;$j++) {
            $z = $i*$j;
  echo $j."*".$i."=".$z;
  echo "\t";    }
        echo "</br>";
  }
}
```
- 正金字塔

```php
function zTower($n)
{
   for($i=1;$i<=$n;$i++) {
        for($t=0;$t<2*$i-1;$t++)
            echo "*";
  		echo "<br />";
   }
}
```

- 倒金字塔

```php
function ReverTower($n)
{
    for($i=$n;$i>0;$i--)
    {
        for($j=0;$j<$n-$i;$j++)
          echo "&nbsp";
  	for($k=0;$k<2*$i-1;$k++)
          echo "* ";
        echo "<br />";
  }
}
```

- 冒泡排序

```php
   $arr=[2,3,5,1,2,1,9,6];
   function maopao($arr) {
     $number = count($arr);
	 if($number <=1) {
        return $arr;
     }
    for($i=1;$i<$number;$i++){
     for($j=0;$j<=$number-$i;$j++) {
         if($arr[$j]>$arr[$j+1]) {
            $tmp = $arr[$j+1];
            $arr[$j] = $tmp;
            $arr[$j+1] = $arr[$j];
         } 
     }
    }
    return $arr;
   }
```
