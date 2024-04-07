## 一、安装虚拟机

这里使用：VMware Workstation Player，下载地址：https://www.vmware.com/cn/products/workstation-player.html

### 1.下载其.exe文件：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231638683.png" alt="image-20240123163805561" style="zoom: 50%;" />

### 2.下载好后双击安装包

### 3.安装向导的操作：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231642563.png" alt="image-20240123164241526" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231643486.png" alt="image-20240123164351452" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231646325.png" alt="image-20240123164617287" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231647358.png" alt="image-20240123164712323" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231647254.png" alt="image-20240123164741215" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231648517.png" alt="image-20240123164807470" style="zoom:80%;" />

### 4.在桌面首次双击VMware：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231702061.png" alt="image-20240123170203038" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231702420.png" alt="image-20240123170224391" style="zoom:80%;" />

## 二、下载&配置Linux发行版

这里使用ubuntu的桌面版，下载地址：https://releases.ubuntu.com/18.04/

### 1.下载.iso文件：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231657143.png" alt="image-20240123165740111" style="zoom:67%;" />

### 2.配置ubuntu：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231730647.png" alt="image-20240123173019609" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231734100.png" alt="image-20240123173457066" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231737289.png" alt="image-20240123173705257" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231739288.png" alt="image-20240123173902233" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231741097.png" alt="image-20240123174125057" style="zoom:80%;" />
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231745566.png" alt="image-20240123174508529" style="zoom:80%;" />

---------------------------------分割线------------------------------------

正常情况下到这里就成功配置好了linux了，非常好，我这里遇到了问题：
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231749085.png" alt="image-20240123174938061" style="zoom:67%;" />

这个问题就是cpu没有开启虚拟化(可以在任务管理器->性能->cpu的界面看到是否开启虚拟化)，可以在bios配置开启虚拟化，具体步骤：

> 关机==->==开机的时候按F1/Del==->==进入bios==->==按F7==->==点选 [Advanced]页面并点选[CPU Configuration]选项==->==点选[Intel(VMX) Virtualization Technology]选项并设置为[Enabled]==->==按压键盘F10键，点击[Ok]

参考链接：

