# Job Board Database Schema Assessment

## Overview
This assessment demonstrates a database schema design for a job board platform, along with a simple frontend interface that displays job listings.

## Database Schema Design

### Core Entities & Relationships

#### 1. **Users Table** (`users`)
- **Purpose**: Central user management for job seekers, founders, and admins
- **Key Design**: Role-based access control with `role` field supporting multiple user types
- **Fields**: Standard user fields with timestamps for audit trails

#### 2. **Companies Table** (`companies`)
- **Purpose**: Company information and branding
- **Key Design**: Includes startup-specific fields like `stage` and `industry` for better job matching
- **Fields**: Logo URLs, descriptions, and categorization fields

#### 3. **Founders Table** (`founders`)
- **Purpose**: Links users to companies with founder-specific information
- **Key Design**: One-to-one relationship with users (unique constraint on user_id)
- **Fields**: Title, bio, and company association

#### 4. **Jobs Table** (`jobs`)
- **Purpose**: Job postings with comprehensive details
- **Key Design**: Includes salary ranges, location flexibility, and categorization
- **Fields**: Salary min/max with currency, job type, level, and category

#### 5. **Applications Table** (`applications`)
- **Purpose**: Tracks job applications and their status
- **Key Design**: Prevents duplicate applications with unique index on (user_id, job_id)
- **Fields**: Status tracking from application to offer/rejection

#### 6. **Matches Table** (`matches`)
- **Purpose**: AI-powered job matching system
- **Key Design**: Score-based matching with boolean flag for strong matches
- **Fields**: Match score (0-100) and strong match indicator

#### 7. **Chats & Messages Tables** (`chats`, `messages`)
- **Purpose**: Communication between job seekers and founders
- **Key Design**: Separate chat sessions with threaded messaging
- **Fields**: Timestamps for message tracking and chat history

## Design Decisions

### 1. **Normalization (3NF)**
- Each table represents a single entity
- No redundant data storage
- Proper foreign key relationships

### 2. **Scalability & Extensibility**
- Timestamp fields for audit trails
- Flexible categorization fields
- Structure ready for future features

### 3. **Performance Optimization**
- Indexes on frequently queried fields
- Unique constraints to prevent data duplication
- Efficient relationship design

### 4. **Data Integrity**
- Foreign key constraints
- Unique indexes where appropriate
- NOT NULL constraints on required fields

## Frontend Implementation

The frontend displays:
- Job cards with all details from the schema
- Match scores and application functionality
- Founder information and interactive elements

## Assessment Deliverables

✅ **DBML Schema**: Complete database schema with all required tables and relationships  
✅ **Frontend Interface**: Simple interface displaying job data  
✅ **Design Documentation**: Explanation of schema decisions  
✅ **Working Application**: Frontend that can be viewed in any browser
