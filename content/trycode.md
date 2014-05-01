Title: 测试代码
Slug: try-code

try this code

    :::python
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

代码完毕