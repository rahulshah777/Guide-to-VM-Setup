# 📱 App Development Project – Module 4 Progress Update

> **Course:** Mobile Application Development  
> **Student:** Rahul Shah  
> **Last Updated:** April 2026  

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Module Progress Tracker](#module-progress-tracker)
- [App Concept & Purpose](#app-concept--purpose)
- [Design Principles Applied](#design-principles-applied)
- [Wireframes & UI Layout](#wireframes--ui-layout)
- [Conversation Design](#conversation-design)
- [Digital Infrastructure Considerations](#digital-infrastructure-considerations)
- [Code Structure](#code-structure)
- [GitHub Setup & Resources](#github-setup--resources)
- [Next Steps – Week 5 to 8](#next-steps--week-5-to-8)
- [APA References](#apa-references)

---

## Project Overview

This project documents the design and development of an Android mobile application built across eight modules. Each module adds a new layer of planning, design, and code. By Week 8, the completed app will demonstrate applied knowledge of Android development, UI/UX design principles, conversation design, and digital infrastructure planning.

---

## Module Progress Tracker

| Module | Focus Area | Status |
|--------|-----------|--------|
| M1 | Project outline, app concept, initial GitHub setup | ✅ Complete |
| M2 | Android fundamentals – views, layouts, orientation | ✅ Complete |
| M3 | User interaction, menus, navigation patterns | ✅ Complete |
| M4 | UI design principles, wireframes, conversation design | ✅ Complete |
| M5 | [Upcoming] | 🔲 Pending |
| M6 | [Upcoming] | 🔲 Pending |
| M7 | [Upcoming] | 🔲 Pending |
| M8 | Final submission | 🔲 Pending |

---

## App Concept & Purpose

**App Name:** [Your App Name]  
**Platform:** Android  
**Target Users:** [Describe your target users — e.g., students, professionals, general public]  

**Problem Statement:**  
[Describe the problem your app solves in 2–3 sentences.]

**Core Features:**
- [Feature 1]
- [Feature 2]
- [Feature 3]
- [Feature 4]

---

## Design Principles Applied

Drawing from the Mockplus Android design guide and Google's Material Design framework, the following principles have been applied to this project (Babich, 2018):

### ✅ Material Design
The app follows Google's Material Design visual language, using consistent color schemes, typography, and component spacing to create a familiar and intuitive interface.

### ✅ Visual Hierarchy
Layouts prioritize content-first design using grids and whitespace. Decorative elements have been minimized to reduce distraction and guide user attention to key actions.

### ✅ Standard System Patterns
Reusable Android components (RecyclerView, BottomNavigationView, ToolBar) are used instead of custom components to reduce cognitive load and development overhead.

### ✅ Motion & Animation
Transitions between screens use Android's built-in animation APIs to convey spatial relationships and provide visual continuity between views.

### ✅ Accessibility
The app supports:
- Minimum touch target sizes (48dp x 48dp)
- Sufficient color contrast ratios
- Content descriptions for screen readers

### ✅ Prototyping & Testing
Wireframes were created before development began. Iterative testing validates layout and interaction decisions at each stage.

---

## Wireframes & UI Layout

Wireframes serve as the blueprint for the app's layout, navigation, and functionality. They were completed before coding began to align design decisions with user needs and technical requirements (Cognizant, 2020).

### Screen Map

```
[ Splash Screen ]
       |
[ Home / Dashboard ]
       |
  _____|_____
 |           |
[Feature A] [Feature B]
       |
[ Detail View ]
       |
[ Settings / Profile ]
```

### Layout Decisions

| Screen | Layout Type | Key Components |
|--------|------------|----------------|
| Home | ConstraintLayout | RecyclerView, FAB, ToolBar |
| Detail View | ScrollView | CardView, ImageView, TextView |
| Settings | LinearLayout | SwitchCompat, EditText, Button |
| Navigation | BottomNavigationView | 3–5 primary destinations |

> 📌 **Note:** Wireframe images will be added to the `/wireframes` folder in the repository.

---

## Conversation Design

Based on Google's Conversation Design guidelines, the following interaction principles have been applied to user-facing flows in the app (Google for Developers, 2024):

| Design Topic | Application in This App |
|---|---|
| **User Intent** | App flows are designed around what users are trying to accomplish, not app structure |
| **Persona** | The app uses a consistent tone — clear, helpful, and concise |
| **Interaction Flow** | Task flows are linear with minimal required steps |
| **Feedback** | Visual and haptic feedback confirms every user action |
| **Error Handling** | Friendly error messages with recovery options are shown for invalid inputs |
| **Is Conversation the Right Fit?** | Evaluated and determined that a visual UI serves this use case better than voice alone |

---

## Digital Infrastructure Considerations

Aligned with Cognizant's 10 key digital infrastructure considerations, the following back-end and architectural decisions support the app's design goals (Cognizant, 2020):

- **Scalability:** The app is architected using MVVM (Model-View-ViewModel) to support future feature expansion
- **Security:** User data is handled with input validation and no sensitive data is stored locally in plain text
- **Performance:** Images are loaded asynchronously to avoid blocking the main thread
- **Resilience:** Network calls include retry logic and timeout handling
- **Monitoring:** Logcat and crash reporting are set up for debugging during development

---

## Code Structure

```
/app
 ├── /manifests
 │    └── AndroidManifest.xml
 ├── /java
 │    └── com.example.[appname]
 │         ├── MainActivity.java
 │         ├── [Feature]Activity.java
 │         ├── /viewmodel
 │         ├── /model
 │         └── /adapter
 ├── /res
 │    ├── /layout
 │    │    ├── activity_main.xml
 │    │    └── [feature]_layout.xml
 │    ├── /drawable
 │    ├── /values
 │    │    ├── colors.xml
 │    │    ├── strings.xml
 │    │    └── themes.xml
 │    └── /menu
 └── /wireframes
      ├── home_wireframe.png
      └── detail_wireframe.png
```

---

## GitHub Setup & Resources

This project is version-controlled using GitHub Classroom. The following resources were used to set up and manage the repository:

- 🔗 [Introduction to GitHub – GitHub Lab](https://lab.github.com/githubtraining/introduction-to-github)
- 🔗 [Hello World – GitHub Guides](https://guides.github.com/activities/hello-world/)
- 🔗 [GitHub Classroom Repository](#) ← *Replace with your actual link*

### Git Workflow Used

```bash
# Clone the repository
git clone [your-classroom-repo-url]

# Stage changes
git add .

# Commit with a message
git commit -m "M4: Added wireframes and updated UI layout"

# Push to GitHub
git push origin main
```

---

## Next Steps – Week 5 to 8

- [ ] Implement core feature logic (M5)
- [ ] Connect UI to data layer / local database (M5–M6)
- [ ] Add navigation component and back-stack management (M6)
- [ ] Conduct user testing and refine UI (M7)
- [ ] Final polish, documentation, and submission (M8)
- [ ] Record demo video and update Wiki (M8)

---

## APA References

Android Developers. (2023). *Material design for Android*. Google. https://developer.android.com/design

Babich, N. (2018). *The beginner's guide to Android app design*. Mockplus. https://www.mockplus.com/blog/post/android-app-design

Cognizant. (2020). *10 key digital infrastructure considerations* (CODEx3520). https://www.cognizant.com/whitepapers/10-key-digital-infrastructure-considerations-codex3520.pdf

DiMarzio, J. (2017). *Beginning Android programming with Android Studio* (4th ed.). Wiley.

Google for Developers. (2024). *Conversation design*. https://developers.google.com/assistant/conversation-design/welcome

---

> 📌 This README is a living document and will be updated each module through Week 8.
