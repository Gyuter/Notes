##### 绝对值和距离的基本性质

设$x$、$y$、$z$是有理数。

1. （绝对值的非退化性）我们有$|x|\geq 0$。另外，$|x|=0$当且仅当$x=0$。

   $x>0$时，$|x|=x>0$；$x=0$时，$|x|=0$；$x<0$时，$|x|=-x>0$。

   我们可以简单地得到$|x|\geq x,|x|\geq -x$。

2. （绝对值的三角不等式）$|x+y|\leq |x|+|y|$

   * 若$x+y\geq 0$，$|x+y|=x+y\leq|x|+|y|$。
   * 若$x+y<0$，$|x+y|=-x-y\leq |x|+|y|$。

3. 不等式$-y\leq x\leq y$当且仅当$y\geq|x|$。特别地，$-|x|\leq x \leq |x|$。

   必要性

   由小于等于号的传递性，可知$-y\leq y$，两边同时加上$y$可得$0\leq 2y$，进而$y\geq 0$。（引理4.1.11）

   * 若$x\geq 0$，$y\geq x=|x|$，该情况下的结论得证。
   * 若$x< 0$，由$-y\leq x=-|x|$，两边同时加上$y+|x|$可得$|x|\leq y$,该情况下的结论得证。

   充分性

   显然$y\geq |x|\geq 0$，$-|x|\leq 0$，故$y\geq -|x|$。

   $x\geq 0$时，$y\geq |x|=x$，$y\geq -|x|=-x$，由后者可得$-y\leq x$。结论得证。

   $x\leq 0$时，$y\geq |x|=-x$，$y\geq -|x|=x$，由前者可得$x\geq -y$。结论得证。

   令$y=|x|$，显然满足$|x|\geq|x|$,所以有$-y\leq x\leq  y$，即$-|x|\leq x\leq |x|$。