<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biyonal College - Student Portal</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- LOGIN PAGE -->
    <div id="loginPage" class="page active">
        <div class="login-container">
            <div class="login-box">
                <h1>🎓 Biyonal College</h1>
                <h2>Student Portal Login</h2>
                <form id="loginForm">
                    <div class="form-group">
                        <label for="username">Username:</label>
                        <input type="text" id="username" name="username" required placeholder="Enter your username">
                    </div>
                    <div class="form-group">
                        <label for="password">Password:</label>
                        <input type="password" id="password" name="password" required placeholder="Enter your password">
                    </div>
                    <button type="submit" class="btn-login">Login</button>
                </form>
                <p id="errorMessage" class="error-message"></p>
                <div class="demo-credentials">
                    <p><strong>Demo Credentials:</strong></p>
                    <p>Username: <code>student1</code></p>
                    <p>Password: <code>pass123</code></p>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN PORTAL PAGE -->
    <div id="portalPage" class="page">
        <!-- NAVBAR -->
        <nav class="navbar">
            <div class="nav-container">
                <h1 class="logo">🎓 Biyonal College Portal</h1>
                <ul class="nav-links">
                    <li><a href="#" data-page="courses" class="nav-btn">Courses</a></li>
                    <li><a href="#" data-page="hod" class="nav-btn">HOD Directory</a></li>
                    <li><a href="#" data-page="records" class="nav-btn">Student Records</a></li>
                    <li><a href="#" data-page="admission" class="nav-btn">Admission & Fees</a></li>
                    <li><a href="#" data-page="entry-exit" class="nav-btn">Entry & Exit</a></li>
                    <li><a href="#" id="logoutBtn" class="nav-btn logout">Logout</a></li>
                </ul>
            </div>
        </nav>

        <!-- COURSES PAGE -->
        <div id="courses" class="content-page active">
            <div class="container">
                <h2>Available Courses</h2>
                <div class="search-bar">
                    <input type="text" id="searchCourses" placeholder="Search courses...">
                </div>
                <div class="courses-grid" id="coursesGrid"></div>
            </div>
        </div>

        <!-- HOD DIRECTORY PAGE -->
        <div id="hod" class="content-page">
            <div class="container">
                <h2>Head of Departments Directory</h2>
                <div class="search-bar">
                    <input type="text" id="searchHOD" placeholder="Search by department or name...">
                </div>
                <table class="hod-table" id="hodTable">
                    <thead>
                        <tr>
                            <th>Department</th>
                            <th>HOD Name</th>
                            <th>Contact Number</th>
                            <th>Email</th>
                        </tr>
                    </thead>
                    <tbody id="hodTableBody"></tbody>
                </table>
            </div>
        </div>

        <!-- STUDENT RECORDS PAGE -->
        <div id="records" class="content-page">
            <div class="container">
                <h2>Student Records Portal</h2>
                <div class="tabs">
                    <button class="tab-btn active" data-tab="view-records">View Records</button>
                    <button class="tab-btn" data-tab="add-student">Add Student</button>
                    <button class="tab-btn" data-tab="update-marks">Update Marks</button>
                </div>

                <!-- View Records Tab -->
                <div id="view-records" class="tab-content active">
                    <div class="search-bar">
                        <input type="text" id="searchStudent" placeholder="Search by student name or ID...">
                    </div>
                    <table class="student-table" id="studentTable">
                        <thead>
                            <tr>
                                <th>Student ID</th>
                                <th>Name</th>
                                <th>Course</th>
                                <th>Email</th>
                                <th>Marks</th>
                                <th>Rank</th>
                            </tr>
                        </thead>
                        <tbody id="studentTableBody"></tbody>
                    </table>
                </div>

                <!-- Add Student Tab -->
                <div id="add-student" class="tab-content">
                    <form id="addStudentForm" class="student-form">
                        <div class="form-group">
                            <label for="studentName">Student Name:</label>
                            <input type="text" id="studentName" required>
                        </div>
                        <div class="form-group">
                            <label for="studentCourse">Course:</label>
                            <select id="studentCourse" required>
                                <option>Bachelor of Computer Science</option>
                                <option>Bachelor of Information Technology</option>
                                <option>Bachelor of English</option>
                                <option>Bachelor of Science</option>
                                <option>Bachelor of Business Administration</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="studentEmail">Email:</label>
                            <input type="email" id="studentEmail" required>
                        </div>
                        <div class="form-group">
                            <label for="studentMarks">Marks:</label>
                            <input type="number" id="studentMarks" min="0" max="100" required>
                        </div>
                        <button type="submit" class="btn-primary">Add Student</button>
                    </form>
                </div>

                <!-- Update Marks Tab -->
                <div id="update-marks" class="tab-content">
                    <form id="updateMarksForm" class="student-form">
                        <div class="form-group">
                            <label for="updateStudentId">Student ID:</label>
                            <input type="text" id="updateStudentId" required>
                        </div>
                        <div class="form-group">
                            <label for="updateMarks">New Marks:</label>
                            <input type="number" id="updateMarks" min="0" max="100" required>
                        </div>
                        <button type="submit" class="btn-primary">Update Marks</button>
                    </form>
                </div>
            </div>
        </div>

        <!-- ADMISSION & FEES PAGE -->
        <div id="admission" class="content-page">
            <div class="container">
                <h2>Admission & Fee Portal</h2>
                <div class="tabs">
                    <button class="tab-btn active" data-tab="pre-booking">Pre-Booking</button>
                    <button class="tab-btn" data-tab="fee-payment">Fee Payment</button>
                    <button class="tab-btn" data-tab="status">Admission Status</button>
                </div>

                <!-- Pre-Booking Tab -->
                <div id="pre-booking" class="tab-content active">
                    <form id="preBookingForm" class="admission-form">
                        <h3>Reserve Your Seat</h3>
                        <div class="form-group">
                            <label for="fullName">Full Name:</label>
                            <input type="text" id="fullName" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email:</label>
                            <input type="email" id="email" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number:</label>
                            <input type="tel" id="phone" required>
                        </div>
                        <div class="form-group">
                            <label for="course">Course:</label>
                            <select id="course" required>
                                <option>Bachelor of Computer Science</option>
                                <option>Bachelor of Information Technology</option>
                                <option>Bachelor of English</option>
                                <option>Bachelor of Science</option>
                                <option>Bachelor of Business Administration</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="qualifications">Qualifications:</label>
                            <input type="text" id="qualifications" placeholder="e.g., 12th pass">
                        </div>
                        <button type="submit" class="btn-primary">Reserve Seat</button>
                    </form>
                </div>

                <!-- Fee Payment Tab -->
                <div id="fee-payment" class="tab-content">
                    <form id="feePaymentForm" class="admission-form">
                        <h3>Pay Your Admission Fee</h3>
                        <div class="form-group">
                            <label for="paymentName">Name:</label>
                            <input type="text" id="paymentName" required>
                        </div>
                        <div class="form-group">
                            <label for="amount">Amount (₹):</label>
                            <select id="amount" required>
                                <option value="5000">₹5,000 - Registration Fee</option>
                                <option value="50000">₹50,000 - Semester Fee</option>
                                <option value="150000">₹1,50,000 - Annual Fee</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="paymentMethod">Payment Method:</label>
                            <select id="paymentMethod" required>
                                <option>Credit Card</option>
                                <option>Debit Card</option>
                                <option>Net Banking</option>
                                <option>UPI</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="cardNumber">Card/UPI Details:</label>
                            <input type="text" id="cardNumber" placeholder="Enter card number or UPI ID" required>
                        </div>
                        <button type="submit" class="btn-primary">Process Payment</button>
                    </form>
                </div>

                <!-- Admission Status Tab -->
                <div id="status" class="tab-content">
                    <div class="status-container">
                        <h3>Check Your Admission Status</h3>
                        <div class="search-bar">
                            <input type="text" id="statusEmail" placeholder="Enter your email to check status">
                            <button onclick="checkStatus()" class="btn-primary">Check Status</button>
                        </div>
                        <div id="statusResult"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- ENTRY & EXIT PAGE -->
        <div id="entry-exit" class="content-page">
            <div class="container">
                <h2>Campus Entry & Exit Portal</h2>
                <div class="tabs">
                    <button class="tab-btn active" data-tab="mark-entry">Mark Entry</button>
                    <button class="tab-btn" data-tab="mark-exit">Mark Exit</button>
                    <button class="tab-btn" data-tab="records">Attendance Records</button>
                </div>

                <!-- Mark Entry Tab -->
                <div id="mark-entry" class="tab-content active">
                    <form id="markEntryForm" class="entry-form">
                        <h3>Mark Campus Entry</h3>
                        <div class="form-group">
                            <label for="entryStudentId">Student ID:</label>
                            <input type="text" id="entryStudentId" required>
                        </div>
                        <div class="form-group">
                            <label for="entryPurpose">Purpose of Visit:</label>
                            <select id="entryPurpose" required>
                                <option>Class</option>
                                <option>Lab Work</option>
                                <option>Library</option>
                                <option>Sports</option>
                                <option>Canteen</option>
                                <option>Other</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="entryTime">Entry Time:</label>
                            <input type="time" id="entryTime" required>
                        </div>
                        <button type="submit" class="btn-primary">Mark Entry</button>
                    </form>
                </div>

                <!-- Mark Exit Tab -->
                <div id="mark-exit" class="tab-content">
                    <form id="markExitForm" class="entry-form">
                        <h3>Mark Campus Exit</h3>
                        <div class="form-group">
                            <label for="exitStudentId">Student ID:</label>
                            <input type="text" id="exitStudentId" required>
                        </div>
                        <div class="form-group">
                            <label for="exitTime">Exit Time:</label>
                            <input type="time" id="exitTime" required>
                        </div>
                        <div class="form-group">
                            <label for="exitNotes">Notes:</label>
                            <textarea id="exitNotes" placeholder="Any additional notes..."></textarea>
                        </div>
                        <button type="submit" class="btn-primary">Mark Exit</button>
                    </form>
                </div>

                <!-- Attendance Records Tab -->
                <div id="records-tab" class="tab-content">
                    <div class="search-bar">
                        <input type="text" id="searchAttendance" placeholder="Search by student ID...">
                    </div>
                    <table class="attendance-table" id="attendanceTable">
                        <thead>
                            <tr>
                                <th>Student ID</th>
                                <th>Entry Time</th>
                                <th>Exit Time</th>
                                <th>Duration</th>
                                <th>Purpose</th>
                                <th>Notes</th>
                            </tr>
                        </thead>
                        <tbody id="attendanceTableBody"></tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>

