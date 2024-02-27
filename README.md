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
# Main Program Loop
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
# Third Project -(Password Generator)
import random
l=int(input("Enter the number of length of the generator : "))
a1="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
a2="abcdefghijklmnopqrstuvwxyz"
all=a1+a2
r=''.join(random.sample(all,l))
print(r)

# Fourth Project -( Rock,Paper and Scissors Game)
import random
while True:
    print("In this game we just find the choice of the user snd computer if they are same then the output will come according to the ")
    print("user's choice and computer's choice.....so Best of Luck of this game 😊😊")
    user = input("Enter a choice which you want......(rock, paper, scissors): ")
    ls = ["rock", "paper", "scissors"]
    computer = random.choice(ls)
    print(f"\nYour choice {user}, computer choice {computer}.\n")
    if user == computer:
        print(f"Both players selected {user}. It's a tie!")
    elif user == "rock":
        if computer == "scissors":
            print("Rock smashes scissors! You win 👑👑 !")
        else:
            print("Paper covers rock! You lose 🤗🤗...")
    elif user == "paper":
        if computer == "rock":
            print("Paper covers rock! You win 👑👑 !")
        else:
            print("Scissors cuts paper! You lose 🤗🤗...")
    elif user == "scissors":
        if computer == "paper":
            print("Scissors cuts paper! You win 👑👑 !")
        else:
            print("Rock smashes scissors! You lose 🤗🤗...")

    play_again = input("Play again? (yes/no): ")
    if play_again.lower() != "yes":
        break

# Fifth Project -( Contact Book )
contacts=[]
def contact_menu():
    print("Contact Book menu ")
    print("1. Add Contact")
    print("2. view contact List")
    print("3. Search Contact")
    print("4. Update Contact")
    print("5. Delete Contact")
    print("6. EXIT")
def addcontact():
    Name=input("Enter the User's name : ")
    Phonenumber=input("Enter the User's Phone number : ")
    Email=input("Enter the User's Email : ")
    Address=input("Enter the User's Address : ")
    contact = {"Name": Name,"Phone Number": Phonenumber, "Email": Email,"Address": Address }
    contacts.append(contact)
    print("Contact added successfully!")
def contactlist():
    if contacts:
        print("All Contacts:")
        for contact in contacts:
            print("Name:", contact["Name"])
            print("Phone Number:", contact["Phone Number"])
            print("Email:", contact["Email"])
            print("Address:",contact["Address"])
            print("-------------------")
    else:
        print("No contacts found.")
def searchcontact():
    search_term = input("Enter the name or email of the contact to search: ")
    found_contacts = []
    for contact in contacts:
        if search_term.lower() in contact["Name"].lower() or search_term.lower() in contact["Email"].lower():
            found_contacts.append(contact)
    if found_contacts:
        print("Matching contacts found:")
        for contact in found_contacts:
            print("Name:", contact["Name"])
            print("Phone Number:", contact["Phone Number"])
            print("Email:", contact["Email"])
            print("Address:",contact["Address"])
            print("-------------------")
    else:
        print("No matching contacts found.")
def updatecontact():
    name = input("Enter the name of the contact to update: ")
    found_contact = None
    for contact in contacts:
        if contact["Name"].lower() == name.lower():
            found_contact = contact
            break
    if found_contact:
        print("Contact found. Enter new details:")
        found_contact["Name"] = input("Enter the new name: ")
        found_contact["Phone Number"] = input("Enter the new phone number: ")
        found_contact["Email"] = input("Enter the new email: ")
        found_contact["Address"]=input("Enter the new address:")
        print("Contact updated successfully!")
    else:
        print("Contact not found.")
def deletecontact():
    name = input("Enter the name of the contact to delete: ")
    for contact in contacts:
        if contact["Name"].lower() == name.lower():
            contacts.remove(contact)
            print("Contact deleted successfully!")
            break
    else:
        print("Contact not found.")
# Main program loop
while True:
    contact_menu()
    choice = input("Enter your choice (1-6): ")

    if choice == "1":
        addcontact()
    elif choice == "2":
        contactlist()
    elif choice == "3":
        searchcontact()
    elif choice == "4":
        updatecontact()
    elif choice == "5":
        deletecontact()
    elif choice == "6":
        print("you are Exit from Contact Book .....")
        break
    else:
        print("Invalid Choice . Please Enter The Valid Choice.......")
