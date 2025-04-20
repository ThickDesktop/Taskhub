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

Add screenshots here showing the login screen, task list, and dark mode appearance.

---

## License

This project is open-source and released under the MIT License.
