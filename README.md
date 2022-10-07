# Unity


## Requirements

- Create and activate a virtual environment
- Run `pip install -r requirements.txt` to install dependencies
- Create a `.env` file and add the following data:

```
DJANGO_SECRET_KEY=
PG_NAME=
PG_USER=
PG_PASSWORD=
PG_HOST=
PG_PORT=
PG_TEST_NAME=
DEFAULT_FROM_EMAIL=
EMAIL_HOST=
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
EMAIL_PORT=
```

- Install and run [Redis](https://redis.io/topics/quickstart)
- Run `python3 manage.py migrate` to create the database
- Run following commands simultaneously in different terminals:

  - Run `python3 manage.py runserver`.
  - Run `celery -A cache_celery.celery worker -l info`.
  - Run `celery -A cache_celery.celery beat -l info`.

- Run `python3 manage.py test` to run the tests.

- The server will start in [http://127.0.0.1:8000](http://127.0.0.1:8000)

##

### Completed Tasks

- [x] Added subscriber checkbox with `useState hook` in the `widgets.js`.
- [x] Created a Django project inside the repo.
- [x] Created Django app with name - unity.
- [x] Created a data model to store the emails.
- [x] Exposed an REST API to be used by the widget to submit the email data.
- [x] Created a Django view for listing the emails. As shown in the figma file for reference.
- [x] Bonus
  - [x] Created a celery periodic task that runs every Monday and Wednesday and `sends newsletter via email` to all subscribers.
  - [x] Printed the `number of new emails` added in the current calendar month to the console.
  - [x] Added `unit testing`.
  - [x] Added `GitHub Actions CI` for the project.
  - [x] Added `token` based authentication.
  - [x] Added API documentation using `drf-spectacular`.

##

## Endpoints

- `GET /api/v1/unity/subscribers/` - To get one/all the subscribers.
- `POST /api/v1/unity/subscribe/` - To subscribe to the newsletter.
- `PUT /api/v1/unity/subscribers/` - To update the subscriber.
- `DELETE /api/v1/unity/subscribers/` - To delete the subscriber.
- `POST /api/v1/token/create` - To get the token.
- `GET /api/v1/schema/swagger` - To get the API documentation.
- `ANY /api/v1/unity/dummy` - To get the API documentation.

- `GET /api/v1/unity` - To get the list of subscribers.

