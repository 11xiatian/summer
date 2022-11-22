# 网络空间安全数学里的求某一个数的Euler函数值

### Euler函数值：比N小且与N互素的数的个数就称为N的Euler函数值

~~~c
#include <stdio.h>

    int Euler(int N){
            int res = N,a = N;
            for(int i = 2;i*i <= a;i ++){
                if(a%i == 0){
                    res = res / i*(i - 1);//先进行除法是为了防止中间数据的溢出
                    while(a % i == 0) a /= i;
                }
            }
            if(a > 1)res = res / a * (a - 1);
            return res;
        }
    int main()
    {
        int N,x;
        int Euler(int N);
        printf("Enter the value of N to calculate the value of the Euler function N\n");
        scanf("%d",&N);//输入N的值
        x = Euler(N);
        printf("Euler(%d) = %d",N,x);
        return 0;
    }
~~~

