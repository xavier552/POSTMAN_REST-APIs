# [📮 CRUD — JSONPlaceholder API Testing](#)

> A complete CRUD Postman collection using **JSONPlaceholder** API — covering all HTTP methods with **status code checks**, **response body assertions**, **environment variable storage**, and **response time validations** on every request.

![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![JSONPlaceholder](https://img.shields.io/badge/JSONPlaceholder-REST%20API-6C63FF?style=for-the-badge)
![Test Scripts](https://img.shields.io/badge/Test%20Scripts-JS-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

> 🌐 **Base URL:** `https://jsonplaceholder.typicode.com`

---

## 📋 Requests in This Collection

| Method      | Request Name              | Endpoint        | Status Code |
|-------------|---------------------------|-----------------|-------------|
| 🔵 GET      | Retrieve All Posts        | `/posts`        | ✅ 200      |
| 🔵 GET      | Retrieve Single Post      | `/posts/1`      | ✅ 200      |
| 🔵 GET      | Not Found                 | `/posts/9999`   | ✅ 404      |
| 🟢 POST     | Create New Post           | `/posts`        | ✅ 201      |
| 🟡 PUT      | Full Update Post          | `/posts/1`      | ✅ 200      |
| 🟠 PATCH    | Partial Update Post       | `/posts/1`      | ✅ 200      |
| 🔴 DELETE   | Remove Post               | `/posts/1`      | ✅ 200      |

---

## ✅ Status Code Tests

Every request includes a status code assertion:

| Request               | Expected Status |
|-----------------------|-----------------|
| GET All Posts         | `200`           |
| GET Single Post       | `200`           |
| GET Not Found         | `404`           |
| POST Create           | `201`           |
| PUT Full Update       | `200`           |
| PATCH Partial Update  | `200`           |
| DELETE Remove         | `200`           |

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

---

## 🔍 Response Body Tests

**GET All Posts**
```javascript
pm.test("Response is an array", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.be.an('array');
});

pm.test("First post has id, title and body", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0]).to.have.property('id');
    pm.expect(jsonData[0]).to.have.property('title');
    pm.expect(jsonData[0]).to.have.property('body');
});
```

**GET Single Post**
```javascript
pm.test("Post id is 1", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.id).to.eql(1);
});

pm.test("Title is not empty", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.not.be.empty;
});
```

**POST Create**
```javascript
pm.test("Title matches request", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.eql("Xavier Test Post");
});
```

**PUT Full Update**
```javascript
pm.test("Title is updated", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.eql("Xavier Updated Post");
});
```

**PATCH Partial Update**
```javascript
pm.test("Title is patched", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.title).to.eql("Xavier Patched Title");
});
```

**DELETE & GET 404**
```javascript
pm.test("Response body is empty object", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.eql({});
});
```

---

## 💾 Environment Variables

| Variable        | Set By              | Value Stored              |
|-----------------|---------------------|---------------------------|
| `{{post_id}}`   | GET All Posts       | First post's `id`         |
| `{{post_title}}`| GET Single Post     | Post `title`              |
| `{{new_post_id}}`| POST Create        | Newly created post `id`   |

```javascript
pm.environment.set("post_id", jsonData[0].id);
pm.environment.set("post_title", jsonData.title);
pm.environment.set("new_post_id", jsonData.id);
```

---

## ⏱️ Response Time Tests

Every request checks response time stays under **500ms**:

```javascript
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});
```

---

## 📥 Download & Import Collection

> Click the button below to download the Postman collection file and import it directly into Postman.

[![Download Collection](https://img.shields.io/badge/Download-Collection%20JSON-FF6C37?style=for-the-badge&logo=postman&logoColor=white)](./CRUD_JSONPlaceholder.postman_collection.json)

**Or import directly in Postman:**
1. Click the link above to download the `.json` file
2. Open **Postman** → Click **Import**
3. Drop the downloaded file → Click **Import** ✅

---

## ▶️ How to Run in Postman

1. Import `CRUD_JSONPlaceholder.postman_collection.json` into Postman
2. Create a new **Environment** (e.g. `JSONPlaceholder_env`)
3. Select the environment from the top-right dropdown
4. Open any request and click **Send** ▶️
5. Click the **Test Results** tab to see all tests pass ✅

---

## 🤖 Run with Newman (CLI)

**Install Newman:**
```bash
npm install -g newman
npm install -g newman-reporter-htmlextra
```

**Run Collection:**
```bash
newman run CRUD_JSONPlaceholder.postman_collection.json
```

**Generate HTML Report:**
```bash
newman run CRUD_JSONPlaceholder.postman_collection.json -r htmlextra --reporter-htmlextra-export reports/report.html
```

---

## 🛠️ Tools Used

| Tool                    | Purpose                              |
|-------------------------|--------------------------------------|
| 📮 Postman              | API testing & collection management  |
| 🪐 JSONPlaceholder       | Free practice REST API               |
| 🤖 Newman               | CLI runner for automation            |
| 🌍 Postman Environment  | Storing dynamic response values      |
| 🐙 GitHub               | Version control & portfolio          |

---

*Made by [Xavier Varghese](https://github.com/xavier552) · Associate QA Engineer 🇮🇳*
