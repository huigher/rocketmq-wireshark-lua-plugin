forked from [arthur-zhang/rocketmq-wireshark-lua-plugin](https://github.com/arthur-zhang/rocketmq-wireshark-lua-plugin)

修改点：
1. 将原有的固定端口自动解码转换为通过"Decode As..."方式动态解码，便于一些使用非标RocketMQ端口场景

已知问题：
1. 目前是通过远端端口是否大于10000来判断数据包是Request还是Response，在一些极端场景下，比如客户端本地端口轮转特别快、或者服务端使用了大于10000的非标RocketMQ端口，会导致识别出错。未来可能会修改为通过header中的flag来判断……