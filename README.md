# Репозиторий документов по проекту *Remy*
## Бизнес требования от 01.03.2024
- С доступом на любом устройстве
- не ограничивать хранилище в объёме, но монетизация объёма
- B2C и B2B
- Можно поставить на предприятие: не только SaaS но и On-Premise
- *(посмотреть на open source решение для бизнеса)*
- неограниченный объём файлов для загрузки
- поддержка работы без интернета, сохранение задачи отправки файлов при отсутствии интернета, синхронизация при восстановлении соединения

## Функциональные требования
1. Use Case: Загрузка медиафайлов
	- Актор: Пользователь (любитель фотографии, профессиональный фотограф, компания)
	- Контекст применения: Пользователь хочет загрузить фото или видео в облачное хранилище.
	- Конечная цель: Медиафайлы успешно загружены в облачное хранилище.
	- Результат: Медиафайлы доступны в облаке для дальнейшего использования.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для загрузки.
		2. Система проверяет формат и размер файлов. 
#TODO: Определить поддерживаемые форматы для хранения
(например PNG, JPEG, GIF, MP4, MOV, WEBP, WEBM, WMV)
		3. Медиафайлы загружаются в облако.
		4. Система присваивает файлам уникальные идентификаторы.
		5. Пользователю отображается уведомление об успешной загрузке.
	- Расширения:
		- Если формат файла не поддерживается, пользователю предлагается конвертировать файл.
		- Если размер файла превышает лимит, пользователь может выбрать сжатие файла перед загрузкой.
	- Исключения:
		- Ошибка загрузки из-за отсутствия интернет-соединения.
	- Циклы:
		- Пользователь может продолжать выбирать и загружать дополнительные медиафайлы.

2. Use Case: Офлайн-режим работы
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет загрузить файлы в хранилище в отсутствие интернет-соединения.
	- Конечная цель: Файлы сохраняются локально и автоматически загружаются в облако при восстановлении соединения.
	- Результат: Файлы успешно синхронизированы с облачным хранилищем после восстановления интернет-соединения.
	- Основной поток:
  	1. Пользователь выбирает файлы для загрузки в облако в режиме отсутствия интернета.
  	2. Приложение сохраняет задачу на загрузку файлов локально.
  	3. При восстановлении интернет-соединения, приложение автоматически начинает загрузку файлов в облако.
  	4. Пользователь получает уведомление о успешной синхронизации файлов.
	- Расширения:
	- Возможность просмотра и редактирования метаданных файлов в офлайн-режиме.
	- Исключения:
	- Неудачная попытка синхронизации из-за ошибок соединения или недостаточного пространства в облаке.
3. Use Case: Автоматическое тегирование медиафайлов
	- Актор: Система
	- Контекст применения: После загрузки медиафайлов в облако.
	- Конечная цель: К каждому медиафайлу автоматически присвоены теги на основе его содержания.
	- Результат: Улучшение поиска и организации медиафайлов.
	- Основной поток:
		1. Система анализирует содержание загруженных медиафайлов.
		2. Используя алгоритмы машинного обучения, система определяет ключевые объекты и сцены.
		3. К файлам автоматически присваиваются соответствующие теги.
		4. Пользователь получает уведомление о завершении процесса тегирования.
	- Расширения:
		- Пользователь может добавлять, удалять или редактировать теги вручную.
	- Исключения:
		- Ошибка при распознавании содержимого файла.
	- Циклы:
		- Процесс повторяется для каждого нового медиафайла, загружаемого в систему.
4. Use Case 6: Просмотр медиафайлов
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет просмотреть медиафайлы в облаке.
	- Конечная цель: Медиафайлы отображаются для просмотра.
	- Результат: Пользователь просматривает медиафайлы.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для просмотра.
		2. Система отображает выбранные медиафайлы.
		3. Пользователь может переключаться между файлами, увеличивать их или вращать.
	- Расширения:
		- Просмотр в режиме слайд-шоу.
	- Исключения:
		- Ошибка загрузки медиафайла для просмотра.
5. Use Case: Модуль монетизации
	- Актор: Пользователь
	- Контекст применения: Пользователь выбирает или изменяет свой тарифный план хранилища.
	- Конечная цель: Пользователь подписывается на подходящий платный тарифный план.
	- Результат: Увеличение объема хранилища в соответствии с выбранным тарифным планом.
	- Основной поток:
	1. Пользователь заходит в раздел настроек учетной записи.
	2. Переходит в раздел управления подпиской.
	3. Выбирает новый тарифный план из предложенных.
	4. Вводит данные платежной карты или подтверждает платеж через другую платежную систему.
	5. Система обрабатывает платеж и активирует новый тарифный план.
	- Расширения:
	- Предложение специальных условий для B2B клиентов.
	- Исключения:
	- Ошибка платежа из-за проблем с банковской картой или платежной системой.
