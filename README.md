let contacts = [];

function addContact() {
    let name = prompt("Enter contact name:");
    let phone = prompt("Enter contact phone number:");
    let email = prompt("Enter contact email:");

    contacts.push({ name: name, phone: phone, email: email });
    console.log("Contact added successfully!");
}

function displayContacts() {
    console.log("Contact List:");
    contacts.forEach((contact, index) => {
        console.log(Name: ${contact.name}, Phone: ${contact.phone}, Email: ${contact.email});
    });
}

function editContact() {
    let contactIndex = prompt("Enter the index of the contact you want to edit:");
    if (contactIndex < 0 || contactIndex >= contacts.length) {
        console.log("Invalid index!");
        return;
    }

    let name = prompt("Enter new contact name:");
    let phone = prompt("Enter new contact phone number:");
    let email = prompt("Enter new contact email:");

    contacts[contactIndex] = { name: name, phone: phone, email: email };
    console.log("Contact edited successfully!");
}

function deleteContact() {
    let contactIndex = prompt("Enter the index of the contact you want to delete:");
    if (contactIndex < 0 || contactIndex >= contacts.length) {
        console.log("Invalid index!");
        return;
    }

    contacts.splice(contactIndex, 1);
    console.log("Contact deleted successfully!");
}

while (true) {
    let option = prompt("Choose an option: \n1. Add contact \n2. Display contacts \n3. Edit contact \n4. Delete contact \n5. Exit");

    switch (option) {
        case "1":
            addContact();
            break;
        case "2":
            displayContacts();
            break;
        case "3":
            editContact();
            break;
        case "4":
            deleteContact();
            break;
        case "5":
            console.log("Exiting program...");
            return;
        default:
            console.log("Invalid option, please try again.");
    }
}
