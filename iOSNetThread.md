<h3 id="￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼net"> ￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼网络与多线程 </h3>

**进程的基本概念**


**多线程的基本概念**


**线程的创建与启动**

```
￼￼// 4.block语法启动⼀一个线程
    [threadQueue addOperationWithBlock:^(void) {
if (![t isMainThread]) {
}
NSInvocationOperation *op = [[NSInvocationOperation alloc] initWithTarget:self
                                                                 selector:@selector(mutableThread)
                                                                   object:nil];
[threadQueue addOperation:op];
```

**NSThread的常用方法**

```
 (BOOL)isMultiThreaded;
 (NSThread *)currentThread;
 (void)sleepForTimeInterval:(NSTimeInterval)ti;
// 退出当前线程
 (void)exit;
 (BOOL)isMainThread
```

**GCD(Grand Central Dispatch)**

```
// 创建⼀一个队列
// 创建异步线程
    dispatch_async(dispatch_get_main_queue(), ^{
    });
```

**子线程的内存管理**

```
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼// 创建⼦子线程
- (void)mutableThread {
    // 创建⾃自动释放池
                          withObject:nil
                      waitUntilDone:NO];
```

**NSRunloop的基本概念**

- 线程的生命周期存在五个状态:新建、就绪、运行、阻塞、死亡 
- NSRunLoop可以保持一个线程一直为活动状态,不会马上销毁掉

**定时器在多线程的使用**

在多线程中使用定时器必须开启Runloop,因为只有开启Runloop保持线程为活动 状态,才能保持定时器能不断执行

```
￼￼- (void)runThread {
                                     target:self
                                   selector:@selector(timeAction)
                                   userInfo:nil
                                    repeats:YES];
     // 开启Runloop来使线程保持存活状态
     [[NSRunLoop currentRunLoop] run];
     [pool release];
```

**￼￼￼￼￼￼￼￼HTTP请求**

```
Http请求主要由两部分组成:http请求头、http请求体 ·POST请求才有请求体 ·请求的参数有两种形式:1.放在URL后面,2.放在请求体中
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼URL: http://weibo.com/mechenwei?page=1&pagesize=20
```

**￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼HTTP响应**

HTTP响应主要由两部分组成:响应头、响应内容 ·HTTP响应有个状态码,标示响应的结果,例如200表示成功,404未找到页面

```
HTTP响应头:
```

**￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼访问网络的基本流程**
- 生成NSURLRequest请求
- 通过NSURLConnection发送请求
- 通过返回NSURLRespond实例和NSError实例分析结果
- 接受返回数据


```
timeoutInterval 超时时间 
NSURLRequest *request = [NSURLRequest requestWithURL:url cachePolicy:NSURLRequestUseProtocolCachePolicy timeoutInterval:60];
```

```
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼NSMutableURLRequest *request = [[NSMutableURLRequest alloc] init];
```

**  同步请求用法**

```
// 构造url
```

**￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼异步请求用法**

- 第一种方式

```
    [_data appendData:data];
} 

// 接受加载的数据
} 
// 数据加载完以后调⽤用
```

- 第二种方式

```
// 开一个子线程
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼- (IBAction)asychroRequest:(id)sender {
// 启动⼀一个新的线程加载数据
```

**xml和json的基本概念**

**￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼解析的开源框架**

- XML Sax解析,NSXMLParser等
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼














































