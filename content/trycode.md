Title: 测试代码
Slug: try-code



本文用于测试博文各个插件的表现效果。包括Markdown Extra、Latex、语法高亮、评论。


## Markdown Extra

### 注脚

这就是注脚[^1]。


### 表格

表格的语法[如此](http://michelf.ca/projects/php-markdown/extra/#table)，对齐方式只支持右对齐。

| Item      |    Value | Qty |
| --------- | --------:| ---:|
| Computer  | 1600 USD |   5 |
| Phone     |   12 USD |  12 |
| Pipe      |    1 USD | 234 |


### 代码

try this code. 内部的代码`if ab is None`是什么样子的呢？

```python
from codecs import open
from collections import defaultdict
from functools import partial
from itertools import chain, groupby
from operator import attrgetter, itemgetter

class Generator(object):
    """Baseclass generator"""

    def __init__(self, context, settings, path, theme, output_path, **kwargs):
        self.context = context
        self.settings = settings
        self.path = path
        self.theme = theme
        self.output_path = output_path

        for arg, value in kwargs.items():
            setattr(self, arg, value)

    def get_template(self, name):
        """Return the template by name.
        Use self.theme to get the templates to use, and return a list of
        templates ready to use with Jinja2.
        """
        if name not in self._templates:
            try:
                self._templates[name] = self.env.get_template(name + '.html')
            except TemplateNotFound:
                raise Exception('[templates] unable to load %s.html from %s'
                                % (name, self._templates_path))
        return self._templates[name]
```

代码完毕



[^1]: 注脚的内容是很小的。