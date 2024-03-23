# Autograd test cases

## 1
### input
x^y^z
### output
z: ((ln(y)*y^z)*ln(x))*x^y^z

y: (z*(1/y)*y^z)*ln(x)*x^y^z

x: y^z*(1/x)*x^y^z
### check
passed

## 2
### input
sin(cos(x))
### output
x: cos(cos(x))*-(sin(x))
### check
passed

## 3
### input
pow(x\*y+z/w+19\*log(2,t),x+y+z)
### output
x: (x\*y+z/w+19\*log(2,t))^(x+y+z)\*((x+y+z)/(x\*y+z/w+19\*log(2,t))\*(y)+ln(x\*y+z/w+19\*log(2,t)))

y: (x\*y+z/w+19\*log(2,t))^(x+y+z)\*((x+y+z)/(x\*y+z/w+19\*log(2,t))\*(x)+ln(x\*y+z/w+19\*log(2,t)))

z: (x\*y+z/w+19\*log(2,t))^(x+y+z)\*((x+y+z)/(x\*y+z/w+19\*log(2,t))\*((w)/w^2)+ln(x\*y+z/w+19\*log(2,t)))

w: (x\*y+z/w+19\*log(2,t))^(x+y+z)\*((x+y+z)/(x\*y+z/w+19\*log(2,t))\*((0-z)/w^2))

t: (x\*y+z/w+19\*log(2,t))^(x+y+z)\*((x+y+z)/(x\*y+z/w+19\*log(2,t))\*(19\*(1/t\*ln(2))/ln(2)^2))
### check
