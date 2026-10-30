# Online Course App – Assessment Feature

This project extends the IBM Django online course application with an assessment feature.

## Features
- Course, lesson, instructor, learner and enrollment management.
- Questions linked to courses, choices linked to questions, and submissions linked to enrollments.
- Django admin inlines for lessons, questions and choices.
- Authenticated course enrollment and assessment submission.
- Automatic grading and a detailed assessment result page.

## Run locally

1. Create and activate a virtual environment.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Create database migrations and migrate:
   ```bash
   python manage.py makemigrations onlinecourse
   python manage.py migrate
   ```
4. Create an administrator:
   ```bash
   python manage.py createsuperuser
   ```
5. Start the server:
   ```bash
   python manage.py runserver
   ```
6. Open `http://127.0.0.1:8000/admin/`, add a course, lessons, questions and choices. Add at least one question with one or more correct choices.
7. Register a learner account, enroll in the course, and submit the assessment.

## Assessment data model
- `Question`: belongs to a `Course`; stores `question_text` and `grade`.
- `Choice`: belongs to a `Question`; stores `choice_text` and `is_correct`.
- `Submission`: belongs to an `Enrollment`; stores selected choices through a many-to-many relationship.

## Notes
The application uses SQLite by default. Bootstrap is loaded from its public CDN, so an internet connection is needed for Bootstrap styling in the browser.
