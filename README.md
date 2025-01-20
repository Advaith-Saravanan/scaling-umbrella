# scaling-umbrella

# To-Do List Application

def display_menu():
    print("1. Add a task")
    print("2. View tasks")
    print("3. Mark task as completed")
    print("4. Exit")

def add_task(tasks):
    task = input("Enter a new task: ")To-Do List Application
Description: The To-Do List application is a simple yet powerful tool designed to help users manage their tasks efficiently. Written in Python, this text-based application allows users to:

Add New Tasks: Users can input new tasks to be added to their to-do list.

View Tasks: The application displays all the tasks, along with their completion status.

Mark Tasks as Completed: Users can mark tasks as completed, updating their status in the list.

Exit the Application: Users can safely exit the application when they are done managing their tasks.

Features:

User-Friendly Menu: The application provides a straightforward menu to navigate different functionalities.

Task Management: Users can easily add, view, and update tasks.

Status Tracking: The application keeps track of whether tasks are completed or not.

Usage:

Run the application by executing the todo_list.py script in a Python environment.

Follow the on-screen prompts to interact with the application.

Add tasks as they come up, view the list to keep track, and mark tasks as completed once they are done.

Example Workflow:

Start the application.

Add a task: "Buy groceries."

View tasks to see the new task added to the list.

Mark the task as completed once groceries are bought.

Exit the application.
    tasks.append({"task": task, "completed": False})
    print(f"Task '{task}' added!")

def view_tasks(tasks):
    if not tasks:
        print("No tasks available.")
    else:
        for index, task in enumerate(tasks):
            status = "Completed" if task["completed"] else "Not Completed"
            print(f"{index + 1}. {task['task']} [{status}]")

def mark_task_completed(tasks):
    view_tasks(tasks)
    task_number = int(input("Enter the task number to mark as completed: ")) - 1
    if 0 <= task_number < len(tasks):
        tasks[task_number]["completed"] = True
        print(f"Task '{tasks[task_number]['task']}' marked as completed!")
    else:
        print("Invalid task number.")

def main():
    tasks = []
    while True:
        display_menu()
        choice = input("Choose an option: ")
        if choice == "1":
            add_task(tasks)
        elif choice == "2":
            view_tasks(tasks)
        elif choice == "3":
            mark_task_completed(tasks)
        elif choice == "4":
            print("Exiting the application. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
