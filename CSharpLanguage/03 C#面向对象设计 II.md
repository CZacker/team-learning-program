


# 03 C#���������� II


**֪ʶ�ṹ��**

![ͼ1 ֪ʶ�ṹ](https://img-blog.csdnimg.cn/20200909155219848.png)

---
## 5������

��1�����Ը�������루���⣩

![ͼ2 Class Diagram](https://img-blog.csdnimg.cn/20200908121525946.png)


```c
public class Animal
{
    public int Age;
    public double Weight;
    public bool Sex;
    public Animal(int age, double weight, bool sex)
    {
        Age = age;
        Weight = weight;
        Sex = sex;
    }
    public void Eat()
    {
        Console.WriteLine("Animal Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Animal Sleep.");
    }
    public override string ToString()
    {
        return string.Format("Animal Age:{0},Weight:{1},Sex:{2}",
            Age, Weight, Sex);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal al = new Animal(1, 1.2, false);
        Console.WriteLine("Animal Age:{0},Weight:{1},Sex:{2}",
            al.Age, al.Weight, al.Sex);
        // Animal Age:1,Weight:1.2,Sex:False

        al.Age = -1;
        al.Weight = -0.5;
        Console.WriteLine(al);
        // Animal Age:-1,Weight:-0.5,Sex:False
    }
}
```

��2������Ľ����Java���Խ��������ķ�����

![ͼ3 Class Diagram](https://img-blog.csdnimg.cn/20200908121838952.png)

```c
public class Animal
{
    private int _age;
    private double _weight;
    private readonly bool _sex;
    public int GetAge()
    {
        return _age;
    }
    public void SetAge(int value)
    {
        _age = (value > 0) ? value : 0;
    }
    public double GetWeight()
    {
        return _weight;
    }
    public void SetWeight(double value)
    {
        _weight = (value > 0) ? value : 0;
    }
    public bool GetSex()
    {
        return _sex;
    }
    public Animal(int age, double weight, bool sex)
    {
        _age = (age > 0) ? age : 0;
        _weight = (weight > 0) ? weight : 0;
        _sex = sex;
    }
    public void Eat()
    {
        Console.WriteLine("Animal Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Animal Sleep.");
    }
    public override string ToString()
    {
        return string.Format("Animal Age:{0},Weight:{1},Sex:{2}",
            _age, _weight, _sex);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal al = new Animal(1, 1.2, false);
        Console.WriteLine("Animal Age:{0},Weight:{1},Sex:{2}",
            al.GetAge(), al.GetWeight(), al.GetSex());
        // Animal Age:1,Weight:1.2,Sex:False

        al.SetAge(-1);
        al.SetWeight(-0.5);
        Console.WriteLine(al);
        // Animal Age:0,Weight:0,Sex:False
    }
}
```

��3�����Ե����

![ͼ4 Class Diagram](https://img-blog.csdnimg.cn/20200908122140438.png)

```c
public class Animal
{
    private int _age;
    private double _weight;
    private readonly bool _sex;
    public int Age
    {
        get { return _age; }
        set { _age = (value > 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value > 0) ? value : 0; }
    }
    public bool Sex
    {
        get { return _sex; }
    }
    public Animal(int age, double weight, bool sex)
    {
        _age = (age > 0) ? age : 0;
        _weight = (weight > 0) ? weight : 0;
        _sex = sex;
    }
    public void Eat()
    {
        Console.WriteLine("Animal Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Animal Sleep.");
    }
    public override string ToString()
    {
        return string.Format("Animal Age:{0},Weight:{1},Sex:{2}",
            Age, Weight, Sex);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Animal al = new Animal(1, 1.2, false);
        Console.WriteLine("Animal Age:{0},Weight:{1},Sex:{2}",
            al.Age, al.Weight, al.Sex);
        // Animal Age:1,Weight:1.2,Sex:False

        al.Age = -1;
        al.Weight = -0.5;
        Console.WriteLine(al);
        // Animal Age:0,Weight:0,Sex:False
    }
}
```

˵����C#������dataʱ�Ϳ��Զ���`set`��`get`������
- `get`�������ȡ������
- `set`�����帳ֵ������`value`��ʾ����Ĳ���ֵ��

��4�����Եļ�

![ͼ5 Class Diagram](https://img-blog.csdnimg.cn/20200908123716795.png)

```c
public class Animal
{
    private int _age;
    private double _weight;
    public int Age
    {
        get { return _age; }
        set { _age = (value > 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value > 0) ? value : 0; }
    }
    public bool Sex { get; private set; }
    public Animal(int age, double weight, bool sex)
    {
        _age = (age > 0) ? age : 0;
        _weight = (weight > 0) ? weight : 0;
        Sex = sex;
    }
    public void Eat()
    {
        Console.WriteLine("Animal Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Animal Sleep.");
    }
    public override string ToString()
    {
        return string.Format("Animal Age:{0},Weight:{1},Sex:{2}",
            Age, Weight, Sex);
    }
}
class Program
{
    static void Main(string[] args)
    {
        Animal al = new Animal(1, 1.2, false);
        Console.WriteLine("Animal Age:{0},Weight:{1},Sex:{2}",
            al.Age, al.Weight, al.Sex);
        // Animal Age:1,Weight:1.2,Sex:False

        al.Age = -1;
        al.Weight = -0.5;
        Console.WriteLine(al);
        // Animal Age:0,Weight:0,Sex:False
    }
}
```


---
## 6��������

**6.1 ����**

�Ǽ������е�һ���������ԣ���ʹ�ü������е�Ԫ��������Ԫ��һ�����ʡ�

**6.2 �﷨�ṹ**

```c
public Ԫ������ this[int index]
{
    get { ... }
    set { ... }
}
public Ԫ������ this[string name]
{
    get { ... }
    set { ... }
}
```

��5������������ʵ�ֶԼ�����`StudentSet`��Ԫ��`Student`�ķ��ʡ�

![ͼ6 Class Diagram](https://img-blog.csdnimg.cn/20200908125836707.png)

```c
public class Student
{
    private string _name;
    public string Name
    {
        get { return _name; }
        set
        {
            _name = string.IsNullOrEmpty(value)
                ? "NULL"
                : value;
        }
    }
    public long ID { get; set; }
    public Student(long id, string name)
    {
        ID = id;
        _name = name;
    }
    public override string ToString()
    {
        return string.Format("ID:{0},Name:{1}", ID, Name);
    }
}

public class StudentSet
{
    private readonly int _maxCount = 500;
    private readonly Student[] _stus;
    public int Count
    {
        get; private set;
    }
    public StudentSet()
    {
        Count = 0;
        _stus = new Student[_maxCount];
    }
    public void Add(Student stu)
    {
        if (stu == null)
            throw new ArgumentNullException();
        if (Count == _maxCount)
            throw new IndexOutOfRangeException();

        _stus[Count] = stu;
        Count++;
    }
    public Student this[int index]
    {
        get
        {
            if (index < 0 || index > Count - 1)
                throw new IndexOutOfRangeException();
            return _stus[index];
        }
        set
        {
            if (index < 0 || index > Count - 1)
                throw new IndexOutOfRangeException();

            if (value == null)
                throw new ArgumentNullException();
            _stus[index] = value;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        StudentSet stuSet = new StudentSet();
        stuSet.Add(new Student(10086, "����"));
        stuSet.Add(new Student(95988, "����"));
        stuSet[1].Name = string.Empty;
        Console.WriteLine(stuSet.Count); // 2
        Console.WriteLine(stuSet[0]); // ID:10086,Name:����
        Console.WriteLine(stuSet[1]); // ID:95988,Name:NULL
        Console.WriteLine(stuSet[2]);
        //δ������쳣:  System.IndexOutOfRangeException: ����������������ޡ�
    }
}
```


---
## 7���ӿ�

**7.1 ����**

- �ӿ�������Ƶ���ͼ����ֻ�ṩ������û��ʵ�֡�
- �ӿڲ�����ֱ��ʵ�����������������ͬ����
- C#����һ����ʵ�ֶ���ӿڣ�ע����̳е����𣩡�
- �ӿھ��ǰ���һϵ�в���ʵ�ֵķ�����������Щ������ʵ�ֽ����̳������ࡣ

**7.2 ��ʾ**

![ͼ7 Class Diagram](https://img-blog.csdnimg.cn/20200908130439364.png)

��6��������ͼ����`Dog`ʵ��`IAnimal`�ӿ�

![ͼ8 Class Diagram](https://img-blog.csdnimg.cn/20200908130626106.png)

```c
public interface IAnimal
{
    int Age { get; set; }
    double Weight { get; set; }
    void Eat();
    void Sleep();
}

public class Dog : IAnimal
{
    private int _age;
    private double _weight;
    public int Age
    {
        get { return _age; }
        set { _age = (value >= 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value >= 0) ? value : 0; }
    }
    public void Eat()
    {
        Console.WriteLine("Dog Eat");
    }
    public void Sleep()
    {
        Console.WriteLine("Dog Sleep");
    }
}

class Program
{
    static void Main(string[] args)
    {
        IAnimal al = new Dog();
        al.Age = 1;
        al.Weight = 2.5;
        Console.WriteLine("Dog:Age={0},Weight={1}",
            al.Age, al.Weight);
        // Dog:Age=1,Weight=2.5
        al.Eat();
        // Dog Eat
        al.Sleep();
        // Dog Sleep
    }
}
```

��7�����ýӿ�ʵ�֡�����ϵͳ��

ĳ����Ա��Raiser����Ŀǰ״̬����Ҫ�������ֶ������Dog������Bird�����㣨Fish���������ֶ���ֻ��Ҫ����˯����Sleep���ͳԷ���Eat�����ɡ�����Ƹ�����ϵͳ��Ҫ�����������Ƶġ�����ԭ�򡱡�

����һ�����ڳ����ಿ���Ѿ�������

![ͼ9 ���ó�����ʵ������ϵͳ](https://img-blog.csdnimg.cn/2020091218043517.png)


��������

![ͼ10 ���ýӿ�ʵ������ϵͳ](https://img-blog.csdnimg.cn/20200908135547691.png)

```c
public interface IAnimal
{
    int Age { get; set; }
    double Weight { get; set; }
    void Eat();
    void Sleep();
}

public class Bird : IAnimal
{
    private int _age;
    private double _weight;
    public int Age
    {
        get { return _age; }
        set { _age = (value >= 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value >= 0) ? value : 0; }
    }
    public void Eat()
    {
        Console.WriteLine("Bird Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Bird Sleep.");
    }
    public void Fly()
    {
        Console.WriteLine("Bird Fly.");
    }
}

public class Dog : IAnimal
{
    private int _age;
    private double _weight;
    public int Age
    {
        get { return _age; }
        set { _age = (value >= 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value >= 0) ? value : 0; }
    }
    public void Eat()
    {
        Console.WriteLine("Dog Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Dog Sleep.");
    }
    public void Run()
    {
        Console.WriteLine("Dog Run.");
    }
}

public class Fish : IAnimal
{
    private int _age;
    private double _weight;
    public int Age
    {
        get { return _age; }
        set { _age = (value >= 0) ? value : 0; }
    }
    public double Weight
    {
        get { return _weight; }
        set { _weight = (value >= 0) ? value : 0; }
    }
    public void Eat()
    {
        Console.WriteLine("Fish Eat.");
    }
    public void Sleep()
    {
        Console.WriteLine("Fish Sleep.");
    }
    public void Swim()
    {
        Console.WriteLine("Fish Swim.");
    }
}

public class Raiser
{
    public void Raise(IAnimal al)
    {
        al.Eat();
        al.Sleep();
    }
}

class Program
{
    static void Main(string[] args)
    {
        Raiser rsr = new Raiser();
        rsr.Raise(new Dog());
        // Dog Eat.
        // Dog Sleep.

        rsr.Raise(new Bird());
        // Bird Eat.
        // Bird Sleep.

        rsr.Raise(new Fish());
        //Fish Eat.
        //Fish Sleep.
    }
}
```

**7.3 �ӿڣ�interface��������ࣨabstract class��**

��1����ͬ�㣺
- �ӿ�������඼������ֱ��ʵ��������

��2����ͬ�㣺
- �������е����ݺͲ����������������η������ӿ��е����ݺͲ������������������η���
- �������п����д�ʵ����ķ�������abstract�����������ӿ�ֻ���з�����������
- ��������������ͨ��override�ؼ��ָ�д���󷽷������ӿڱ�����ֱ��ʵ�֡�

��8��һ�������ʵ�ֶ���ӿڣ���Ҫע�����ӿ��������������Ĵ���

��ʽһ��

![ͼ11 Class Diagram](https://img-blog.csdnimg.cn/20200908140142289.png)

```c
public interface IHighWayWorker
{
    void HighWayOperation();
    void Build();
}

public interface IRailWayWorker
{
    void RailWayOperation();
    void Build();
}

public class Worker : IRailWayWorker, IHighWayWorker
{
    public void HighWayOperation()
    {
        Console.WriteLine("HighWayOperation.");
    }
    public void RailWayOperation()
    {
        Console.WriteLine("RailWayOperation");
    }
    public void Build()
    {
        Console.WriteLine("HighWay,RailWay,Build.");
    }
}

class Program
{
    static void Main(string[] args)
    {
        Worker wr = new Worker();
        wr.Build(); // HighWay,RailWay,Build.
        IHighWayWorker hwr = new Worker();
        hwr.Build(); // HighWay,RailWay,Build.
        hwr.HighWayOperation(); // HighWayOperation.
        IRailWayWorker rwr = new Worker();
        rwr.Build(); // HighWay,RailWay,Build.
        rwr.RailWayOperation();// RailWayOperation
    }
}
```

��ʽ����

![ͼ12 Class Diagram](https://img-blog.csdnimg.cn/20200908140557927.png)

```c
public interface IHighWayWorker
{
    void HighWayOperation();
    void Build();
}

public interface IRailWayWorker
{
    void RailWayOperation();
    void Build();
}

public class Worker : IHighWayWorker, IRailWayWorker
{
    public void HighWayOperation()
    {
        Console.WriteLine("HighWayOperation.");
    }
    public void RailWayOperation()
    {
        Console.WriteLine("RailWayOperation");
    }
    void IHighWayWorker.Build()
    {
        Console.WriteLine("HighWay Build.");
    }
    void IRailWayWorker.Build()
    {
        Console.WriteLine("RailWay Build.");
    }
    // ע�⣺void IHighWayWorker.Build()��void IRailWayWorker.Build()
    // ǰ�治�ܹ����������η���
}

class Program
{
    static void Main(string[] args)
    {
        Worker wr = new Worker();
        //wr.Build(); ��������
        IHighWayWorker hwr = new Worker();
        hwr.Build();//HighWay Build.
        hwr.HighWayOperation();//HighWayOperation.
        IRailWayWorker rwr = new Worker();
        rwr.Build();//RailWay Build.
        rwr.RailWayOperation();//RailWayOperation
    }
}
```

---
## 8������

��9���洢`int`�������͵ļ��ϼ�������

```c
public class IntSet
{
    private readonly int _maxSize;
    private readonly int[] _set;
    public IntSet()
    {
        _maxSize = 100;
        _set = new int[_maxSize];
        //...
    }
    public void Insert(int k, int x)
    {
        //....
        _set[k] = x;
    }
    public int Locate(int k)
    {
        //...
        return _set[k];
    }
}

class Program
{
    static void Main(string[] args)
    {
        IntSet iSet = new IntSet();
        iSet.Insert(0, 123);
        int i = iSet.Locate(0);
        Console.WriteLine(i); // 123
    }
}
```

��10���洢`string`�������͵ļ��ϼ�������

```c
public class StringSet
{
    private readonly int _maxSize;
    private readonly string[] _set;
    public StringSet()
    {
        _maxSize = 100;
        _set = new string[_maxSize];
        //...
    }
    public void Insert(int k, string x)
    {
        //....
        _set[k] = x;
    }
    public string Locate(int k)
    {
        //...
        return _set[k];
    }
}

class Program
{
    static void Main(string[] args)
    {
        StringSet strSet = new StringSet();
        strSet.Insert(0, "abc");
        string j = strSet.Locate(0);
        Console.WriteLine(j); // abc
    }
}
```

��11������`object`��洢ͨ���������͵ļ��ϼ�������


```c
public class GSet
{
    private readonly int maxSize;
    private readonly object[] _set;
    public GSet()
    {
        maxSize = 100;
        _set = new object[maxSize];
        //...
    }
    public void Insert(int k, object x)
    {
        //....
        _set[k] = x;
    }
    public object Locate(int k)
    {
        //...
        return _set[k];
    }
}

class Program
{
    static void Main(string[] args)
    {
        GSet gSet1 = new GSet();
        gSet1.Insert(0, 123);
        int k1 = (int)gSet1.Locate(0);
        Console.WriteLine(k1); // 123

        GSet gSet2 = new GSet();
        gSet2.Insert(0, "abc");
        string k2 = (string)gSet2.Locate(0);
        Console.WriteLine(k2); // abc

        GSet gSet3 = new GSet();
        gSet3.Insert(0, 123);
        gSet3.Insert(1, "abc");//����ʱ����ͨ��������ʱ�����쳣��
        int k3 = (int)gSet3.Locate(1); //����ʹ�ô������Ͱ�ȫ���⡣
        Console.WriteLine(k3);
        // δ������쳣:  System.InvalidCastException: ָ����ת����Ч��
    }
}
```

���Ͷ��壺�����������͡�

�ڱ���ʱ��һ���������ʹ���ò������ͣ��ɶ������Ͱ�ȫ�������Ӱ�칤��Ч�ʡ�

��12�����÷���`T`�洢ͨ���������͵ļ��ϼ�������

```c
public class GSet<T>
{
    private readonly int _maxSize;
    private readonly T[] _set;
    public GSet()
    {
        _maxSize = 100;
        _set = new T[_maxSize];
        //...
    }
    public void Insert(int k, T x)
    {
        //....
        _set[k] = x;
    }
    public T Locate(int k)
    {
        //...
        return _set[k];
    }
}

class Program
{
    static void Main(string[] args)
    {
        GSet<int> gSet1 = new GSet<int>();
        gSet1.Insert(0, 123);
        int k1 = gSet1.Locate(0);
        Console.WriteLine(k1); // 123

        GSet<string> gSet2 = new GSet<string>();
        gSet2.Insert(0, "abc");
        string k2 = gSet2.Locate(0);
        Console.WriteLine(k2); // abc
    }
}
```

���ǰ�`T`��Ϊ���Ͳ�������Ȼ����Ҳ���Զ�`T`����Լ����


��13��Ϊ���Ͳ���`T`����Լ��������`T`ֻ����ֵ���͡�

```c
public class GSet<T> where T : struct
{
    private readonly int _maxSize;
    private readonly T[] _set;
    public GSet()
    {
        _maxSize = 100;
        _set = new T[_maxSize];
        //...
    }
    public void Insert(int k, T x)
    {
        //....
        _set[k] = x;
    }
    public T Locate(int k)
    {
        //...
        return _set[k];
    }
}

class Program
{
    static void Main(string[] args)
    {
        GSet<int> gSet1 = new GSet<int>();
        gSet1.Insert(0, 123);
        int k1 = gSet1.Locate(0);
        Console.WriteLine(k1); // 123

        // GSet<string> gSet2 = new GSet<string>(); // �������
        // ���� CS0453 ���͡�string�������ǲ�����Ϊ null ֵ�����ͣ�
        // ���������������ͻ򷽷���GSet < T >���еĲ�����T��	
    }
}
```

�йط���Լ�����Բ鿴����ͼ�ģ�
- [����ͼ�ģ�C#�����еķ��� I](https://mp.weixin.qq.com/s?__biz=MzIyNDA1NjA1NQ==&mid=2651013150&idx=1&sn=f91d81a00062d81d10e22a39c3dfb799&chksm=f3e32786c494ae908df44b253a45693ebbaff4f4e447712e9a037ae423276f5269b24675c625&token=1451124869&lang=zh_CN#rd)
- [����ͼ�ģ�C#�����еķ��� II](https://mp.weixin.qq.com/s/Zy09wOrB-M3U_jGt0MSbLA)


---
## 9��������֮��Ĺ�ϵ

![ͼ13 ������ϵ](https://img-blog.csdnimg.cn/20200909151212562.png)

```c
public class Oxygen
{
    //...
}

public class Water
{
    //...
}

public abstract class Animal
{
    public int Age;
    public double Weight;
    public abstract void Eat();
    public abstract void Sleep();
    public abstract void Breed();
    public abstract void Metabolism(Oxygen o2, Water water);
}
```

![ͼ14 �̳й�ϵ](https://img-blog.csdnimg.cn/20200909151400979.png)

```c
public class Bird : Animal
{
    public string Feather;
    public void Fly()
    {
        //...
    }
    public void Egg()
    {
        //...
    }
    public override void Eat()
    {
        //...
    }
    public override void Sleep()
    {
        //...
    }
    public override void Breed()
    {
        //...
    }
    public override void Metabolism(Oxygen o2, Water water)
    {
        //...
    }
}

public class Penguin : Bird
{
    //...
}

public class Goose : Bird
{
    //...
}

public class Duck : Bird
{
    //...
}
```


![ͼ15 ������ϵ](https://img-blog.csdnimg.cn/20200909151625397.png)

```c
public class Climate
{
    //...
}

public class Penguin : Bird
{
    private Climate _climate;
    //...
}
```

![ͼ16 ʵ�ֹ�ϵ](https://img-blog.csdnimg.cn/20200909151759894.png)

```c
public interface ILanguage
{
    void Speak();
}
public class DonaldDuck : Duck, ILanguage
{
    public void Speak()
    {
        //...
    }
    //...
}
```

