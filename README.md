# openEduMedia
为教育准备的静态文件（视频流/文档/图片）解决方案

openEduMedia致力于提供静态文件的开源解决方案，构建通用的视频流/文档/图片 存储服务，对外提供标准接口，支持OAuth2/CAS/LDAP等标准认证协议，可以为任何系统所用

openEduMedia模仿存储服务领域最优秀的实现S3，为用户提供与云端存储服务无异的局域网实现

# 缘起
我过去两年的工作和教育相关，同高校打交道较多，信息技术在学校的应用越来越广泛，其中待填的坑也多。

开源运动在软件行业已经成为主流，前沿领域领域尤其如此，我近来比较热衷折腾ai/深度学习/nlp，在这些领域，人们采用开放的工具和组件，协作与共享。而在教育领域，春风未抵江南岸

高校技术方面坑多的原因在此不列举，前人述备矣。我比较关注信息的流通和共享，高校内信息孤岛众多，其中的一个重要原因是各个系统各自封闭，喜欢重造车轮，有方的有三角形的。深层的原因不论述。当然我们也看到好的变化，一些好的学校里，统一身份认证这种有利于协作的模式，正在流行，开放的接口也越来越多。国外高校流行的技术，国内也在借鉴，mooc兴起后，许多高校在资源上也有了开放的倾向，这些都是很酷的变化

我们将在openEduClub这个组织下，聚集对教育技术有兴趣的小伙伴，利用开源运动的成果，构建开放的组件和服务

# openEduMedia技术架构
openEduMedia选择的组件皆为开源组件，相关开源协议我们将在文末链接

openEduMedia将由以下组件构成：

*  nginx：作为静态文件/视频流服务器，同时也作为webapp的前端
  *  直播
  *  点播
  *  文件下载
*  minio：提供类S3的存储服务
  *  主流语言的SDK
*  webapp
  *  用户入口，用于管理（CURD）静态文件
  *  可以用任何语言实现，我将给出python实现范例
*  共享与协作
  *  标准认证接口（OAuth2/CAS/LDAP）在webapp里实现

# 设计原则
*  解耦，组件互相独立，可以单独选用
*  提供标准接口，在SDK之外，支持RESTful HTTP操作
