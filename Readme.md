# Задание №7. Оптимизация `test-suite` и сбор `DX`-метрик

## Оптимизация test-suite

В этом задании предлагаю вам попрактиковаться в оптимизации `test-suite` на примере `dev.to`.

Поскольку у вас уже есть развёрнутый локально `dev.to`, сделанный в рамках задания `№3`, предлагаю работать в нём же.

Вооружитесь инструментами, рассмотренными на лекции, и разгоните этот `test-suite`!

## Сбор DX-метрики

Чтобы запечатлеть свой прогресс и в дальнейшем защитить его от деградации, сделайте сбор `DX`-метрики времени выполнения `test-suite` в `InfluxDB` и постройте график в `Chronograf`.

Сделать это очень просто с помощью https://github.com/influxdata/TICK-docker и https://github.com/palkan/influxer.

Подумайте, как бы вам было удобно прикрепить отправку метрики в `InfluxDB` к прогону тестов.

## Hints

Старайтесь держать `feedback-loop` коротким. `test-suite` целиком в один процесс выполняется около 10 минут, это очень долго. Используйте семлирование. Если вы обнаружите проблему, то выберите какой-нибудь один тест, на котором она воспроизводится, и исправьте её, работая с этим тестом.

Попробуйте все инструменты из `test-prof`!

`json-flamegraph` для всего `test-suite` целиком занимает около `1Gb`. `Speedscope.app` открыть его не может.

C отчётом `stackprof` для всего `test-suite` можно работать через `CLI stackprof`, и через `qcachegrind`.

С `ruby-prof` надо работать ещё аккуратнее, потому что он, как `tracing profiler`, собирает очень много данных, с которыми в дальнейшем тяжело работать.


## Чек-лист для сдачи задания
- [x] `PR` с оптимизацией в https://github.com/spajic/task-3
- [x] В описание `PR` добавить `case-study` проделанной работы и достигнутых результатов
- [x] Добавить скриншот с графиком изменения времени прогона `test-suite` в `Chronograf`
