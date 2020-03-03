## Welcome to wangyu's GitHub Pages

You can use the [editor on GitHub](https://github.com/kexijia/kexijia.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/kexijia/kexijia.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

# Contents  
- [深度学习](#深度学习)  
- [数值计算](#数值计算)
  - [迭代法](#迭代法)
- [Design idea and innovation point](#design-idea-and-innovation-point)  
  - [Background](#background) 
  - [Design inspirations](#design-inspirations) 
  - [Innovation point](#innovation-point)  
  - [Developmental vision](#developmental-vision) 

<h1 id="1">数值计算</h1>
<h2 id="2">迭代法</h2>

利用二分法求根，首先要确定求根区间[x_low, x_high],并且所求得方程f(x)=0,f(x)需要在所求的区间内是单调且连续的，根据连续函数的介值性(f在取区间两个端点的值异号，那么在这个区间内必存在方程的根.）通过每次将区间一分为二，确定根的范围，来求方程的根.

```python
#二分法求方程的根
from sympy import *

def f(x):
    return  exp(x)+ x**3 - 2*x+5 # 方程的根约为-2.10


x_low = -4.0
x_high = 2.0
e = 0.0001 

f_low = f(x_low)
f_high = f(x_high)

if f_low * f_high > 0:
    print('No Sultion')


while abs(x_high-x_low) > e:
    x_mid = (x_low + x_high) /2
    f_mid = f(x_mid)

    if f_low * f_mid < 0:
        x_high = x_mid
        f_high = f(x_mid)
    elif f_mid * f_high < 0:
        x_low = x_mid
        f_low = f_mid

    else:
        x_low = x_mid
        x_high = x_mid
    
x_root = (x_high+x_low)/2.0

print(x_root)

```


牛顿迭代法（Newton's method）是一种求解方程的近似解得方法.因为很多方程并没有求根公式，因此，在允许的误差范围内，求出方程的近似解对于解方程也是一种重要的方法.

  
```python
#牛顿迭代法求根
from sympy import *
def f(x):
    return exp(x)+ x**3 - 2*x+5

x = symbols("x")  # 符号x，自变量

dify = diff(f(x),x) #求导

print(dify)

x0 = 1.5
e = 0.000001

while abs(f(x0)) > e:
    x0 = x0 - f(x0)/(dify.subs('x', x0))
    print(x0)
```




