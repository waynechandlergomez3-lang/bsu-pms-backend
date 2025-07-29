===========================================
PARKING MANAGEMENT SYSTEM (PMS) DOCUMENTATION
===========================================

Table of Contents
----------------
1. Project Overview
2. System Requirements
3. Installation Steps
4. Key Features
5. Database Setup
6. Configuration
7. Usage Guide
8. Common Issues
9. Maintenance

1. PROJECT OVERVIEW
------------------
A comprehensive parking management system built with Laravel (backend) and React (frontend). 
The system manages parking spaces, user accounts, vehicle registration, and real-time space monitoring.

2. SYSTEM REQUIREMENTS
---------------------
Backend (Laravel):
- PHP >= 8.0.2
- MySQL 5.7 or higher
- Composer 2.x
- Required PHP Extensions:
  * mbstring
  * xml
  * mysql
  * bcmath
  * tokenizer
  * json

Frontend (React):
- Node.js >= 14.x
- NPM >= 6.x
- Modern web browser (Chrome, Firefox, Edge)
- React 18.2.0

3. INSTALLATION STEPS
--------------------
A. Backend Setup:

1. Navigate to backend directory:
   cd Capstone-PMS-backend

2. Install PHP dependencies:
   composer install

3. Set up environment:
   cp .env.example .env

4. Configure database in .env:
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=pms_db
   DB_USERNAME=root
   DB_PASSWORD=

5. Generate application key:
   php artisan key:generate

6. Run critical migrations in order:
   php artisan migrate:fresh
   php artisan migrate --path=database/migrations/2014_10_12_000000_create_users_table.php
   php artisan migrate --path=database/migrations/2024_05_11_093905_create_roles_table.php
   php artisan migrate --path=database/migrations/2024_07_24_000002_add_roles_id_to_users_table.php
   php artisan migrate --path=database/migrations/2023_07_23_000000_create_parking_layouts_table.php
   php artisan migrate --path=database/migrations/2023_07_23_000000_create_parking_slots_table.php
   php artisan migrate --path=database/migrations/2023_07_24_000000_create_parking_assignments_table.php

7. Start Laravel server:
   php artisan serve

B. Frontend Setup:

1. Navigate to frontend directory:
   cd ../frontend-PMS

2. Install dependencies:
   npm install

3. Start development server:
   npm start

4. KEY FEATURES
--------------
- Interactive Parking Layout Editor
- Real-time Space Management
- User Role Management
- Vehicle Registration System
- Space Assignment System
- QR Code Integration
- Reports Generation

5. DATABASE SETUP
----------------
The system requires the following tables (in order of creation):
1. users
2. roles
3. parking_layouts
4. parking_slots
5. parking_assignments
6. vehicles
7. qr_codes
8. feedback
9. incident_reports

6. CONFIGURATION
---------------
Backend (.env settings):
- APP_URL=http://localhost:8000
- JWT_SECRET=(generated automatically)
- CORS settings (if needed)

Frontend (environment):
- Backend API URL: http://localhost:8000
- All API requests should include authentication tokens

7. USAGE GUIDE
-------------
A. Admin Functions:
   - Create/Edit parking layouts
   - Manage user accounts
   - Generate reports
   - Monitor space usage

B. User Functions:
   - View available spaces
   - Make reservations
   - Register vehicles
   - Report incidents

C. Layout Editor Tools:
   - View Mode (H key)
   - Draw Mode (D key)
   - Edit Mode (V key)
   - Line drawing
   - Text annotation
   - Space types:
     * Standard
     * Compact
     * Handicap
     * EV (Electric Vehicle)

8. COMMON ISSUES
---------------
1. Database Connection:
   - Verify MySQL is running
   - Check credentials in .env
   - Ensure database exists

2. CORS Issues:
   Solution: Check CORS configuration in Laravel

3. Migration Errors:
   Solution: Run migrations in correct order

4. Authentication Issues:
   Solution: Clear browser cache and tokens

9. MAINTENANCE
-------------
Regular Tasks:
1. Database backups
2. Log rotation
3. Security updates
4. Performance monitoring

Security Best Practices:
1. Keep all dependencies updated
2. Regular security audits
3. Implement rate limiting
4. Monitor error logs
5. Regular backup verification

===========================================
For additional support or questions:
Contact: [09273915603]
Last Updated: July 29, 2025
===========================================
