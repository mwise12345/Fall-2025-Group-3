# Fall-2025-Group-3
MIST 4610 Dr. Sri Fall 2025 Group 3 Section 2

## Team Name
62775 Group 3

## Team Members
1. Matthew Wise
2. Ghasan Awad
3. Trisha Kattoju
4. Marrissa Le
5. Isaac Lee

# Problem Description

Our task is to develop a relationship database to represent the operations of a digital streaming service. The data model will represent operations involving the user and operational side of the company. Information will need to be stored about departments, employees, and on the user side, watch history, favorites, and more. Data related to the content on the streaming platform will be stored as well such as content type and genres. We are to populate the databases and model the relationships to enable the digital streaming service to seamlessly operate its data and scale.

# Data Model Explanation

Our model is centered on the Account Owner, the entity that represents the primary user who holds the account. The model holds information regarding the owner’s name, email, and password. This Account Owner entity serves as the root for three main branches: Payments, Tickets, and Profiles. The account owner can have many payments. Payment info stored includes credit card number, card type, and transaction dates. The second branch leads to the Profile table. An account owner can create multiple profiles for their account. Profile data includes the profile name.

There are two key branches that come from the Profile table. First, the Watch History table logs every video a profile plays and the date watched. Since one profile can watch many videos over time, this is a one-to-many relationship.

The Favorites table is the second entity that is connected with the profile table. A profile can add many content items to their personal "Favorites" and a single content item like a popular movie can be favorited by many different profiles. Because of this many-to-many relationship, the Favorites table serves as an associative entity that links the Profile and Content tables.

The Content entity represents our entire media catalog of movies and series. It stores descriptive data like the title, release year, duration, language, and content type of a show or movie. To organize this large catalog, we have a Genre table, which defines all possible genres. A single movie can be in multiple genres (like action and science-fiction), and a single genre may apply to many movies. To model this many-to-many relationship, we created the Content Genre associative table, which links the content id to the genre id. The Genre table branches out to a join table called Genre_has_Genre with a many to many recursive relationship, allowing a genre like 'Psychological Thriller' to be linked to its parent, 'Thriller'. A subgenre can have many genres and a subgenre can have many genres.

Finally, our model involves the internal operations of the company. The Department entity represents our internal departments such as billing and customer support. Inside a department, there are many employees. Employee data stored includes name, email, job title, and their hire date. Each employee also has a supervisor, and a supervisor can oversee many employees, indicating a one-to-many recursive relationship.

When a customer has a problem, they need to contact an employee. An account owner can have many support tickets, and an Employee (like a support agent) can work on many tickets. This many-to-many relationship is handled by the Ticket associative table, which links the account owner who has a problem to the Employee assigned to help them. A ticket has a request date and a resolve date.

# Data Model

<img width="2134" height="1260" alt="image" src="https://github.com/user-attachments/assets/b01358a1-4450-4cb4-914b-4b15fe7b67b6" />

# Data Dictionary

Data Dictionary to be put here

# Queries

<img width="1614" height="938" alt="image" src="https://github.com/user-attachments/assets/471369ad-23ff-4122-a3fe-e6df9f05e199" />