// ==================== DATA ====================
const coursesData = [
    {
        id: 1,
        name: 'Bachelor of Computer Science',
        description: 'Learn programming, algorithms, and software development',
        duration: '4 years',
        credits: 120
    },
    {
        id: 2,
        name: 'Bachelor of Information Technology',
        description: 'IT infrastructure, databases, and networking',
        duration: '4 years',
        credits: 120
    },
    {
        id: 3,
        name: 'Bachelor of English',
        description: 'Literature, writing, and communication skills',
        duration: '3 years',
        credits: 90
    },
    {
        id: 4,
        name: 'Bachelor of Science (Physics)',
        description: 'Physics, mechanics, and quantum theory',
        duration: '3 years',
        credits: 90
    },
    {
        id: 5,
        name: 'Bachelor of Business Administration',
        description: 'Management, finance, and business strategy',
        duration: '3 years',
        credits: 90
    },
    {
        id: 6,
        name: 'Bachelor of Science (Chemistry)',
        description: 'Organic chemistry, biochemistry, and laboratory skills',
        duration: '3 years',
        credits: 90
    },
    {
        id: 7,
        name: 'Bachelor of Engineering (Civil)',
        description: 'Structural design, construction, and infrastructure',
        duration: '4 years',
        credits: 120
    },
    {
        id: 8,
        name: 'Bachelor of Engineering (Mechanical)',
        description: 'Mechanical systems, thermodynamics, and design',
        duration: '4 years',
        credits: 120
    }
];

