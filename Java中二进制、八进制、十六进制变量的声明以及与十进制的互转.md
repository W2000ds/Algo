Java中数值变量进制的声明：
**二进制变量的声明以0b为前缀；**
**八进制变量的声明以0为前缀；**
**十六进制变量的声明以0x为前缀。**

二进制、八进制、十六进制数值在运用时候自动转为对应的十进制的值

```java
    public static void main(String[] args)
    {
        int a = 0b11;   //声明二进制变量
        int b = 011;    //声明八进制变量
        int c = 11;     //声明十进制变量
        int d = 0x11;   //声明十六进制变量
        System.out.println("a："+a); //3
        System.out.println("b："+b); //9
        System.out.println("c："+c); //11
        System.out.println("d："+d); //17
    }
```

**十进制转二进制：Integer.toBinaryString(i);**
**十进制转八进制：Integer.toOctalString(i);**
**十进制转十六进制：Integer.toHexString(i);**

```java
 public static void main(String[] args)
    {
        int a = 21;
        System.out.println("十进制21对应的二进制为："+Integer.toBinaryString(a));  //10101
        System.out.println("十进制21对应的八进制为："+Integer.toOctalString(a));   //25
        System.out.println("十进制21对应的十六进制为："+Integer.toHexString(a));    //15
    }
```

