# to-do-list
tasks=[]
#1
def add_task():
    task=input("Enter Your Tasks")
    tasks.append(task)
    print(f"{task} Task Has Been Added")
#2
def display():
    if len(tasks)==0:
        print("No Tasks Available!")
    else:
        print("Your Tasks")
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")
#3
def remove():
    if len(tasks) == 0:
        print("No tasks available to remove!")
        return
    
    display()
	    try:
	        data=int(input("Enter Your Tasks NO"))-1
	        if 0<=data<len(tasks):
	            reuse= tasks.pop(data)
	            print(f"""Task {reuse} removed successfully!
	                    Remaining Tasks""")
	            display()    
	        else:
	            print(" Invalid Task Number! Please enter a valid number.")
	    except ValueError:
	        print("Invalid Input! Please enter a number.")
#4
def update():
    display()
    try:
        store=int(input(" Which Task Do You Want to Update? Enter Task No"))-1
        if 0<=store<len(tasks):
            new_task = input("Enter the updated task: ")
            tasks[store] = new_task
            print("Task updated successfully!")
            display()
        else:
            print("Invalid Task Number! Please enter a valid number.")
    except ValueError:
        print("Invalid Input! Please enter a number.")

while True:
    print("""MENU
1.Add Tasks
2.Show Tasks
3.Remove Tasks
4.Update Tasks
5.Exit""")
    try:
        select=int(input("Enter Tasks NO You Wanna Perform"))
        if select==1:
                add_task()
        elif select==2:
                display()
        elif select==3:
                remove()
        elif select==4:
                update()
        elif select==5:
                break
        else:
                print("Invalid Choice! Please Enter a Number Between 1 to 5.")
    except ValueError:
        print("Invalid Input! Please enter a number.")
