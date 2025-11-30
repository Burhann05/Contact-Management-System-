class ContactManager:
    def __init__(self):
        self.contacts = []

    def add_contact(self, name, phone):
        self.contacts.append({"Name": name, "Phone": phone})
        print(f" Contact '{name}' added successfully.\n")

    def search_contact(self, name):
        found = [c for c in self.contacts if c["Name"].lower() == name.lower()]
        if found:
            print(" Contact Found:")
            for contact in found:
                print(f"Name: {contact['Name']}, Phone: {contact['Phone']}")
        else:
            print("contact not found.\n")

    def display_contacts(self):
        if not self.contacts:
            print(" No contacts to display.\n")
        else:
            print("\n All Contacts:")
            for i, contact in enumerate(self.contacts, 1):
                print(f"{i}. Name: {contact['Name']}, Phone: {contact['Phone']}")
            print()


# Example usage
if __name__ == "__main__":
    manager = ContactManager()

    while True:
        print("1. Add Contact\n2. Search Contact\n3. Display All Contacts\n4. Exit")
        choice = input("Choose an option (1-4): ")

        if choice == '1':
            name = input("Enter name: ")
            phone = input("Enter phone number: ")
            manager.add_contact(name, phone)

        elif choice == '2':
            name = input("Enter name to search: ")
            manager.search_contact(name)

        elif choice == '3':
            manager.display_contacts()

        elif choice == '4':
            print("Exiting Contact Manager. Goodbye!")
            break

        else:
            print("Invalid choice. Please try again.\n")
