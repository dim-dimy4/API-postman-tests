# API Testing Project with Postman & Newman

This repository contains automated API tests using [JSONPlaceholder](https://jsonplaceholder.typicode.com), written in Postman and executable via Newman CLI.  
The purpose is to demonstrate testing of common REST methods (GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS) with assertions on status codes and response content.

---

## Covered Endpoints

| Method | Endpoint              | Description                    |
|--------|------------------------|--------------------------------|
| `GET`  | `/posts/1`             | Retrieve a post by ID          |
| `POST` | `/posts`               | Create a new post              |
| `PUT`  | `/posts/1`             | Full update of a post          |
| `PATCH`| `/posts/1`             | Partial update of a post       |
| `DELETE`| `/posts/1`            | Delete a post                  |
| `HEAD` | `/posts/1`             | Check response headers         |
| `OPTIONS` | `/posts`           | Verify allowed HTTP methods    |

---

## Tech Stack

- [Postman](https://www.postman.com/) – request management and test scripting  
- [Newman](https://github.com/postmanlabs/newman) – command-line test runner  
- JavaScript test assertions (inside Postman)  
- HTML report generation via Newman

---

## How to Run Tests

### Prerequisites
- Node.js installed
- Newman installed globally:
```bash
npm install -g newman
```
## To install Newman
```bash
npm install -g newman-reporter-html
```

## Run the tests
```bash
newman run TestCollection.postman_collection.json
```
## Generate an HTML Report
```bash
newman run TestCollection.postman_collection.json -r html --reporter-html-export newman-report.html
```
## Example Test (in Postman)
```bash
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response has title", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("title");
});

```
## Project Structure
```bash
api-postman-tests/
├── README.md
├── TestCollection.postman_collection.json
└── newman-report.html
```
## Contacts
E-mail: kachuk.mail@gmail.com
LinkedIn: [Dmytro Kachuk](https://www.linkedin.com/in/dmytro-kachuk-289628206/)  
