# java多用户聊天程序的实现过程。服务端客户端都需要多线程吗?

Q:

谁能给我说一下java多用户聊天程序的实现过程。服务端客户端都需要多线程吗？需要把IP和用户ID一对一存起来还是存线程或者存socket

A:

服务端需要创建线程池来管理客户端的连接线程，避免系统资源过度浪费。也就是说服务端的socket一直监听，有请求进来就把这个请求分配给线程池去处理，而socket继续监听，接受下一个请求，如果让socket自己来处理请求，则后续的请求就都无法进入了。
服务端以map形式存放客户端数据，key=客户名称；value=聊天内容，即存放客户端的输出流。

如果需要代码，我可以给你一套参考。

追问

```
每个用户对应一个服务端线程吗？线程池可以将线程和用户对应起来？不用IP？
```

追答

```
作为客户端，在使用的时候先创建昵称，并且把昵称发送到服务端进行验证，如果该昵称被占用了，则改名，如果可以用，则服务端返回信息，xx昵称，你好。Map里面存放的是昵称和客户端的输出流。
```

追问

```
不懂。我以为是接受到一个客户端的socket然后建立一个对应的线程？用这个线程单独的和该用户交流。
同学说要用IP我就不会了
```

追答

没有这么麻烦的。我给你一个客户端的代码，你一目了然。

```java
public class chatClient {
	private Socket clientSocket;

public chatClient()
	{
		try 
		{

			clientSocket = new Socket("localhost",12580);
			
		} 
		catch (Exception e) 
		{
			e.printStackTrace();
		}
	}

/*
	* 客户端启动的方法
	*/
	public void start()
	{
		try
		{
			/*
			* 创建Scanner，读取用户输入内容
			* 目的是设置客户端的昵称
			*/
			Scanner scanner = new Scanner(System.in);
			inputNickName(scanner);
			
			/*
			* 将用于接收服务器端发送过来的信息的线程启动
			*/
			Runnable run = new GetServerMsgHandler();
			Thread t = new Thread(run);
			t.start();		
			
			/*
			* 建立输出流，给服务端发信息
			*/
			OutputStream os = clientSocket.getOutputStream();
			OutputStreamWriter osw = new OutputStreamWriter(os,"UTF-8");
			PrintWriter pw = new PrintWriter(osw,true);
			
			while(true)
			{
				pw.println(scanner.nextLine());
			}
		}
		catch(Exception e)
		{
			e.printStackTrace();
		}
		finally
		{
			if(clientSocket !=null)
			{
				try
				{
					clientSocket.close();
				}
				catch(IOException e)
				{
					e.printStackTrace();
				}
			}
		}
	}

public static void main(String[] args)
	{
		chatClient client = new chatClient();	
		client.start();
	}
}
```

追问

```
一个电脑多个账号用的是客户端多线程吗？
还有服务端是怎么转发聊天信息的
```

追答

```
我这个聊天是个简单的，没有账号，只有昵称，服务端转发聊天信息分两种，群发或者是私聊，这是我写的，如果你需要看代码，这里发不上来，留联系方式吧。
```

https://zhidao.baidu.com/question/391894846780647445.html