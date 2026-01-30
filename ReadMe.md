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