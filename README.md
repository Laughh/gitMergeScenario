## Usage
client中的output是conflict文件和conflict tuple输出的路径，gitPath是git仓库下载和存放的路径，可以自行修改。

需要进行分析的repo可以按照addSimpleRepo中的格式手动设置。即(项目名，远程URL)，设置好之后直接运行client的main方法。

jgit的clone指令由于国内的网络问题，可能会出错，需要先手动下载到本地。

## Function
#### 收集conflict文件
遍历git历史，收集conflict文件，输出到output/conflictFiles中，以commitId\filepaht\filename.java\conflict files的格式存储
#### 收集conflict tuple
遍历上一个步骤收集到的flies，从conflict marks中抽取出conflict tuple，以projectname.json的格式存储到output/mergeTuples中
#### 对conflict tuple进行统计
统计结果输出到标准输出中，如：

<img width="435" alt="image" src="https://user-images.githubusercontent.com/61650772/178206331-3eb4b3ca-4567-42d8-8387-21c96a6bd8ef.png">
