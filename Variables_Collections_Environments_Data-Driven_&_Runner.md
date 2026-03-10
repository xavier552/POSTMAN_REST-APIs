# [📮 VARIABLE - TRY — Postman Variables Practice - 9View API Document) ](https://documenter.postman.com/preview/36836284-a4dda12c-1ab6-40cc-a498-75db78720698?environment=&versionTag=latest&apiName=CURRENT&version=latest&documentationLayout=classic-single-column&documentationTheme=light&logo=&logoDark=&top-bar=FFFFFF&right-sidebar=303030&highlight=FF6C37&top-bar-dark=212121&right-sidebar-dark=303030&highlight-dark=FF6C37)

> A hands-on Postman collection demonstrating the use of **Collection**, **Global**, and **Environment** variables along with **Data Driven Testing** using external data files.

---

## 📋 Requests in This Collection

| Method    | Request Name                        | What It Demonstrates                        |
|-----------|-------------------------------------|---------------------------------------------|
| 🔵 GET    | Retrieve data (Collection as URL)   | Using `{{URL}}` as a Collection variable    |
| 🟢 POST   | Year as GLOBAL & m4 as Environment  | Global `{{Year-24}}` + Environment `{{m4}}`|
| 🟢 POST   | Data Driven                         | External data file variable `{{Device}}`   |

---

## 🔵 GET — Retrieve Data (Collection as URL)

```
GET {{URL}}
```

> The base URL is stored as a **Collection variable** `{{URL}}` so it can be reused across all requests without hardcoding.

---

## 🟢 POST — Year as GLOBAL & m4 as Environment

```
POST {{URL}}
```

**Request Body:**
```json
{
  "name": "{{m4}}",
  "data": {
    "year": {{Year-24}},
    "price": 3000.0,
    "CPU model": "m4 10 core",
    "Hard disk size": "1 TB"
  }
}
```

| Variable      | Scope             | Value Example       |
|---------------|-------------------|---------------------|
| `{{URL}}`     | Collection        | `https://api.restful-api.dev/objects/` |
| `{{m4}}`      | Environment       | `Apple MacBook M4`  |
| `{{Year-24}}` | Global            | `2024`              |

---

## 🟢 POST — Data Driven

```
POST {{URL}}
```

**Request Body:**
```json
{
  "name": "{{Device}}",
  "data": {
    "year": {{Year-24}},
    "price": 3000.0,
    "CPU model": "m4 10 core",
    "Hard disk size": "1 TB"
  }
}
```

> `{{Device}}` is injected from an external **CSV or JSON data file** during the Collection Runner iteration — a different device name is posted on each run.

**Sample Data File (CSV):**
```
Device
Apple MacBook M4
Samsung Galaxy S24
OnePlus 13
```

**Sample Data File (JSON):**
```json
[
  { "Device": "Apple MacBook M4" },
  { "Device": "Samsung Galaxy S24" },
  { "Device": "OnePlus 13" }
]
```

---

## 🔑 Variables Used

| Variable      | Scope       | Description                          |
|---------------|-------------|--------------------------------------|
| `{{URL}}`     | Collection  | Base API URL reused across requests  |
| `{{m4}}`      | Environment | Device name from environment setup   |
| `{{Year-24}}` | Global      | Year value shared across collections |
| `{{Device}}`  | Data File   | Injected per iteration via Runner    |

---

## ▶️ How to Run

**Import & Setup:**
1. Import `VARIABLE - TRY.postman_collection.json` into Postman
2. Set up your **Environment** — add `m4` variable with value `Apple MacBook M4`
3. Set up your **Global** variable — add `Year-24` with value `2024`
4. Set `URL` in **Collection variables** to `https://api.restful-api.dev/objects/`

**Run Data Driven Test:**
1. Open **Collection Runner**
2. Select the `VARIABLE - TRY` collection
3. Upload your CSV or JSON data file
4. Set iterations count to match your data rows
5. Click **Run** ▶️

---

## 🛠️ Tools Used

| Tool                  | Purpose                              |
|-----------------------|--------------------------------------|
| 📮 Postman            | API testing & collection management  |
| 📊 CSV / JSON Files   | Data driven test inputs              |
| 🌐 restful-api.dev    | Practice REST API endpoint           |
| 🐙 GitHub             | Version control & portfolio          |

---

*Made by [Xavier Varghese](https://github.com/xavier552) · Associate QA Engineer 