const hodData = [
    { department: 'Computer Science', name: 'Dr. Rajesh Kumar', contact: '+91-9876543210', email: 'rajesh.kumar@biyonal.edu' },
    { department: 'Information Technology', name: 'Prof. Priya Sharma', contact: '+91-9876543211', email: 'priya.sharma@biyonal.edu' },
    { department: 'English', name: 'Dr. Anita Singh', contact: '+91-9876543212', email: 'anita.singh@biyonal.edu' },
    { department: 'Physics', name: 'Prof. Vikram Patel', contact: '+91-9876543213', email: 'vikram.patel@biyonal.edu' },
    { department: 'Chemistry', name: 'Dr. Neha Gupta', contact: '+91-9876543214', email: 'neha.gupta@biyonal.edu' },
    { department: 'Business Administration', name: 'Prof. Arjun Desai', contact: '+91-9876543215', email: 'arjun.desai@biyonal.edu' },
    { department: 'Civil Engineering', name: 'Dr. Ravi Mendis', contact: '+91-9876543216', email: 'ravi.mendis@biyonal.edu' },
    { department: 'Mechanical Engineering', name: 'Prof. Sunil Nair', contact: '+91-9876543217', email: 'sunil.nair@biyonal.edu' }
];

let studentsData = [
    { id: 'S001', name: 'Rohit Sharma', course: 'Bachelor of Computer Science', email: 'rohit@college.edu', marks: 85, rank: 1 },
    { id: 'S002', name: 'Priya Desai', course: 'Bachelor of Information Technology', email: 'priya@college.edu', marks: 78, rank: 2 },
    { id: 'S003', name: 'Arun Singh', course: 'Bachelor of English', email: 'arun@college.edu', marks: 72, rank: 3 }
];

