# Elastic

## Управление потреблением памяти.

После установки по умолчанию Elastic у меня сразу съедал 2Gb памяти и остальным программам на виртуалке памяти просто не оставалось.  
C ElasticSearch 5 документация изменилась.

Изменение ES_HEAP_SIZE в /etc/default/elasticsearch и в etc/init.d/elasticsearch, не дают эффекта. Запуск ps aux | grep elasticsearch, показывал:

`/usr/bin/java -Xms2g -Xmx2g # aka 2G min and max ram`

Необхоидмо внести следующие изменения:

`/etc/elasticsearch/jvm.options`


```python
# Xms represents the initial size of total heap space
# Xmx represents the maximum size of total heap space

-Xms512m 
-Xmx512m 

# the settings shipped with ES 5 were: -Xms2g
# the settings shipped with ES 5 were: -Xmx2g
```

