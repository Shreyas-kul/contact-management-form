Project Description:
This Contact Management form is a full-stack application that allows users to store, edit, and delete contact details. It includes features such as adding contact information (First Name, Last Name, Email, and Phone Number), displaying them in a table, and managing the contacts through editing and deleting actions. The front-end is built with React while the back-end uses Node.js and MongoDB for data storage.
  
Setup Instructions:
Prerequisites:
Node.js: You should have Node.js installed. If not, you can download it here.
MongoDB: You need a MongoDB instance running. You can either set it up locally or use a cloud service like MongoDB Atlas.
Git: Git should be installed on your system.

Database Schema:
The backend uses MongoDB to store the contact information. Below is the schema for the Contact collection:
const mongoose = require('mongoose');

const contactSchema = new mongoose.Schema({
  firstName: {
    type: String,
    required: true,
  },
  lastName: {
    type: String,
    required: true,
  },
  email: {
    type: String,
    required: true,
    unique: true,
  },
  phone: {
    type: String,
    required: true,
  },
});

module.exports = mongoose.model('Contact', contactSchema);


How the App Works:
Frontend (React):

Users can add a new contact via a form with fields for First Name, Last Name, Email, and Phone.
The contact data is displayed in a table format, with options to edit or delete each contact.
When a user edits a contact, the form is pre-filled with the current details and updates the contact in the database when submitted.
Backend (Node.js & Express):

The server handles API routes for creating, reading, updating, and deleting contacts from the MongoDB database.
The routes are defined as:
POST /contacts: Add a new contact.
GET /contacts: Retrieve all contacts.
PUT /contacts/:id: Update an existing contact.
DELETE /contacts/:id: Delete a contact.
