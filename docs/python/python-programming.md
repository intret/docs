# Python 编程

## 多环境配置文件

config.py：

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
import os
from os import getenv
basedir = os.path.abspath(os.path.dirname(__file__))
class Config(object):
    DEBUG = False
    TESTING = False
    MYSQL_HOST = getenv('MYSQL_HOST', '192.168.1.1')
    # get attribute
    def __getitem__(self, key):
        return self.__getattribute__(key)
class ProductionConfig(Config):
    DEBUG = False
    MSSQL_HOST = getenv('MSSQL_HOST', '192.168.8.8')
class DevelopmentConfig(Config):
    DEBUG = True
    MSSQL_HOST = getenv('MSSQL_HOST', '192.168.4.4')
class TestingConfig(Config):
    TESTING = True
mapping = {
    'development': DevelopmentConfig,
    'testing': TestingConfig,
    'production': ProductionConfig,
    'default': DevelopmentConfig
}
APP_ENV = os.environ.get('APP_ENV', 'default').lower()
config = mapping[APP_ENV]()
```

使用：

```python
from config import config

print(config.MYSQL_HOST)
```

