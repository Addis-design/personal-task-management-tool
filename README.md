# Personal Task Management Tool
This is a simple personal task management tool that allows users to manage daily tasks, prioritize them, and mark them as complete. Each task has a title, description, priority level (high, medium, low), and a due date.
## Features
The web app has the following features
- Create new tasks with title, description, priority, and due date
- View all tasks in a list format
- Edit existing tasks
- Delete tasks
- Mark tasks as complete
## Technology Stack
- Frontend: React.js
- Backend: Node.js with Express.js
- Database: MongoDB
## Prerequisites
Before you begin, ensure you have met the following requirements:
- Node.js 
- npm 
- MongoDB 
## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.
### Clone the Repository

```
git clone https://github.com/Addis-design/personal-task-management-tool.git 
cd personal-task-management-tool
```
### Backend Setup
1. Navigate to the backend directory:
   ```
   cd server
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file in the backend directory and add your MongoDB connection string:
   ```
   MONGODB_URI=”mongodb://127.0.0.1:27017/task_management”
   ```
4. Start the backend server:
   ```
   npm start
   ```

The backend server should now be running on `http://localhost:8080`.
### Frontend Setup

1. Open a new terminal and navigate to the frontend directory:
   ```
   cd client
   ```

2. Install dependencies:
   ```
   npm install
   ```
3. Start the frontend development server:
   ```
   npm start
   ```
The frontend application should now be running on `http://localhost:3000`.
## Usage
1.	Open your web browser and go to `http://localhost:3000`
2.	Use the form to create a new task by entering the title, description, priority, and due date
3.	View your tasks in the list below the form
4.	Click on a task to edit its details
5.	Use the delete button to remove a task
6.	Use the checkbox to mark a task as complete
7.	Navigate to the task page to view the added tasks
## API Endpoints
- `POST /tasks`: Create a new task
- `GET /tasks`: Retrieve all tasks
- `PUT /tasks/:id`: Update a specific task
- `DELETE /tasks/:id`: Delete a specific task
## Database Schema
```javascript
const taskSchema = new mongoose.Schema({
  title: { type: String, required: true },
  description: { type: String },
  priority: { type: String, enum: ['high', 'medium', 'low'], default: 'medium' },
  dueDate: { type: Date, required: true },
  completed: { type: Boolean, default: false },
});
```

## Potential Challenges and Reflection
Potential challenges in building this tool could be managing state and synchronization between the front and backend. As users interact with tasks, ensuring that the frontend state stays in sync with the backend database can be tricky, especially when multiple users access the system simultaneously.
To address this challenge, I could implement:
1.	Optimistic UI updates - Update the UI immediately on user actions, then sync with the backend.
2.	Real-time updates - Use WebSockets or Server-Sent Events to push updates to connected clients.
3.	Proper error handling - Implement robust error handling to manage failed API requests and data inconsistencies.
4.	Caching strategies - Implement client-side caching to reduce server load and improve performance.
5.	Concurrency control - Use versioning or timestamps to handle conflicts when multiple users edit the same task.
## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
## License
No License

