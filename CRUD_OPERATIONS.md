# [📮 CRUD Operations — API Testing  - (view api documentation) ](https://documenter.postman.com/preview/36836284-e2060cdf-971a-49eb-9017-93b4269e066b?environment=&versionTag=latest&apiName=CURRENT&version=latest&documentationLayout=classic-single-column&documentationTheme=dark&logo=&logoDark=&top-bar=FFFFFF&right-sidebar=303030&highlight=FF6C37&top-bar-dark=212121&right-sidebar-dark=303030&highlight-dark=FF6C37)

> Practicing CRUD operations using Postman with the [restful-api.dev](https://restful-api.dev) REST API.


---

## 🌐 Base URL

```
https://api.restful-api.dev/objects
```

---

## 📋 Requests

| Method         | Endpoint                  | Action                  |
|----------------|---------------------------|-------------------------|
| 🔵 GET         | `/objects/`               | Retrieve all objects    |
| 🔵 GET         | `/objects?id=4`           | Fetch single object     |
| 🔵 GET         | `/objects?id=4&id=3`      | Fetch multiple objects  |
| 🟢 POST        | `/objects/`               | Create new object       |
| 🟡 PUT         | `/objects/{id}`           | Full update             |
| 🟠 PATCH       | `/objects/{id}`           | Partial update          |
| 🔴 DELETE      | `/objects/{id}`           | Remove object           |

---

## 🟢 POST — Request Body

```json
{
  "name": "Apple MacBook M4",
  "data": {
    "year": 2024,
    "price": 3000.99,
    "CPU model": "m4 10 core",
    "Hard disk size": "1 TB"
  }
}
```

## 🟡 PUT — Request Body

```json
{
  "name": "Apple MacBook M4",
  "data": {
    "year": 2024,
    "price": 4000.99,
    "CPU model": "m4 10 core",
    "Hard disk size": "2 TB"
  }
}
```

## 🟠 PATCH — Request Body

```json
{
  "name": "Apple(M4-Pro)"
}
```

---

## 🛠️ Tools Used

| Tool                 | Purpose                             |
|----------------------|-------------------------------------|
| 📮 Postman           | API testing & collection management |
| 🌐 restful-api.dev   | Practice REST API endpoint          |
| 🐙 GitHub            | Version control & portfolio         |

---

*Made by [Xavier Varghese](https://github.com/xavier552) · Associate QA Engineer 🇮🇳*
