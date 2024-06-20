---
Title: WEB101&WEB102 Final_Journal 
categories: [WEB101&WEB102, Final_Journal]
tags: [WEB101&WEB102]
---

## Topic : Tellonym Clone Project 
---

This report provides a overview of our journey in developing a clone of Tellonym, a social networking platform known for its anonymous messaging features. Our project centered around building the backend using Hono and Prisma, alongside going through .tsx files for frontend development and Shadcn UI for interface design. Our goal was to make our version work like Tellonym, with features like real-time messaging and user profiles. Throughout this report, we delved through development journey, challenges faced, solutions implemented, and insights gained from the guidance and consultation provided by our lecturer.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Work Distribution](#work-distribution)
3. [Lecturer Guidance](#lecturer-guidance)
4. [Authentication](#authentication)
5. [Home Page](#home-page)
6. [Chats](#chats)
7. [Profile (Public and Private)](#profile-public-and-private)
8. [Followers and Following](#followers-and-following)
9. [Authentication](#authentication)
10. [Challenges and Solutions](#challenges-and-solutions)
11. [Key Takeaways](#key-takeaways)
12. [Drawbacks](#drawbacks)
13. [Conclusion](#conclusion)

---

## Project Overview

1. **Project Scope**: The project aimed to replicate Tellonym's key features including real-time messaging, user profiles, and social interactions.

2. **Technologies Used**: Leveraged `.tsx` files for frontend development with Shadcn UI components, and utilized MongoDB for real-time communication and SQL databases for other data storage needs.

3. **Implementation Strategy**: Divided development into frontend and backend tasks, focusing on modular design and effective collaboration through Git.

---

## Work Distribution

### Team Responsibilities in Tellonym Clone Project

1. **Chimi Gyeltshen: Authentication Feature**

   - **Frontend**:
     - Utilized `.tsx` files and Shadcn UI for UI design.

   - **Backend**:
     - Implemented JWT for authentication.

2. **Khem Raj Galley and Tandin Om: Homepage Development**

   - **Frontend**:
     - Used `.tsx` files and Shadcn UI for components.

   - **Backend**:
     - Managed MongoDB schema design and API endpoints.

3. **Namgyel Wangchuk: Public Profiles**

   - **Frontend**:
     - Designed using `.tsx` files, Shadcn UI, and Tailwind CSS.

   - **Backend**:
     - Handled MongoDB schema design and API development.

4. **Rangjung Yeshi Norbu and Kanisha Pradhan: Chatbox Feature**

   - **Frontend**:
     - Implemented UI components and WebSocket communications.

   - **Backend**:
     - Designed MongoDB schema and managed message handling.

5. **Pema Dolkar: Private Profiles**

   - **Frontend**:
     - Developed UI using `.tsx` files and Shadcn UI.

   - **Backend**:
     - Integrated MongoDB and implemented API functionalities.

6. **Yonten Kinley Tenzin: Follower and Following Pages**

   - **Frontend**:
     - Managed with `.tsx` files, Shadcn UI, and React Icons.

   - **Backend**:
     - Oversaw CRUD operations, MongoDB management for user relationships, and API implementation.


7. **Collaboration**: Used GitHub for version control and collaboration, ensuring everyone could work on different parts of the project simultaneously. Together we designed the database schemas.

---

## Lecturer Guidance

The consultation played a vital role in guiding the Tellonym clone project, offering knowledge in database schema design with a focus on MongoDB for real-time communication and SQL for other functionalities. Sir provided a comprehensive project overview, helped us understand the structure and interactions between different components. Regular feedback sessions and continuous support were crucial in helping us tackle difficult topics like WebSocket setup and user authentication. This guidance ensured that we learned important lessons and overcame obstacles effectively while developing the project.

Below is the **Schema Design** and the **Project Overview** of our project.

![schema](/assets/img/schema.png)

## Authentication

**Frontend Development**

1. **User Login and Registration**: Implemented forms for user login and registration using Shadcn components.

2. **Authentication Flow**: Ensured smooth authentication flow, redirecting users to the homepage upon successful login.

**Backend Development**

1. **Endpoints**: Created endpoints for user registration, login, and logout.

2. **Token Management**: Implemented JWT for managing user sessions securely.

## Home Page

**Frontend Development**

During the first week, we focused on developing the homepage for Tellonym.

1. **Designing the Database Schema and API Endpoints**: We began by designing the database schema and API endpoints to fetch homepage data.

2. **UI Design**: We used Shadcn UI and reusable components to display all replied tells on the homepage. This was challenging, but we learned how to effectively use reusable components.

3. **Reusable Components**: Initially, we struggled to use reusable components across multiple pages, like the navigation bar. After a few days of trial and error, we became confident in using these components.

4. **User Interface Design**: Mimicking Tellonym's UI was tough. We used Tailwind CSS for arranging components and React Icons to enhance the UI.

**Frontend Features**

1. **User Interface**: The homepage shows the user's profile picture, name, and other details. It also displays tells from people the user follows.

2. **Interaction Buttons**: Users can like, share, or comment on tells using React Icons, making interactions easy.

3. **Recommendations**: The homepage suggests new users to follow based on user interactions and interests.

**Backend Features**

1. **Server Setup**: The server handles all user requests to ensure smooth operation.

2. **Database Storage**: All messages and profile information are stored in MongoDB, keeping data safe and accessible.

**How It Works**

1. **WebSocket Connection**: Establishes a connection to the server upon opening the homepage.

2. **Real-Time Updates**: Allows immediate updates for tells, likes, and comments without refreshing the page.

---

## Chats

**Frontend Development**

1. **Database Schema**: Designed using MongoDB for chats.

2. **UI Design**: Implemented using WebSockets, Shadcn UI, and React Icons. We created two UI components: one for the chat list and one for personal messages.

**Frontend Features**

1. **Message Display**: Messages are shown in chat bubbles, with user messages on the right and received messages on the left.

2. **Input and Send Button**: Users can type messages and send them using a pink send button. Messages appear instantly due to real-time updates.

**Backend Features**

1. **Server Setup**: Built with Node.js and Hono, handling connections and requests.

2. **WebSocket Connection**: Manages real-time communication with Socket.io.

3. **Database Storage**: Messages are stored in MongoDB Atlas, ensuring they are saved and retrievable.

**How It Works**

1. **Connecting**: Users connect to the backend server using WebSockets.

2. **Joining a Room**: Users join a specific chat room based on a unique room ID.

3. **Sending a Message**: Messages are sent to the backend server, saved to the database, and displayed in the chat room.

---

## Profile (Public and Private)

**Frontend Development**

1. **Relation Schema and Endpoints**: Designed relation schema and endpoints for public and private profiles.

2. **UI Design**: Used Shadcn UI and Tailwind CSS to design reusable components for profiles.

**Frontend Features**

1. **Private Profile**: Shows user profile details and allows replying to tells.

2. **Public Profile**: Displays user information and allows following or messaging.

**Backend Development**

1. **Endpoints**: Created endpoints to manage user data and interactions.

---

## Followers and Following

**Frontend Development**

1. **UI Design**: Designed the UI for follower and following pages.

**Backend Features**

1. **CRUD Functionality**: Implemented follow and unfollow actions with CRUD operations in the backend.

---

**Challenges**

1. **Initial Setup**: Struggled with initial setup and understanding of JWT but resolved with research and guidance from the lecturer.

---

## Challenges and Solutions

1. **Using Reusable Components**: Initially struggled but eventually mastered the use of reusable components.

2. **UI Design**: Faced difficulties mimicking Tellonym’s UI but became more confident with Tailwind CSS and React Icons.

3. **Database Integration**: Had trouble connecting two databases (MongoDB and Postgres) but resolved to use MongoDB.

4. **WebSocket Implementation**: Needed to complete authentication first; worked on demo implementation.

5. **Frontend and Backend Connection**: Many team members faced difficulties connecting the frontend and backend effectively.

6. **Collaboration**: Managed collaborative repositories and used new technologies through effective communication.

---

## Key Takeaways

1. **Learning Curve**: Gained significant experience with new technologies like Shadcn UI, WebSockets, and Tailwind CSS.

2. **Reusable Components**: Improved understanding and utilization of reusable components, enhancing code efficiency and maintainability.

3. **Real-Time Communication**: Successfully implemented real-time features using WebSockets, which is a critical aspect of modern web applications.

4. **Team Collaboration**: Enhanced team collaboration skills through effective use of GitHub and regular communication.

5. **Problem-Solving**: Developed strong problem-solving skills by overcoming various technical challenges and integrating feedback from the lecturer.

---

## Drawbacks

1. **Incomplete Integration**: Many team members struggled with connecting the frontend and backend, leading to incomplete integration of some features.

2. **Initial Struggles with Tools**: Faced initial difficulties with new tools and frameworks, which slowed down progress in the early stages.

3. **Limited Experience**: Lack of prior experience with technologies like JWT and WebSockets led to delays and required additional learning time.

4. **Dependency Issues**: Encountered dependency issues with some libraries and components, which required troubleshooting and workarounds.

---

## Conclusion

We successfully implemented key features of Tellonym such as the homepage, chat, profiles, and followers/following functionality. We faced challenges but learned a lot, becoming more confident in our web development skills. The project provided valuable experience and we look forward to further improving our Tellonym clone.
