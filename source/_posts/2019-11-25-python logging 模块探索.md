---
title: python logging 模块探索 
date: 2019-11-25 00:47:41
categories: python
---

`logging` 模块内部的数据结构如下


```python
class LogRecord(object):
    """
    A LogRecord instance represents an event being logged.
    """
    def getMessage(self):
```

_logRecordFactory = LogRecord 将类看成是函数

rv.__dict__.update(dict)

```python
class PercentStyle(object):
    def format(self, record):
class StrFormatStyle(PercentStyle):
class StringTemplateStyle(PercentStyle):
```


```python
class Formatter(object):
    """
    Formatter instances are used to convert a LogRecord to text.
    def __init__(self, fmt=None, datefmt=None, style='%'):
    def formatMessage(self, record):
```


a formatting string

```python
class Filter(object):
    """
    Filter instances are used to perform arbitrary filtering of LogRecords.
    def filter(self, record):
class Filterer(object):
    """
    A base class for loggers and handlers which allows them to share
    common code.
    """
```



```python
class Handler(Filterer):
    """
    Handler instances dispatch logging events to specific destinations.

    def handle(self, record):
        """
        Conditionally emit the specified logging record.

class StreamHandler(Handler):
    """
    A handler class which writes logging records, appropriately formatted,
    to a stream. Note that this class does not close the stream, as
    sys.stdout or sys.stderr may be used.
    """

class FileHandler(StreamHandler):
    """
    A handler class which writes formatted logging records to disk files.
    """
```

```python
class Manager(object):
    """
    There is [under normal circumstances] just one Manager instance, which
    holds the hierarchy of loggers.
    """
    def getLogger(self, name):
    """
    Get a logger with the specified name (channel name), creating it
    if it doesn't yet exist. This name is a dot-separated hierarchical
    name, such as "a", "a.b", "a.b.c" or similar.
```

```python
class Logger(Filterer):
    """
    Instances of the Logger class represent a single logging channel. A
    "logging channel" indicates an area of an application. Exactly how an
    "area" is defined is up to the application developer. Since an
    application can have any number of areas, logging channels are identified
    by a unique string. Application areas can be nested (e.g. an area
    of "input processing" might include sub-areas "read CSV files", "read
    XLS files" and "read Gnumeric files"). To cater for this natural nesting,
    channel names are organized into a namespace hierarchy where levels are
    separated by periods, much like the Java or Python package namespace. So
    in the instance given above, channel names might be "input" for the upper
    level, and "input.csv", "input.xls" and "input.gnu" for the sub-levels.
    There is no arbitrary limit to the depth of nesting.
    """
```

```python
class LoggerAdapter(object):
    """
    An adapter for loggers which makes it easier to specify contextual
    information in logging output.
    """
    def __init__(self, logger, extra):
```
