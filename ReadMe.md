# Module 8 – Lab 1: Logical and Physical Models

## Overview
This lab designs the logical and physical database models for a general Blogging application.

## Requirements
- Store users with basic user-related fields
- Users can create multiple posts
- Posts contain a title, description, and image
- Users can like posts
- Users can comment on posts

---

## Logical Model

### Entities
- User
- Post
- Comment
- Like

### Attributes

#### User
- user_id
- name
- email
- password_hash
- created_at

#### Post
- post_id
- title
- description
- image_url
- created_at

#### Comment
- comment_id
- content
- created_at

#### Like
- like_id
- created_at

### Relationships
- A User can create many Posts (1-to-many)
- A User can write many Comments (1-to-many)
- A Post can have many Comments (1-to-many)
- Users can like many Posts, and Posts can be liked by many Users (many-to-many via Like)

---

## Physical Model

### Tables

#### users
- id (INT, Primary Key, Auto Increment)
- name (VARCHAR)
- email (VARCHAR, UNIQUE)
- password_hash (VARCHAR)
- created_at (DATETIME)

#### posts
- id (INT, Primary Key, Auto Increment)
- user_id (INT, Foreign Key → users.id)
- title (VARCHAR)
- description (TEXT)
- image_url (VARCHAR)
- created_at (DATETIME)

#### comments
- id (INT, Primary Key, Auto Increment)
- post_id (INT, Foreign Key → posts.id)
- user_id (INT, Foreign Key → users.id)
- content (TEXT)
- created_at (DATETIME)

#### likes
- id (INT, Primary Key, Auto Increment)
- post_id (INT, Foreign Key → posts.id)
- user_id (INT, Foreign Key → users.id)
- created_at (DATETIME)
- Unique constraint on (post_id, user_id)

---

## Summary
This lab defines both the logical and physical models for a blogging application. 
The logical model identifies entities and relationships, while the physical model 
translates those concepts into database tables and constraints. This design will 
be used as the foundation for the MongoDB and MySQL implementations in later labs.