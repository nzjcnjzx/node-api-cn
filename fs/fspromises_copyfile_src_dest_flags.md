< !——YAML
补充:v10.0.0
- - >

*“src”{string|Buffer|URL}源文件名复制
*“dest”{string|Buffer|URL}复制操作的目标文件名
*“标志”{数字}修饰符用于复制操作。* *默认值:* *“0”。
*返回:{承诺}

异步复制' src '到' est '。默认情况下，如果是“最”，就会被覆盖。
已经存在。“承诺”将会得到解决，没有关于成功的争论。

节点。js不保证复制操作的原子性。如果一个
在打开要写入的目标文件Node.js之后发生错误
将尝试删除目标。

“flags”是一个指定行为的可选整数
复制操作。可以创建一个由位元组成的掩码
或两个或两个以上的值。
“fs.constants。COPYFILE_EXCL | fs.constants.COPYFILE_FICLONE”)。

*’fs.constants。COPYFILE_EXCL ' -复制操作将会失败，如果是“最好的”。
的存在。
*’fs.constants。复制操作将尝试创建一个
即写即拷reflink。如果平台不支持写时复制，则a
使用回退复制机制。
*’fs.constants。COPYFILE_FICLONE_FORCE '——复制操作将尝试这样做
创建一个即写即拷reflink。如果平台不支持写时复制，
然后操作将失败。

例子:

”“js
const fs =要求(fs);

/ /目的地。txt将在默认情况下被创建或覆盖。
fsPromises.copyFile(“源。txt”、“destination.txt”)
犹豫(()= > console.log(来源。txt被复制到destin.txt ')
.catch(()= >控制台。日志(“无法复制文件”);
' ' '

如果第三个参数是一个数字，那么它指定“flags”，如
下面的例子。

”“js
const fs =要求(fs);
const {COPYFILE_EXCL} = fs.constant;

//使用COPYFILE_EXCL，如果目的地失败，操作将失败。三种存在。
fsPromises.copyFile(“源。txt”、“目的地。txt”,COPYFILE_EXCL)
犹豫(()= > console.log(来源。txt被复制到destin.txt ')
.catch(()= >控制台。日志(“无法复制文件”);
' ' '
