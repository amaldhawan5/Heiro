import datetime

tasks = []

def show_menu():
    print("\n📚 Student Helper Chatbot")
    print("1. Ask Study Question")
    print("2. Add Task")
    print("3. View Tasks")
    print("4. Delete Task")
    print("5. Study Tips")
    print("6. Exit")

def study_help():
    question = input("Ask your study question: ")
    print("\n🤖 Answer:")
    
    # Basic AI-like responses
    if "math" in question.lower():
        print("Try breaking the problem step by step. Practice formulas daily.")
    elif "science" in question.lower():
        print("Focus on concepts and diagrams. Revise NCERT thoroughly.")
    elif "history" in question.lower():
        print("Make timelines and short notes for better memory.")
    else:
        print("That's a great question! Try researching it and revising regularly.")

def add_task():
    task = input("Enter your task: ")
    time = input("Enter time (HH:MM): ")
    tasks.append({"task": task, "time": time})
    print("✅ Task added successfully!")

def view_tasks():
    if not tasks:
        print("No tasks yet.")
    else:
        print("\n📝 Your Tasks:")
        for i, t in enumerate(tasks):
            print(f"{i+1}. {t['task']} at {t['time']}")

def delete_task():
    view_tasks()
    try:
        num = int(input("Enter task number to delete: "))
        tasks.pop(num-1)
        print("❌ Task deleted.")
    except:
        print("Invalid choice.")

def study_tips():
    print("\n📌 Study Tips:")
    print("- Study in 25 min sessions (Pomodoro)")
    print("- Revise daily")
    print("- Practice questions")
    print("- Avoid distractions")

# Main loop
while True:
    show_menu()
    choice = input("Enter your choice: ")

    if choice == "1":
        study_help()
    elif choice == "2":
        add_task()
    elif choice == "3":
        view_tasks()
    elif choice == "4":
        delete_task()
    elif choice == "5":
        study_tips()
    elif choice == "6":
        print("Goodbye! Keep studying 📖")
        break
    else:
        print("Invalid choice.")
