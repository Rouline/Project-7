# Project-7
Assignment 7: creating phone book
f="contacts.txt"
f1=open(f, "a+")
f1.close

def welcome():
entry=int(input("""Welcome to My Contact Book Menu.
>>>my Contact Book commands are: 1, 2, 3, 4 or 5 <<<
                    1. List contacts
                    2. Add a Contact
                    3. Display Contact
                    4. Remove a Contact
                    5. Quit
                    Type in your Entry(1, 2, 3, 4 or 5):  """))

return entry 


def phonebook():
contact = {}

while True:
entry = welcome()

if entry == 1:
ifbool(contact) != False:
for k, v in contact.items():
print(k, '-->', v)
            #else inform the user that the contact book is empty
else:
print("You have an empty phonebook! Go back to the menu to add a new contact")
        #Decision for the second entry
elif entry ==2:
            #request for phonebook and contact name
phone_number=int(input("Please enter a number: "))       

fname = input("Input your First Name: ")

mname = input("Input your Middle Name: ")

lname = input("Input your Last Name: ")
contact_name = (lname + " " + fname + " " + mname)
mnames=contact_name.split()
for i in range(0, len(mnames)):
if i <len(mnames) -1:
print(mnames[1][0], end=" ")
else:
print(mnames[i])

email_address = input("Input your Email Address: ")
country = input("Input your Country: ")
city = input("Input your City: ")
zip_code = input("Input your Zip Code: ")
print(country + " " + city + " " + zip_code)

            #check if the contact number already exists in Phonebook
            #if it does not, update current contact list in Phonebook
ifphone_number not in contact.items():
contact.update({contact_name: phone_number})
print("Contact successfuly saved")
print("Your updated phonebook is Shown below: ")
                #loop through phonebook and display each contact in a separate line
for k, v in contact.items():
print(k, '-->', v)
                #else display a message to inform the user the contact already exists
else:
print("That contact already exists in your phonebook")
        #create a desition for the third entry
elif entry == 3:
            #Initiate a name variable which user wishes to view
name=input("Enter Full Names i.elname,fname and mname of the contact details you wish to view:  ")
            #create a condition to check if the entered name is in the phonebook
if name in contact_name:
                #if yes, print the required contact
print("The contact is", name, ":", contact[name])
            #else inform the user that the contact does not exist
else:
print("That contact does not exist! Return to the main menu to enter the contact")

        #create a decision for entry 4
elif entry == 4:
            #initiate a name variable
name=input("Enter Full Names i.elname,fname and mname  of the contact you wish to delete: ")
            #check if the contact exists
if name in contact:
                #print the required contact
print("The contact is", name, ":", contact[name])
            #else inform the user that the contact does not exist
else:
print("That contact does not exist! Return to the main menu to enter the contact")


confirm=input("Are you sure you wish to delete this contact? Yes/No: ")
ifconfirm.capitalize()=="Yes":
contact.pop(name, None)
for k, v in contact.items():
print("Your update Phonebook is shown below: ")
print(k, "-->", v)

else:
print("Return to main menu")

elif entry == 5:
print("Thanks for using the My Contact Book. Am Rouline")
break
else:
print("Incorect Entry!")

contactss = str("[" + fname + " " + mname + " " + lname + ", " + email_address + ", "+ country + "," + city  + "]/n")


        f1=open(f, "a")
f1.write(contactss)
print("This contact\n " + contactss + "has been added successfuly")

phonebook()
