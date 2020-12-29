# Trivia_API APP
 This project is a simple view for some questions and their answers , there are some categories for these questions , every question has a difficulty level from one to five. You can add new question or delete exsisting questions, also you can search for specific question.Additionally there is a simple quiz game that select random questions and you answer to them and get a score finally based on your answers.
 
 All backend code follows PEP8 style guidelines

 # Getting started
  pre-requisities and local development:
   
   Backend:

    install dependencies by naviging to the `/backend` directory and running:

        ```bash
        pip install -r requirements.txt
        ```
        With Postgres running, restore a database using the trivia.psql file provided. From the backend folder in terminal run:
        ```bash
        psql trivia < trivia.psql
        ```
        To run the server, execute:
        ```bash
        export FLASK_APP=flaskr
        export FLASK_ENV=development
        flask run
        ```
        This will run locally on http://127.0.0.1:5000 and is a proxy in the frontend cofiguration
     
     Frontend:

        ```bash
        npm start
        ```
        This will start http://localhost:3000 to view the frontend react app
  
  # Tests
   To run tests excute:
    ```
    dropdb trivia_test
    createdb trivia_test
    psql trivia_test < trivia.psql
    python test_flaskr.py
    ```


 # API Reference
  # Getting Started
    Base URL: At present this app can only be run locally and is not hosted as a base URL. The backend app is hosted at http://127.0.0.1:5000/ which is set as a proxy in the frontend configuration.
    
    Authentication: This version of the app does not require authentication or API keys

  # Error Handling
    errors are returned as JSON objects in the following format:
    {
        'success':False,
        'error':404,
        'message':'resource not found'
    }
    The API will return these error types:
    404: resource not found
    422: Unprocessable Entity
    500: Internal Server Error
    
  # Endpoints:
   # GET /categories
    General:
    Returns list of categories of questions
    Sample: curl http://127.0.0.1:5000/categories
        {
        "num_of_results": 6,
        "results": [
            [
            "Science"
            ],
            [
            "Art"
            ],
            [
            "Geography"
            ],
            [
            "History"
            ],
            [
            "Entertainment"
            ],
            [
            "Sports"
            ]
        ],
        "success": true
        }
    #######################################################################################################
   # GET /questions
    General:
    Returns list of questions which are paginated as every page has 10 questions
    Returns total num. of questions
    Sample: curl http://127.0.0.1:5000/questions
        {
        "categories": [
            [
            "Science"
            ],
            [
            "Art"
            ],
            [
            "Geography"
            ],
            [
            "History"
            ],
            [
            "Entertainment"
            ],
            [
            "Sports"
            ]
        ],
        "questions": [
            {
            "answer": "Muhammad Ali",
            "category": 4,
            "difficulty": 1,
            "id": 9,
            "question": "What boxer's original name is Cassius Clay?"
            },
            {
            "answer": "Apollo 13",
            "category": 5,
            "difficulty": 4,
            "id": 2,
            "question": "What movie earned Tom Hanks his third straight Oscar nomination, in 1996?"
            },
            {
            "answer": "Tom Cruise",
            "category": 5,
            "difficulty": 4,
            "id": 4,
            "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
            },
            {
            "answer": "Edward Scissorhands",
            "category": 5,
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
            },
            {
            "answer": "Brazil",
            "category": 6,
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
            },
            {
            "answer": "Uruguay",
            "category": 6,
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
            },
            {
            "answer": "George Washington Carver",
            "category": 4,
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
            },
            {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
            },
            {
            "answer": "The Palace of Versailles",
            "category": 3,
            "difficulty": 3,
            "id": 14,
            "question": "In which royal palace would you find the Hall of Mirrors?"
            },
            {
            "answer": "Agra",
            "category": 3,
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
            }
        ],
        "success": true,
        "total_questions": 19
        }
        #######################################################################################################
   # DELETE /questions/{question_id}
    General:
    Deletes the question that has {question_id} from the database
    
    Sample: curl -X DELETE http://127.0.0.1:5000/questions/50
        {
        "deleted": 50,
        "num_of_results": 18,
        "results": [
            {
            "answer": "Muhammad Ali",
            "category": 4,
            "difficulty": 1,
            "id": 9,
            "question": "What boxer's original name is Cassius Clay?"
            },
            {
            "answer": "Apollo 13",
            "category": 5,
            "difficulty": 4,
            "id": 2,
            "question": "What movie earned Tom Hanks his third straight Oscar nomination, in 1996?"
            },
            {
            "answer": "Tom Cruise",
            "category": 5,
            "difficulty": 4,
            "id": 4,
            "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
            },
            {
            "answer": "Edward Scissorhands",
            "category": 5,
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
            },
            {
            "answer": "Brazil",
            "category": 6,
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
            },
            {
            "answer": "Uruguay",
            "category": 6,
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
            },
            {
            "answer": "George Washington Carver",
            "category": 4,
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
            },
            {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
            },
            {
            "answer": "The Palace of Versailles",
            "category": 3,
            "difficulty": 3,
            "id": 14,
            "question": "In which royal palace would you find the Hall of Mirrors?"
            },
            {
            "answer": "Agra",
            "category": 3,
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
            },
            {
            "answer": "Escher",
            "category": 2,
            "difficulty": 1,
            "id": 16,
            "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
            },
            {
            "answer": "Mona Lisa",
            "category": 2,
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
            },
            {
            "answer": "One",
            "category": 2,
            "difficulty": 4,
            "id": 18,
            "question": "How many paintings did Van Gogh sell in his lifetime?"
            },
            {
            "answer": "Jackson Pollock",
            "category": 2,
            "difficulty": 2,
            "id": 19,
            "question": "Which American artist was a pioneer of Abstract Expressionism, and a leading exponent of action painting?"
            },
            {
            "answer": "Blood",
            "category": 1,
            "difficulty": 4,
            "id": 22,
            "question": "Hematology is a branch of medicine involving the study of what?"
            },
            {
            "answer": "Scarab",
            "category": 4,
            "difficulty": 4,
            "id": 23,
            "question": "Which dung beetle was worshipped by the ancient Egyptians?"
            },
            {
            "answer": "tom",
            "category": 4,
            "difficulty": 2,
            "id": 25,
            "question": "what is the name of voldemort"
            },
            {
            "answer": "a",
            "category": 4,
            "difficulty": 1,
            "id": 49,
            "question": "a"
            }
        ],
        "success": true
        }
        #######################################################################################################
   # POST /questions/add
    General:
    insert new question in the database
    
    Sample: curl --header "Content-Type: application/json" -X POST -d "{\"question\":\"what??\",\"answer\":\"yess!!\",\"difficulty\":2,\"category\":2}" http://127.0.0.1:5000/questions/add
        {
        "added": 51,
        "num_of_results": 19,
        "results": [
            {
            "answer": "Muhammad Ali",
            "category": 4,
            "difficulty": 1,
            "id": 9,
            "question": "What boxer's original name is Cassius Clay?"
            },
            {
            "answer": "Apollo 13",
            "category": 5,
            "difficulty": 4,
            "id": 2,
            "question": "What movie earned Tom Hanks his third straight Oscar nomination, in 1996?"
            },
            {
            "answer": "Tom Cruise",
            "category": 5,
            "difficulty": 4,
            "id": 4,
            "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
            },
            {
            "answer": "Edward Scissorhands",
            "category": 5,
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
            },
            {
            "answer": "Brazil",
            "category": 6,
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
            },
            {
            "answer": "Uruguay",
            "category": 6,
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
            },
            {
            "answer": "George Washington Carver",
            "category": 4,
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
            },
            {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
            },
            {
            "answer": "The Palace of Versailles",
            "category": 3,
            "difficulty": 3,
            "id": 14,
            "question": "In which royal palace would you find the Hall of Mirrors?"
            },
            {
            "answer": "Agra",
            "category": 3,
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
            },
            {
            "answer": "Escher",
            "category": 2,
            "difficulty": 1,
            "id": 16,
            "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
            },
            {
            "answer": "Mona Lisa",
            "category": 2,
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
            },
            {
            "answer": "One",
            "category": 2,
            "difficulty": 4,
            "id": 18,
            "question": "How many paintings did Van Gogh sell in his lifetime?"
            },
            {
            "answer": "Jackson Pollock",
            "category": 2,
            "difficulty": 2,
            "id": 19,
            "question": "Which American artist was a pioneer of Abstract Expressionism, and a leading exponent of action painting?"
            },
            {
            "answer": "Blood",
            "category": 1,
            "difficulty": 4,
            "id": 22,
            "question": "Hematology is a branch of medicine involving the study of what?"
            },
            {
            "answer": "Scarab",
            "category": 4,
            "difficulty": 4,
            "id": 23,
            "question": "Which dung beetle was worshipped by the ancient Egyptians?"
            },
            {
            "answer": "tom",
            "category": 4,
            "difficulty": 2,
            "id": 25,
            "question": "what is the name of voldemort"
            },
            {
            "answer": "a",
            "category": 4,
            "difficulty": 1,
            "id": 49,
            "question": "a"
            },
            {
            "answer": "yess!!",
            "category": 3,
            "difficulty": 2,
            "id": 51,
            "question": "what??"
            }
        ],
        "success": true
        }
    #######################################################################################################
   # POST /questions/search
    General:
    searches the database and returns questions that {search_term} is part of the question
    Sample: curl --header "Content-Type: application/json" -X POST -d "{\"searchTerm\":\"what\"}" http://127.0.0.1:5000/questions/search
        {
        "num_of_results": 4,
        "results": [
            {
            "answer": "Mona Lisa",
            "category": 2,
            "difficulty": 3,
            "id": 17,
            "question": "La Giaconda is better known as what?"
            },
            {
            "answer": "Blood",
            "category": 1,
            "difficulty": 4,
            "id": 22,
            "question": "Hematology is a branch of medicine involving the study of what?"
            },
            {
            "answer": "tom",
            "category": 4,
            "difficulty": 2,
            "id": 25,
            "question": "what is the name of voldemort"
            },
            {
            "answer": "yess!!",
            "category": 3,
            "difficulty": 2,
            "id": 51,
            "question": "what??"
            }
        ],
        "success": true
        }
    #######################################################################################################
   # GET /categories/{category_id}/questions
    General:
    Returns list of questions in specific category
    Sample: curl http://127.0.0.1:5000/categories/2/questions
        {
        "current_category": 3,
        "num_of_results": 4,
        "results": [
            {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
            },
            {
            "answer": "The Palace of Versailles",
            "category": 3,
            "difficulty": 3,
            "id": 14,
            "question": "In which royal palace would you find the Hall of Mirrors?"
            },
            {
            "answer": "Agra",
            "category": 3,
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
            },
            {
            "answer": "yess!!",
            "category": 3,
            "difficulty": 2,
            "id": 51,
            "question": "what??"
            }
        ],
        "success": true
        }
    #######################################################################################################
   # POST /quiz
    General:
    Returns a random question every time from selected categry by the user
    The random question shoud not be repeated again in the same quiz
    Sample: curl --header "Content-Type: application/json" --request POST --data "{\"quiz_category\":{\"id\":2},\"previous_questions\":[16,17]}" http://127.0.0.1:5000/quiz
        {
        "results": {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
        },
        "success": true
        }


 # Author
  Mostafa Elhabrok

 # Acknowledgements
  The awesome team of Udacity# trivia_api
