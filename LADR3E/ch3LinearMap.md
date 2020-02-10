##### 线性映射加法和标量乘的结果仍然是线性映射

$$
(S+T)(u+v)=S(u+v)+T(u+v)=Su+Sv+Tu+Tv=(S+T)(u)+(S+T)(v)
$$

$$
(\lambda T)(\mu v)=\lambda(T(\mu v))=\lambda\mu T(v)=\mu (\lambda T)(v)
$$

##### $\mathcal{L}(V,W)$是向量空间

设$S,T,J\in \mathcal{L}(V,W) \ a,b\in F$

* 交换性
  $$
  (S+T)(v)=Sv+Tv=Tv+Sv=(T+S)(v)
  $$

* 结合性
  $$
  ((S+T)+J)(v)=(S+T)v+Jv=Sv+Tv+Jv=Sv+(T+J)v=(S+(T+J))(v)
  $$

  $$
  ((ab)S)(v)=(ab)(Sv)=a(bS)(v)=(a(bS))(v)
  $$

* 加法单位元

  存在零映射$0\in \mathcal{L}(V,W)$，$(S+0)(v)=Sv+0v=Sv+0=Sv$。

* 加法逆元

  对于$S$，定义线性映射$T$，使得$\forall v\in V,Tv=-(Sv)$，故
  $$
  (S+T)(v)=Sv+Tv=Sv+(-Sv)=0
  $$

* 乘法单位元

  线性映射$\forall v\in V,Iv=v$。

* 分配性质
  $$
  (a(S+T))(v)=a((S+T)(v))=a(Sv+Tv)=aSv+aTv=(aS)(v)+(aT)(v)=(aS+aT)(v)
  $$

  $$
  ((a+b)S)(v)=(a+b)(Sv)=aSv+bSv=(aS+bS)(v)
  $$

##### 线性映射的乘积是线性映射

$$
(ST)(u+v)=S(T(u+v))=S(Tu+Tv)=S(Tu)+S(Tv)=(ST)(u)+(ST)v
$$

$$
(ST)(\lambda v)=S(T(\lambda v))=S(\lambda (Tv))=\lambda S(Tv)=\lambda (ST)(v)
$$

##### 习题3.A.7 每个从一维向量空间到其自身的线性映射都是乘以某个标量

设向量$v$是一维向量空间$V$的基向量，因为$Tv\in V$，故$\exist \lambda,s.t. \ Tv=\lambda v$。$\forall u=kv\in V,Tu=T(kv)=k(Tv)=k\lambda v=\lambda kv=\lambda u$。

##### 习题3.A.3

设$v_1=(1,0,...,0)，...,v_n= (0,...,1)$，显然这是$V$的一组基，设$Tv_1=(A_{1,1},A_{2,1},...,A_{m,1}),...,Tv_n=(A_{1,n},A_{2,n},...A_{m,n})$。那么$\forall v\in F^n,$
$$
Tv=T(\sum_{i=1}^nx_iv_i)=\sum_{i=1}^nx_iTv_i=(\sum_{i=1}^nA_{1,i}x_i,...,\sum_{i=1}^nA_{m,i}x_i)
$$

##### 习题3.A.4

若$v_i,...,v_m$是线性相关的，则存在一组不全为$0$的系数$a_1,...,a_m,s.t. \sum_{i=1}^m a_iv_i=0$，那么$T(\sum_{i=1}^ma_iv_i)=\sum_{i=1}^ma_iTv_i=T(0)=0$，这就说明$Tv_1,...,Tv_m$线性相关，与已知矛盾，故假设错误。

##### 习题3.A.8

$$
\begin{equation}
\varphi(v)=
\begin{cases}
v_1& v1=v2\\
0& v1\neq v2
\end{cases}
\end{equation}
$$

##### 习题3.A.9

令$a,b\in R$，$\varphi(a+bi)=a$
$$
\varphi((a+bi)+(c+di))=\varphi((a+c)+(b+d)i)=a+c=\varphi(a+bi)+\varphi(c+di)
$$

$$
\forall a\in R,\varphi(ia)=0\neq ai=i\varphi(a)
$$

