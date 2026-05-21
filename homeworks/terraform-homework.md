Задание 1


Выполните код проекта. Найдите в state-файле секретное содержимое созданного ресурса random_password, пришлите в качестве ответа конкретный ключ и его значение.   
```"result": "Zaft0uZu5J9zMLZs",```

Раскомментируйте блок кода, примерно расположенный на строчках 29–42 файла main.tf. Выполните команду terraform validate. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.
Выполните код. В качестве ответа приложите: исправленный фрагмент кода и вывод команды docker ps.
terraform-home<img width="1185" height="912" alt="image" src="https://github.com/user-attachments/assets/fa9441a7-520d-4cc2-a096-22d81e107bc1" />
Замените имя docker-контейнера в блоке кода на hello_world. Не перепутайте имя контейнера и имя образа. Мы всё ещё продолжаем использовать name = "nginx:latest". Выполните команду terraform apply -auto-approve. Объясните своими словами, в чём может быть опасность применения ключа -auto-approve. Догадайтесь или нагуглите зачем может пригодиться данный ключ? В качестве ответа дополнительно приложите вывод команды docker ps.
<img width="1267" height="884" alt="image" src="https://github.com/user-attachments/assets/bd6a91cd-0852-4337-8d55-704c125cb5fc" />
Автоматически подтверждает выполнение операций БЕЗ ручной проверки планируемых изменений

Может привести к случайному удалению или изменению критических ресурсов в production

В случае ошибки в конфигурации может вызвать простой сервисов или потерю данных

Невозможно отменить изменения после применения

Уничтожьте созданные ресурсы с помощью terraform. Убедитесь, что все ресурсы удалены. Приложите содержимое файла terraform.tfstate.
Объясните, почему при этом не был удалён docker-образ nginx:latest. Ответ ОБЯЗАТЕЛЬНО НАЙДИТЕ В ПРЕДОСТАВЛЕННОМ КОДЕ, а затем ОБЯЗАТЕЛЬНО ПОДКРЕПИТЕ строчкой из документации terraform провайдера docker. (ищите в классификаторе resource docker_image )
```resource "docker_image" {
  name         = "nginx:latest"
  keep_locally = true
}
```


<img width="642" height="392" alt="image" src="https://github.com/user-attachments/assets/6e9a2108-2374-4cdb-bb68-3524dc457825" />

keep_locally - (Optional, boolean) If true, then the Docker image won't be deleted on destroy operation. If this is false, it will delete the image from the docker local storage on destroy operation.
