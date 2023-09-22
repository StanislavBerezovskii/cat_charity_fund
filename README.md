# Project QRKot_Spreadsheets:
A training project completed as part of the "Yandex.Practicum, Python Developer+" online course.
Project QRKot is a platform for a charity fund for cats.
___

## About:
The foundation collects donations for various targeted projects: such as medical care for cats in need,
setting up cat colonies in the basement, getting food for cats left without care - for any purpose,
related to supporting the cat population.

- Fund Projects:
Several targeted projects can be opened in the QRKot Foundation.
Each project has a name, description and a target amount planned to be raised.
After the required amount is collected, the project is closed.
Donations to projects are received on a First In, First Out basis:
all donations go to the project that was opened earlier than others;
when this project reaches the target amount and is closed -
donations are starting to pour in for the next project.

- Donations:
Any user can make a donation and accompany it with a comment.
Donations are not targeted: they are given to the fund, not to a specific project.
Every donation received is automatically transfered to the first open project,
who has not yet collected the required amount. If the donation is more than the required amount or
There are no open projects in the Fund - the remaining money is waiting for the opening of the next project.
When creating a new project, all uninvested donations are automatically
are investing in a new project.
___

## Technologies:
* [Python version 3.9 and higher](https://www.python.org/downloads/)
* [FastAPI](https://fastapi.tiangolo.com/)
* [FastAPI Users](https://fastapi-users.github.io/fastapi-users/10.1/)
* [SQLAlchemy](https://www.sqlalchemy.org/)
* [Alembic](https://alembic.sqlalchemy.org/en/latest/index.html)
___

## Installation:
Clone the project:
   ```
   git clone https://github.com/sniki-ld/cat_charity_fund.git
   ```
Go to the project folder:
   ```
   cd cat_charity_fund
   ```
Create and activate a virtual environment:
   ```
   python -m venv venv
   ```
   ```
   source venv/Scripts/activate
   ```
Update your package manager (pip):
   ```
   pip3 install --upgrade pip
   ```
Install the required dependencies:
   ```
   pip install -r requirements.txt
   ```
Create a file with environment variables `.env`:
   ```
   touch .env
   ```
Set the environment variables:
   ```
   APP_TITLE=<your application name>
   APP_DESCRIPTION=<your project description>
   DATABASE_URL=<database connection settings, for example: sqlite+aiosqlite:///./development.db>
   SECRET=<secret key>
   FIRST_SUPERUSER_EMAIL=<email of the first superuser>
   FIRST_SUPERUSER_PASSWORD=<first superuser password>
   ```
___

## Usage:
Create migrations to create the database:
  ```
  alembic revision --autogenerate -m "<ваше название миграции>"
  ```
Apply migrations to create the database:
  ```
  alembic upgrade head
  ```
To run the project, run the command:
  ```
  uvicorn app.main:app --reload
  ```

_If the following variables were set in the `.env` file
`FIRST_SUPERUSER_EMAIL` and `FIRST_SUPERUSER_PASSWORD`,
then the first time the application is launched, a superuser will be created in the database.
This data can be used for authorization._
___

## API Documentation:
Project documentation:
 - `/docs` — documentation in Swagger format;
 - `/redoc` — documentation in ReDoc format.
___

## Project Author:
Stanislav Berezovskii
___

## Licensing:
- ### **MIT License**
___