let bookings = [];
let payments = [];
let admissions = [];
let attendanceRecords = [];

// ==================== PAGE NAVIGATION ====================
function showPage(pageName) {
    // Hide all pages
    document.querySelectorAll('.page').forEach(page => page.classList.remove('active'));
   
    if (pageName === 'login') {
        document.getElementById('loginPage').classList.add('active');
    } else {
        document.getElementById('portalPage').classList.add('active');
        showContentPage(pageName);
    }
}

function showContentPage(contentName) {
    document.querySelectorAll('.content-page').forEach(page => page.classList.remove('active'));
    const page = document.getElementById(contentName);
    if (page) page.classList.add('active');
   
    // Update active nav button
    document.querySelectorAll('.nav-btn').forEach(btn => btn.classList.remove('active'));
    document.querySelector(`[data-page="${contentName}"]`)?.classList.add('active');
   
    // Initialize data based on page
    if (contentName === 'courses') displayCourses();
    else if (contentName === 'hod') displayHOD();
    else if (contentName === 'records') displayStudents();
    else if (contentName === 'entry-exit') displayAttendance();
}

// ==================== AUTHENTICATION ====================
document.getElementById('loginForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    const errorMessage = document.getElementById('errorMessage');
   
    if (username === 'student1' && password === 'pass123') {
        localStorage.setItem('isLoggedIn', 'true');
        localStorage.setItem('username', username);
        errorMessage.textContent = '';
        showPage('courses');
        document.getElementById('username').value = '';
        document.getElementById('password').value = '';
    } else {
        errorMessage.textContent = 'Invalid username or password!';
    }
});

document.getElementById('logoutBtn').addEventListener('click', function(e) {
    e.preventDefault();
    localStorage.removeItem('isLoggedIn');
    localStorage.removeItem('username');
    showPage('login');
});

// Check authentication on load
window.addEventListener('load', function() {
    if (localStorage.getItem('isLoggedIn') === 'true') {
        showPage('courses');
    } else {
        showPage('login');
    }
});

// ==================== COURSES PAGE ====================
function displayCourses(courses = coursesData) {
    const coursesGrid = document.getElementById('coursesGrid');
    coursesGrid.innerHTML = '';
   
    courses.forEach(course => {
        const courseCard = document.createElement('div');
        courseCard.className = 'course-card';
        courseCard.innerHTML = `
            <h3>${course.name}</h3>
            <p>${course.description}</p>
            <div class="course-info">
                <p><strong>Duration:</strong> ${course.duration}</p>
                <p><strong>Credits:</strong> ${course.credits}</p>
            </div>
        `;
        coursesGrid.appendChild(courseCard);
    });
}

document.getElementById('searchCourses').addEventListener('input', function(e) {
    const searchTerm = e.target.value.toLowerCase();
    const filtered = coursesData.filter(course =>
        course.name.toLowerCase().includes(searchTerm) ||
        course.description.toLowerCase().includes(searchTerm)
    );
    displayCourses(filtered);
});

// ==================== HOD DIRECTORY PAGE ====================
function displayHOD(hods = hodData) {
    const hodTableBody = document.getElementById('hodTableBody');
    hodTableBody.innerHTML = '';
   
    hods.forEach(hod => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${hod.department}</td>
            <td>${hod.name}</td>
            <td>${hod.contact}</td>
            <td>${hod.email}</td>
        `;
        hodTableBody.appendChild(row);
    });
}

document.getElementById('searchHOD').addEventListener('input', function(e) {
    const searchTerm = e.target.value.toLowerCase();
    const filtered = hodData.filter(hod =>
        hod.department.toLowerCase().includes(searchTerm) ||
        hod.name.toLowerCase().includes(searchTerm)
    );
    displayHOD(filtered);
});

// ==================== STUDENT RECORDS PAGE ====================
function displayStudents(students = studentsData) {
    const tbody = document.getElementById('studentTableBody');
    tbody.innerHTML = '';
   
    students.forEach(student => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${student.id}</td>
            <td>${student.name}</td>
            <td>${student.course}</td>
            <td>${student.email}</td>
            <td>${student.marks}</td>
            <td>${student.rank}</td>
        `;
        tbody.appendChild(row);
    });
}

