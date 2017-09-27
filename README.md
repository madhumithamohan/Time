import java.net.*;
import java.io.*;
import java.util.*;
public class Timeserver
{
public static void main(String[] args)throws Throwable
{
DatagramSocket dsender =new DatagramSocket();
InetAddress addr = InetAddress.getLocalHost();
System.out.println("Server ready");
while(true)
{
Thread.sleep(1000);
Date date=new Date();
byte[] time=date.toString().getBytes();
DatagramPacket pac=new DatagramPacket(time,time.length,addr,2000);
dsender.send(pac);
}
}
}