6. Use Case 9: Создание альбомов и коллекций
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет организовать медиафайлы в альбомы или коллекции для удобного доступа и просмотра.
	- Конечная цель: Альбомы или коллекции успешно созданы и организованы.
	- Результат: Медиафайлы упорядочены в альбомах или коллекциях по выбору пользователя.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для включения в альбом или коллекцию.
		2. Пользователь задает название и, при желании, описание альбома или коллекции.
		3. Система создает альбом или коллекцию с выбранными медиафайлами.
		4. Пользователю отображается уведомление о создании альбома или коллекции.
	- Расширения:
		- Добавление обложки для альбома или коллекции.
	- Исключения:
		- Ошибка при создании альбома или коллекции.
7. Use Case 11: Просмотр и навигация по файловой системе хранилища пользователя
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет просмотреть структуру своего облачного хранилища и перемещаться по папкам.
	- Конечная цель: Пользователь может легко навигировать по своей файловой системе и находить нужные медиафайлы.
	- Результат: Пользователь просматривает и перемещается по файловой системе своего хранилища.
	- Основной поток:
		1. Пользователь открывает интерфейс файловой системы в своем хранилище.
		2. Система отображает структуру папок и файлов пользователя.
		3. Пользователь переходит между папками, просматривая содержимое.
		4. Пользователь выбирает медиафайл или папку для дальнейших действий (например, просмотр, загрузка).
	- Расширения:
		- Возможность просмотра медиафайлов в режиме предварительного просмотра прямо в файловой системе.
	- Исключения:
		- Ошибка при загрузке содержимого папки.
8. Use Case 3: Поиск по медиафайлам
	- Актор: Пользователь
	- Контекст применения: Пользователь ищет определенные медиафайлы в своем архиве.
	- Конечная цель: Найти и отобразить медиафайлы, соответствующие критериям поиска пользователя.
	- Результат: Пользователь получает список медиафайлов, удовлетворяющих запросу.
	- Основной поток:
		1. Пользователь вводит ключевые слова или выбирает теги для поиска.
		2. Система проводит поиск по базе данных метаданных и тегов.
		3. Система отображает список медиафайлов, соответствующих критериям поиска.
		4. Пользователь может просмотреть или скачать найденные медиафайлы.
	- Расширения:
		- Поиск по дате создания, местоположению и другим метаданным.
	- Исключения:
		- Не найдено медиафайлов, соответствующих критериям поиска.
9. Use Case 4: Удаление дубликатов медиафайлов
	- Актор: Система
	- Контекст применения: После загрузки пользователем новых медиафайлов.
	- Конечная цель: Идентификация и предложение пользователю удалить дубликаты медиафайлов для оптимизации хранилища.
	- Результат: Уменьшение количества дубликатов, освобождение места в облачном хранилище.
	- Основной поток:
		1. Система анализирует новые и существующие медиафайлы на предмет дубликатов.
		2. Идентифицированные дубликаты отображаются пользователю с предложением удалить.
		3. Пользователь принимает решение об удалении дубликатов.
		4. Система удаляет выбранные дубликаты и уведомляет пользователя об успешном завершении.
	- Расширения:
		- Автоматическое удаление дубликатов с предварительным уведомлением пользователя.
	- Исключения:
		- Ошибка при идентификации дубликатов.
10. Use Case 5: Конвертация форматов медиафайлов
	- Актор: Пользователь #TODO: Система может предложить конвертацию самостоятельно
	- Контекст применения: Пользователь хочет изменить формат медиафайла для совместимости или оптимизации хранения.
	- Конечная цель: Медиафайл успешно конвертирован в выбранный формат.
	- Результат: Файл доступен в новом формате в облачном хранилище.
	- Основной поток:
		1. Пользователь выбирает медиафайл для конвертации.
		2. Пользователь выбирает целевой формат файла.
		3. Система конвертирует файл в выбранный формат.
		4. Система уведомляет пользователя о завершении конвертации.
	- Расширения:
		- Выбор между сжатием с потерей и без потери качества.
		- Возможность отката конвертации.
	- Исключения:
		- Ошибка конвертации из-за несовместимости форматов.
