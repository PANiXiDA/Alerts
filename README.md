# ElastAlert

мониторинг на основе логов в эластике

ссылка на документацию https://elastalert2.readthedocs.io/en/latest/index.html

для каждого сервиса создается новое правило в папке rules, про типы правил можно почитать в документации 
https://elastalert2.readthedocs.io/en/latest/ruletypes.html#rule-types

все добавления правил и изменения должны пройти через ревью, пуш в ветку master обновляет правила мониторинга, 
для каждого нового сервиса создаем отдельное правило в папке rules с указанием имени сервиса и среды.

**Перед созданием правила индекс должен существовать в эластике**
**Все имена правил должны быть уникальны**


## Запуск в Docker
```
docker run -d --name elastalert --restart=always \
-v $(pwd)/config.yaml:/opt/elastalert/config.yaml \
-v $(pwd)/rules:/opt/elastalert/rules \
jertel/elastalert2 --verbose
```
