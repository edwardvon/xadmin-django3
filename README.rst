Xadmin-django3
============================================

说明
-----------
基于官方xadmin-django2 2.0.1版本，修复已知bug，在Python3.7 + Django3.0.3环境下运行通过。

目前只修复了我碰到的问题，欢迎提issue以及讨论修改方法


requirements
-------------
 * django==3.0.3
 * django-crispy-forms==1.8.1
 * django-import-export==2.0.2
 * django-reversion==3.0.7
 * django-formtools==2.2.0
 * future==0.18.2
 * httplib2==0.9.2
 * six==1.14.0


使用
-------------
- 请暂时不要使用setup.py进行安装（待修正）
1.在django项目目录下建立extra_apps文件夹，将本仓库中xadmin文件夹拷贝到其中；

2.在django项目的settting.py 添加extra_apps目录

    import sys  
    
    ...  
    
    sys.path.insert(0, os.path.join(BASE_DIR, 'extra_apps'))


3.将'xadmin', 'crispy_forms', 'reversion', 'django.cong'添加到 INSTALLED_APPS:


    INSTALLED_APPS = [
    
        ...
        
        'xadmin',
        'crispy_forms',
        'reversion',
        'django.conf',
        
        ...
        
    ]


官方文档
-------------

-  English (coming soon)
-  `Chinese`_

.. _Chinese: https://xadmin.readthedocs.org/en/latest/index.html


目前已修复bug
-------------
- 2020/02/25更新：AttributeError: module 'xadmin' has no attribute 'site'; 解决方法：https://github.com/edwardvon/xadmin-django3/issues/1


- ForeignKey未配置on_delete参数引起的错误

- 模块包名称变更引发的错误:
    * django.core.urlresolvers => django.urls
    * django.utils.six => six
    * django.utils.encoding.python_2_unicode_compatible => future.utils.python_2_unicode_compatible
    * ...
    * 等（记不清了）
      
- "ManyToManyField" object has no attribute 'rel'错误

- Exception: Relate Lookup field must a related field 错误

- xadmin\views\website.py login和logout 函数及参数变更引发的错误

- 国际化问题报异常：ImportError: cannot import name 'javascript_catalog' from 'django.views.i18n'
      注：请在project\setting.py 的 INSTALLED_APPS中补充添加 'django.conf'

- 异常 'DateTimeField' object has no attribute 'rel'

- ModuleNotFoundError: No module named 'django.contrib.formtools' fromtools版本太低

- ImportError: cannot import name 'QUERY_TERMS' from 'django.db.models.sql.query' 错误

- ImportError: cannot import name 'password_reset_confirm' from 'django.contrib.auth.views' 错误

- AttributeError: 'Settings' object has no attribute 'MIDDLEWARE_CLASSES'

- TypeError: forms.Field.__init__() takes 1 positional argument but 6 were given

- render() got an unexpected keyword argument 'renderer'

- 还有些想不起来了...



