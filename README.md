# Mobile App Development Project — README & Wiki Outline

Course: App Development Concepts  
Student: Rahul Shah  
GitHub Repository: Guide-to-VM-Setup 
Last Updated: April 2026

---

## Version Changelog

| Version | Date | Status | Description |
|---------|------|--------|-------------|
| v1.0 | Week 1 | ✅ Complete | Initial project concept and app idea submitted |
| v2.0 | Week 3 | ✅ Complete | App architecture outline; identified UI/data layer structure |
| v3.0 | Week 5 | ✅ Complete | Database design added; SQLite schema drafted; wireframes created |
| v4.0 | Week 6 | 🔄 Current|SQLite integration updated; Wiki published; GitHub push completed|
| v5.0 | Week 7 | 🔜 Planned | Final code complete; README finalized; full GitHub push |
| v6.0 | Week 8 | 🔜 Planned | Final submission; polished code; presentation-ready |

---

## Project Overview

 App Name:  [Your App Name]  
 Platform:  Android  
 Language:  Kotlin  
 Database:  SQLite (local), with optional GCP cloud backend  
 Architecture Pattern:  Google Jetpack — UI Layer / Data Layer / Optional Domain Layer

Purpose: [Brief 1–2 sentence description of what your app does and who it serves.]

---

## Module 5 Updates (v3.0 — Previous)

- Defined the app's data requirements based on wireframe screens
- Selected SQLite as the local database solution
- Drafted initial schema (tables and columns mapped from wireframe fields)
- Identified the need for a Contract Class to manage column name constants
- Reviewed Google's recommendation to use the Room Persistence Library as an abstraction layer above SQLite

---

## Module 6 Updates (v4.0 — Current)

### Changes Made This Week

-  SQLiteOpenHelper implemented:  Created `AppDbHelper.kt` extending `SQLiteOpenHelper`, overriding `onCreate()` and `onUpgrade()`
-  Schema finalized:  Contract class created with all table and column constants
-  CRUD operations coded:  Insert, query, update, and delete methods completed and tested
-  Wireframe-to-Database mapping confirmed:  All wireframe fields now correspond to database columns
-  Wiki published:  Instructional SQLite Wiki posted to GitHub repository Wiki tab
-  GitHub push completed:  Latest code pushed to GitHub Classroom repository

### Current Database Schema

```
Table: users
  - _id          INTEGER PRIMARY KEY
  - username     TEXT
  - email        TEXT
  - created_at   TEXT

Table: entries
  - _id          INTEGER PRIMARY KEY
  - user_id      INTEGER (foreign key → users._id)
  - title        TEXT
  - content      TEXT
  - timestamp    TEXT
```

### Wireframe Summary

The app consists of the following screens (each mapped to database tables above):

1.  Login / Registration Screen  → reads/writes `users` table
2.  Dashboard / Home Screen  → queries `entries` table by `user_id`
3.  New Entry Screen  → inserts into `entries` table
4.  Entry Detail Screen  → reads and updates a single `entries` row
5.  Settings Screen  → updates `users` table fields

### Architecture Layers (Current)

```
┌─────────────────────────────┐
│         UI Layer            │  Activities / Fragments / Jetpack Compose
├─────────────────────────────┤
│      Domain Layer           │  Use Cases (optional — added for reused logic)
├─────────────────────────────┤
│       Data Layer            │  Repositories → SQLiteOpenHelper / Room
└─────────────────────────────┘
```

---

## Planned Updates (v5.0 — Next)

- [ ] Migrate raw SQLite calls to Room Persistence Library
- [ ] Connect GCP Cloud SQL as optional remote backup
- [ ] Complete all remaining UI screens
- [ ] Add input validation and error handling
- [ ] Write unit tests for database operations
- [ ] Update README with final architecture diagram

---

## SQLite Wiki — Quick Reference for Classmates

> Full Wiki available on the repository Wiki tab.

### Step 1 — Define Your Schema (Contract Class)
```kotlin
object AppContract {
    object UserEntry : BaseColumns {
        const val TABLE_NAME = "users"
        const val COLUMN_USERNAME = "username"
        const val COLUMN_EMAIL = "email"
    }
}
```

### Step 2 — Create the Database
```kotlin
class AppDbHelper(context: Context) : SQLiteOpenHelper(context, "App.db", null, 1) {
    override fun onCreate(db: SQLiteDatabase) {
        db.execSQL("CREATE TABLE users (_id INTEGER PRIMARY KEY, username TEXT, email TEXT)")
    }
    override fun onUpgrade(db: SQLiteDatabase, old: Int, new: Int) {
        db.execSQL("DROP TABLE IF EXISTS users")
        onCreate(db)
    }
}
```

### Step 3 — Insert Data
```kotlin
val db = dbHelper.writableDatabase
val values = ContentValues().apply {
    put(AppContract.UserEntry.COLUMN_USERNAME, "JohnDoe")
    put(AppContract.UserEntry.COLUMN_EMAIL, "john@example.com")
}
db.insert(AppContract.UserEntry.TABLE_NAME, null, values)
```

### Step 4 — Query Data
```kotlin
val cursor = db.query("users", null, null, null, null, null, null)
while (cursor.moveToNext()) {
    val name = cursor.getString(cursor.getColumnIndexOrThrow("username"))
}
cursor.close()
```

### Step 5 — Close Connection
```kotlin
override fun onDestroy() {
    dbHelper.close()
    super.onDestroy()
}
```

---

## GCP Integration Note

Google Cloud Platform credits can be used to provision a  Cloud SQL (MySQL)  or  Firebase Realtime Database  instance as a remote backend. The app uses SQLite locally for offline access, then syncs to GCP when a network connection is available — implementing Google's recommended offline-first architecture.

---

## References

Android Developers. (2026).   Guide to app architecture  . Google. https://developer.android.com/topic/architecture

Android Developers. (2025).   Save data using SQLite  . Google. https://developer.android.com/training/data-storage/sqlite

GitHub. (2024).   Introduction to GitHub  . https://lab.github.com/githubtraining/introduction-to-github

GitHub. (2024).   Hello World  . https://guides.github.com/activities/hello-world/

Simform. (2023).   Mobile app database selection  . https://www.simform.com/mobile-app-developers-database-selection/
