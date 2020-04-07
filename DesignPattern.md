## 设计模式

### 01单例模式
下面介绍3种线程安全的单例模式。

```

    /// <summary>
    /// 简单的线程安全的单例模式
    /// </summary>
    class Singleton01
    {
        private static readonly object _locker = new object();
        private static Singleton01 _singleton;
        private Singleton01() { }

        public static Singleton01 Instance
        {
            get
            {
                lock (_locker)
                {
                    if (_singleton == null)
                        _singleton = new Singleton01();
                }
                return _singleton;
            }
        }
    }

    /// <summary>
    /// 借助Lazy<T>，实现线程安全的单例模式非常简单
    /// </summary>
    class Singleton02
    {
        private Singleton02() { }
        private static Lazy<Singleton02> _singleton = new Lazy<Singleton02>(() => new Singleton02(), isThreadSafe: true);

        public static Singleton02 Instance
        {
            get
            {
                return _singleton.Value;
            }
        }
    }

    /// <summary>
    /// 借助嵌套类优雅地实现单例模式
    /// </summary>
    class Singleton03
    {
        private Singleton03() { }
        public static Singleton03 Instance { get {return Nested._singleton; } }

        private class Nested
        {
            // Explicit static constructor to tell C# compiler
            // not to mark type as beforefieldinit
            static Nested()
            {
            }
            internal static Singleton03 _singleton = new Singleton03();
        }
    }

```