document.getElementById('searchStudent').addEventListener('input', function(e) {
    const searchTerm = e.target.value.toLowerCase();
    const filtered = studentsData.filter(student =>
        student.name.toLowerCase().includes(searchTerm) ||
        student.id.toLowerCase().includes(searchTerm)
    );
    displayStudents(filtered);
});

document.getElementById('addStudentForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const newStudent = {
        id: 'S' + String(studentsData.length + 1).padStart(3, '0'),
        name: document.getElementById('studentName').value,
        course: document.getElementById('studentCourse').value,
        email: document.getElementById('studentEmail').value,
        marks: parseInt(document.getElementById('studentMarks').value),
        rank: 0
    };
   
    studentsData.push(newStudent);
    updateRanks();
    displayStudents();
    this.reset();
    alert('Student added successfully!');
});

document.getElementById('updateMarksForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const studentId = document.getElementById('updateStudentId').value;
    const newMarks = parseInt(document.getElementById('updateMarks').value);
   
    const student = studentsData.find(s => s.id === studentId);
    if (student) {
        student.marks = newMarks;
        updateRanks();
        displayStudents();
        this.reset();
        alert('Marks updated successfully!');
    } else {
        alert('Student not found!');
    }
});

function updateRanks() {
    studentsData.sort((a, b) => b.marks - a.marks);
    studentsData.forEach((student, index) => {
        student.rank = index + 1;
    });
}

// ==================== TAB NAVIGATION ====================
document.querySelectorAll('.tab-btn').forEach(btn => {
    btn.addEventListener('click', function() {
        const tabId = this.dataset.tab;
        const tabContainer = this.closest('.container') || this.parentElement;
       
        // Remove active from all buttons in this container
        tabContainer.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        // Add active to clicked button
        this.classList.add('active');
       
        // Hide all tab contents in this container
        tabContainer.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
        // Show the clicked tab content
        const tabElement = tabContainer.querySelector(`#${tabId}`);
        if (tabElement) {
            tabElement.classList.add('active');
        }
    });
});

// ==================== ADMISSION & FEES PAGE ====================
document.getElementById('preBookingForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const booking = {
        id: 'RES' + Math.random().toString(36).substr(2, 9).toUpperCase(),
        name: document.getElementById('fullName').value,
        email: document.getElementById('email').value,
        phone: document.getElementById('phone').value,
        course: document.getElementById('course').value,
        qualifications: document.getElementById('qualifications').value,
        date: new Date().toLocaleDateString(),
        status: 'Confirmed'
    };
   
    bookings.push(booking);
    admissions.push({
        email: booking.email,
        status: 'Pending',
        date: booking.date
    });
   
    alert(`Seat Reserved Successfully!\nReservation ID: ${booking.id}\nYou will receive a confirmation email shortly.`);
    this.reset();
});

document.getElementById('feePaymentForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const payment = {
        id: 'PAY' + Math.random().toString(36).substr(2, 9).toUpperCase(),
        name: document.getElementById('paymentName').value,
        amount: document.getElementById('amount').value,
        method: document.getElementById('paymentMethod').value,
        cardNumber: document.getElementById('cardNumber').value,
        date: new Date().toLocaleDateString()
    };
   
    payments.push(payment);
   
    alert(`Payment Processed Successfully!\nTransaction ID: ${payment.id}\nAmount: ₹${payment.amount}\nReceipt will be sent to your email.`);
    this.reset();
});

function checkStatus() {
    const email = document.getElementById('statusEmail').value;
    const statusResult = document.getElementById('statusResult');
   
    const admission = admissions.find(a => a.email === email);
   
    if (admission) {
        const statusClass = admission.status.toLowerCase();
        statusResult.innerHTML = `
            <h4>Admission Status</h4>
            <p><strong>Email:</strong> ${email}</p>
            <p><strong>Status:</strong> <span class="status-badge ${statusClass}">${admission.status}</span></p>
            <p><strong>Date:</strong> ${admission.date}</p>
        `;
    } else {
        statusResult.innerHTML = '<p style="color: red;">No admission record found for this email.</p>';
    }
}

