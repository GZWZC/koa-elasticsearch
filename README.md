# koa-elasticsearch



这是一个监控系统项目，但涉及到业务代码，所以代码不开放，只提供搭建过程。

首先你要知道你需要es来做什么。
es的中文权威指南地址：https://www.elastic.co/guide/cn/elasticsearch/guide/current/index.html

1.安装java sdk。
建议安装sdk8：http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html

2.根据你的系统下载elasticsearch。
下载地址：https://www.elastic.co/downloads/elasticsearch

3.进入下载后并解压后的elasticsearch文件夹，Terminal在elasticsearch目录里执行操作。
如果你是在 Windows 上面运行 Elasticseach，你应该运行 bin\elasticsearch.bat 而不是 bin\elasticsearch 。
mac:
    

    cd elasticsearch
    ./bin/elasticsearch

window:

    cd elasticsearch
    bin\elasticsearch.bat

四:测试 Elasticsearch 是否启动成功

 1.利用chrome插件测试 Elasticsearch 是否启动成功：

> elasticsearch-head
应用商店：https://chrome.google.com/webstore/detail/elasticsearch-head/ffmkiejjmecolpfloofpjologoblkegm

2.nodeJs测试，看Terminal是否输入`All is well`

    var elasticsearch = require('elasticsearch'); 
    var client = new elasticsearch.Client({ 	
        host: 'localhost:9200', 	
        log: 'trace' 
    });
    client.ping({
    	// ping usually has a 3000ms timeout
    	requestTimeout: 1000
    }, function (error) {
	    if (error) {
    	    console.trace('elasticsearch cluster is down!');
    	} else {
	        console.log('All is well');
	    }
    });

