# Управление зависимостями

{% note info %}

В данном разделе описана функциональность, доступная только в среде выполнения `python37-preview`.

{% endnote %}

Сервис {{ sf-name }} может автоматически устанавливать зависимости, необходимые для работы функции. Для этого при создании новой [версии функции](../../operations/function/version-manage.md#func-version-create) сервис выполнит команду `pip install` в корне проекта (каталога с функцией). 

Чтобы указать необходимые для работы функции библиотеки, перечислите их в файле `requirements.txt`. Более подробно с форматом файла `requirements.txt` можно ознакомиться в [документации pip](https://pip.pypa.io/en/stable/user_guide/#requirements-files).

Пример файла `requirements.txt`:

```
boto3==1.13.15
attrs=19.3.0
```

Процесс установки зависимостей имеет ограничения. Подробнее об этом читайте в разделе [{#T}](../../concepts/limits.md). Ознакомиться с журналом установки зависимостей можно по ссылке, которая отображается в списке операций.