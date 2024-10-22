# ISWD Project

## Project Overview
This project utilizes Django for the backend to manage user data and interactions with a frontend built using Vue.js.

## Installation and Setup
Clone the repository:
```bash
git clone https://github.com/mati-kw/iswd.git
cd iswd
```
## Backend Setup
- Navigate to the backend directory, set up the virtual environment, and start the Django server:

```bash
cd backend
pipenv install
pipenv shell
python manage.py migrate
python manage.py runserver
```
- create a local database called: `iswd_db`.
- In backend directory create a `secrets.json` file with such content:
```bash
{
  "DATABASE_PASSWORD": "your_password_here"
}
```

## Frontend Setup
Navigate to the frontend directory and start the Vue.js application:

```bash
cd ../frontend
npm install
npm run dev
```

## How to Contribute
To contribute to this project, please follow these steps:

- Fork the repository.
- Create a feature branch: git checkout -b new-feature
- Commit your changes: git commit -m 'Add some feature'
- Push to the branch: git push origin new-feature
- Submit a merge request.


