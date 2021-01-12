[Триггер](../../functions/concepts/trigger/index.md) для {{ iot-short-name }} предназначен для управления сообщениями, которыми обмениваются устройства и реестры. Он создается для топиков: принимает из них копии сообщений и передает в функцию для обработки. Триггер должен находиться в одном облаке с устройством или реестром, из топика которого он читает сообщения.  
 
Вы можете создать триггер:
* Для [стандартного топика](../../iot-core/concepts/topic.md), реализованного сервисом.

	{% include [monitoring-topic](../iot-core/monitoring-topic.md) %}

* Для топика с произвольными [сабтопиками](../../iot-core/concepts/topic.md#subtopic) и подстановочными символами.
* Для [алиаса](../../iot-core/concepts/topic.md#aliases) топика.
 
Триггеру для {{ iot-short-name }} необходим [сервисный аккаунт](../../iam/concepts/users/service-accounts.md) для вызова функции. 