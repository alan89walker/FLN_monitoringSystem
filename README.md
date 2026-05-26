# FLN Daily Monitoring System

A comprehensive web-based monitoring system for tracking Foundation Literacy and Numeracy (FLN) progress across schools and clusters.

## Overview

The FLN Daily Monitoring System is a full-stack application designed to help educational institutions:
- Track daily classroom progress and student attendance
- Monitor student performance metrics
- Generate analytics dashboards with filtered reports
- Export attendance data to PDF reports
- Manage multi-school and cluster-level data

## Features

✨ **Core Features**
- Multi-page workflow for seamless data entry
- Responsive UI optimized for desktop and mobile devices
- Real-time data persistence to MySQL database
- Interactive analytics dashboard with filters
- PDF export functionality for attendance reports
- Context-aware teacher and student data loading
- Cluster and school-level management

## Tech Stack

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Backend**: PHP 7.x+
- **Database**: MySQL/MariaDB
- **PDF Generation**: TCPDF
- **Server**: XAMPP/Apache

## Prerequisites

Before you start, ensure you have the following installed:
- **XAMPP** (includes Apache, MySQL, PHP)
- **PHP 7.0+**
- **MySQL 5.7+**
- **Web Browser** (Chrome, Firefox, Safari, Edge)
- **Composer** (for dependency management)

[Download XAMPP](https://www.apachefriends.org/)

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/FLN_monitoringSystem.git
cd FLN_monitoringSystem
```

### 2. Set Up XAMPP

1. Start XAMPP Control Panel
2. Enable **Apache** and **MySQL** modules
3. Click "Admin" next to MySQL to access phpMyAdmin

### 3. Configure Database

1. Open `http://localhost/phpmyadmin` in your browser
2. Create a new database:
   ```sql
   CREATE DATABASE fln_monitoring;
   ```
3. Import the database schema:
   - Navigate to the **Import** tab
   - Select `database/fln_monitoring.sql`
   - Click **Import**

### 4. Move Project to XAMPP

```bash
cp -r FLN_monitoringSystem C:\xampp\htdocs\
```

### 5. Install Dependencies

```bash
cd C:\xampp\htdocs\FLN_monitoringSystem
composer install
```

### 6. Configure API

Update database connection in `api/config.php`:

```php
define('DB_HOST', 'localhost');
define('DB_USER', 'root');
define('DB_PASS', '');
define('DB_NAME', 'fln_monitoring');
```

### 7. Access the Application

Open your browser and navigate to:

```
http://localhost/FLN_monitoringSystem/
```

## Workflow

1. **Select Cluster** → Choose your cluster from the landing page
2. **Select School** → Pick the specific school from available options
3. **Enter Monitoring Data** → Fill in the daily progress form with:
   - Teacher information
   - Student attendance
   - Performance metrics
4. **Submit Data** → Data is automatically saved to the database
5. **View Dashboard** → Access analytics dashboard to:
   - Filter by date, school, or class
   - View attendance trends
   - Export reports to PDF

## Project Structure

```
FLN_monitoringSystem/
├── index.html                    # Landing page
├── cluster.html                  # Cluster selection
├── schools.html                  # School selection
├── class-progress.html           # Monitoring form
├── dashboard.html                # Analytics dashboard
├── script.js                     # Main JavaScript logic
├── dashboard.js                  # Dashboard functionality
├── styles.css                    # Global styles
│
├── api/                          # Backend PHP APIs
│   ├── config.php               # Database configuration
│   ├── db.php                   # Database connection
│   ├── save_monitoring.php      # Save monitoring data
│   ├── get_schools.php          # Fetch schools
│   ├── export_attendance_pdf.php # PDF generation
│   └── ...
│
├── database/                     # Database scripts
│   ├── fln_monitoring.sql       # Main schema
│   ├── attendance_analytics.sql # Analytics seed
│   └── sync_workbook_data.php   # Data sync
│
└── assets/                       # Static assets
    ├── mobile-nav.js
    ├── back-to-top.js
    └── styles/
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/get_schools.php` | GET | Fetch all schools |
| `/api/save_monitoring.php` | POST | Save monitoring data |
| `/api/export_attendance_pdf.php` | POST | Export to PDF |
| `/api/get_school_context.php` | GET | Get school details |
| `/api/attendance_analytics.php` | GET | Fetch analytics data |

## Dashboard Features

- 📊 Real-time analytics with filters
- 🔍 Advanced filtering (date, school, class)
- 📥 One-click PDF export
- 📱 Responsive data tables
- 📈 Performance charts

## Database Features

### Included Data

The system includes:
- Multiple schools and clusters
- Teacher and student records
- Historical attendance data
- Performance metrics

### Schema

Key tables:
- `schools` - School information
- `teachers` - Teacher details
- `students` - Student records
- `attendance` - Daily attendance logs
- `performance_metrics` - Student performance data
- `clusters` - Cluster groupings

## Troubleshooting

### XAMPP Issues
- **Apache won't start**: Check if port 80 is already in use
- **MySQL won't start**: Ensure no other database service is running

### Database Issues
- **Connection failed**: Verify credentials in `api/config.php`
- **Table errors**: Re-import the database schema from `database/fln_monitoring.sql`

### PDF Export
- Ensure `TCPDF-main/` directory exists and is writable
- Check folder permissions for `assets/` directory
- Use `http://localhost/...` URLs (not `file:///...`)

## Performance Notes

- Always access via `http://localhost/...` for proper API functionality
- Clear browser cache if experiencing data inconsistencies
- Optimize PDF exports for large datasets
- Use MySQL indexes for faster queries on large data

## Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Support

For issues, questions, or suggestions:
- Open an [Issue](https://github.com/yourusername/FLN_monitoringSystem/issues)
- Check the documentation
- Contact the development team

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- TCPDF library for PDF generation
- Bootstrap framework for responsive design
- Built for FLN program monitoring and analysis

---

**Status**: Active Development  
**Last Updated**: May 2026
