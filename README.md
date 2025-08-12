# Multipublisher_upload_post

Полная автоматизация создания и публикации AI‑видео для соцсетей
Описание проекта
Этот n8n-флоу реализует автоматизированный пайплайн: от генерации идеи и сценария ролика — до публикации готового видео на всех ключевых соцсетях (TikTok, Instagram, YouTube, Facebook, LinkedIn и др.). Решение сочетает мощности OpenAI, генерацию изображений/видео через Flux и Kling (PiAPI), синтез речи на ElevenLabs, видеомонтаж на Creatomate, а подробный трекинг ведётся через Google Sheets и Google Drive.

Задача: создать яркое POV‑shorts видео под каждую идею из Google Sheets, наложить voice over, авторские субтитры, промо‑описание — и мгновенно растиражировать на платформах одним кликом.

🧩 Технологии и сервисы
n8n — оркестрация автоматизации и интеграций.

OpenAI (GPT‑4, GPT‑4o‑mini) — генерация сценариев, раскадровок, voiceover'ов и описаний.

PiAPI (Flux/Kling) — генерация hyper-realistic изображений и short‑видео.

ElevenLabs — генерация энергичной дубляжа-озвучки.

Creatomate — автоматический монтаж final видео (клипы, субтитры, аудио).

Google Sheets/Drive — хранение идей, истории, готового контента.

upload-post.com API — автопостинг на все площадки (TikTok, Instagram, YouTube, Facebook, LinkedIn).

💡 Как работает пайплайн
Загрузка идей:

Идеи для роликов берутся из Google Sheets (Лист2). Можно использовать готовый шаблон.

Генерация сценария и подписей:

OpenAI (через специальные промпты) создает 5 частей сюжета + короткие кликбейт‑caption для соцсетей.

Генерация изображений:

Для каждой сцены строится детализированный, POV-ориентированный prompt.

Flux (PiAPI) делает hyperrealistic вертикальные изображения (540x960), имитируя контент TikTok/Instagram.

Видеогенерация:

Каждое изображение превращается в короткий видеоклип при помощи Kling (PiAPI).

Проводится мониторинг, автоматическая обработка неудач и повторные попытки.

Генерация и интеграция voiceover:

OpenAI пишет объёмный, юморной voiceover-текст, оптимизированный под ролик.

ElevenLabs синтезирует аудиодорожку. Файл заливается на Google Drive.

Монтаж полного ролика:

Creatomate комбинирует все generated видео + voiceover + субтитры в один динамичный ролик.

Финальный файл автоматически попадает на Google Drive, с открытым доступом по ссылке.

Оформление описания:

OpenAI по аудиодорожке генерирует релевантное соцсетевое описание для TikTok/Instagram/YouTube и др.

Публикация:
Видео и промо‑текст автоматически отправляются через upload-post.com API на все подключённые платформы.

Статусы и ссылки обновляются в Google Sheets.


<img width="1536" height="1024" alt="3393c1a0-0c44-47d7-ba22-c467ff1bcd39" src="https://github.com/user-attachments/assets/f921a9e5-a7b8-481b-ab47-b1296ede116e" />

📋 Структура n8n-флоу (ключевые ноды)

Шаг	Узел в n8n	Задача
1	Load Google Sheet	Получение идеи для ролика
2	Generate Video Captions	Генерация креативных подписей/сцен
3	Create List & Validate list	Формирование массива сцен
4	Generate Image Prompts	Расширение и “кинематографизация” промптов
5	Generate Image + ожидание	Создание изображений
6	Image-to-Video	Генерация коротких видео из изображений
7	Промпт для текста VO + Generate voice	Написание и озвучка voiceover
8	Upload Voice Audio + Set Access Permissions	Загрузка на Google Drive
9	Match captions with videos	Сопоставление сцен, видео, аудио
10	Render Final Video (Creatomate)	Автоматический монтаж
11	Upload Final Video + Set Permissions	Google Drive, доступ ссылкой
12	Get Audio from Video	Распознавание аудио для описания
13	Generate Description...	Автогенерация соцсетевых описаний
14	Read Video	Подготовка для автопостинга
15	Upload Video...to [platform]	Публикация на TikTok, Instagram, YouTube, Facebook, LinkedIn
16	Update Google Sheet	Логирование, трекинг итогов

🛠️ Быстрый старт
Настройте сервисы и получите API-ключи:

OpenAI, PiAPI (для Flux/Kling), ElevenLabs, Creatomate, Google Cloud (Sheets+Drive), upload-post.com.

Создайте или скопируйте Google Sheet по шаблону.

Импортируйте JSON-флоу в ваш n8n (подходит для self-hosted и cloud-версии).

Укажите свои ключи и настройки в специальных нодах Set API Keys.

Готово! Достаточно добавить идею в Google Sheet — и ролик будет создан и опубликован автоматически.

🏆 Плюсы этого решения
100% без рук: процесс “от идеи до публикации” полностью автоматизирован.

Viral-ready: искусственно “вирушные”, edgy-сценарии для соцсетей.

Любая платформа: единый постинг во все важные соцсети, включая ролики для shorts/reels.

Лёгкое масштабирование: работает с любыми тематиками и объёмами.

⚠️ Требования
n8n 1.81.4+

аккаунты в OpenAI, PiAPI, ElevenLabs, Creatomate, upload-post.com

включенный Google Sheets и Google Drive API

OAuth–клиент для Google-аккаунта

📜 Лицензия
MIT — свободно используйте и дорабатывайте под свои нужды.



Видео и промо‑текст автоматически отправляются через upload-post.com API на все подключённые платформы.

Статусы и ссылки обновляются в Google Sheets.
