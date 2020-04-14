## 精度

- Q16.16 乘除精度太低了，计算出来的值，小数点第2位就错啦
```vim
num1:1999.500000, num2:1.100000
add, a1=2000.599976, a2=2000.599976
sub, a1=1998.400024, a2=1998.400024
div, a1=1817.727173, a2=1817.717163
mul, a1=2199.449951, a2=2199.462158
```


## 基准测试

```vim
[fananchong@host-192-168-23-57 Release]$ ./testfixint  1 1000000
normal add      count: 1000000          cost:3 ms       3 ns/op
fix16 add       count: 1000000          cost:5 ms       5 ns/op
normal sub      count: 1000000          cost:2 ms       2 ns/op
fix16 sub       count: 1000000          cost:6 ms       6 ns/op
normal mul      count: 1000000          cost:2 ms       2 ns/op
fix16 mul       count: 1000000          cost:8 ms       8 ns/op
normal div      count: 1000000          cost:2 ms       2 ns/op
fix16 div       count: 1000000          cost:25 ms      25 ns/op
normal sin      count: 1000000          cost:10 ms      10 ns/op
fix16 sin       count: 1000000          cost:10 ms      10 ns/op
```