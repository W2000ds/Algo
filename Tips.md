### 保留需要位数，四舍五入

> double d = 123.212378;
> String s = String.format("%.nf", d);
> double v = Double.parseDouble(s);

> byte：-2^7 ~ 2^7-1，即-128 ~ 127。1字节。Byte。末尾加B
>
> short：-2^15 ~ 2^15-1，即-32768 ~ 32767。2字节。Short。末尾加S
>
> 有符号int：-2^31 ~ 2^31-1，即-2147483648 ~ 2147483647。4字节。Integer。
>
> 无符号int：0~2^32-1。
>
> long：-2^63 ~ 2^63-1，即-9223372036854774808 ~ 9223372036854774807。8字节。Long。末尾加L。（也可以不加L）
>

BigDeminal&BigInteger

```java
package ustc.lichunchun.bigdataapi;
 
import java.math.BigInteger;
 
public class BigIntegerDemo1 {
 
	public static void main(String[] args) {
		BigInteger bi1 = new BigInteger("123456789") ;	// 声明BigInteger对象
		BigInteger bi2 = new BigInteger("987654321") ;	// 声明BigInteger对象
		System.out.println("加法操作：" + bi2.add(bi1)) ;	// 加法操作
		System.out.println("减法操作：" + bi2.subtract(bi1)) ;	// 减法操作
		System.out.println("乘法操作：" + bi2.multiply(bi1)) ;	// 乘法操作
		System.out.println("除法操作：" + bi2.divide(bi1)) ;	// 除法操作
		System.out.println("最大数：" + bi2.max(bi1)) ;	 // 求出最大数
		System.out.println("最小数：" + bi2.min(bi1)) ;	 // 求出最小数
		BigInteger result[] = bi2.divideAndRemainder(bi1) ;	// 求出余数的除法操作
		System.out.println("商是：" + result[0] + 
			"；余数是：" + result[1]) ;
	}
}
```

```java
package ustc.lichunchun.bigdataapi;
 
import java.math.BigDecimal;
 
public class BigDecimalDemo01 {
 
	public static void main(String[] args) {
		System.out.println("加法运算：" + MyMath.round(MyMath.add(10.345,3.333),1)) ;
		System.out.println("减法运算：" + MyMath.round(MyMath.sub(10.345,3.333),3)) ;
		System.out.println("乘法运算：" + MyMath.round(MyMath.mul(10.345,3.333),4)) ;
		System.out.println("除法运算：" + MyMath.div(10.345,3.333,3)) ;
	}
}
class MyMath{
	public static double add(double d1,double d2){		// 进行加法计算
		BigDecimal b1 = new BigDecimal(d1) ;
		BigDecimal b2 = new BigDecimal(d2) ;
		return b1.add(b2).doubleValue() ;
	}
	public static double sub(double d1,double d2){		// 进行减法计算
		BigDecimal b1 = new BigDecimal(d1) ;
		BigDecimal b2 = new BigDecimal(d2) ;
		return b1.subtract(b2).doubleValue() ;
	}
	public static double mul(double d1,double d2){		// 进行乘法计算
		BigDecimal b1 = new BigDecimal(d1) ;
		BigDecimal b2 = new BigDecimal(d2) ;
		return b1.multiply(b2).doubleValue() ;
	}
	public static double div(double d1,double d2,int len){		// 进行除法计算
		BigDecimal b1 = new BigDecimal(d1) ;
		BigDecimal b2 = new BigDecimal(d2) ;
		return b1.divide(b2,len,BigDecimal.ROUND_HALF_UP).doubleValue() ;
	}
	public static double round(double d,int len){	// 进行四舍五入
		BigDecimal b1 = new BigDecimal(d) ;
		BigDecimal b2 = new BigDecimal(1) ; // 技巧
		return b1.divide(b2,len,BigDecimal.ROUND_HALF_UP).doubleValue() ;
	}
};
```



二分模板



归并排序



最大公约数与最小公倍数

```java
static int gcd(int a,int b){
       return b == 0 ? a:gcd(b,a%b);
     }
//返回值为a和b的最小公倍数
int lcm(int a, int b){
	return a/gcd(a,b)*b;//最小公倍数=两数之积÷两数最大公约数    
	}
```

日历类

```java
1 cal.set (2013, 5, 4, 13, 44, 51)；//年月日时分秒 (月份0代表1月) 
2 cal.set (Calendar.YEAR, 2014)；//年 
3 cal.set (Calendar.MONTH, 7)；//月 (月份0代表1月) 
4 cal.set (Calendar.DATE, 11)；//日 
5 cal.set (Calendar.HOUR_OF_DAY, 15)；//时 
6 cal.set (Calendar.MINUTE, 33)；//分 
7 cal.set (Calendar.SECOND, 32)；//秒 
//获取
1 cal.get (Calendar.YEAR)；//年 
2 cal.get (Calendar.MONTH) + 1;//月 (必须要+1) 
3 cal.get (Calendar.DATE)；//日 
4 cal.get (Calendar.HOUR_OF_DAY)；//时 
5 cal.get (Calendar.MINUTE)；//分 
6 cal.get (Calendar.SECOND)；//秒 
7 cal.get (Calendar.DAY_OF_WEEK)；//星期 (Locale.ENGLISH情况下，周日是1,剩下自己推算)
//加
    cal.add (Calendar.YEAR, 1)；//年 
 cal.add (Calendar.MONTH, 1)；//月 
 cal.add (Calendar.DATE, 1)；//日 
 cal.add (Calendar.HOUR_OF_DAY, -1)；//时 
cal.add (Calendar.MINUTE, 1)；//分 
 cal.add (Calendar.SECOND, 1)；//秒 
 cal.add (Calendar.DATE, 7)；//周
```

BufferReader

```java
	   InputStreamReader in = new InputStreamReader(System.in);
        BufferedReader br = new BufferedReader(in);
        String[] nums = br.readLine().split(" ");

        n = Integer.parseInt(nums[0]);
        m = Integer.parseInt(nums[1]);
```

StringBuilder

```java
StringBuilder sb = new StringBuilder();
// 对象名.length() 序列长度
System.out.println(sb.length());  // 0
// 对象名.append() 追加到序列
sb.append("hello");
System.out.println(sb);  // hello
// 97代表的是是'a'
sb.appendCodePoint(97);
System.out.println(sb);  // helloa
// 链式编程
sb.append(1).append("world").append(2);
System.out.println(sb);  // helloa1world2
// 索引是5的位置替换成空格
sb.setCharAt(5, ' ');
System.out.println(sb);  // hello 1world2
// 指定位置0前插入0
sb.insert(0, 0);
System.out.println(sb);  // 0hello 1world2
// 删除索引6(包含)至索引14(不包含)的字符串
sb.delete(6, 14);
System.out.println(sb);  // 0hello
// StringBuilder类型转换成String类型
String s = sb.toString();
System.out.println(s);  // 0hello

// 以及还有截取、反转、替换等方法
```

计算质数

```java
bool is_prime(int n){
    if(n < 2) return false;
    for(int i = 2;i <= n / i;i ++){ //优化内容
        if(n % i == 0){
            return false;
        }
    }
    return true;
}
```

```java
String.valueOf(i)//int型转String
```

