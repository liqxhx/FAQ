# [常见的Socket异常](https://www.cnblogs.com/549294286/p/3947756.html)
# [java.net.SocketException: Connection reset的解决方案](https://blog.csdn.net/a718515028/article/details/79078508)
* 如果一端的Socket被关闭（或主动关闭，或因为异常退出而 引起的关闭），另一端仍发送数据，发送的第一个数据包引发该异常(Connect reset by peer)  

* 一端退出，但退出时并未关闭该连接，另一端如果在从连接中读数据则抛出该异常（Connection reset）

```java
public static byte[] sendMessage(String url, int port, byte[] request) {
        byte[] res = null;
        Socket socket = null;
        InputStream is = null;
        OutputStream os = null;
        try {
            socket = new Socket(url, port);
            os = socket.getOutputStream();
            os.write(request);
            os.flush();
            is = socket.getInputStream();
            ByteArrayOutputStream bos = new ByteArrayOutputStream();
            byte[] buffer = new byte[1024];
            int count = 0;
            do {
                count = is.read(buffer);
                bos.write(buffer, 0, count);
            } while (is.available() != 0);
            res = bos.toByteArray();
            os.close();
            is.close();
            socket.close();
        } catch (Exception ex) {
            try {
                if (is != null) {
                    is.close();
                }
                if (socket != null)
                    socket.close();
            } catch (Exception e) {
            }
        }
        return res;
    }
```
