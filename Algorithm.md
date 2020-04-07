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

### 02冒泡排序

```
    class BubbleSort
{
    /// <summary>
    /// 冒泡升序排序
    /// </summary>
    /// <param name="oldArray"></param>
    /// <returns></returns>
    public static int[] SortByAscend(int[] oldArray)
    {
        for (int i = 0; i < oldArray.Length-1; i++)
        {
            for (int j = 0; j < oldArray.Length-1-i; j++)
            {
                if (oldArray[j]>oldArray[j+1])
                {
                    int temp = oldArray[j];
                    oldArray[j] = oldArray[j+1];
                    oldArray[j+1] = temp;
                }
            }
        }
        return oldArray;
    }
    /// <summary>
    /// 冒泡降序排序
    /// </summary>
    /// <param name="oldArray"></param>
    /// <returns></returns>
    public static int[] SortByDescend(int[] oldArray)
    {
        for (int i = 0; i < oldArray.Length - 1; i++)
        {
            for (int j = 0; j < oldArray.Length-1-i; j++)
            {
                if (oldArray[j] < oldArray[j+1])
                {
                    int temp = oldArray[j];
                    oldArray[j] = oldArray[j+1];
                    oldArray[j+1] = temp;
                }
            }
        }
        return oldArray;
    }
}


    var arr = new int[] { 1,3,5,9,6,5,2,4,8,3};
    var ascArr = BubbleSort.SortByAscend(arr);//输出结果：1,2,3,3,4,5,5,6,8,9
    Console.WriteLine(string.Join(",",ascArr));
    var arr2 = new int[] { 1, 3, 5, 9, 6, 5, 2, 4, 8, 3 };
    var descArr = BubbleSort.SortByDescend(arr2);//输出结果：9,8,6,5,5,4,3,3,2,1
    Console.WriteLine(string.Join(",", descArr));

```
