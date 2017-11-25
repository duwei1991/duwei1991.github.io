2题 109
3题 编译出错
4题 nowcoderhello
5题 8
6题 我是构造块 我是构造块 我是静态块 我是构造块

9题 lo W

11题 129

14题
public static int countPoints(int rSquare)
{
    double r = Math.abs(Math.sqrt(rSquare));
    System.out.println(r);
    int count = 0;
    for (int x = (int) (0 - r); x <= r; x++)
    {
    for (int y = (int) (0 - r); y <= r; y++)
    {
    if (x * x + y * y == rSquare)
    {
    count += 1;
    }
    }
    }
    return count;
}

15题
public static int leastMajorityMultiple(int a, int b, int c, int d, int e)
{
    int count = 0;
    int i = 1;
    while (true)
    {
    if (i % a == 0) count++;
    if (i % b == 0) count++;
    if (i % c == 0) count++;
    if (i % d == 0) count++;
    if (i % e == 0) count++;
    if (count >= 3)
    {
    break;
    }
    count = 0;
    i++;
    }
    return i;
}

16题
public static int leastMonotoSquence(int[] seq){
    if (seq.length <= 0)
    {
    return 0;
    }
    int max1 = 0;// 上升
    int max2 = 0;// 下降
    Queue<Integer> q1 = new LinkedList<Integer>();
    q1.offer(seq[0]);
    Queue<Integer> q2 = new LinkedList<Integer>();
    q2.offer(seq[0]);
    for (int i = 1; i < seq.length; i++)
    {
    if (seq[i] < seq[i - 1])
    {
    if (q1.size() > max1)
    {
    max1 = q1.size();
    q1.clear();
    }
    }
    q1.offer(seq[i]);

    if (seq[i] > seq[i - 1])
    {
    if (q2.size() > max2)
    {
    max2 = q2.size();
    q2.clear();
    }
    }
    q2.offer(seq[i]);

    if (seq[i] == seq[i - 1])
    {
    q1.clear();
    q2.clear();
    }
    }
    if (q1.size() > max1)
    {
    max1 = q1.size();
    q1.clear();
    }
    if (q2.size() < max2)
    {
    max2 = q2.size();
    q2.clear();
    }
    return Math.max(max1, max2);
}
