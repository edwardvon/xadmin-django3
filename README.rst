Xadmin-django3
============================================

说明
-----------
基于官方xadmin-django2 2.0.1版本，修复已知bug，在Python3.7 + Django3.0.3环境下运行通过。

目前只修复了我碰到的问题，欢迎提issue以及讨论修改方法

官方文档
-------------

-  English (coming soon)
-  `Chinese`_

.. _Chinese: https://xadmin.readthedocs.org/en/latest/index.html


目前已修复bug
-------------

- ForeignKey未配置on_delete参数引起的错误
- 模块包名称变更引发的错误:
      django.core.urlresolvers => django.urls 
      django.utils.six => six 
      django.utils.encoding.python_2_unicode_compatible => future.utils.python_2_unicode_compatible
      ...
      等（记不清了）
- "ManyToManyField" object has no attribute 'rel'错误
- Exception: Relate Lookup field must a related field 错误
- xadmin\views\website.py login和logout 函数及参数变更引发的错误
- 国际化问题报异常：ImportError: cannot import name 'javascript_catalog' from 'django.views.i18n'
      注：请在project\setting.py 的 INSTALLED_APPS中补充添加 'django.conf'

- 异常 ‘DateTimeField‘ object has no attribute 'rel'
- ModuleNotFoundError: No module named 'django.contrib.formtools' fromtools版本太低
- ImportError: cannot import name 'QUERY_TERMS' from 'django.db.models.sql.query' 错误
- ImportError: cannot import name 'password_reset_confirm' from 'django.contrib.auth.views' 错误
- AttributeError: 'Settings' object has no attribute 'MIDDLEWARE_CLASSES'
- TypeError: forms.Field.__init__() takes 1 positional argument but 6 were given
- render() got an unexpected keyword argument 'renderer'

- 还有些想不起来了...



