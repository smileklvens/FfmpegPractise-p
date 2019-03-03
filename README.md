### 基本语法
- 基本类型：short，int 
- 指针：就是内存地址 ：void *，char*
- 数组：连续的存储空间 
  
- 自定义类型：结构体
```
struct st
{
      int a;
      int b;
};

sst.a = 10 ;
```
- 枚举：

```
enum e_type
{
  red=10,
  green=20,
  black=30
}; 
```
- 算数运算

```
类似java中的+-*/ %
```
- if for 类似java 
```
for (size_t a = 0; a < 50; a+=2)
    {
        printf("a=%d\n",a);
    }

```
- while

```
while (1)
    {
        printf("");
    }
```
- 函数

```
#include <stdio.h>
int sum(int a,int b){
    return(a+b);
}
int main (int argc,char*argv[]){
   int result ;
   result = (sum(3,5)) ;
   printf("resutlt=%d",result);
   return 0;
}

```
- 文件

```
    FILE* file;
    char buf[1024] = {0,};

    file = fopen("1.txt","a+");
    fwrite("hello world!",1,13,file);

    rewind(file);
    fread(buf,1,26,file);
    fclose(file);


```
- 指针本身运算，指针所指内容操作
1. 栈空间所函数创建和释放，默认4M
2. 堆空间
3. 内存映射（一般用于数据库）

内存分配
void* mem = malloc(size);//一般在堆空间
释放内存（不释放的话，会泄露或者产生野指针）
free(mem);
函数指针:既函数的地址

```
int (*f)(int ,int );
```
### 编译
编译器：GCC/CLANG
1. 命令
```
gcc/clang -g -O2 -o test.c -I... _L... _I
-g:输出调试信息
-O:对输出文件做指令优化
-o：输出文件
-I:指定头文件
—L:指定库文件位置
-l：指定使用哪个库
```
2.编译过程静态库并外部引入
- 预编译(将头文件和源代码放在一起，copy)
- 编译
- 链接，动态链接/静态链接（.O与其他库链接）

```
$  clang -g -c add.c  
$  libtool -static -o libmylib.a add.o
$  ls -lat libmylib.a
$  clang -g -o testlib  test.c -I . -L . -lmylib
$  ./testlib
```
[部分源码](https://github.com/smileklvens/ffmpegPractise)
## 如有疏漏，请指出不胜感激，如有问题可以通过如下方式联系我 
>[简书](https://www.jianshu.com/p/20cdcb1bce1b)
[csdn](http://blog.csdn.net/qq_19307133/article/details/79058392)
[掘金](https://juejin.im/post/5a5b366af265da3e58594f00)
[klvens跑码场](https://smileklvens.coding.me)

