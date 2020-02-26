## Welcome to GitHub Pages

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
- [Design idea and innovation point](#design-idea-and-innovation-point)  
  - [Background](#background) 
  - [Design inspirations](#design-inspirations) 
  - [Innovation point](#innovation-point)  
  - [Developmental vision](#developmental-vision) 

<h1 id="1">数值计算</h1>

    ```python
    #!/usr/bin/env python
    from sympy import *
    def f(x):

    return exp(x)+ x**3 - 2*x+5

    x = symbols("x")  # 符号x，自变量

    dify = diff(f(x),x) #求导

    print(dify)

    x0 = 1.5  #初值
    e = 0.000001  #精度

    while abs(f(x0)) > e:
      x0 = x0 - f(x0)/(dify.subs('x', x0))
    print(x0)
    ```




