## 算法

### 01斐波那契数列
有一列数1，1，2，3，5，8，........，求第30个数。

```
    class Fibonacci
    {
        public static int F(int n)
        {
            if (n <= 2) return 1;
            return F(n - 2) + F(n - 1);
        }
    }

    var i=Fibonacci.F(30);
    Console.WriteLine(i);//832040

```
