# Python&MATLAB科学计算

> MTALAB在科学计算方面是一门非常优秀的语言，但是它昂贵的价格与庞大的体积给我们的计算带来了很多不便。Python作为开源的程序语言，可以跨平台使用甚至在在使用arm的手机端都可以使用。对可以尝试用Python来代替MATLAB来进行一些简单的运算。

### 一、线性代数及方程相关计算

1. 线性方程组的求解

   - 方程组

       $$ 27x_1 + 9x_2 + 3x_3 + x_4 = 0 $$

       $$27x_1 + 6x_2 + x_3 = 0$$

       $$x_1 + x_2 + x_3 + x_4 = 8$$

       $$3x_1 + 2x_2 + x_3 = -4$$

       

   - Python求解
   
     ```python
     import numpy as np
     
     A = np.array([
         [27,9,3,1],
         [27,6,1,0],
         [1,1,1,1],
         [3,2,1,0]
     ])
     B = np.array([0,0,8,-4]).T
     Res = np.linalg.solve(A,B)
     print("The result is = ",Res)
    #Result is 1,-5,3,9
     ```

   - MATLAB求解
   
     ```matlab
     clear;clc;
     
     A = [27 9 3 1
         27 6 1 0
         1 1 1 1
         3 2 1 0];
     B = [0 0 8 -4]';
     
     A\B
    %Result is 1,-5,3,9
     ```
   
     

### 二、微积分相关计算

> 微积分的的计算Python主要是运用[Sympy库](https://docs.sympy.org/latest/modules/integrals/integrals.html)。
>
> integrate(f, x) returns the indefinite integral $\int f dx$
>
> integrate(f, (x, a, b)) returns the definite integral $\int _a^bfdx$
>
> MATLAB函数： int(f,x,a,b)  And int(f,x)

1. 一阶定积分(不定积分省略)

   - 积分方程

     $$\int (x^2 + x + 1)$$

   - Python 实现

     ```python
     from sympy import *
     x = Symbol('x')
     Res = integrate(x**2 + x + 1,x)
     
     print(Res)
     # x**3/3 + x**2/2 + x
     ```

   - MATLAB实现

     ```matlab
     clear;clc;
     
     syms x;
     f = x^2 + x + 1;
     int(f)
     %(x*(2*x^2 + 3*x + 6))/6
     ```

### 三、统计相关计算

1. 排列组合

   -   题目

     $A_5^2,C_7^3$

   - Python自己编程实现

     ```python
     class Permutation:
         def fact(self,num):
             if num == 1:
                 return num
             else:
                 return num*self.fact(num-1)
         def detect(self,n,m):
             assert m<=n ,"m should be less than for n "
         def A(self,n,m):
             self.detect(n,m)
             return self.fact(n)/self.fact(n-m)
         def C(self,n,m):
             self.detect(n,m)
             return self.fact(n)/(self.fact(m)*self.fact(n-m))
     P = Permutation()
     Res_one = P.A(5,2)
     Res_two = P.C(7,3)
     
     print("the Res_one is {}\nthe Res_two is {}".format(Res_one,Res_two))
     #the Res_one is 20.0
     #the Res_two is 35.0
     ```

   - 利用Python的第三方库Scipy实现

     ```python
     from scipy.special import comb, perm
     Res_one = perm(5,2)
     Res_two = comb(7,3)
     
     print("the Res_one is {}\nthe Res_two is {}".format(Res_one,Res_two))
     #the Res_one is 20.0
     #the Res_two is 35.0
     ```

     