# codsoft_taskon
I will do the things as easy as I want and this is for my Knowledge .
# first Project - (TO-DO LIST)
import os
t1=[]
def clear():
    os.system('clear' if os.name == 'codsoft' else 'code')
def menu():
    clear()
    print("To-Do List App")
    print("1.Add Tasks")
    print("2.View Tasks")
    print("3.Mark as completed")
    print("4.Delete task")
    print("5.Exit")
def addtask():
    t = input("Enter your desired new task : ")
    t1.append({"task": t, "completed": False})
    input("Task added.If you Continue the tasks then go to choice after pressing Enter Button ......")
def viewtasks():
    clear()
    print("The complete To-Do List:")
    for i,t in enumerate(t1,start=1):
        status="Done" if t["completed"] else "Not done"
        print(f"{i}.{t['task']}-Status:{status}")
    input("Press enter to continue...")
def marktaskcompleted():
    viewtasks()
    t_num=int(input("Enter the task number to mark as completed: ")) -1
    if 0<=t_num<len(t1):
        t1[t_num]["completed"]=True
        input("Task marked as completed.Press enter to continue...")
    else:
        input("Invalid task number.Press enter to continue...")
def deletetask():
    viewtasks()
    t_num = int(input("Enter the task number to delete: ")) - 1
    if 0 <= t_num < len(t1):
        del t1[t_num]
        input("Task deleted. Press Enter to continue...")
    else:
        input("Invalid task number. Press Enter to continue...")


while True:
    menu()
    choice = input("Enter your choice(1/2/3/4/5): ")

    if choice == '1':
        addtask()
    elif choice == '2':
        viewtasks()
    elif choice == '3':
        marktaskcompleted()
    elif choice == '4':
        deletetask()
    elif choice == '5':
        exit()
        break
    else:
        print("Invalid choice.Press enter to continue...")

# Second Project -( Calculator )
print("1. Addition")
print("2. Subtraction")
print("3. Multipication")
print("4. Division")
print("5. Modulodivision")
print("6. Square")
print("Exit - enter any other Number which are not presented below . ")
while True :
    choice = int(input("Enter the your choice which you want to operated in calculator....."))
    if choice<=6:
        a = int(input("Enter the first number for operation ......"))
        b = int(input("Enter the second number for operation ......."))
        if choice == 1 :
            s = a + b
            print(s)
        elif choice == 2:
            su = a - b
            print(su)
        elif choice == 3:
            m = a * b
            print(m)
        elif choice == 4:
            d = a / b
            print(d)
        elif choice == 5:
            mo = a % b
            print(mo)
        elif choice == 6:
            sq = a ** b
            print(sq)
    else:
        print("Exit ....")
        break
