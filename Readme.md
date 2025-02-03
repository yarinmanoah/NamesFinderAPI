# Names Finder API

A Flask-based RESTful API that manages and serves name-related data. This API allows you to store, retrieve, and manage names with their categories and first characters.

## Features

- List all names in the database
- Search names by first letter
- Filter names by category
- Combined search by letter and category
- Get random name suggestions
- Add new names to the database
- Delete existing names

## Technology Stack

- Python 3.9
- Flask (Web Framework)
- MongoDB (Database)
- Flasgger (Swagger UI Documentation)
- Python-dotenv (Environment Variables Management)

## Prerequisites

- Python 3.9 or higher
- MongoDB Atlas account or local MongoDB installation
- Git (for cloning the repository)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yarinmanoah/NamesFinderAPI.git
cd NamesFinderAPI
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the project root and add your MongoDB configuration:
```env
DB_CONNECTION_STRING=your_mongodb_cluster_url
DB_NAME=your_database_name
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

## Running the Application

1. Start the Flask server:
```bash
python app.py
```

2. The API will be available at `http://localhost:8088`
3. Access the Swagger documentation at `http://localhost:8088/apidocs`

## API Endpoints

### GET Endpoints

- `GET /list_all_names` - Retrieve all names from the database
- `GET /list_by_letter/<char>` - Get names starting with a specific letter
- `GET /list_by_category/<category>` - Get names from a specific category
- `GET /list_by_letter_and_category?letter=<letter>&category=<category>` - Get names by letter and category
- `GET /list_random_name` - Get a random name from the database

### POST Endpoints

- `POST /add_name` - Add a new name to the database
  ```json
  {
    "FirstChar": "A",
    "content": "Alex",
    "category": "Male"
  }
  ```

### DELETE Endpoints

- `DELETE /delete_name/<id>` - Delete a name by its ID

## Response Format

Names are returned in the following format:

```json
{
    "_id": "unique-identifier",
    "FirstChar": "A",
    "category": "Male",
    "content": "Alex"
}
```

## Error Handling

The API includes comprehensive error handling:

- 200: Successful operation
- 201: Resource created successfully
- 400: Bad request / Invalid input
- 404: Resource not found
- 500: Server error

## Deployment

This API is configured for deployment on Vercel. The `vercel.json` configuration file is included in the repository.

## License

Copyright (c) 2024 Yarin Manoah


## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Support

For support, please open an issue in the GitHub repository.

## Contact

Yarin Manoah | yarinmanoah1443@gmail.com