// ==================== ENTRY & EXIT PAGE ====================
document.getElementById('markEntryForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const record = {
        studentId: document.getElementById('entryStudentId').value,
        purpose: document.getElementById('entryPurpose').value,
        entryTime: document.getElementById('entryTime').value,
        exitTime: null,
        notes: '',
        duration: 'Ongoing'
    };
   
    attendanceRecords.push(record);
    alert('Entry marked successfully!');
    this.reset();
    displayAttendance();
});

document.getElementById('markExitForm').addEventListener('submit', function(e) {
    e.preventDefault();
   
    const studentId = document.getElementById('exitStudentId').value;
    const exitTime = document.getElementById('exitTime').value;
    const notes = document.getElementById('exitNotes').value;
   
    const record = attendanceRecords.find(r => r.studentId === studentId && !r.exitTime);
   
    if (record) {
        record.exitTime = exitTime;
        record.notes = notes;
       
        const [entryH, entryM] = record.entryTime.split(':').map(Number);
        const [exitH, exitM] = exitTime.split(':').map(Number);
        const duration = ((exitH * 60 + exitM) - (entryH * 60 + entryM));
        record.duration = `${Math.floor(duration / 60)}h ${duration % 60}m`;
       
        alert('Exit marked successfully!');
        this.reset();
        displayAttendance();
    } else {
        alert('No active entry found for this student!');
    }
});