11. Use Case 8: Синхронизация медиафайлов между устройствами
	- Актор: Пользователь
	- Контекст применения: Пользователь использует несколько устройств для доступа к облачному хранилищу.
	- Конечная цель: Медиафайлы синхронизированы между всеми устройствами пользователя.
	- Результат: Пользователь имеет доступ к одинаковому набору медиафайлов с любого устройства.
	- Основной поток:
		1. Пользователь вносит изменения в медиафайлы с одного устройства.
		2. Система автоматически синхронизирует изменения с другими устройствами пользователя.
	- Расширения:
		- Ручной запуск синхронизации.
	- Исключения:
		- Ошибка синхронизации из-за отсутствия интернет-соединения.
12. Use Case 10: Поделиться медиафайлами
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет поделиться медиафайлами с другими людьми.
	- Конечная цель: Медиафайлы доступны для просмотра или скачивания другими людьми по ссылке.
	- Результат: Получатели имеют доступ к поделенным медиафайлам.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для общего доступа.
		2. Система генерирует ссылку.
		3. Пользователь получает подтверждение о том, что общий доступ реализован.
		4. Пользователь выбирает способ поделиться ссылкой общего доступа(сохранить в буфер, соцсети, email).
	- Расширения:
		- Установка срока действия ссылки на медиафайлы.
	- Исключения:
		- Ошибка при создании ссылки или отправке медиафайлов.
13. Use Case 7: Управление приватностью медиафайлов
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет изменить настройки доступа к своим медиафайлам.
	- Конечная цель: Настройки приватности успешно применены к выбранным медиафайлам.
	- Результат: Медиафайлы имеют обновленные настройки приватности.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для изменения настроек приватности.
		2. Пользователь выбирает уровень доступа: только по ссылке или приватный.
		3. Система применяет выбранные настройки приватности к медиафайлам.
		4. Система уведомляет пользователя о успешном изменении настроек.
	- Расширения:
		- Настройка доступа на уровне папок.
	- Исключения:
		- Ошибка при изменении настроек приватности.
14. Use Case 12: Просмотр фото и видео с превью в интерфейсе приложения
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет просмотреть свои фото и видео в удобном интерфейсе файловой системы.
	- Конечная цель: Предоставить пользователю простой и удобный интерфейс для просмотра медиа.
	- Результат: Пользователь просматривает фото и видео в галерее с использованием превью.
	- Основной поток:
		1. Пользователь открывает галерею в облачном сервисе.
		2. Система отображает медиафайлы с превью.
		3. Пользователь кликает на превью для просмотра фото или видео в полном размере.
		4. Пользователь может пролистывать медиа в полноэкранном режиме.
	- Расширения:
		- Возможность включить слайд-шоу медиафайлов.
	- Исключения:
		- Ошибка при загрузке превью или полноразмерных медиафайлов.
15. Use Case 13: Загрузка медиафайлов на устройство
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет загрузить медиафайлы из облачного хранилища на свое устройство.
	- Конечная цель: Медиафайлы успешно загружены на устройство пользователя.
	- Результат: Пользователь имеет доступ к медиафайлам в оффлайне.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для загрузки на устройство.
		2. Пользователь инициирует процесс загрузки.
		3. Система загружает выбранные файлы на устройство пользователя.
		4. Пользователь получает уведомление о завершении загрузки.
	- Расширения:
		- Выбор качества или разрешения файла перед загрузкой для экономии места на устройстве.
	- Исключения:
		- Ошибка загрузки из-за проблем с соединением или недостаточным местом на устройстве.
16. Use Case 14: Сжатие файлов
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет сжать медиафайлы для экономии места в облачном хранилище.
	- Конечная цель: Медиафайлы успешно сжаты без значительной потери качества.
	- Результат: Сжатые медиафайлы занимают меньше места в хранилище.
	- Основной поток:
		1. Пользователь выбирает медиафайлы для сжатия.
		2. Пользователь выбирает тип сжатия (с потерей или без потери качества).
		3. Система сжимает выбранные файлы в соответствии с настройками пользователя.
		4. Система уведомляет пользователя о завершении процесса сжатия.
	- Расширения:
		- Предварительный просмотр файла до и после сжатия для оценки качества.
		- Возможность отката изменений.
	- Исключения:
		- Ошибка сжатия из-за неподдерживаемого формата файла.
