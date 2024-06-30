shell 使用split命令将文件grpc-app.zip分割成最大50mb小块
split -b 50m grpc-app.zip grpc-app-part-

这个命令使用 split 工具将名为 grpc-app.zip 的文件分割成最大 50MB 的小块文件。

具体操作如下：

split -b 50m grpc-app.zip grpc-app-part-
-b 50m 表示每个小块文件的最大大小为 50MB
grpc-app.zip 是要分割的源文件
grpc-app-part- 是生成的小块文件的前缀名称
这样就会在当前目录下生成一系列名为 grpc-app-part-aa、grpc-app-part-ab、grpc-app-part-ac 等的小块文件。这些小块文件可以单独传输或备份,然后在需要的时候重新合并。

如何重新合并

要重新合并分割好的文件,可以使用以下命令:

复制
cat grpc-app-part-* > grpc-app.zip
这个命令会将所有名称以 grpc-app-part- 开头的文件连接起来,生成一个名为 grpc-app.zip 的完整文件。

具体步骤如下:

确保所有分割好的文件都在同一个目录下。
运行命令 cat grpc-app-part-* > grpc-app.zip
cat 命令用于连接多个文件
grpc-app-part-* 是使用通配符匹配所有以 grpc-app-part- 开头的文件
> grpc-app.zip 将连接后的内容重定向到 grpc-app.zip 文件中
运行这个命令后,就可以得到一个与原始 grpc-app.zip 文件内容完全相同的文件了。
