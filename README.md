
-1
# project structure :

pets-adoption-platform/
|
|___src/
|   |_____routes/
|   |      |________pets.routes.js
|   |      |________clinics.routes.js
|   |      |________articles.routes.js
|   |_____controllers/
|   |      |___________pets.controller.js
|   |      |___________clinics.controller.js
|   |      |___________articles.controller.js
|   | 
|   |_____middlewares
|   |_____Data/ (or)   models/  when dealing with mongoDB   (pet.model.js, clinic.model.js ,...)                
|   |     |______data.js                                  
|   |                                       
|   |_____app.js
|   |_____server.js
|___ .gitIgnore
|___ .env
└── README.md 
__________________________________
# libraries :
|     express
|---------------
|     morgan
|---------------
|     dotenv 
|---------------
|     nodemon
_____________________________________________________________________________

-2 + 3
# APIs

## Get available pets in my City

- Method : Get
- Endpoint: '/api/pets'
- Query Parameters : location (optional ) , type (optional)
- Response:

// Get : '/api/pets?location=lattakia&type=cat'
  { "message" : "pets retrieved successfully",
    "pets": [
      { "id": 1,
        "name": "bmbush",
        "type": "cat",
        "location": "lattakia" 
      },
      ...
    ]
  }
  
- Errors:
  - 400 (invalid query params)
  - 404 (no pets found)

## find open clinic for emergency

- Method : Get
- Endpoint: '/api/clinics/emergency'
- Query Parameters : location (required ) , open (optional)
- Response:

// Get : '/api/clinics/emergency?location=lattakia&open=true'
  { "message" : "clinics retrieved successfully",
    "clinics": [
      { "id": 1,
        "name": "clinica1",
        "emergency"= true
        "open" : true,
        "location": "lattakia", 
        "phone" : "7777"
      },
      ...
    ]
  }
  
- Errors:
  - 400 (missing (location) or invalid query params)
  - 404 (no clinics open found)

## search articles by pet type

- Method : Get
- Endpoint: '/api/articles'
- Query Parameters : petType(optional)
- Response:

// Get : '/api/articles?petType=dog'
  { "message" : "article retrieved successfully",
    "article":{
       "id": 1,
        "name": "clinica1",
        "petType"= dog
       
      }
  }
  
- Errors:
  - 400 (invalid query params)
  - 404 (no article found for this petType)




