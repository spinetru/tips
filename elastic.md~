

В ElasticSearch 5 документация изменилась, что означает, что ни один из вышеперечисленных ответов не работал у меня.

Я попытался изменить ES_HEAP_SIZE в /etc/default/elasticsearch и в etc/init.d/elasticsearch, но когда я запустил ps aux | grep elasticsearch, результат все еще показывал:

`/usr/bin/java -Xms2g -Xmx2g # aka 2G min and max ram`

Мне пришлось внести следующие изменения:

`/etc/elasticsearch/jvm.options`

    # Xms represents the initial size of total heap space
    # Xmx represents the maximum size of total heap space

    -Xms1g 
    -Xmx1g 
    # the settings shipped with ES 5 were: -Xms2g
    # the settings shipped with ES 5 were: -Xmx2g


