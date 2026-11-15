# Результаты сценариев

В `results.json` находятся статусы и числа сценариев. Файлы `tablestats.txt` и
`tablestats_plain.txt` создаёт команда `bash ops.sh tablestats`. Файл
`repair.txt` создаёт `bash ops.sh repair`, а `compaction.txt` — `bash ops.sh compact`.

Блоки ниже копируются в README и заполняются числами своего прогона.

## `bulk` - вставка 10 000

| Что вставлено | Сколько | Время |
|---|---|---|
| События пользователя 1001 (`login`, `purchase`, `view`) | 10 000 | |

Время можно взять из вывода `bulk` или из `artifacts.bulk.seconds` в секундах.
Среднее за запись = время / 10 000.

## `consistency` - ONE и QUORUM

| Уровень | Запись, мс | Чтение, мс |
|---|---|---|
| ONE | | |
| QUORUM | | |

Числа находятся в `artifacts.consistency` в секундах. Для таблицы их нужно
перевести в миллисекунды.

## Сжатие - `tablestats`

| Таблица | Space used (total) | SSTable count | SSTable Compression Ratio |
|---|---|---|---|
| `user_actions` (LZ4) | | | |
| `user_actions_none` (без сжатия) | | | |

Источник - `tablestats.txt` и `tablestats_plain.txt`.

## Bloom-фильтр

| Показатель | Значение |
|---|---|
| Bloom filter false positives | |
| Bloom filter false ratio | |

Источник - `tablestats.txt`, секция `hw3.user_actions`.

## `compaction` - TWCS и TTL

| Показатель | Значение |
|---|---|
| Стратегия компакции | |
| default_time_to_live | |
| События с TTL 5 секунд: до / после истечения | |

Источник - `results/results.json`, раздел `artifacts.compaction`, и `compaction.txt`.

## `data` и `repair`

Для `data` в README нужны статус и краткий перечень проверенного
(`scenarios.data` в `results.json`). Для `repair` нужны финальные строки
`repair.txt` и объяснения раздела 7.
