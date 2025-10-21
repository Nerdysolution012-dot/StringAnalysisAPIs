Got it ✅ — here’s a **cleaner, more compact single-file README.md**, perfect for your GitHub repo.
Just copy everything below and paste it into your `README.md` file directly 👇

---

````markdown
# 🧠 String Analysis API (.NET 8)

A RESTful Web API built with **ASP.NET Core (.NET 8)** that analyzes strings and returns computed properties such as length, palindrome status, unique characters, word count, and character frequency — all stored **in-memory** without any database.

---

## 🚀 Features

- Analyze strings and compute:
  - ✅ Length
  - ✅ Palindrome check
  - ✅ Unique characters
  - ✅ Word count
  - ✅ SHA256 hash (unique ID)
  - ✅ Character frequency map
- Store analyzed strings in memory
- Fetch all analyzed strings
- Get a specific string by its hash ID
- Filter strings by custom query parameters

---

## ⚙️ Setup Instructions

1. **Clone Repository**
   ```bash
   git clone https://github.com/Nerdysolution012-dot/StringAnalysisAPIs.git
   cd StringAnalysisAPIs
````

2. **Run Application**

   ```bash
   dotnet run
   ```

3. **Test via Swagger**
   Open your browser and go to:

   ```
   https://localhost:7124/swagger
   ```

   *(Port may vary)*

---

## 📚 API Endpoints

### 🔹 1. POST `/api/strings`

Analyze and store a string.

**Request**

```json
{
  "value": "madam loves coding"
}
```

**Response**

```json
{
  "id": "809ca892add9beeb5ec3fae8e9b1103e0af91f22d209e32cb33b2f897ad344de",
  "value": "madam loves coding",
  "properties": {
    "length": 18,
    "is_palindrome": false,
    "unique_characters": 13,
    "word_count": 3,
    "sha256_hash": "809ca892add9beeb5ec3fae8e9b1103e0af91f22d209e32cb33b2f897ad344de",
    "character_frequency_map": {
      "m": 2,
      "a": 2,
      "d": 2,
      " ": 2,
      "l": 1,
      "o": 2,
      "v": 1,
      "e": 1,
      "s": 1,
      "c": 1,
      "i": 1,
      "n": 1,
      "g": 1
    }
  },
  "created_at": "2025-10-21T19:46:29Z"
}
```

---

### 🔹 2. GET `/api/strings`

Retrieve all analyzed strings.

**Response**

```json
[
  {
    "id": "809ca892add9beeb5ec3fae8e9b1103e0af91f22d209e32cb33b2f897ad344de",
    "value": "madam loves coding",
    "properties": { ... },
    "created_at": "2025-10-21T19:46:29Z"
  }
]
```

---

### 🔹 3. GET `/api/strings/{id}`

Fetch a specific string by its SHA256 hash.

**Response (found)**

```json
{
  "id": "sha256_hash_value",
  "value": "madam loves coding",
  "properties": { ... },
  "created_at": "2025-10-21T19:46:29Z"
}
```

**Response (not found)**

```json
{
  "error": "String does not exist in the system."
}
```

---

### 🔹 4. GET `/api/strings/query`

Filter analyzed strings.

**Example**

```
/api/strings/query?is_palindrome=false&min_length=5&contains_character=a
```

**Supported Filters**

| Parameter            | Type   | Description                                    |
| -------------------- | ------ | ---------------------------------------------- |
| `is_palindrome`      | bool   | Filter by palindrome strings                   |
| `word_count`         | int    | Filter by exact word count                     |
| `min_length`         | int    | Filter by minimum string length                |
| `contains_character` | string | Filter strings containing a specific character |

---

### 🔹 5. DELETE `/api/strings/{id}`

Delete a string by its hash ID.

**Response**

```json
{
  "message": "String deleted successfully."
}
```

---

## 🧪 Testing Steps on Swagger

1. Open `https://localhost:7124/swagger`
2. Expand **POST /api/strings**

   * Enter a string (e.g., `"madam loves coding"`)
   * Click **Execute**
3. Copy the `"id"` from the response
4. Use it in **GET /api/strings/{id}**
5. Try **GET /api/strings/query** for filtering
6. Optionally use **DELETE /api/strings/{id}**

---





