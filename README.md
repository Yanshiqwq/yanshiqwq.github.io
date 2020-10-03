# MCAPI

---

<!--<link rel="stylesheet" href="../Library/katex.min.css">-->

## 屑延时的屑API,~~```速度有亿点慢```~~

### 调用方法
1. [Forge](#Forge)  
1-1. [调用地址](#Forge.Url)  
1-2. [请求头](#Forge.Request)  
1-3. [参数](#Forge.RequestNum)  
1-4. [例子1](#Forge.Example1)  
1-5. [例子2](#Forge.Example2)  
1-6. [例子3](#Forge.Example3)  
1-7. [PHP源码](#Forge.PHP)  
2. [Optifine](#Optifine)  
2-1. [调用地址](#Optifine.Url)  
2-2. [请求头](#Optifine.Request)  
2-3. [参数](#Optifine.RequestNum)  
2-4. [例子1](#Optifine.Example1)  
2-5. [例子2](#Optifine.Example2)  
2-7. [PHP源码](#Optifine.PHP)  
3. [Fabric](#Fabric)  
3-1. [调用地址](#Fabric.Url)  
3-2. [请求头](#Fabric.Request)  
3-3. [参数](#Fabric.RequestNum)  
3-4. [例子1](#Fabric.Example1)  
3-5. [例子2](#Fabric.Example2)  
3-7. [PHP源码](#Fabric.PHP)  
4. [MCPE](#MCPE)  
4-1. [调用地址](#MCPE.Url)  
4-2. [请求头](#MCPE.Request)  
4-3. [参数](#MCPE.RequestNum)  
4-4. [例子1](#MCPE.Example1)  
4-5. [例子2](#MCPE.Example2)  
4-6. [例子3](#MCPE.Example3)  
4-7. [PHP源码](#MCPE.PHP)  
5. [命令助手](#commandAssistant)  
5-1. [调用地址](#CommandAssistant.Url)  
5-2. [请求头](#CommandAssistant.Request)  
5-3. [参数](#CommandAssistant.RequestNum)  
5-4. [例子1](#CommandAssistant.Example1)  
5-5. [例子2](#CommandAssistant.Example2)  
5-6. [PHP源码](#CommandAssistant.PHP)  
6. [Blocktopograph](#btr)  
6-1. [调用地址](#Blocktopograph.Url)  
6-2. [请求头](#Blocktopograph.Request)  
6-3. [参数](#Blocktopograph.RequestNum)  
6-4. [例子1](#Blocktopograph.Example1)  
6-5. [例子2](#Blocktopograph.Example2)  
6-6. [PHP源码](#Blocktopograph.PHP)  
7. [HMCL](#HMCL)  
7-1. [调用地址](#HMCL.Url)  
7-2. [请求头](#HMCL.Request)  
7-3. [参数](#HMCL.RequestNum)  
7-4. [例子1](#HMCL.Example1)  
7-5. [例子2](#HMCL.Example2)  
7-6. [PHP源码](#HMCL.PHP)  
8. [Rift](#Rift)  
8-1. [调用地址](#Rift.Url)  
8-2. [请求头](#Rift.Request)  
8-3. [参数](#Rift.RequestNum)  
8-4. [例子1](#Rift.Example1)  
8-5. [例子2](#Rift.Example2)  
8-7. [PHP源码](#Rift.PHP)  
9. [BlockBench](#BlockBench)  
9-1. [调用地址](#BlockBench.Url)  
9-2. [请求头](#BlockBench.Request)  
9-3. [参数](#BlockBench.RequestNum)  
9-4. [例子1](#BlockBench.Example1)  
9-5. [例子2](#BlockBench.Example2)  
9-7. [PHP源码](#BlockBench.PHP)  
10. [方块启动器](#BlockLauncher)  
10-1. [调用地址](#BlockLauncher.Url)  
10-2. [请求头](#BlockLauncher.Request)  
10-3. [参数](#BlockLauncher.RequestNum)  
10-4. [例子1](#BlockLauncher.Example1)  
10-5. [例子2](#BlockLauncher.Example2)  
10-7. [PHP源码](#BlockLauncher.PHP)  
11. [Java运行时](#Java)  

<span id="Forge"></span>

#### Forge

<span id="Forge.Url"></span>

- 调用地址
`http://yanshiqwq.um5.net/api/mc/forge`

<br><span id="Forge.Request"></span>

- 请求头
```json
{
	"method"    :"[list/json/download]",
	"url"	    :"[true/false]",
	"mcversion" : "[Minecraft版本]",
	"version"   : "[Forge版本号]"
}
```  

> 其中`method`为必要参数


- 相当于:
`http://yanshiqwq.um5.net/api/mc/forge/?method=[list/json/download]&url=[true/false]&mcversion=[Minecraft版本]&version=[Forge版本号]`

<span id="Forge.RequestNum"></span>

**各种参数**

|  method  |           用途               |
|----------|------------------------------|
|   list   |列出所有有Forge的Minecraft版本 |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="Forge.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/forge/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"1.16.1","1.15.2","1.15.1","1.15","1.14.4","1.14.3","1.14.2","1.13.2","1.12.2","1.12.1","1.12","1.11.2","1.11","1.10.2","1.10","1.9.4","1.9","1.8.9","1.8.8","1.8","1.7.10_pre4","1.7.10","1.7.2","1.6.4","1.6.3","1.6.2","1.6.1"
	]
}
```

<span id="Forge.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/forge/?method=list&ncversion=1.15.2`

结果:

```json
{
	"error": 0,
	"names": [
		"forge-1.15.2-31.2.0-installer.jar",
		"forge-1.15.2-31.1.99-installer.jar",
		"forge-1.15.2-31.1.98-installer.jar",
		"forge-1.15.2-31.1.97-installer.jar",
		"forge-1.15.2-31.1.95-installer.jar",
		"forge-1.15.2-31.1.93-installer.jar",
		"forge-1.15.2-31.1.92-installer.jar",
		"forge-1.15.2-31.1.91-installer.jar",
		......
		"forge-1.15.2-31.0.1-installer.jar"
	]
}
```

<span id="Forge.Example3"></span>

再举亿个栗子:

`http://yanshiqwq.um5.net/api/mc/forge/?method=json&mcversion=1.15.2&version=31.1.77`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/forge/forge-1.15.2-31.1.77-installer.jar",
	"filename": "forge-1.15.2-31.1.77-installer.jar",
	"md5": "80c000a2b7f009696c5a9ca44175adcf",
	"sha1": "8e6b7d777d0a8201211b8f97a910a037c59d7f9b",
	"sha256": "61c2cbd347fe18f1a65dfd0a72afc93381ab5923cec3e04dbe136ecc5df51dfd",
	"filesize": "6.43MB",
	"mcversion": "1.15.2"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 6432944
Content-Type: application/java-archive
Date: Thu, 13 Aug 2020 12:48:53 GMT
Etag: "df8adc8a62bd61:0"
Last-Modified: Sat, 16 May 2020 17:23:58 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#Optifine)

`http://yanshiqwq.um5.net/api/mc/forge/index.php`

<span id="Forge.PHP"></span>

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("mcversion",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("method",$_GET) && array_key_exists("url",$_GET) && array_key_exists("mcversion",$_GET)){
			$method = $_GET["method"];
			$mcversion = $_GET["mcversion"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				for ($x=2; $x<=$length-1; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/forge/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/forge/'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("mcversion",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			$version = $_GET["version"];
			if($method == "download"){
				$mcversion = $_GET["mcversion"];
				$filename = "./".$mcversion."/forge-".$mcversion."-".$version."-installer.jar";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				header("HTTP/1.1 302 Found");
				echo "<script> window.onload=function(){window.location.href='./".$filename."'} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$mcversion = $_GET["mcversion"];
				$version = $_GET["version"];
				$filename = "./".$mcversion."/forge-".$mcversion."-".$version."-installer.jar";
				if(!file_exists($filename)){
					header("content-type:application/json");
					$filename = "http://".$_SERVER['HTTP_HOST']."/api/mc/forge/".$mcversion."/forge-".$mcversion."-".$version."-installer.jar";
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$filename = "forge-".$mcversion."-".$version."-installer.jar";
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/forge/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","mcmcversion":"'.$mcversion.'"}';
				echo $text;
				exit;
			}
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$mcversion = $_GET["mcversion"];
				$file_list = scandir("./".$mcversion);
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET) && array_key_exists("mcversion",$_GET)){
			$method = $_GET["method"];
			$mcversion = $_GET["mcversion"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./".$mcversion."/");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
				exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			$url = $_GET["url"];
			if($method == "list"){
				if($url == "true"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-3;
					for ($x=2; $x<=$length-1; $x++) {
						echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/forge/'.$file_list[$x].'",';
					}
					echo '"http://'.$_SERVER['HTTP_HOST'],'/api/mc/forge/'.$file_list[$length].'"';
					echo "]}";
					exit;
				}elseif($url == "false"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-3;
					for ($x=2; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}else{
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR_URL","message":"请输入正确的url参数!"}';
					exit;	
				}
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="Optifine"></span>

#### Optifine

<span id="Optifine.Url"></span>

- 调用地址
`http://yanshiqwq.um5.net/api/mc/optifine`

<br><span id="Optifine.Request"></span>

- 请求头
```json
	{
		"method" : "[list/json/download]",
		"url"	 : "[true/false]",
		"version": "[Minecraft版本]+'_HD_U_'+[Optifine版本号](+Optifine预览版本)",
		"preview": "[true/false]"
	}
```  

> 其中`method`为必要参数

- 相当于:

`http://yanshiqwq.um5.net/api/mc/optifine/?method=[list/json/download]&url=[true/false]&version=[Minecraft版本]+[Optifine版本号](+Optifine预览版本)`

<span id="Optifine.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有Optifine版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

|   preview    |           用途              |
|----------|-----------------------------|
|   true   |      输出正式版文件名     |
|   false  |      输出预览版文件名     |

<span id="Optifine.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/Optifine/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"Previews",
		"OptiFine_1.16.1_HD_U_G2.jar",
		"OptiFine_1.14.4_HD_U_F5.jar",
		"OptiFine_1.14.4_HD_U_F4.jar",
		"OptiFine_1.14.4_HD_U_F3.jar",
		"OptiFine_1.14.4_HD_U_F2.jar",
		"OptiFine_1.14.3_HD_U_F2.jar",
		"OptiFine_1.14.3_HD_U_F1.jar",
		"OptiFine_1.13_HD_U_E4.jar",
		"OptiFine_1.13.2_HD_U_F5.jar",
		......
		"OptiFine_1.7.2_HD_U_E4.jar"
	]
}
```

<span id="Optifine.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/optifine/?method=json&version=1.14.4_HD_U_F2`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/optifine/optifine_1.14.4_HD_U_F2.jar",
	"filename": "optifine_1.14.4_HD_U_F2.jar",
	"md5": "e93eea0b5ffcf2ba40284e249a05e47d",
	"sha1": "ad8a8f60931f48e2873238d1460268bb4111f6c9",
	"sha256": "f8c0a0b46ef5764bfab0b542673e62e392ff2ef0d71dd45c7b0d929c0dcc8aff",
	"filesize": "2.65MB",
	"version": "1.14.4_HD_U_F2"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Content-Type: application/java-archive
Last-Modified: Sun, 17 May 2020 09:26:02 GMT
Accept-Ranges: bytes
ETag: "ca23b52e2d2cd61:0"
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
Date: Thu, 13 Aug 2020 13:45:13 GMT
Content-Length: 2646948
```

<span id="Optifine.Example3"></span>

再举亿个栗子:

`http://yanshiqwq.um5.net/api/mc/optifine//?method=json&preview=true&version=1.15.2_HD_U_G1_pre13`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/optifine/previews/preview_optifine_1.15.2_HD_U_G1_pre13.jar",
	"filename": "preview_optifine_1.15.2_HD_U_G1_pre13.jar",
	"md5": "f6baf7e232a6f3d605db1632eae656b3",
	"sha1": "c66d412c4cb46c6f2c76c224dc45a62d30ee8b43",
	"sha256": "5d313c3d00ef0e5496fc31709c07a8c152d22a125dc6326daedeeb4f68e83233",
	"filesize": "5.43MB",
	"version": "1.15.2_HD_U_G1_pre13"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 5434242
Content-Type: application/java-archive
Date: Fri, 14 Aug 2020 07:40:27 GMT
Etag: "d5a4d727d34d61:0"
Last-Modified: Wed, 27 May 2020 23:20:44 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#Fabric)

<span id="Optifine.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/optifine/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(array_key_exists("preview",$_GET)){
			$preview = $_GET["preview"];
			if($preview == "true"){
				if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
					exit;
				}
				if(array_key_exists("url",$_GET)){
					$method = $_GET["method"];
					if($method == "list" && $_GET["url"] == "false"){
						header("content-type:application/json");
						echo '{"error":0,"names":[';
						$file_list_ = scandir("./pewviews/");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-4;
						for ($x=2; $x<=$length-1; $x++) {
							echo '"'.$file_list[$x].'",';
						}
						echo '"'.$file_list[$length].'"';
						echo "]}";
						exit;
					}
					if($method == "list" && $_GET["url"] == "true"){
						header("content-type:application/json");
						echo '{"error":0,"url":[';
						$file_list_ = scandir("./previews/");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-4;
						for ($x=2; $x<=$length-1; $x++) {
							echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/previews/'.$file_list[$x].'",';
						}
						echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/previews/'.$file_list[$length].'"';
						echo "]}";
					exit;
					}
				}
				if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
					$method = $_GET["method"];
					if($method == "download"){
						$version = $_GET["version"];
						$filename = "preview_optifine_".$version.".jar";
						if(!file_exists("./previews/".$filename)){
							header("content-type:application/json");
							echo '{"error":"NO_SUCH_FILE"5,"message":"文件不存在","filename":"'.$filename.'"}';
							exit;
						}
						echo "<script> window.onload=function(){window.location.href='./previews/".$filename."';} </script>";
						exit;
					}
					if($method == "json"){
						header("content-type:application/json");
						$version = $_GET["version"];
						$filename = "preview_optifine_".$version.".jar";
						if(!file_exists("./previews/".$filename)){
							header("content-type:application/json");
							echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
							exit;
						}
						$md5 = md5_file("./previews/".$filename);
						$sha1 = sha1_file("./previews/".$filename);
						$filesize = filesize("./previews/".$filename);
						$filesize = $filesize / 1000000;
						$filesize = sprintf("%.2f",$filesize);
						$filesize = (string)$filesize;
						$sha256 = hash_file("sha256", "./previews/".$filename);
						$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/previews/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
						echo $text;
						exit;
					}
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
					exit;
				}
				if(array_key_exists("method",$_GET)){
					$method = $_GET["method"];
					if($method == "list"){
						header("content-type:application/json");
						echo '{"error":0,"names":[';
						$file_list_ = scandir("./previews/");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-3;
						for ($x=2; $x<=$length-1; $x++) {
							echo '"'.$file_list[$x].'",';
						}
						echo '"'.$file_list[$length].'"';
						echo "]}";
						exit;
					}else{
						header("content-type:application/json");
						echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
						exit;
					}
				}else{
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
					exit;
				}
			}
		}
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-4;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-2; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "optifine_".$version.".jar";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE"5,"message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "optifine_".$version.".jar";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/optifine/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=3; $x<=$length-2; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
/?>
```

<span id="Fabric"></span>

#### Fabric

<span id="Fabric.Url"></span>

- 调用地址
	`http://yanshiqwq.um5.net/api/mc/fabric`

<br><span id="Fabric.Request"></span>

- 请求头
```json
	{
		"method" : "[list/json/download]",
		"url"	 : "[true/false]",
		"build"	 : "[Fabric版本号]",
		"api"	 : "[FabricAPI版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:
	 `http://yanshiqwq.um5.net/api/mc/forge/?method=[list/json/download]&url=[true/false]&build=[Fabric版本号]&api=[FabricAPI版本号]`

<span id="Fabric.RequestNum"></span>

**各种参数**

|  method  |           用途               |
|----------|------------------------------|
|   list   |列出所有有Fabric版本 |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="Fabric.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/fabric/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"fabric-build-393_api-0.17.0.jar",
		"fabric-build-392_api-0.16.4.jar",
		"fabric-build-390_api-0.16.3.jar",
		"fabric-build-387_api-0.16.1.jar",
		"fabric-build-386_api-0.16.0.jar",
		"fabric-build-385_api-0.16.2.jar",
		"fabric-build-384_api-0.16.0.jar",
		"fabric-build-382_api-0.15.2.jar",
		"fabric-build-380_api-0.15.1_1.16.jar",
		"fabric-build-380_api-0.15.1_1.16.1.jar",
		"fabric-build-379_api-0.15.0_1.16.jar",
		"fabric-build-379_api-0.15.0_1.16.1.jar",
		"fabric-build-377_api-0.14.6.jar",
		......
		"fabric-build-36_api-0.1.0.jar",
		"fabric-build-20w14_infinite_api-0.5.7.jar"
	]
}
```

<span id="Fabric.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/fabric/?method=json&build=373&api=0.14.2`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/fabric/fabric-build-373_api-0.14.2.jar",
	"filename": "fabric-build-373_api-0.14.2.jar",
	"md5": "10f10c05cf05035eed9855949ef00172",
	"sha1": "8559795219b2aea7b27d1bc3da625482dfe15200",
	"sha256": "c24238547f733f0f950818c8de793d2425be9f7bac6fdb1ee2a3967c36b3ece3",
	"filesize": "0.62MB",
	"build": "373"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Content-Type: application/java-archive
Last-Modified: Thu, 23 Jul 2020 16:48:53 GMT
Accept-Ranges: bytes
ETag: "947dfd251161d61:0"
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
Date: Thu, 13 Aug 2020 14:00:15 GMT
Content-Length: 615714
```

[点击跳过PHP代码](#Optifine)

<span id="Fabric.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/fabric/index.php`

源码:

```php
</?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				if(!array_key_exists("method",$_GET) && !array_key_exists("build",$_GET)){
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
					exit;
				}
				if(array_key_exists("url",$_GET)){
					$method = $_GET["method"];
					if($method == "list" && $_GET["url"] == "false"){
						header("content-type:application/json");
						echo '{"error":0,"names":[';
						$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
						$length = sizeof($file_list)-2;
						for ($x=3; $x<=$length-1; $x++) {
							echo '"'.$file_list[$x].'",';
						}
						echo '"'.$file_list[$length].'"';
						echo "]}";
						exit;
					}
					if($method == "list" && $_GET["url"] == "true"){
						header("content-type:application/json");
						echo '{"error":0,"url":[';
						$file_list_ = scandir("./");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-2;
						for ($x=3; $x<=$length-1; $x++) {
							echo '"'.$file_list[$x].'",';
						}
						echo '"'.$file_list[$length].'"';
						echo "]}";
						exit;
					}
				}
				if(array_key_exists("method",$_GET) && array_key_exists("build",$_GET)){
					if(!array_key_exists("api",$_GET)){
						echo '{"error":"INPUT_ERROR_NO_API","message":"请输入API版本!"}';
					}
					$method = $_GET["method"];
					if($method == "download"){
						$build = $_GET["build"];
						$api = $_GET["api"];
						$filename = "fabric-build-".$build."_api-$api.jar";
						if(!file_exists($filename)){
							header("content-type:application/json");
							echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
							exit;
						}
						header("HTTP/1.1 302 Found");
						echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
						exit;
					}
					if($method == "json"){
						header("content-type:application/json");
						$build = $_GET["build"];
						$api = $_GET["api"];
						$filename = "fabric-build-".$build."_api-$api.jar";
						if(!file_exists($filename)){
							header("content-type:application/json");
							echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
							exit;
						}
						$md5 = md5_file($filename);
						$sha1 = sha1_file($filename);
						$filesize = filesize($filename);
						$filesize = $filesize / 1000000;
						$filesize = sprintf("%.2f",$filesize);
						$filesize = (string)$filesize;
						$sha256 = hash_file("sha256", $filename);
						$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/fabric/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","build":"'.$build.'"}';
						echo $text;
						exit;
					}
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
					exit;
				}
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
/?>
```

<span id="MCPE"></span>

#### MCPE

<span id="MCPE.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/mcpe`

<br><span id="MCPE.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"mcversion" : "[Minecraft版本]",
		"version"   : "[MCPE版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `http://yanshiqwq.um5.net/api/mc/mcpe/?method=[list/json/download]&url=[true/false]&mcversion=[Minecraft版本]&version=[MCPE版本号]`

<span id="MCPE.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有MCPE版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="MCPE.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/mcpe/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"1.16","1.15","1.14","1.13","1.12","1.11","1.10","1.9","1.8","1.7","1.6","1.5","1.4","1.2","1.1","1.0","0.x"
	]
}
```

<span id="MCPE.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/mcpe/?method=list&mcversion=1.16`

结果:

```json
{
	"error": 0,
	"names": [
		"Minecraft.PE.1.16.0.63.apk",
		"Minecraft.PE.1.16.0.61.apk",
		"Minecraft.PE.1.16.0.60.apk",
		"Minecraft.PE.1.16.0.59.apk",
		"Minecraft.PE.1.16.0.58.apk",
		"Minecraft.PE.1.16.0.57.apk",
		"Minecraft.PE.1.16.0.55.apk",
		"Minecraft.PE.1.16.0.53.apk",
		"Minecraft.PE.1.16.0.51.apk"
	]
}
```

<span id="MCPE.Example3"></span>

再举亿个栗子:

`http://yanshiqwq.um5.net/api/mc/mcpe/?method=json&mcversion=1.16&version=1.16.0.63`

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/mcpe/Minecraft.PE.1.16.0.63.apk",
	"filename": "Minecraft.PE.1.16.0.63.apk",
	"md5": "057584a3f959cc5c02d7f5e8434fc245",
	"sha1": "b34de7555b68b547e5a215a7e815b7cfaa9d2e40",
	"sha256": "5bfe9912e3e1c2002ab4734b1936255546b5da6002fdbfb094d7e35c31a3fa31",
	"filesize": "104.60MB",
	"mcversion": "1.16"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 104595425
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 07:32:33 GMT
Etag: "1f1682afde32d61:0"
Last-Modified: Mon, 25 May 2020 21:51:46 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#CommandAssistant)

<span id="MCPE.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/mcpe/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("method",$_GET) && array_key_exists("url",$_GET) && array_key_exists("mcversion",$_GET)){
			$method = $_GET["method"];
			$mcversion = $_GET["mcversion"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./".$mcversion."/");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./".$mcversion."/");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				for ($x=2; $x<=$length-1; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/mcpe/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/mcpe/'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("mcversion",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			$version = $_GET["version"];
			if($method == "download"){
				$mcversion = $_GET["mcversion"];
				$filename = "./".$mcversion."/Minecraft.PE.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				header("HTTP/1.1 302 Found");
				echo "<script> window.onload=function(){window.location.href='./".$filename."'} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$mcversion = $_GET["mcversion"];
				$version = $_GET["version"];
				$filename = "./".$mcversion."/Minecraft.PE.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					$filename = "http://".$_SERVER['HTTP_HOST']."/api/mc/mcpe/".$filename;
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$filename = "Minecraft.PE.".$version.".apk";
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/mcpe/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","mcversion":"'.$mcversion.'"}';
				echo $text;
				exit;
			}
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$mcversion = $_GET["mcversion"];
				$file_list = scandir("./".$mcversion);
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET) && array_key_exists("mcversion",$_GET)){
			$method = $_GET["method"];
			$mcversion = $_GET["mcversion"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./".$mcversion."/");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
				exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			$url = $_GET["url"];
			if($method == "list"){
				if($url == "true"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-2;
					for ($x=5; $x<=$length-1; $x++) {
						echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/mcpe/'.$file_list[$x].'",';
					}
					echo '"http://'.$_SERVER['HTTP_HOST'],'/api/mc/mcpe/'.$file_list[$length].'"';
					echo "]}";
					exit;
				}elseif($url == "false"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-2;
					for ($x=2; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}else{
					header("content-type:application/json");
					echo '{"error":"INPUT_ERROR_URL","message":"请输入正确的url参数!"}';
					exit;	
				}
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=5; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="CommandAssistant"></span>

#### 命令助手

<span id="CommandAssistant.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/commandassistant`

<br><span id="CommandAssistant.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[命令助手版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `http://yanshiqwq.um5.net/api/mc/commandassistant/?method=[list/json/download]&url=[true/false]&version=[CommandAssistant版本号]`

<span id="CommandAssistant.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有命令助手版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="CommandAssistant.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/commandassistant/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"Command.Assistant.1.2.13.apk",
		"Command.Assistant.1.2.12.apk",
		"Command.Assistant.1.2.11.apk",
		"Command.Assistant.1.2.10.apk",
		"Command.Assistant.1.2.9.apk",
		"Command.Assistant.1.2.8.apk",
		"Command.Assistant.1.2.7.apk",
		"Command.Assistant.1.2.6.apk",
		"Command.Assistant.1.2.5.apk",
		"Command.Assistant.1.2.4.apk",
		"Command.Assistant.1.2.3.apk",
		"Command.Assistant.1.2.2.apk",
		"Command.Assistant.1.2.1.apk",
		"Command.Assistant.1.2.0.apk",
		"Command.Assistant.1.1.1.apk",
		"Command.Assistant.1.0.1.apk"
	]
}
```

<span id="CommandAssistant.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/commandassistant/?method=json&version=1.0.1`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/commandassistant/Command.Assistant.1.0.1.apk",
	"filename": "Command.Assistant.1.0.1.apk",
	"md5": "73ebe67ec71fb7f43d127258129f2ed8",
	"sha1": "acaed63b512820f1ceefbfc5bfe235940ebb7b77",
	"sha256": "82b0c467b2d92e5b327ed9018f6b8069ce270609173715e6f2f4be99fffb213c",
	"filesize": "1.21MB",
	"version": "1.0.1"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 1214288
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 08:06:49 GMT
Etag: "801ca925514d41:0"
Last-Modified: Thu, 05 Jul 2018 11:40:45 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#CommandAssistant)

<span id="CommandAssistant.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/commandassistant/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-4;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-2; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "Command.Assistant.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE"5,"message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "Command.Assistant.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-2; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="Blocktopograph"></span>

#### Blocktopograph

<span id="Blocktopograph.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/Blocktopograph`

<br><span id="Blocktopograph.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[Btr版本号]+[汉化版填.cn,原版填.en]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/Blocktopograph/?method=[list/json/download]&url=[true/false]&version=[Btr版本号]+[语言后缀]`

<span id="Blocktopograph.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有Btr版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="Blocktopograph.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/Blocktopograph/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"Blocktopograph.v1.9.3.cn.apk",
		"Blocktopograph.v1.8.9.en.apk",
		"Blocktopograph.v1.8.8.en.apk",
		"Blocktopograph.v1.7.en.apk",
		"Blocktopograph.v1.6.en.apk"
	]
}
```

<span id="Blocktopograph.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/Blocktopograph/?method=json&version=1.6.en`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/blocktopograph/Blocktopograph.v1.6.en.apk",
	"filename": "Blocktopograph.v1.6.en.apk",
	"md5": "4b0e7698b2b788988d8f1bd388929b52",
	"sha1": "f8c0c50521423e8787491b43f7e83cc03e617d97",
	"sha256": "377c659f9694fce56db6b4132063be7ccf697f367da3e3653d00be8f27b1e5db",
	"filesize": "3.54MB",
	"version": "1.6.en"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 3538092
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 08:32:04 GMT
Etag: "a8016834a6ad61:0"
Last-Modified: Tue, 04 Aug 2020 10:32:11 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#HMCL)

<span id="Blocktopograph.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/blocktopograph/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-4;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-2; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocktopograph/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocktopograph/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "Blocktopograph.v".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "Blocktopograph.v".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocktopograph/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-2; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="HMCL"></span>

#### HMCL

<span id="HMCL.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/hmcl`

<br><span id="HMCL.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[HMCL版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/hmcl/?method=[list/json/download]&url=[true/false]&version=[HMCL版本号]`

<span id="HMCL.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有HMCL版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="HMCL.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/hmcl/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"HMCL-3.3.172.exe",
		"HMCL-3.3.170.exe",
		"HMCL-3.3.163.exe",
		"HMCL-3.3.162.exe",
		"HMCL-3.3.160.exe",
		"HMCL-3.3.158.exe",
		"HMCL-3.2.149.exe",
		"HMCL-3.2.146.exe",
		"HMCL-3.2.139.exe",
		"HMCL-3.2.136.exe",
		"HMCL-3.2.130.exe",
		"HMCL-2.3.5.4.exe"
	]
}
```

<span id="HMCL.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/hmcl/?method=json&version=2.3.5.4`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/commandassistant/HMCL-2.3.5.4.exe",
	"filename": "HMCL-2.3.5.4.exe",
	"md5": "d530ad13569e1aeca86b4d1ebf3aa978",
	"sha1": "de4444cdd67958af000a990a70d363c99f35b782",
	"sha256": "50ec3d28dda6775cbb1920029fd4fe36572051b3e3f81392152f9b5bc44adb0c",
	"filesize": "0.97MB",
	"version": "2.3.5.4"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 3538092
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 08:32:04 GMT
Etag: "a8016834a6ad61:0"
Last-Modified: Tue, 04 Aug 2020 10:32:11 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#Rift)

<span id="HMCL.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/hmcl/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-4;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-2; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "HMCL-".$version.".exe";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE"5,"message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "HMCL-".$version.".exe";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/commandassistant/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-2; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="Rift"></span>

#### Rift

<span id="Rift.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/rift`

<br><span id="Rift.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[Rift版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/Rift/?method=[list/json/download]&url=[true/false]&version=[Rift版本号]`

<span id="Rift.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有Btr版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="Rift.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/Rift/?method=list`

结果:

```json
{
  "error": 0,
  "names": [
    "Rift-1.0.4-106.jar",
    "Rift-1.0.4-105.jar",
    "Rift-1.0.4-87.jar",
    "Rift-1.0.4-86.jar",
    ...
    "Rift-1.0.0-0.jar",
  ]
}
```

<span id="Rift.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/Rift/?method=json&version=1.0.4-106`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/rift/Rift-1.0.4-106.jar",
	"filename": "Rift-1.0.4-106.jar",
	"md5": "f03458c67d729c440553cd88046e0503",
	"sha1": "2d523f42012265949561409803725bea904f2b34",
	"sha256": "63a3d1f2dc58e4d71b0dc185ce2e7857ae7aa8c871fe537bfd7fa1b0bc881513",
	"filesize": "0.18MB",
	"mcversion": "1.0.4-106"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 180301
Content-Type: application/java-archive
Date: Sat, 15 Aug 2020 09:36:49 GMT
Etag: "f7b7ea49a52dd61:0"
Last-Modified: Tue, 19 May 2020 06:18:18 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#BlockBench)

<span id="Rift.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/Rift/index.php`

源码:

```php
<?php
	$path = 'http://'.$_SERVER['HTTP_HOST'].'/api/mc/rift/';
	//文件夹路径
	$before = 2;
	//method=list时前面去掉的项数(包括"."和"..")
	$after = 3;
	//method=list时后面去掉的项数
	if($_GET==[]){
		header("content-type:application/json");
		echo '{"error":"NO_INPUT","message":"请输入参数!"}';
		exit;
	}else{
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				if(array_key_exists("url",$_GET)){
					if($_GET["url"] == "true"){
						header("content-type:application/json");
						echo '{"error":0,"url":[';
						$file_list_ = scandir("./../Rift/./././../Rift/./");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-$after;
						for ($x=$before; $x<=$length-1; $x++) {
							echo '"'.$path.$file_list[$x].'",';
						}
						echo '"'.$path.$file_list[$length].'"';
						echo "]}";
						exit;
					}else{
						header("content-type:application/json");
						echo '{"error":0,"names":[';
						$file_list_ = scandir("./");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-$after;
						for ($x=$before; $x<=$length-1; $x++) {
							echo '"'.$path.$file_list[$x].'",';
						}
						echo '"'.$path.$file_list[$length].'"';
						echo "]}";
						exit;
					}
				}else{
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-$after;
					for ($x=$before; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}
			}
			if(array_key_exists("version",$_GET)){
				$version = $_GET["version"];
				$filename = "Rift-".$version.".jar";
				//列表内文件名规则
				$path .= $filename;
				//文件夹路径
				if($method == "download"){
					if(!file_exists($filename)){
						header("content-type:application/json");
						echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
						exit;
					}
					echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
					exit;
				}
				if($method == "json"){
					header("content-type:application/json");
					if(!file_exists($filename)){
						header("content-type:application/json");
						echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
						exit;
					}
					$md5 = md5_file($filename);
					$sha1 = sha1_file($filename);
					$filesize = filesize($filename);
					$filesize = $filesize / 1000000;
					$filesize = sprintf("%.2f",$filesize);
					$filesize = (string)$filesize;
					$sha256 = hash_file("sha256", $filename);
					$text = '{"error":0,"url":"'.$path.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","mcversion":"'.$version.'"}';
					echo $text;
					exit;
				}
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
			if(array_key_exists("url",$_GET)){
				if($method == "list" && $_GET["url"] == "false"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-$after;
					for ($x=$before; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="Rift"></span>

#### Rift

<span id="Rift.Url"></span>

- 调用地址
	`http://yanshiqwq.um5.net/api/mc/rift`

<br><span id="Rift.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[Rift版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/Rift/?method=[list/json/download]&url=[true/false]&version=[Rift版本号]`

<span id="Rift.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有Btr版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="Rift.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/Rift/?method=list`

结果:

```json
{
  "error": 0,
  "names": [
    "Rift-1.0.4-106.jar",
    "Rift-1.0.4-105.jar",
    "Rift-1.0.4-87.jar",
    "Rift-1.0.4-86.jar",
    ...
    "Rift-1.0.0-0.jar",
  ]
}
```

<span id="Rift.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/Rift/?method=json&version=1.0.4-106`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/rift/Rift-1.0.4-106.jar",
	"filename": "Rift-1.0.4-106.jar",
	"md5": "f03458c67d729c440553cd88046e0503",
	"sha1": "2d523f42012265949561409803725bea904f2b34",
	"sha256": "63a3d1f2dc58e4d71b0dc185ce2e7857ae7aa8c871fe537bfd7fa1b0bc881513",
	"filesize": "0.18MB",
	"mcversion": "1.0.4-106"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 180301
Content-Type: application/java-archive
Date: Sat, 15 Aug 2020 09:36:49 GMT
Etag: "f7b7ea49a52dd61:0"
Last-Modified: Tue, 19 May 2020 06:18:18 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#BlockBench)

<span id="Rift.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/Rift/index.php`

源码:

```php
<?php
	$path = 'http://'.$_SERVER['HTTP_HOST'].'/api/mc/rift/';
	//文件夹路径
	$before = 2;
	//method=list时前面去掉的项数(包括"."和"..")
	$after = 3;
	//method=list时后面去掉的项数
	if($_GET==[]){
		header("content-type:application/json");
		echo '{"error":"NO_INPUT","message":"请输入参数!"}';
		exit;
	}else{
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				if(array_key_exists("url",$_GET)){
					if($_GET["url"] == "true"){
						header("content-type:application/json");
						echo '{"error":0,"url":[';
						$file_list_ = scandir("./../Rift/./././../Rift/./");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-$after;
						for ($x=$before; $x<=$length-1; $x++) {
							echo '"'.$path.$file_list[$x].'",';
						}
						echo '"'.$path.$file_list[$length].'"';
						echo "]}";
						exit;
					}else{
						header("content-type:application/json");
						echo '{"error":0,"names":[';
						$file_list_ = scandir("./");
						natcasesort($file_list_);
						arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
						$x = 0;
						foreach($file_list_ as $key => $value){
							$x = $x + 1;
							$file_list[$x] = $value;
						}
						$length = sizeof($file_list)-$after;
						for ($x=$before; $x<=$length-1; $x++) {
							echo '"'.$path.$file_list[$x].'",';
						}
						echo '"'.$path.$file_list[$length].'"';
						echo "]}";
						exit;
					}
				}else{
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-$after;
					for ($x=$before; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}
			}
			if(array_key_exists("version",$_GET)){
				$version = $_GET["version"];
				$filename = "Rift-".$version.".jar";
				//列表内文件名规则
				$path .= $filename;
				//文件夹路径
				if($method == "download"){
					if(!file_exists($filename)){
						header("content-type:application/json");
						echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
						exit;
					}
					echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
					exit;
				}
				if($method == "json"){
					header("content-type:application/json");
					if(!file_exists($filename)){
						header("content-type:application/json");
						echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
						exit;
					}
					$md5 = md5_file($filename);
					$sha1 = sha1_file($filename);
					$filesize = filesize($filename);
					$filesize = $filesize / 1000000;
					$filesize = sprintf("%.2f",$filesize);
					$filesize = (string)$filesize;
					$sha256 = hash_file("sha256", $filename);
					$text = '{"error":0,"url":"'.$path.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","mcversion":"'.$version.'"}';
					echo $text;
					exit;
				}
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
			if(array_key_exists("url",$_GET)){
				if($method == "list" && $_GET["url"] == "false"){
					header("content-type:application/json");
					echo '{"error":0,"names":[';
					$file_list_ = scandir("./");
					natcasesort($file_list_);
					arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
					$x = 0;
					foreach($file_list_ as $key => $value){
						$x = $x + 1;
						$file_list[$x] = $value;
					}
					$length = sizeof($file_list)-$after;
					for ($x=$before; $x<=$length-1; $x++) {
						echo '"'.$file_list[$x].'",';
					}
					echo '"'.$file_list[$length].'"';
					echo "]}";
					exit;
				}
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="BlockBench"></span>

#### BlockBench

<span id="BlockBench.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/blockBench`

<br><span id="BlockBench.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[BlockBench版本号]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/BlockBench/?method=[list/json/download]&url=[true/false]&version=[BlockBench版本号]`

<span id="BlockBench.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有BlockBench版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="BlockBench.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/blockBench/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"Blockbench_3.6.5.exe",
		"Blockbench_3.6.4.exe",
		"Blockbench_3.6.3.exe",
		"Blockbench_3.6.2.exe",
		......
		"Blockbench_1.10.2.exe"
	]
}
```

<span id="BlockBench.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/blockbench/?method=json&version=1.10.2`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/blockbench/blockbench_1.10.2.exe",
	"filename": "blockbench_1.10.2.exe",
	"md5": "d315f5a5e474e29a388c6cfea6fc6df2",
	"sha1": "1e0f0b2094579b9dc9c6ad6f5d0a0205df924380",
	"sha256": "eaf47e4031a0cb593c5d9da867ced066e1eeaf5182956d363dc3d61218481971",
	"filesize": "36.88MB",
	"version": "1.10.2"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 3538092
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 08:32:04 GMT
Etag: "a8016834a6ad61:0"
Last-Modified: Tue, 04 Aug 2020 10:32:11 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#BlockLauncher)

<span id="BlockBench.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/BlockBench/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-4;
				for ($x=2; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-3;
				for ($x=2; $x<=$length-2; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blockbench/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blockbench/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "blockbench_".$version.".exe";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "blockbench_".$version.".exe";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blockbench/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-2; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```


<span id="BlockLauncher"></span>

#### 方块启动器

<span id="BlockLauncher.Url"></span>

- 调用地址 
	`http://yanshiqwq.um5.net/api/mc/blocklauncher`

<br><span id="BlockLauncher.Request"></span>

- 请求头
```json
	{
		"method"    : "[list/json/download]",
		"url"	    : "[true/false]",
		"version"   : "[是否为Pro版本]+[MC版本]"
	}
```  

> 其中`method`为必要参数

- 相当于:

	 `正式版: http://yanshiqwq.um5.net/api/mc/blocklauncher/?method=[list/json/download]&url=[true/false]&version=(Pro)+[MC版本]`

<span id="BlockLauncher.RequestNum"></span>

**各种参数**

|  method  |           用途              |
|----------|-----------------------------|
|   list   |列出所有Btr版本          |
|   json   |以json格式显示文件详细信息     |
| download |下载文件                      |

|   url    |           用途              |
|----------|-----------------------------|
|   true   |      以网址模式输出文件名     |
|   false  |      以正常模式输出文件名     |

<span id="BlockLauncher.Example1"></span>

举个栗子:

`http://yanshiqwq.um5.net/api/mc/blocklauncher/?method=list`

结果:

```json
{
	"error": 0,
	"names": [
		"BlockLauncher.Pro.1.16.1.apk",
		"BlockLauncher.Pro.1.14.1.apk",
		"BlockLauncher.Pro.1.13.1.apk",
		......
		"BlockLauncher.Pro.1.0.6.apk",
		"BlockLauncher.1.12.0.apk",
		"BlockLauncher.1.2.10.apk"
	]
}
```
<span id="BlockLauncher.Example2"></span>

再举个栗子:

`http://yanshiqwq.um5.net/api/mc/blocklauncher/?method=json&version=Pro.1.16.1`

结果:

```json
{
	"error": 0,
	"url": "http://yanshiqwq.um5.net/api/mc/blocklauncher/BlockLauncher.Pro.1.16.1.apk",
	"filename": "BlockLauncher.Pro.1.16.1.apk",
	"md5": "d3d4ab2fabf0d2769e2949e443df93f4",
	"sha1": "ab2132326c6a54fb320415fbc97226fbd359b627",
	"sha256": "cb6434c2df4da05bb719a675de6b7ac16211d81b44ba7364b29bee7ebdca31ed",
	"filesize": "32.91MB",
	"version": "Pro.1.16.1"
}
```

把`method=json`改成`method=download`就可以下载啦!
响应头:

```http
HTTP/1.1 200 OK
Accept-Ranges: bytes
Content-Length: 32914202
Content-Type: application/vnd.android.package-archive
Date: Sat, 15 Aug 2020 12:48:33 GMT
Etag: "ae32b80cf6cd61:0"
Last-Modified: Fri, 07 Aug 2020 15:25:38 GMT
Server: Microsoft-IIS/10.0
X-Powered-By: ASP.NET
```

[点击跳过PHP代码](#Java)

<span id="BlockLauncher.PHP"></span>

`http://yanshiqwq.um5.net/api/mc/blocklauncher/index.php`

源码:

```php
<?php
	if(array_key_exists("html",$_GET)){
		if($_GET["html"]=="true"){
			echo '<strong><h3>文件列表加载中...<button class="button" style="vertical-align:middle" onclick="window.location.href=&quot;../&quot;"><span>返回</span></button></h3></strong>';
			echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
			exit;
		}
	}
	if($_GET==[]){
		echo '<script>window.onload=function(){window.location.href="./ShowHTML.php"}</script>';
		exit;
	}else{
		if(!array_key_exists("method",$_GET) && !array_key_exists("version",$_GET)){
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
			exit;
		}
		if(array_key_exists("url",$_GET)){
			$method = $_GET["method"];
			if($method == "list" && $_GET["url"] == "false"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}
			if($method == "list" && $_GET["url"] == "true"){
				header("content-type:application/json");
				echo '{"error":0,"url":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-1; $x++) {
					echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocklauncher/'.$file_list[$x].'",';
				}
				echo '"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocklauncher/'.$file_list[$length].'"';
				echo "]}";
			exit;
			}
		}
		if(array_key_exists("method",$_GET) && array_key_exists("version",$_GET)){
			$method = $_GET["method"];
			if($method == "download"){
				$version = $_GET["version"];
				$filename = "BlockLauncher.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				echo "<script> window.onload=function(){window.location.href='./".$filename."';} </script>";
				exit;
			}
			if($method == "json"){
				header("content-type:application/json");
				$version = $_GET["version"];
				$filename = "BlockLauncher.".$version.".apk";
				if(!file_exists($filename)){
					header("content-type:application/json");
					echo '{"error":"NO_SUCH_FILE","message":"文件不存在","filename":"'.$filename.'"}';
					exit;
				}
				$md5 = md5_file($filename);
				$sha1 = sha1_file($filename);
				$filesize = filesize($filename);
				$filesize = $filesize / 1000000;
				$filesize = sprintf("%.2f",$filesize);
				$filesize = (string)$filesize;
				$sha256 = hash_file("sha256", $filename);
				$text = '{"error":0,"url":"http://'.$_SERVER['HTTP_HOST'].'/api/mc/blocklauncher/'.$filename.'","filename":"'.$filename.'","md5":"'.$md5.'","sha1":"'.$sha1.'","sha256":"'.$sha256.'","filesize":"'.$filesize.'MB","version":"'.$version.'"}';
				echo $text;
				exit;
			}
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_METHOD","message":"请输入正确的method值!"}';
			exit;
		}
		if(array_key_exists("method",$_GET)){
			$method = $_GET["method"];
			if($method == "list"){
				header("content-type:application/json");
				echo '{"error":0,"names":[';
				$file_list_ = scandir("./");
				natcasesort($file_list_);
				arsort($file_list_, SORT_STRING | SORT_FLAG_CASE | SORT_NATURAL);
				$x = 0;
				foreach($file_list_ as $key => $value){
					$x = $x + 1;
					$file_list[$x] = $value;
				}
				$length = sizeof($file_list)-2;
				for ($x=3; $x<=$length-1; $x++) {
					echo '"'.$file_list[$x].'",';
				}
				echo '"'.$file_list[$length].'"';
				echo "]}";
				exit;
			}else{
				header("content-type:application/json");
				echo '{"error":"INPUT_ERROR","message":"请输入正确的参数!"}';
				exit;
			}
		}else{
			header("content-type:application/json");
			echo '{"error":"INPUT_ERROR_NO_METHOD","message":"缺少method值!"}';
			exit;
		}
	}
?>
```

<span id="Java"></span>

#### Java运行时

<span id="Java.Url"></span>

- 下载地址
`http://yanshiqwq.um5.net/api/mc/jre-8u261-windows-i586.exe`
