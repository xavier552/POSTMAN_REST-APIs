# [📮 Jsonplaceholder_workex — API Test Scripts- (View API Documentation)](https://documenter.postman.com/preview/36836284-44f5ae43-6421-4846-99eb-d683bd8dde67?environment=&versionTag=latest&apiName=CURRENT&version=latest&documentationLayout=classic-single-column&documentationTheme=light&logo=&logoDark=&top-bar=FFFFFF&right-sidebar=303030&highlight=FF6C37&top-bar-dark=212121&right-sidebar-dark=303030&highlight-dark=FF6C37)

> A Postman collection practicing real-world **test scripting** on the JSONPlaceholder API — covering status code checks, response body assertions, environment variable storage, and response time validation.


> 🌐 **Base URL:** `https://jsonplaceholder.typicode.com`

---

## 📋 Requests in This Collection

| Method    | Request Name | Endpoint        |
|-----------|--------------|-----------------|
| 🔵 GET    | Get Posts    | `/posts`        |

---

## 🔵 GET — Get Posts

```
GET https://jsonplaceholder.typicode.com/posts
```

> Fetches all posts and runs 3 automated test scripts to validate the response.

---

## ✅ Status Code Tests

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

| Test                  | Expected | Status Code |
|-----------------------|----------|-------------|
| ✅ Response is OK     | `200`    | 🟢 Pass     |

---

## 🔍 Response Body Tests

```javascript
// Store response JSON
Setvariable = pm.response.json();
idfive = Setvariable[4].title;
idsevenbody = Setvariable[6].body;

// Assert id 5 title
pm.test("verify title as nesciunt quas odio", function () {
    pm.expect("nesciunt quas odio").to.eql(idfive);
});

// Store id 7 body to environment variable
pm.environment.set("body", "idsevenbody");
```

| Test                              | Field Checked        | Expected Value          |
|-----------------------------------|----------------------|-------------------------|
| 🔍 Verify ID 5 title              | `[4].title`          | `nesciunt quas odio`    |
| 💾 Store ID 7 body to environment | `[6].body` → `{{body}}` | Saved to env variable |

---

## ⏱️ Response Time Tests

```javascript
pm.test("Response time is less than 300ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(300);
});
```

| Test                        | Threshold  |
|-----------------------------|------------|
| ⏱️ Response time check      | `< 300ms`  |

---

## 🔑 Environment Variables Used

| Variable   | Scope       | Set By                        | Value               |
|------------|-------------|-------------------------------|---------------------|
| `{{body}}` | Environment | `pm.environment.set("body")`  | ID 7's body text    |

---

## 📝 All Test Scripts at a Glance

```javascript
// ✅ 1. Check response code is 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// 🔍 2. Verify id 5 title is "nesciunt quas odio"
Setvariable = pm.response.json();
idfive = Setvariable[4].title;
idsevenbody = Setvariable[6].body;

pm.test("verify title as nesciunt quas odio", function () {
    pm.expect("nesciunt quas odio").to.eql(idfive);
});

// 💾 3. Store id 7 body to environment variable
pm.environment.set("body", "idsevenbody");

// ⏱️ 4. Check response time is below 300ms
pm.test("Response time is less than 300ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(300);
});
```

---

## ▶️ How to Run

1. Import `Jsonplaceholder_workex.postman_collection.json` into Postman
2. Create an **Environment** in Postman (e.g. `Jsonplaceholder_env`)
3. Select the environment before running
4. Open the `Get` request and click **Send** ▶️
5. Check the **Test Results** tab to see all tests pass ✅

---

## 🛠️ Tools Used

| Tool                       | Purpose                              |
|----------------------------|--------------------------------------|
| 📮 Postman                 | API testing & test script execution  |
| 🪐 JSONPlaceholder          | Free practice REST API               |
| 🌍 Postman Environment     | Storing dynamic response values      |
| 🐙 GitHub                  | Version control & portfolio          |

---

*Made by [Xavier Varghese](https://github.com/xavier552) · Associate QA Engineer 