function displayAttendance(records = attendanceRecords) {
    const tbody = document.getElementById('attendanceTableBody');
    tbody.innerHTML = '';
   
    records.forEach(record => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${record.studentId}</td>
            <td>${record.entryTime}</td>
            <td>${record.exitTime || 'Ongoing'}</td>
            <td>${record.duration}</td>
            <td>${record.purpose}</td>
            <td>${record.notes || '-'}</td>
        `;
        tbody.appendChild(row);
    });
}

document.getElementById('searchAttendance').addEventListener('input', function(e) {
    const searchTerm = e.target.value.toLowerCase();
    const filtered = attendanceRecords.filter(record =>
        record.studentId.toLowerCase().includes(searchTerm)
    );
    displayAttendance(filtered);
});

// ==================== NAVIGATION LINKS ====================
document.querySelectorAll('[data-page]').forEach(link => {
    link.addEventListener('click', function(e) {
        if (this.id !== 'logoutBtn') {
            e.preventDefault();
            showContentPage(this.dataset.page);
        }
    });
});

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    color: #333;
}

/* PAGE VISIBILITY */
.page {
    display: none;
}

.page.active {
    display: block;
}

/* ==================== LOGIN PAGE ====================*/
.login-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 20px;
}

.login-box {
    background: white;
    padding: 40px;
    border-radius: 10px;
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
    width: 100%;
    max-width: 400px;
}

.login-box h1 {
    text-align: center;
    margin-bottom: 10px;
    color: #667eea;
    font-size: 2.5em;
}

.login-box h2 {
    text-align: center;
    margin-bottom: 30px;
    color: #555;
    font-size: 1.5em;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    margin-bottom: 8px;
    font-weight: 600;
    color: #333;
}

.form-group input,
.form-group select,
.form-group textarea {
    width: 100%;
    padding: 12px;
    border: 2px solid #e0e0e0;
    border-radius: 5px;
    font-size: 1em;
    transition: border-color 0.3s;
    font-family: inherit;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
    outline: none;
    border-color: #667eea;
    background-color: #f8f9ff;
}

.btn-login,
.btn-primary {
    width: 100%;
    padding: 12px;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1em;
    font-weight: 600;
    cursor: pointer;
    transition: transform 0.3s, box-shadow 0.3s;
}

.btn-login:hover,
.btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 20px rgba(102, 126, 234, 0.4);
}

.error-message {
    color: #d32f2f;
    margin-top: 15px;
    text-align: center;
    font-weight: 600;
    display: none;
}

.demo-credentials {
    margin-top: 20px;
    padding: 15px;
    background: #f0f4ff;
    border-radius: 5px;
    border-left: 4px solid #667eea;
}

.demo-credentials p {
    margin: 5px 0;
    font-size: 0.9em;
}

.demo-credentials code {
    background: white;
    padding: 2px 6px;
    border-radius: 3px;
    font-family: monospace;
    color: #667eea;
}

/* ==================== NAVBAR ====================*/
.navbar {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 15px 0;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    position: sticky;
    top: 0;
    z-index: 100;
}

.nav-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
}

.logo {
    color: white;
    font-size: 1.5em;
    white-space: nowrap;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 30px;
    flex-wrap: wrap;
}

.nav-links a {
    color: rgba(255, 255, 255, 0.8);
    text-decoration: none;
    font-weight: 500;
    cursor: pointer;
    transition: color 0.3s, padding-bottom 0.3s;
    padding-bottom: 5px;
    border-bottom: 3px solid transparent;
}

.nav-links a:hover,
.nav-links a.active {
    color: white;
    border-bottom-color: white;
}

.logout {
    background: rgba(255, 255, 255, 0.2);
    padding: 8px 16px !important;
    border-radius: 5px;
    transition: all 0.3s;
}

.logout:hover {
    background: rgba(255, 255, 255, 0.3);
}

/* ==================== CONTENT PAGES ====================*/
.content-page {
    display: none;
}

.content-page.active {
    display: block;
    animation: fadeIn 0.3s;
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.container {
    max-width: 1200px;
    margin: 40px auto;
    padding: 40px;
    background: white;
    border-radius: 10px;
    box-shadow: 0 5px 30px rgba(0, 0, 0, 0.2);
}

.container h2 {
    color: #667eea;
    margin-bottom: 30px;
    font-size: 2em;
    text-align: center;
}

.container h3 {
    color: #667eea;
    margin-bottom: 20px;
}

.container h4 {
    color: #667eea;
    margin-bottom: 15px;
}

/* ==================== SEARCH BAR ====================*/
.search-bar {
    display: flex;
    gap: 10px;
    margin-bottom: 25px;
}

.search-bar input {
    flex: 1;
    padding: 12px;
    border: 2px solid #e0e0e0;
    border-radius: 5px;
    font-size: 1em;
}

.search-bar input:focus {
    outline: none;
    border-color: #667eea;
}

/* ==================== TABS ====================*/
.tabs {
    display: flex;
    gap: 10px;
    margin-bottom: 30px;
    border-bottom: 2px solid #e0e0e0;
    flex-wrap: wrap;
}

.tab-btn {
    padding: 12px 25px;
    background: transparent;
    border: none;
    color: #666;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
    border-bottom: 3px solid transparent;
}

.tab-btn.active {
    color: #667eea;
    border-bottom-color: #667eea;
}

.tab-btn:hover {
    color: #667eea;
}

.tab-content {
    display: none;
}

.tab-content.active {
    display: block;
    animation: fadeIn 0.3s;
}

/* ==================== COURSES PAGE ====================*/
.courses-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 25px;
}

.course-card {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 25px;
    border-radius: 10px;
    color: white;
    box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
    transition: transform 0.3s, box-shadow 0.3s;
}

.course-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(102, 126, 234, 0.5);
}

.course-card h3 {
    margin-bottom: 15px;
    font-size: 1.3em;
    color: white;
}

.course-card p {
    font-size: 0.95em;
    line-height: 1.6;
    margin-bottom: 10px;
}

.course-info {
    background: rgba(255, 255, 255, 0.2);
    padding: 10px;
    border-radius: 5px;
    font-size: 0.9em;
}

/* ==================== TABLES ====================*/
.hod-table,
.student-table,
.attendance-table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

.hod-table thead,
.student-table thead,
.attendance-table thead {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
}

.hod-table th,
.student-table th,
.attendance-table th {
    padding: 15px;
    text-align: left;
    font-weight: 600;
}

.hod-table td,
.student-table td,
.attendance-table td {
    padding: 12px 15px;
    border-bottom: 1px solid #e0e0e0;
}

.hod-table tbody tr:hover,
.student-table tbody tr:hover,
.attendance-table tbody tr:hover {
    background: #f5f5f5;
}

/* ==================== FORMS ====================*/
.admission-form,
.student-form,
.entry-form {
    display: flex;
    flex-direction: column;
    gap: 20px;
    max-width: 600px;
}

.admission-form h3,
.student-form h3,
.entry-form h3 {
    margin-bottom: 10px;
}

textarea {
    resize: vertical;
    min-height: 100px;
}

/* ==================== STATUS CONTAINER ====================*/
.status-container {
    padding: 30px;
    background: #f0f4ff;
    border-radius: 10px;
}

#statusResult {
    margin-top: 20px;
    padding: 20px;
    background: white;
    border-radius: 5px;
    border-left: 4px solid #667eea;
}

.status-badge {
    display: inline-block;
    padding: 8px 16px;
    border-radius: 20px;
    font-weight: 600;
    margin-top: 10px;
}

.status-badge.approved {
    background: #4caf50;
    color: white;
}

.status-badge.pending {
    background: #ff9800;
    color: white;
}

.status-badge.rejected {
    background: #d32f2f;
    color: white;
}

.status-badge.confirmed {
    background: #4caf50;
    color: white;
}

/* ==================== SUCCESS MESSAGE ====================*/
.success-message {
    background: #4caf50;
    color: white;
    padding: 15px;
    border-radius: 5px;
    margin: 15px 0;
    text-align: center;
}

/* ==================== RESPONSIVE DESIGN ====================*/
@media (max-width: 1024px) {
    .nav-links {
        gap: 20px;
    }
    
    .container {
        margin: 30px;
        padding: 30px;
    }
}

@media (max-width: 768px) {
    .nav-container {
        flex-direction: column;
        gap: 15px;
    }
    
    .logo {
        font-size: 1.2em;
    }
    
    .nav-links {
        gap: 15px;
        width: 100%;
        justify-content: center;
    }
    
    .nav-links a {
        font-size: 0.9em;
    }
    
    .container {
        margin: 20px;
        padding: 20px;
    }
    
    .container h2 {
        font-size: 1.5em;
    }
    
    .courses-grid {
        grid-template-columns: 1fr;
    }
    
    .tabs {
        flex-direction: column;
    }
    
    .tab-btn {
        width: 100%;
        text-align: left;
        border-bottom: 3px solid #e0e0e0;
    }
    
    .tab-btn.active {
        border-bottom-color: #667eea;
        border-left: 4px solid #667eea;
    }
    
    table {
        font-size: 0.9em;
        overflow-x: auto;
    }
    
    table th,
    table td {
        padding: 10px;
    }
    
    .admission-form,
    .student-form,
    .entry-form {
        max-width: 100%;
    }
    
    .search-bar {
        flex-direction: column;
    }
    
    .search-bar button {
        width: 100%;
    }
}

@media (max-width: 480px) {
    .login-box {
        padding: 25px;
        margin: 20px;
    }
    
    .login-box h1 {
        font-size: 2em;
    }
    
    .logo {
        font-size: 1em;
    }
    
    .nav-links {
        flex-direction: column;
        gap: 10px;
    }
    
    .nav-links a {
        padding: 10px;
        text-align: center;
    }
    
    .container {
        margin: 15px;
        padding: 15px;
    }
    
    .container h2 {
        font-size: 1.3em;
        margin-bottom: 20px;
    }
    
    .container h3 {
        font-size: 1.1em;
    }
    
    .form-group input,
    .form-group select,
    .form-group textarea {
        padding: 10px;
        font-size: 16px;
    }
    
    .btn-login,
    .btn-primary {
        padding: 10px;
        font-size: 0.95em;
    }
    
    table {
        font-size: 0.8em;
    }
    
    table th,
    table td {
        padding: 8px;
    }
    
    .demo-credentials {
        font-size: 0.85em;
        padding: 12px;
    }
    
    .course-card {
        padding: 20px;
    }
    
    .course-card h3 {
        font-size: 1.1em;
    }
    
    .course-info {
        font-size: 0.85em;
    }
}

/* ==================== PRINT STYLES ====================*/
@media print {
    .navbar,
    .tabs,
    .btn-primary,
    .btn-login,
    .search-bar {
        display: none;
    }
    
    .container {
        box-shadow: none;
        padding: 0;
        margin: 0;
    }
    
    body {
        background: white;
    }
}

/* ==================== ACCESSIBILITY ====================*/
a:focus,
button:focus,
input:focus,
select:focus,
textarea:focus {
    outline: 2px solid #667eea;
    outline-offset: 2px;
}

/* ==================== SCROLLBAR STYLES ====================*/
::-webkit-scrollbar {
    width: 10px;
    height: 10px;
}

::-webkit-scrollbar-track {
    background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
    background: #667eea;
    border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
    background: #764ba2;
}
