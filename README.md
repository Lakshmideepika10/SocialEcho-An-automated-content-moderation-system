# SocialEcho-An-automated-content-moderation-system
The project is a social networking platform built using the MERN (MongoDB, Express.js, React.js, Node.js) stack. It incorporates two major features: an automated content moderation system and context-based authentication.

# Table of Contents
Project Overview
Features
Technologies
Schema Diagram
Getting Started
Usage
License

# Project Overview
This project is a social networking platform built using the MERN (MongoDB, Express.js, React.js, Node.js) stack. It incorporates two major features: an automated content moderation system and context-based authentication. These features are accompanied by common functionalities found in social media applications, such as profile creation, post creation and sharing, liking and commenting on posts, and following/unfollowing users.

Automated Content Moderation
The platform's automated content moderation system utilizes various NLP (Natural Language Processing) APIs. These APIs include:

Perspective API: Used for filtering spam, profanity, toxicity, harassment etc.
TextRazor API: Integrated for content categorization.
Hugging Face Interface API: Utilized with BART Large MNLI for content categorization.
A Flask application has been developed to provide similar functionality as the Hugging Face Interface API's classifier. The Flask app utilizes the BART Large MNLI model. It operates as a zero-shot classification pipeline with a PyTorch framework.

The system allows flexibility in choosing different services for API usage or disabling them without affecting overall functionality by using a common interface for interacting with the APIs.

When a user posts content, it undergoes a thorough filtering process to ensure compliance with the community guidelines. Additionally, users have the ability to report posts that they find inappropriate, which triggers a manual review process.

Context-Based Authentication
The platform implements context-based authentication to enhance user account security. It takes into consideration user location, IP address, and device information for authentication purposes. Users can conveniently manage their devices directly from the platform. To ensure data privacy, this information is encrypted using the AES algorithm and securely stored in the database.

In case of a suspicious login attempt, users are promptly notified via email and are required to confirm their identity to protect against unauthorized access.

# User Roles
There are three distinct user roles within the system:

Admin: The admin role manages the overall system, including moderator management, community management, content moderation, monitoring user activity, and more.
Moderators: Moderators manage communities, manually review reported posts, and perform other moderation-related tasks.
General Users: General users have the ability to make posts, like comments, and perform other actions within the platform.

# Features
 User authentication and authorization (JWT)
 User profile creation and management
 Post creation and management
 Commenting on posts
 Liking posts and comments
 Following/unfollowing users
 Reporting posts
 Content moderation
 Context-based authentication
 Device management
 Admin dashboard
 Moderator dashboard
 Email notifications

# Technologies
React.js
Redux
Node.js
Express.js
MongoDB
Tailwind CSS
JWT Authentication
Passport.js
Nodemailer
Crypto-js
Azure Blob Storage
Flask
Hugging Face Transformers

# Schema Diagram
![Schema Diagram](https://github.com/user-attachments/assets/65c03d0b-0ba5-434a-9984-8d96255d1d77)


# Getting Started
# Prerequisites
Before running the application, make sure you have the following installed:

Node.js
MongoDB or MongoDB Atlas account

# Installation
Clone the repository
git clone https://github.com/Lakshmideepika10/SocialEcho-An-automated-content-moderation-system.git
Go to the project directory and install dependencies for both the client and server
cd client
npm install
cd server
npm install
Create a .env file in both the client and server directories and add the environment variables as shown in the .env.example files.
Start the server
cd server
npm start
Start the client
cd client
npm start
# Configuration
Run the admin_tool.sh script from the server directory with permissions for executing the script. This script is used for configuring the admin account, creating the initial communities, and other settings.

./admin_tool.sh
.env Variables
For email service of context-based authentication, the following variables are required:

EMAIL=
PASSWORD=
EMAIL_SERVICE=
For content moderation, you need the PERSPECTIVE_API_KEY and either the INTERFACE_API_KEY or TEXTRAZOR_API_KEY. Visit the following links to obtain the API keys:

Perspective API
TextRazor API
Hugging Face Interface API
If you prefer, the Flask server can be run locally as an alternative to using the Hugging Face Interface API or TextRazor API. Refer to the classifier_server directory for more information.

Note: Configuration for context-based authentication and content moderation features are not mandatory to run the application. However, these features will not be available if the configuration is not provided.

# Usage
Admin
The admin dashboard can be accessed at the /admin route. Use the admin_tool.sh script to configure the admin account. The admin account can be used to manage moderators, communities, and perform other admin-related tasks. You can also enable/disable or switch API services using the admin dashboard.

Moderator
Moderators have specific email domain (@mod.socialecho.com). When registering with an email from this domain, the user is automatically assigned the moderator role. Moderators can be assigned to different communities from the admin dashboard.

# License
This project is licensed under the [MIT License]