17. Use Case 15: Выделение файлов и действия со всеми выделенными файлами одновременно
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет выполнить действия сразу с несколькими медиафайлами (удаление, перемещение, сжатие).
	- Конечная цель: Действия успешно выполнены для всех выбранных медиафайлов.
	- Результат: Пакетное управление медиафайлами упрощает организацию и управление хранилищем.
	- Основной поток:
		1. Пользователь в режиме просмотра файлов выбирает несколько медиафайлов.
		2. Пользователь выбирает действие для выполнения (например, удаление, перемещение в другую папку, сжатие).
		3. Система выполняет выбранное действие для всех выделенных файлов.
		4. Система уведомляет пользователя о результате выполнения действия.
	- Расширения:
		- Возможность отмены действия для предотвращения случайного удаления или изменения файлов.
	- Исключения:
		- Ошибка выполнения действия из-за проблем с доступом к файлам или недостаточных прав пользователя.
18. Use Case 16: Удаление медиафайла
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет удалить медиафайл из облачного хранилища.
	- Конечная цель: Медиафайл успешно удален из хранилища.
	- Результат: Медиафайл больше не доступен в облачном хранилище, освобождая место.
	- Основной поток:
		1. Пользователь выбирает медиафайл для удаления.
		2. Система запрашивает подтверждение у пользователя, чтобы избежать случайного удаления.
		3. Пользователь подтверждает удаление медиафайла.
		4. Система удаляет медиафайл из хранилища.
		5. Пользователю отображается уведомление об успешном удалении файла.
	- Расширения:
		- Возможность восстановления недавно удаленных файлов из корзины или архива. #TODO: Определить срок (30 дней)
	- Исключения:
		- Ошибка удаления файла из-за технических проблем или нарушения прав доступа.
19. Use Case 17: Добавление своего тега к медиафайлу
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет добавить индивидуальный тег к медиафайлу для улучшения организации и поиска.
	- Конечная цель: Медиафайл обогащен пользовательским тегом.
	- Результат: Улучшена организация медиафайлов и облегчен поиск по индивидуальным критериям пользователя.
	- Основной поток:
		1. Пользователь выбирает медиафайл для добавления тега.
		2. Пользователь вводит текст тега и подтверждает добавление.
		3. Система присваивает введенный тег медиафайлу.
		4. Пользователю отображаются изменённые теги медиафайла.
	- Расширения:
		- Возможность выбора из уже существующих тегов.
	- Исключения:
		- Ошибка добавления тега из-за ограничений системы или неверного формата ввода.
20. Use Case 18: Удаление тега из медиафайла
	- Актор: Пользователь
	- Контекст применения: Пользователь хочет удалить ранее добавленный тег из медиафайла.
	- Конечная цель: Тег успешно удален из медиафайла.
	- Результат: Медиафайл больше не ассоциирован с удаленным тегом, что упрощает организацию и поиск.
	- Основной поток:
		1. Пользователь выбирает медиафайл из которого нужно удалить тег.
		2. Пользователь выбирает тег(и), который(е) нужно удалить.
		3. Система запрашивает подтверждение у пользователя на удаление тега(ов).
		4. После подтверждения пользователя, система удаляет выбранный тег из медиафайла.
		5. Пользователю отображается уведомление об успешном удалении тега.
	- Расширения:
		- Возможность одновременного удаления нескольких тегов у медиафайла.
	- Исключения:
		- Ошибка удаления тега из-за технических проблем или ограничений доступа.
21. Use Case: Развертывание системы on-premise
	- Актор: Бизнес-клиент (B2B)
	- Контекст применения: Бизнес-клиент хочет развернуть систему умного хранения фотографий и видео на собственных серверах.
	- Конечная цель: Система успешно развернута в инфраструктуре клиента, полностью интегрирована и настроена под его нужды.
	- Результат: Бизнес-клиент имеет полностью функционирующую систему на своей территории с возможностью полного контроля и управления данными.
	- Основной поток:
		1. Бизнес-клиент обращается в службу поддержки или отдел продаж с запросом на развертывание системы on-premise.
		2. Служба поддержки проводит первичную консультацию, собирает требования и передает запрос в отдел интеграции.
		3. 
		4. Подписание договора на развертывание системы, включая согласование персональных условий, стоимости и сроков реализации.
		5. Команда проекта осуществляет развертывание системы, настройку и интеграцию с существующей инфраструктурой клиента.
		6. Проведение обучения персонала и передача всех необходимых материалов для работы с системой.
		7. Переход системы в эксплуатацию с предоставлением технической поддержки.
	- Расширения:
		- Возможность выбора между стандартной и расширенной версией системы.
	- Исключения:
		- Отказ клиента от дальнейшего сотрудничества из-за неудовлетворения требованиями или ценой.
