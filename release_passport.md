# Паспорт выпуска 1.5.0-rc1 (DOC-17)

## Версия
- Релиз: `1.5.0-rc1`
- Пакет: `app-1.5.0-rc1.zip`
- Source commit: `DEMO-COMMIT-015-NOT-A-REAL-GIT-ID`
- Статус source commit: учебный маркер, не настоящий Git-хеш.

## Цель
Подготовка учебного сервиса заявок к внедрению: проверка связности требований, тестов, доказательств и документации.

## Состав
- Приложение `app-1.5.0-rc1.zip`
- Миграция `M015`
- Схема: `S1` → `S2`
- Резервная копия: `B-1755` (database, attachments, config)

## Среда
- Linux x64
- Python 3.11 или 3.12
- PostgreSQL 15 или 16
- Минимум свободного места: 2048 МиБ

## Зависимости
- PostgreSQL 15/16
- Python 3.11/3.12
- Обязательные параметры: `APP_PORT`, `DB_HOST`, `DB_NAME`, `ATTACHMENTS_DIR`
- Секреты передаются отдельным разрешённым механизмом, в комплект не входят.

## Параметры
- `APP_PORT=8081`
- `DB_HOST=lab-db-01`
- `DB_NAME=service_lab`
- `ATTACHMENTS_DIR=/srv/service_lab/attachments`
- `max_attachments=3`

## Миграция
- `M015` добавляет необязательную категорию.
- Миграция расширяющая.
- Состояние отслеживается по журналу миграций.
- Повтор разрешается только после проверки фактического результата.

## Ограничения
- Восстановление не подтверждено: `last_restore_test = not_available_in_packet`.
- Тест `R_RESTORE` заблокирован: `restore-target-unavailable`.
- Тест `R_PERFORMANCE` не проводился: `not_run`.
- Руководство оператора устарело: версия `1.4.2`, `max_attachments=5`, неверный совет по тайм-ауту.
- Фактический пакет `app-1.5.0-rc1.zip` отсутствует, контроль целостности не подтверждён. Имя файла не заменяет вычисленный хеш.

## Ответственные
- release_owner: `teacher_release`
- technical_executor: `student_engineer`
- test_owner: `student_tester`
- acceptance_owner: `teacher_process`
- support: `student_support`

## Статус готовности
Не готов. Есть блокеры:
- `R_RESTORE` — blocked;
- `R_PERFORMANCE` — not_run;
- документация содержит расхождения.
