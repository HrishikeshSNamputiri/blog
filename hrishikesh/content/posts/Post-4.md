+++ 
draft = true
date = 2024-07-04T07:49:19+05:30
title = "July 3rd"
description = ""
slug = ""
authors = []
tags = []
categories = []
externalLink = ""
series = []
+++

## Training Day 1: July 4 2024

Problems Solved: 2 Green

Problems

1) [A very intresting geometry problem](https://atcoder.jp/contests/abc359/tasks/abc359_c)

2) [A problem regarding concatenation of an integer that many times.](https://atcoder.jp/contests/abc357/tasks/abc357_d)

Analysis of Problem 1:

I was unable to crack the problem on my own. I couldn't visualize what the problem was and I thought of so many wrong ideas which I dont remember now. Turns out, it was rather simple problem but we need to visualize it. They are given two points. $(S_x+0.5,S_y+0.5)$ and $(T_x+0.5,T_y+0.5)$. If we cross one brick, a toll of 1 is given. We need to find the minimum toll required to get from $S=(S_x,S_y)$  and $T=(T_x,T_y)$. Because the bricks are layed horizontally, we need to give toll if we cross 2 coordinates horizontally and if we cross 1 tile vertically. Now if we look closely, a point can be in two position in one tile. And if we move around inside the tile we don't need to give toll. So first we will place the points S and T to the left side of the brick so that it is easier to calculate the distance. To find the left bottom point of the brick, we can use $S_x = \left( \left| S_y - S_x \right| \mod 2 \right)$ and $T_x = \left( \left| T_y - T_x \right| \mod 2 \right)$. Now look closer, the distance between S and T is $(0,0)$ to $(|Tx-Sx|,|T_y-S_y|)$. To find the toll for reaching the point $(|Tx-Sx|,|T_y-S_y|)$, we obviously need to give $y=|T_y-S_y|$ for going up $y$ times. And we need to add on top of y $\max\left(0, \frac{T_x - T_y}{2}\right)$. So the final answer is $T_y+\max\left(0, \frac{T_x - T_y}{2}\right)$.

```
```cpp
#include <bits/stdc++.h>
using namespace std;
#define int long long
#define ll long long
#define ull unsigned long long
#define all(x) x.begin(),x.end()
#define fori(y,n) for(int i=y;i<n;i++)
#define forj(z,m) for(int j=z;j<m;j++)
#define st string
#define ch char
#define bo bool
#define vi vector<int>
#define vs vector<string>
#define vp vector<pair<int,int>>
#define um unordered_map 
#define us unordered_set

// bool is_prime(int){

// }


int32_t main(){
  int sx,sy,tx,ty;
  cin >> sx >> sy >> tx >> ty;
  sx-=(abs(sy-sx)%2);//finding starting of the starting brick
  tx-=(abs(ty-tx)%2);//finding starting of the ending brick
  tx=abs(tx-sx); //instead of calculating the distance from (sx,sy) to (tx,ty),
  ty=abs(ty-sy); //we calculate from (0,0) to (tx-sx,tx-sy)
  int ans=ty + max((int)0,(tx-ty)/2); //here we want to know if you need to go 'd' distance after ty distance. if tx>ty then we need to add d=(tx-ty)/2 to ty for the answer.
  cout << ans << endl;
}
```

Analysis of Problem 2:
For this problem we need to know some prerequisites:

1) Sum of geometric series: 
       $S = a \left( \frac{{r^a - 1}}{{r - 1}} \right)$ 

2) Fermat's Little Theorem:

   It states that if p is a prime number and p does not divide a, then

       $a^{p-1} \equiv 1(\mod p)$

I didn't know about congruence modulo until now. So I studied it. Even though off topic, I studied chinese remainder theorem mathematically.



The problem was to find the concatenated number modulo 998244353 which is a prime number.



For example $n=9$

$V_n=999999999$ , $len=1$ 

$pl=10^{len}=10^1=10$





So $ Ans = \frac{{n \left(10^{\text{{len}}} \cdot n - 1\right)}}{{10^{\text{{len}}} - 1}} $ where $len=$ length of n
