1. запускается код
uvicorn main:app --reload

2. далее переходим по ссылке
http://127.0.0.1:8000/docs

там есть эндпоинты:
POST /api/jobs — для создания задачи на анализ

GET /api/jobs/{jobId} — для получения результатов

3. переходим в POST /api/jobs

нажимаем Try it out, далее заменяем в шаблоне JSON

{
  "source": "drugs.mp4",
  "customerId": "student_user_1",
  "profile": "FULL",
  "detectionClasses": [
    {
      "class": "DRUGS",
      "subclasses": ["alcohol", "drugs"]
    }
  ]
}

далее нажимаем Execute, получаем jobID, копируем его, переходим на GET /api/jobs/{jobId}, нажимаем снова Try it out, вставляем
наш ID и нажимаем Execute.

4. если обработка видео завершилась то вернется JSON файл в котором будет вся информация
