

矩阵在图形变换中的应用
              0 0
    p   = (   4 0   )
              5 3

              0 0
    2*p = (   8 0   )
              10 6

    具体什么情况还是看图吧，反正就是 可以围成两个相似三角形        





让一个点的横坐标扩大1.5倍，纵坐标扩大2倍
        
    T(变换) * (点坐标，列向量)
            x            1.5x 
    T  * (  y  )    = (  2y   )

    因为列向量的元素个数(行数)为 2，所以变换矩阵T的列数为2
        A(m * k) * B(k * n) 的前提是 A的列数 = B的行数

    又因为变换后的结果，即点的坐标为一个有两个元素(行数为2)的列向量，所以变换矩阵T的行数为2
        A(m * k) * B(k * n) = C(m * n)

    T(变换) * (点坐标，列向量)
        a b       x       ax + by
    ( c d ) * ( y ) = ( cx + dy)

                1.5 0
    所以 T = (  0   2 )


    结果:
         1.5   0       x       1.5x
        ( 0    2 ) * ( y ) = (  2y  )





让每个点的横坐标扩大1.5倍，纵坐标扩大2倍
           1.5 0
    T = (  0   2 )

          p1 p2  p3
          0  4   5
    P = ( 0  0   3 )

              0  6  7.5
    T * P = ( 0  0  6  )

        前提: 矩阵T的列数必须和矩阵P的行数一致






把矩阵看作是一种变换
    矩阵表示变换(向量的函数)




    让每个点的横坐标扩大a倍，纵坐标扩大b倍
              x       ax
        T * ( y ) = ( by )

        矩阵相乘前提条件: Col(A) == Row(B)
            所以 T 的列数为 2

        由结果的形式得，T 的行数为 2
            A(m*k) * B(k*n) = C(m*n)

                        a b
        综上所述: T = ( c d )
                       x       ax+by
            那么 T * ( y ) = ( cx+dy )
                           
                           ax
            又因为结果为 ( by )

                       a 0
            所以 T = ( 0 b )





    让每个点关于 x轴 翻转
              x       x
        T * ( y ) = ( -y )
        
              a b
        T = ( c d )

          a b       x       ax+by
        ( c d ) * ( y ) = ( cx+dy )

                   1 0
        所以 T = ( 0 -1 )






    让每个点关于 y轴 翻转
              x       -x
        T * ( y ) = ( y )
        
              a b
        T = ( c d )

          a b       x       ax+by
        ( c d ) * ( y ) = ( cx+dy )

                   -1 0
        所以 T = (  0 1 )





    让每个点关于 原点 翻转(x轴，y轴均翻转)
              x       -x
        T * ( y ) = ( -y )
        
              a b
        T = ( c d )

          a b       x       ax+by
        ( c d ) * ( y ) = ( cx+dy )

                   -1 0
        所以 T = ( 0 -1 )


        另一种思路:
                   1 0                 -1 0
            Tx = ( 0 -1 )       Ty = (  0 1 )

                         x
            Ty * (Tx * ( y ))，由矩阵乘法的结合律有

                          x       -1 0
            (Ty * Tx) * ( y ) = ( 0 -1 )






    沿x方向错切
              x       x + ay
        T * ( y ) = (   y    )
                
              1 a
        T = ( 0 1 )




    沿y方向错切
              x         x
        T * ( y ) = ( bx + y )
                
              1 0
        T = ( b 1 )






    旋转变换: 线段长度不变

              x       ?
        T * ( y ) = ( ? )
    
        y
        |    (x, y)   (j, k)
        |    /     %
        |   /    %
        |  /   %
        | /  %
        |/ %
        ------------------- x

        / 长度为 d
        / 与 x轴 所成角为 A
        / 与 % 所成角为 B

        x = cosA * d
            d = x / cosA

        y = sinA * d
            d = y / sinA

        同理可得
            d = j / cos(A-B)
            d = k / sin(A-B)


        j / cos(A-B) = x / cosA
            j = cos(A-B) * x / cosA
              = (cosAcosB + sinAsinB) * x / cosA
              = cosBx + sinB*(sinA/cosA) * x
              = cosBx + sinB*(y/x)*x
              = cosBx + sinBy

        k / sin(A-B) = y / sinA
            k = sin(A-B) * y / sinA
              = (sinAcosB - cosAsinB) * y / sinA
              = cosBy - sinB*(cosA/sinA) * y
              = cosBy - sinB*(x/y)*y
              = cosBy - sinBx
              = -sinBx + cosBy


        这里用到了，高中的三角公式
            sin(A + B) = sinAcosB + cosAsinB

            cos(A + B) = cosAcosB - sinAsinB

            tan(A + B) = (tanA + tanB) / (1 - tanAtanB)


              x        cosBx + sinBy
        T * ( y ) = ( -sinBx + cosBy )

              cosB sinB
        T = ( -sinB cosB )




矩阵表示变换(向量的函数)
    
    在三维坐标中的应用

    平移操作

    仿射变换(*)

    图形学

