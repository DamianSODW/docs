# Управление правами доступа к функции

Вы можете сделать функцию [публичной](#public) или [приватной](#private), а также [посмотреть какие роли назначены на функцию](#list).

## Сделайте функцию публичной {#public}

Чтобы любой пользователь мог вызывать функцию, необходимо сделать ее публичной, то есть позволить вызывать функцию через HTTP без передачи заголовка авторизации.

{% list tabs %}

- Консоль управления

    Сделайте функцию публичной:
    1. Откройте раздел **{{ sf-name }}** в каталоге с функцией, которую хотите сделать публичной.
    1. В списке функций выберите функцию.
    1. На странице **Обзор** в разделе **Общая информация** нажмите переключатель в поле **Публичная функция**. 
    
- CLI 

    Сделайте функцию публичной: 
    
    ```
    $ yc serverless function allow-unauthenticated-invoke <имя функции>
    ```
    Результат:
    ```
    done (1s)    
    ```

    Также вы можете сделать функцию публичной, назначив на нее роль `serverless.functions.invoker` для всех неавторизованных пользователей — системная группа `allUsers`. О том как назначить роль на функцию читайте в разделе [{#T}](../../iam/operations/roles/grant.md).

{% endlist %}

## Посмотрите роли, назначенные на функцию {#list}


{% list tabs %}
    
- CLI 

    Посмотрите роли, назначенные на функцию: 
    
    ```
    $ yc serverless function list-access-bindings <имя функции>
    ```
    Результат:
    ```
    +------------------------------+--------------+------------+
    |           ROLE ID            | SUBJECT TYPE | SUBJECT ID |
    +------------------------------+--------------+------------+
    | serverless.functions.invoker | system       | allUsers   |
    +------------------------------+--------------+------------+
    ```

{% endlist %}


## Сделайте функцию приватной {#private}

Чтобы вызвать приватную функцию через HTTP, необходимо [аутентифицироваться](./function/function-invoke.md).

{% list tabs %}

- Консоль управления

    Сделайте функцию приватной:
    1. Откройте раздел **{{ sf-name }}** в каталоге с функцией, которую хотите сделать приватной.
    1. В списке функций выберите функцию.
    1. На странице **Обзор** в разделе **Общая функция** нажмите переключатель в поле **Публичная функция**. 
    
- CLI 

    Сделайте функцию приватной:
    ```
    $ yc serverless function deny-unauthenticated-invoke <имя функции>
    ```
    Результат:
    ```
    done (1s)   
    ```

    Также вы можете сделать функцию приватной, отозвав у нее роль `serverless.functions.invoker`. О том как отозвать роль читайте в разделе [{#T}](../../iam/operations/roles/revoke.md).

{% endlist %}

Подробнее о правах, читайте в разделе [{#T}](../security/index.md).