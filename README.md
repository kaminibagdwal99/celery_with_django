What is Celery?

It is a task queue for executing work outside a python web applications HTTP request-response cycle.

A task queue's input is a unit of ork caleed a task. Dedicated worker processes constanly monitor task queue for new work to perform.

Celery is written in python, but the protocal can be implemented in any languague. in addition to python, there node-celery and node-celery-ts for Node,js and PHP client.
 
 Request-broker-celery-Response

 django send task to broker which can be redis / rabbitmq, so broker will work in fifo manner task 1 will be executed first then task 2 , if we have 4 worker and we have 4 task it can be perform simultaneouly.

 suppose we have to schedule a task at some time,so how to perofrm peridioc task.so here celery beat which schedule the task at some time on some day.


 Why Celery if we have multithreading, async and multiprocessing?
 for heavy task use celery

 why to use celery :
 1. third party api
 2. for high CPU intensive tasks
 3. Periodic/Schedule Tasks
 4. For improving the User experience 




# celery_with_django
1.create project and app and install celery and redis
2.In setting.py: CELERY_BROKER_URL = 'redis://127.0.0.1:6379'
                CELERY_ACCEPT_CONTENT = ['application/json']
                CELERY_RESULT_SERIALIZER ='json'
                CELERY_TASK_SERIALIZER = 'json'
                CELERY_TIMEZONE = 'Asia/Kolkata'
                CELERY_RESULT_BACKEND ='django-db'

                #celery beat

                CELERY_BEAT_SCHEDULER = 'django_celery_beat.schedulers:DatabaseScheduler'

3.