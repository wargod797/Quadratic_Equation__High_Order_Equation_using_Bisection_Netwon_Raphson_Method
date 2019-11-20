

```python
#Quadratic Equation


import cmath
print('Enter the Values in format ax^2+bx+c=')
a, b, c = map(int,input().split()) 
d = (b**2) - (4*a*c)
sol1 = (-b-cmath.sqrt(d))/(2*a)
sol2 = (-b+cmath.sqrt(d))/(2*a)
print('The solution are {0} and {1}'.format(sol1,sol2))
```

    Enter the Values in format ax^2+bx+c=
    10 20 30
    The solution are (-1-1.4142135623730951j) and (-1+1.4142135623730951j)
    

![title](image.png)


```python
#Bisection Method
def bisection(f,a,b,N):
    if f(a)*f(b) >= 0:
        print("Bisection method fails.")
        return None
    a_n = a
    b_n = b
    for n in range(1,N+1):
        m_n = (a_n + b_n)/2
        f_m_n = f(m_n)
        if f(a_n)*f_m_n < 0:
            a_n = a_n
            b_n = m_n
        elif f(b_n)*f_m_n < 0:
            a_n = m_n
            b_n = b_n
        elif f_m_n == 0:
            print("Found exact solution.")
            return m_n
        else:
            print("Bisection method fails.")
            return None
    return (a_n + b_n)/2
f = lambda x: x**3 - x - 1 #put your Equation Here
for i in range(0,50):
    if f(i)>0:
        b = i
        a = i-1
        break
N=2500000
approx_phi = bisection(f,a,b,N)
print(approx_phi)
```

    1.3247179572447458
    


```python
f = lambda x: x**2 - x - 1
for i in range(0,5):
    if f(i)>0:
        print(i)
        break
```

    2
    


```python
func = lambda x:x**2-x-1 #put your equation here
derivFunc = lambda x:2*x-1 #put your derivative of eqaution here

def newtonRaphson(x,func,derivFunc): 
    h = func(x) / derivFunc(x) 
    while abs(h) >= 0.000000001: 
        h = func(x)/derivFunc(x) 
        x = x - h     
    print("The value of the root is : ", "%.4f"%x) 
for i in range(0,100):
    if func(i)<0 and derivFunc(i)>0:
        x0=i
newtonRaphson(x0,func,derivFunc) 
```

    The value of the root is :  1.6180
    
