# TaskHub – A Simple Task Manager App using Flutter and Supabase

TaskHub is a clean and easy-to-use Flutter application built to help users stay organized by managing their daily tasks. It includes user login, dark mode support, smooth animations, and the ability to add, edit, or delete tasks in real time. Supabase is used as the backend for authentication and data storage.

---

## What You Can Do With TaskHub

- Sign in securely using email and password
- Add new tasks and view them in a clean list
- Mark tasks as completed or delete them anytime
- See your tasks grouped as "To Do" or "Completed"
- Toggle dark mode to match your theme preference
- View a live count of your remaining tasks in the app bar
- Enjoy a responsive and polished UI built with Flutter

---

## Tools and Technologies Used

- Flutter for the frontend
- Supabase for backend services like authentication and database
- Dart programming language

---

## How to Set Up the App

1. **Clone the Project**
   ```
   git clone https://github.com/your-username/taskhub_app.git
   cd taskhub_app
   ```

2. **Install Dependencies**
   ```
   flutter pub get
   ```

3. **Add Your Supabase Keys**
   - You can add them in the main file during initialization or load them securely using environment variables

4. **Run the App**
   ```
   flutter run
   ```

   You can also use `flutter run -d chrome` to launch it in the browser

---

## Setting Up Supabase

1. Go to [https://supabase.com](https://supabase.com) and create a new project
2. After it loads, go to the Table Editor and create a table named `tasks`
3. Add the following columns:
   - `id` (UUID, Primary key, default uuid_generate_v4())
   - `title` (Text)
   - `is_done` (Boolean)
   - `user_id` (UUID)

4. Enable Row Level Security and create policies so that users can only access their own tasks:
   - For all actions (SELECT, INSERT, UPDATE, DELETE), use the policy:
     ```
     user_id = auth.uid()
     ```

5. Enable Email Authentication in the "Authentication" settings
6. Copy the Project URL and anon/public API key

---

## Supabase Initialization in Flutter

Use this in your `main.dart` or initialization code:
```dart
await Supabase.initialize(
  url: 'https://your-project.supabase.co',
  anonKey: 'your-anon-key',
);
```

---

## Hot Reload vs Hot Restart

| Concept         | Hot Reload                            | Hot Restart                         |
|-----------------|----------------------------------------|-------------------------------------|
| Speed           | Very fast                              | Slower than hot reload              |
| Keeps App State | Yes                                    | No, resets the app state            |
| Use Case        | For small UI or logic changes          | When you need a fresh app start     |
| Recompilation   | No                                     | Yes                                 |

- Use **hot reload** when tweaking UI or making small code changes.
- Use **hot restart** when the app behaves oddly or when changing startup logic.

---
## Screenshots

### App Logo  
<img width="300" alt="App Logo" src="https://github.com/user-attachments/assets/c28145ad-d2f6-42b8-9c60-fd9b34b78fa3" />

### Authentication Screens  
**Login Page**  
<img width="300" alt="Login Page" src="https://github.com/user-attachments/assets/dd8743e7-fd5e-422e-b8b6-0610aa784bc5" />

**Sign Up Page**  
<img width="300" alt="Sign Up Page" src="https://github.com/user-attachments/assets/a59a3ac8-ee7f-462b-8416-5e648ff928d6" />

**Email Confirmation Page**  
<img width="600" alt="Email Confirm Page" src="https://github.com/user-attachments/assets/714f0cfa-0fa2-4916-88a3-01df1f144ca3" />

### Dashboard Views  
**Dark Mode**  
<img width="300" alt="Dashboard Dark" src="https://github.com/user-attachments/assets/a66d421f-54b2-44c2-b5cf-7a1829f9595d" />

**Light Mode**  
<img width="300" alt="Dashboard Light" src="https://github.com/user-attachments/assets/03b18c11-8134-4166-93ae-8b2957e9da02" />

### Add Task  
<img width="300" alt="Add Task" src="https://github.com/user-attachments/assets/304e72af-58c1-45f2-a3cb-bcf9b021e61a" />


### Supabase Dashboard

**Users Table**  
<img width="1470" alt="Screenshot 2025-04-20 at 5 00 31 PM" src="https://github.com/user-attachments/assets/08d8fcdc-bb5c-4055-be90-c61e854a0e34" />

**RLS Policies for `tasks` Table**  
<img width="1467" alt="Screenshot 2025-04-20 at 4 59 50 PM" src="https://github.com/user-attachments/assets/4e692b31-7231-4001-bd20-f0089dfcbd0e" />







---

## License

This project is open-source and released under the MIT License.
