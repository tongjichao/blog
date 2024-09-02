+++
title = 'file xx has a name conflict over xx'
date = 2023-12-04T16:25:59+08:00


+++


最近在编译使用proto时，遇到报错，错误如下

```
panic: proto: file "bytedance.proto" has a name conflict over OAID
previously from: "xxx/baidu"
currently from:  "xxx/bytedance"
See <https://protobuf.dev/reference/go/faq#namespace-conflict>
```
**截图如下**

![截图](/img/pb.jpg)

从报错中，图中错误解决连接，访问，官网给出两种解决方案，分别如下：

![截图2](/img/f2.jpg)

1.方案一：编译器修改： 编译代码时指定  -ldflags "-X google.golang.org/protobuf/reflect/protoregistry.conflictPolicy=warn"

2.方案二：运行时指定 GOLANG_PROTOBUF_REGISTRATION_CONFLICT=warn 即可