22. Use Case: Персонализированные услуги для юридических лиц
	- Актор: Бизнес-клиент (B2B)
	- Контекст применения: Бизнес-клиент заинтересован в получении услуг облачного хранилища на персональных условиях.
	- Конечная цель: Клиент получает доступ к услугам облачного сервиса, адаптированным под его специфические бизнес-требования.
	- Результат: Успешная интеграция и использование сервиса с учетом всех потребностей и требований бизнес-клиента.
	- Основной поток:
		1. 
		2. Менеджер по работе с клиентами проводит первичную встречу (онлайн или офлайн) для обсуждения потребностей и требований клиента.
		3. Отдел продаж и технические специалисты разрабатывают индивидуальное предложение, включая спецификацию услуг, план интеграции и ценообразование.
		4. Предложение представляется клиенту для согласования. При необходимости проводятся дополнительные переговоры для уточнения деталей.
		5. Подписание договора на предоставление услуг с учетом всех согласованных условий.
		6. Реализация проекта в соответствии с планом, включая настройку, интеграцию сервиса и обучение персонала.
		7. Предоставление постоянной технической поддержки и периодическое обновление сервиса в соответствии с договором.
	- Расширения:
		- Разработка и внедрение дополнительных функций по запросу клиента.
	- Исключения:
		- Отказ клиента от предложения на стадии согласования условий из-за финансовых ограничений или изменения бизнес-требований.
## Нефункциональные требования
1. Производительность и Быстродействие
	- Обработка запросов: Обеспечение обработки запросов пользователя (загрузка, поиск, удаление, теггирование) в среднем за 1 секунду или меньше.
	- Инструменты и методы:
		- Применение эффективных алгоритмов и индексирования данных.
		- Использование кэширования для часто запрашиваемых данных.
		- Распределенная обработка данных для минимизации задержек.
2. Масштабируемость
	- Объем хранения и обработки: Способность системы масштабироваться для обслуживания большего количества пользователей и объема данных до 5 TB в месяц.
	- Инструменты и методы:
		- Использование инфраструктуры с возможностью горизонтального масштабирования.
		- Автоматическое расширение ресурсов в зависимости от текущей нагрузки.
3. Безопасность и Конфиденциальность данных
	- Защита данных: Использование современных методов шифрования данных во время передачи и хранения. Реализация механизмов аутентификации и авторизации.
	- Инструменты и методы:
		- SSL/TLS для защиты данных во время передачи.
		- Системы управления доступом и идентификации пользователей.
4. Доступность и Отказоустойчивость
	- Время работы: Цель в 99.9% доступности сервиса для пользователей.
	- Инструменты и методы:
		- Развертывание в высокодоступной облачной инфраструктуре.
		- Использование отказоустойчивых компонентов и дублирование критически важных систем.
5. Резервное копирование и Восстановление
	- Стратегия защиты данных: Автоматическое резервное копирование и возможности восстановления на уровне отдельных файлов и целых архивов.
	- Инструменты и методы:
		- Регулярное резервное копирование данных.
		- Возможность восстановления данных пользователем через интерфейс сервиса.
6. Управление данными
	- Оптимизация хранения: Поддержка эффективных методов сжатия данных и автоматического удаления дубликатов с целью рационального использования ресурсов.
	- Инструменты и методы:
		- Использование алгоритмов сжатия с потерей и без потери для различных типов данных.
		- Разработка алгоритмов для обнаружения и управления дубликатами изображений и видео.
7. Интерфейс пользователя
	- Доступность и удобство: Интерфейс должен быть интуитивно понятным для всех категорий пользователей, адаптирован под мобильные и десктопные устройства.
	- Инструменты и методы:
		- Кроссплатформенность
		- Применение принципов адаптивного и отзывчивого интерфейса.
		- Разработка пользовательских интерфейсов с учетом лучших практик UX/UI.
8. Расширяемость
	- Интеграция и добавление функций: Способность легко добавлять новые функции и интегрироваться с другими сервисами.
	- Инструменты и методы:
		- Предоставление обширного API для интеграции.
		- Соблюдение стандартов совместимости и открытых протоколов.
9. Мониторинг и Логирование
	- Отслеживание и улучшение сервиса: Наличие систем мониторинга и логирования для анализа работы системы и поведения пользователей.
	- Инструменты и методы:
		- Использование инструментов мониторинга реального времени.
		- Логирование операций и событий системы для последующего анализа.
