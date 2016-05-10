# TZCompressor

## Introduction 

同意管理压缩任务的构件

## Installation
`maven`

```xml
<dependency>
    <groupId>tongji.sse</groupId>
    <artifactId>compress</artifactId>
    <version>1.0.0</version>
</dependency>
```

## Usage

1. 初始化
```java
TZCompressor tzCompressor = new TZCompressor();
```

2. 定义一个压缩任务,为压缩任务指定目标路径和资源目录

```java
CompressTask task = new CompressTask("archive/qq","logs"))
```
3. 为压缩任务设置参数

```java
task.setDelay(0);
task.setInterval(60*1000);
```

4. 执行压缩任务

```java
task.start();
```

5. 也可以把task交给TZCompressor管理

```java
tzCompressor.addTask(task,"qq");
// 也可以添加多个
tzCompressor.addTask(anotherTask,"other")
			  .addTask(...)
			  .addTask(...);
```

6. 执行压缩任务

```java
//指定执行
tzCompressor.startTask("qq");
//全部执行
tzCompressor.startAllTask();
```
7. 停止压缩任务
 
```java
//指定执行
tzCompressor.stopTask("qq");
//全部执行
tzCompressor.stopAllTask();
```