1. [虚拟机无法启动-CSDN博客](https://blog.csdn.net/weixin_44866492/article/details/135643479)
2. [Win11虚拟机平台怎么开？Win11打开自带虚拟机平台的方法 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/574675329)

## 三、修改linux配置

先启动并登入ubuntu，密码就是前面设置的密码。==注：==第一次启动大概需要等待13min左右，应该是在初始化（安装系统复制文件等）之类的。

### 1.修改语言为中文

按 `windows` 键，弹出功能搜索按钮，输入 "language"，打开 "region&language"，(忘截图了，拿中文的过来参考)：
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231713221.png" alt="图片" style="zoom:80%;" />

然后点击“manage installed languages”，选择中文简体，apply(这里会下载中文语法包和中文输入法)，然后把汉语拖到语言列表的最上面，最后点击应用到整个系统(这个只是将系统的语言应用为中文显示)：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231841622.png" alt="image-20240123184119514" style="zoom:80%;" />

并且然后注销:
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231845393.png" alt="image-20240123184509334" style="zoom: 67%;" />

重新登入后：
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231851172.png" alt="image-20240123185135123" style="zoom: 50%;" />

然后可以发现，虽然界面是中文了，但是却没法输入中文，所以需要配置中文输入法，同样是按 `windows` 键，弹出功能搜索按钮，输入 "language"，打开 "区域和语言"：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231713221.png" alt="图片" style="zoom:80%;" />

在区域和语言设置中，然后再输入源点击”+“号，添加已安装的中文输入法，然后选择汉语，选择第一个（即通过拼音输入中文）添加：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231713236.png" alt="图片" style="zoom:80%;" />

然后英文的输入源可以删除，格式也改为“中国”。

### 2.修改分辨率

按 `windows` 键，输入 "resolution"，打开“显示”：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231715774.png" alt="图片" style="zoom:80%;" />

然后可以调整分辨率和字体大小，这里我就不调整了：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231715997.png" alt="图片" style="zoom:80%;" />

### 2.修改时间

默认情况下系统的时区可能是有问题的，按 `windows` 键，输入 "time"，点击”日期和时间“，点击”时区“，输入“shanghai”，选择上海中国：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231715000.png" alt="图片" style="zoom:80%;" />

## 四、安装docker软件

这里用命令行安装，可以在ubuntu应用商店安装，但是ubuntu商店没有docker软件。

1. `ctrl+alt+t`打开命令行，输入`sudo apt install docker.io`，需要输入密码（密码不可见）
1. ctrl + L清屏，docker -v查看版本：![image-20240123190116016](https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401231901099.png)

补：执行docker run xxx：当发现没有对应镜像的时候，就会远程拉取对应镜像并输出一句xxx from docker，同时也表示docker安装成功。

## 五、容器化swagger

参考链接：[go restful 生成 swagger 2.0 文档](https://www.jianshu.com/p/a5ebc976650d)和[RESTful API 的实现与调用(GO 版本) ](https://www.cnblogs.com/vpc123/articles/17073613.html)和[Docker容器化部署Swagger三件套:Editor、Codegen、UI=](https://blog.csdn.net/MacwinWin/article/details/108682393)

### 1.swagger-editor安装

```shell
docker pull swaggerapi/swagger-editor
```

> 这步，我这里还需要另外在命令前加上sudo，才能安装成功。大概等待1-4分钟。下一步同理：

### 2.swagger-ui安装

```shell
docker pull swaggerapi/swagger-ui
```

### 3.启动swagger-ui

```shell
docker run -d -p 8082:8080 swaggerapi/swagger-ui
```
> 到这步我遇到报错：`Got permission denied while trying to connect to the Docker daemon socket`，大概意思就是当前用户权限不够，给该用户授权就好了，另外，用户名就是指上面自己设置的用户名，比如我的就是"kaomao"：
>
> 具体命令参考链接：
>
> - [解决Docker运行命令时提示"Got permission denied while trying to connect to the Docker daemon socket"类情况 - lmqljt - 博客园 (cnblogs.com)](https://www.cnblogs.com/Li-JT/p/13994704.html)
>
> - [linux中docker报错：ERROR: Got permission denied while trying to connect to the Docker daemon socket。-CSDN博客](https://blog.csdn.net/qq_45097352/article/details/116105246)

补充：启动swagger-editor（如果喜欢这个界面的，可以使用这个，否则也可以不安装swagger-editor）

```
 docker run -d -p 8081:8080 swaggerapi/swagger-editor
```

### 4.访问swagger服务：

访问这里的就是，先打开swagger-ui或swagger-editor的服务，如：https://ip:8082

> ip通过在ubuntu按ctrl+alt+t，输入`ifconfig`查找，ens33下的inet就是虚拟机的ip了。
> <img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241140611.png" alt="image-20240124113956502" style="zoom: 55%;" />

### 5.连接json

#### 1.swagger-ui方式：

swagger-ui顶部输入json的位置：
![image-20240124114433740](https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241144775.png)

#### 2.swagger-editor方式：

如图：
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241146347.png" alt="image-20240124114656278" style="zoom:60%;" />

### 6.docker关闭：

1. `docker stop $(docker ps -a -q)`：[docker启动、关闭命令 容器启动与关闭命令_关闭容器的命令是什么?-CSDN博客](https://blog.csdn.net/qq_36838191/article/details/89209539)

## 六、使用

### 前言

现在看起来还可以？不！没办法给后端发送请求！因为swagger并没有配置好，贴上配置好的代码(其实就是配置了请求的ip)：

```go
func SwaggerConfig(wsContainer *restful.Container) {
	config := restfulspec.Config{
		WebServices:                   wsContainer.RegisteredWebServices(),
		APIPath:                       "/apidocs.json",
		PostBuildSwaggerObjectHandler: enrichSwaggerObject}
	wsContainer.Add(restfulspec.NewOpenAPIService(config))
}

func enrichSwaggerObject(swo *spec.Swagger) {
	swo.Info = &spec.Info{
		InfoProps: spec.InfoProps{
			Title:       "边缘开发 框架的API文档",
			Description: "这是 边缘开发 框架文档，根据文档调用API",
			Contact: &spec.ContactInfo{
				ContactInfoProps: spec.ContactInfoProps{
					Name:  "边缘开发",
					URL:   "http://www.aurine.cn",
					Email: "aurinerd@aurine.cn",
				},
			},
			License: &spec.License{
				LicenseProps: spec.LicenseProps{
					Name: "MIT",
					URL:  "http://www.aurine.cn",
				},
			},
			Version: "1.0.0",
		},
	}
    //下面的配置使后面的请求地址为：https://localhost:39999/path下的接口
	swo.Host = "localhost:39999" //后端地址
	swo.Schemes = []string{"http"} //这里建议用http,http会报错
}
```

然后，发生了跨域问题，好好好，好好好，这么玩。上代码（这里的跨域的ip是虚拟机swagger的域，请根据自己的情况来配置）：

```go
package middleware

import (
   "github.com/emicklei/go-restful/v3"
)

// 处理跨域请求,支持options访问
func Cors(wsContainer *restful.Container) restful.CrossOriginResourceSharing {
   cors := restful.CrossOriginResourceSharing{
      ExposeHeaders:  []string{"Content-Length", "Access-Control-Allow-Origin", "Access-Control-Allow-Headers", "Content-Type"},
      AllowedDomains: []string{"http://192.168.163.129:8082", "http://192.168.163.129:8082", "http://localhost:30080", "https://localhost:30080"},
      AllowedHeaders: []string{"Content-Type", "AccessToken", "X-CSRF-Token", "Authorization", "Token", "X-Token", "X-User-Id"},
      AllowedMethods: []string{"POST", "GET", "OPTIONS", "DELETE", "PUT"},
      CookiesAllowed: false,
      Container:      wsContainer}

   return cors
}
```

至此，就可以开整了!

### 1.使用:

这里以公司重构项目为例：

#### ①首先

我们需要先登入，通过`system/user/login`接口获取token，图二是获取的token值：

<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241653235.png" alt="image-20240124150837446" style="zoom:55%;" /><img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241653748.png" alt="image-20240124151123495" style="zoom:60%;" />

#### ②其次

是去`/system/user/auth`接口:

这里需要给请求头添加一个字段(token就是放在这里的，细节可以去看前置函数，这里也可以直接传参token，不用放在请求头，根据自己需求改就好了)

```go
ws.Route(ws.GET("/auth").To(func(request *restful.Request, response *restful.Response) {
   restfulx.NewReqCtx(request, response).WithNeedCasbin(false).WithLog("认证信息").Handle(s.Auth)
}).
   Doc("认证信息").
   Param(ws.QueryParameter("username", "username").DataType("string")).
   Param(ws.QueryParameter("menuGroup", "menuGroup").DataType("string")).
   Param(ws.HeaderParameter("X-TOKEN", "X-TOKEN").DataType("string")).
   Metadata(restfulspec.KeyOpenAPITags, tags).
   Writes(vo.AuthVo{}).
   Returns(200, "OK", vo.AuthVo{}))
```
<img src="https://cdn.jsdelivr.net/gh/nmdsbzmhbkyy/images@main/imgs/202401241658529.png" alt="image-20240124165854450" style="zoom:67%;" />

然后其他的接口都同理(应该)，都要带上token，因为这里大批量需要token，所以建议直接在模版文档里面加上就好了。

## other

关于请求发送工具的选择：

> 1. swagger-ui/swagger-edit
>    1. 这两个都差不多，好处主要是，可以看到curl和更直观的文档(但是只是为了测试的话，其实很多信息是可以不用看的)，缺点就是，得开虚拟机和容器，不过有网页版的，笑:)
>    2. swagger-ui：界面相比于edit会简单一点
>    3. :star:swagger-edit：这个是好处就是，可以在线修改json文档（比如前面的json，这个时候建议后端生成的时候给token添加一个默认值，什么默认值都好，主要是这样可以批量替换token，后面发送请求时，可以不用再额外填token了。按ctrl+f，然后在弹出的小弹窗，点下拉小按钮）
>    4. 补充：有些值比如登入的用户名，这种可以直接在后端写好默认值（没有保存功能是这样的）
>    5. 反正能接受它的界面丑，这种方式还是很不错，head也很方便填写
> 2. 另外推荐apifox
>    1. 优点：
>       1. 在线的，至少不用再开一个软件，某个程度上还是有点方便的
>       2. 可以自动生成较真实mock数据(但是只是简单的测试，倒是没必要，就算是测压，也有专门的工具)
>    2. 缺点：
>       1. 填写头部的时候，还要额外点一下head，建议apifox学一下knife4j
>    3. 适合的场景：它是在线的且可视化也还可以，所以感觉比较时候对颜值要求高然后功能较完善的时候使用。
> 3. 关于postman，感觉不太方便，一个是启动慢，还有一个是左边的缩略标签选择有点麻烦，得一层一层点(虽然可以直接搜就是了)。
> 4. 当然，什么时候有平替的knife4j就更好了，knife4j的界面才是真香，看网上说可以替换对应的文件。
> 5. 我推荐用apidoc



下面的有需要的话可以康康，主要是关于swagger.json文件的扩展：

1. docker的端口映射是什么意思：[docker网络之端口映射 =](https://zhuanlan.zhihu.com/p/194307604#:~:text=端口映射主要原理是利用host机的ip地址和端口来访问容器ip和端口，类似我们的家用路由器开启的端口映射，能够将运营商分配的公网IP%2B端口映射成为路由器下方的IP%2B端口。,在端口映射之前先把容器整体架构图放上。 端口映射工作在PREROUTING这个椭圆处。)

2. [如何将 Swagger 导出为 JSON、Markdown、PDF、Word 文档 (apifox.com)](https://apifox.com/apiskills/how-to-export-swagger-md-pdf-word/)
3. [如何将swagger导出为优雅的doc或者pdf文档_swagger doc-CSDN博客](https://blog.csdn.net/weixin_43748936/article/details/111841739#:~:text=如何将swagger json导出为优雅的doc或者pdf文档 所需要的工具： 第一步%3A,第二步： 第三步： %23需求：项目完成后领导要求出一个后端的接口文档，文档要求：输入参数（请求参数），输出参数（响应参数）要清晰明了，即不管是输入参数还是输出参数都要有参数说明。 然后输入输出参数要和实际保持一致。)
4. [swagger + DOCWAY 一步导出为优雅完整的markdown、pdf接口文档-CSDN博客](https://blog.csdn.net/weixin_73077810/article/details/131668462)
5. [ChromeFK插件推荐系列十三:API接口插件推荐_谷歌浏览器 techapi插件-CSDN博客](https://blog.csdn.net/w116858389/article/details/105290223/?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0--blog-131668462.235^v40^pc_relevant_3m_sort_dl_base4&spm=1001.2101.3001.4242.1&utm_relevant_index=3)
6. [如何将swagger json导出为优雅的doc或者pdf文档（详细版）_swagger.json转换-CSDN博客](https://blog.csdn.net/weixin_43748936/article/details/112526592)
7. showdoc

吐槽：gorestful迟到被替代，怎么会有把
