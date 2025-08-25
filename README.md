# Job Board Database Schema Assessment

## Overview
This assessment demonstrates a comprehensive database schema design for a job board platform, along with a functional frontend interface that displays job listings with match scores and application functionality.

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

## Design Principles Applied

### 1. **Normalization (3NF)**
- Each table represents a single entity
- No redundant data storage
- Proper foreign key relationships

### 2. **Scalability & Extensibility**
- Timestamp fields for audit trails
- Flexible categorization fields
- JSON-ready structure for future metadata

### 3. **Performance Optimization**
- Indexes on frequently queried fields
- Unique constraints to prevent data duplication
- Efficient relationship design

### 4. **Data Integrity**
- Foreign key constraints
- Unique indexes where appropriate
- NOT NULL constraints on required fields

## Frontend Implementation

The frontend demonstrates:
- **Job Display**: Shows all job details from the schema
- **Application System**: Tracks applied jobs
- **Match Scores**: Displays AI-generated match percentages
- **Founder Information**: Shows company founder details
- **Interactive Elements**: Apply buttons, chat functionality

## How to Run

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Start the application**:
   ```bash
   npm start
   ```

3. **View the application**:
   Open `http://localhost:3000` in your browser

## Database Schema Visualization

The complete DBML schema is available in `dbml/schema.dbml` and can be visualized using [dbdiagram.io](https://dbdiagram.io).

## Assessment Deliverables

✅ **DBML Schema**: Complete database schema with all required tables and relationships  
✅ **Frontend Interface**: Working React component displaying job data  
✅ **Design Documentation**: Comprehensive explanation of schema decisions  
✅ **Runnable Application**: Complete project that can be executed  

## Future Enhancements

The schema is designed to support:
- Advanced search and filtering
- Recommendation algorithms
- Analytics and reporting
- Multi-language support
- Advanced matching algorithms
- Integration with external job boards
