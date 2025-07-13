
# To-Do List Application (Command-Line)

tasks = []

def show_menu():
    print("\n=== TO-DO LIST MENU ===")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark Task as Completed")
    print("4. Delete Task")
    print("5. Exit")

def add_task():
    task = input("Enter a new task: ")
    tasks.append({"task": task, "completed": False})
    print("completed Task added!")

def view_tasks():
    if not tasks:
        print(" No tasks found.")
        return
    print("\n📋 Your Tasks:")
    for index, task in enumerate(tasks, start=1):
        #status = "completed" if task["completed"] else "incompleted"
        if task["completed"]:
            status = "completed"
        else :
            status = "incompleted"
        print(f"{index}. {task['task']} [{status}]")

def mark_completed():
    view_tasks()
    try:
        task_no = int(input("Enter task number to mark as completed: "))
        if 1 <= task_no <= len(tasks):
            tasks[task_no - 1]["completed"] = True
            print(" Task marked as completed!")
        else:
            print(" Invalid task number.")
    except ValueError:
