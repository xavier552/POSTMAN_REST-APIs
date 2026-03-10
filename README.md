<div align="center">

```
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
░  ██████╗  ██████╗ ███████╗████████╗███╗   ███╗ █████╗ ███╗   ██╗ ░
░  ██╔══██╗██╔═══██╗██╔════╝╚══██╔══╝████╗ ████║██╔══██╗████╗  ██║ ░
░  ██████╔╝██║   ██║███████╗   ██║   ██╔████╔██║███████║██╔██╗ ██║ ░
░  ██╔═══╝ ██║   ██║╚════██║   ██║   ██║╚██╔╝██║██╔══██║██║╚██╗██║ ░
░  ██║     ╚██████╔╝███████║   ██║   ██║ ╚═╝ ██║██║  ██║██║ ╚████║ ░
░  ╚═╝      ╚═════╝ ╚══════╝   ╚═╝   ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝ ░
░              A P I   T E S T I N G   J O U R N E Y                ░
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
```


## 🗂️ What's Inside

</div>

```
Postman_API_Testing/
│
├── 📁 collections/
│   ├── 📮 get-requests/          → GET method practice & assertions
│   ├── 📝 post-requests/         → POST with request body & validation
│   ├── ✏️  put-patch-requests/   → UPDATE operations
│   └── 🗑️  delete-requests/      → DELETE operations & status checks
│
├── 📁 environments/
│   ├── 🌍 dev-environment/       → Dev base URLs & variables
│   └── 🚀 prod-environment/      → Production environment setup
│
├── 📁 test-scripts/
│   ├── ✅ status-code-tests/     → 200, 201, 400, 401, 404, 500
│   ├── 🔍 response-body-tests/   → JSON field & value assertions
│   └── ⏱️  response-time-tests/  → Performance threshold checks
│
├── 📁 newman/                    → Newman CLI automation reports
│
└── 📄 README.md
```

---

<div align="center">

## 📚 Topics Covered

</div>

<table align="center">
  <tr>
    <td align="center">📮<br><b>HTTP Methods</b><br><sub>GET · POST · PUT<br>PATCH · DELETE</sub></td>
    <td align="center">✅<br><b>Status Codes</b><br><sub>2xx · 3xx · 4xx · 5xx<br>200 · 201 · 400 · 401<br>404 · 500</sub></td>
    <td align="center">🔍<br><b>Assertions</b><br><sub>Status Code · Body<br>Headers · Response Time<br>JSON Schema</sub></td>
  </tr>
  <tr>
    <td align="center">🌍<br><b>Environments</b><br><sub>Variables · Globals<br>Dev · Staging · Prod<br>Dynamic Values</sub></td>
    <td align="center">🔐<br><b>Authentication</b><br><sub>Basic Auth · API Key<br>Bearer Token · OAuth 2.0<br>JWT</sub></td>
    <td align="center">📦<br><b>Collections</b><br><sub>Organizing Requests<br>Folders · Pre-request Scripts<br>Collection Runner</sub></td>
  </tr>
  <tr>
    <td align="center">📝<br><b>Request Body</b><br><sub>JSON · Form Data<br>Raw · Binary<br>GraphQL</sub></td>
    <td align="center">⚙️<br><b>Pre-request Scripts</b><br><sub>Dynamic Data<br>Token Generation<br>Setup Logic</sub></td>
    <td align="center">🤖<br><b>Newman CLI</b><br><sub>Automation · CI/CD<br>HTML Reports<br>Command Line Runs</sub></td>
  </tr>
</table>

---

<div align="center">

## 💡 Sample Test Scripts

</div>

**✅ Status Code Assertion**
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

**🔍 Response Body Assertion**
```javascript
pm.test("Response has user id", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.id).to.not.be.null;
    pm.expect(jsonData.name).to.eql("Xavier");
});
```

**⏱️ Response Time Check**
```javascript
pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});
```

**🔐 Set Bearer Token Dynamically**
```javascript
var jsonData = pm.response.json();
pm.environment.set("auth_token", jsonData.token);
```

---

<div align="center">

## 📈 Learning Progress

</div>

```
HTTP Methods (GET/POST)    ████████████████████  100% ✅
Status Code Testing        ████████████████████  100% ✅
PUT / PATCH / DELETE       ████████████████░░░░   80% 🔄
Response Body Assertions   ████████████████░░░░   80% 🔄
Environment Variables      ██████████████░░░░░░   70% 🔄
Authentication Testing     ████████████░░░░░░░░   60% 🔄
Pre-request Scripts        ██████████░░░░░░░░░░   50% 🔄
Collection Runner          ████████░░░░░░░░░░░░   40% 🔄
Newman CLI Automation      ██████░░░░░░░░░░░░░░   30% 🔄
CI/CD Integration          ████░░░░░░░░░░░░░░░░   20% 🔄
```

---

<div align="center">

## 🛠️ Tools Used

</div>

<div align="center">

| Tool                      | Purpose                                  |
|---------------------------|------------------------------------------|
| 📮 Postman                | API testing & collection management      |
| 🤖 Newman                 | CLI runner for Postman collections       |
| 🌐 REST APIs              | Practice endpoints for testing           |
| 🐙 GitHub                 | Version control & portfolio              |

</div>

---

<div align="center">


---

<div align="center">

## 👤 About Me

**Xavier Varghese** — Associate QA Engineer from India 🇮🇳

Learning API Testing with Postman to strengthen my QA skills and move towards full automation.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/xavier-varghese-0b617624a)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/xavier552)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:xaviervarghese468@gmail.com)

---


</div>
