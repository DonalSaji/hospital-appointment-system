# 🏥 CareFlow Hospital - Appointment Management System

A responsive **Hospital Appointment Management System** built using **HTML, CSS, and Vanilla JavaScript**. The application allows users to book appointments, validates user input in real time, displays upcoming appointments, and includes embedded project documentation.

---

# 📌 Features

* ✅ Book new hospital appointments
* ✅ Real-time form validation
* ✅ Name validation (uppercase first letter, no numbers)
* ✅ Age validation (1–130 only)
* ✅ 10-digit mobile number validation
* ✅ Future appointment date validation
* ✅ Department selection validation
* ✅ Optional symptoms/notes field
* ✅ View all upcoming appointments
* ✅ Cancel individual appointments
* ✅ Clear all appointments
* ✅ Responsive UI
* ✅ Pure HTML, CSS, and JavaScript
* ✅ No external libraries or frameworks required

---

# 📂 Project Structure

```
CareFlow-Hospital/
│
├── index.html
└── README.md
```

Everything is contained in a single HTML file.

---

# 🚀 How to Run

1. Download or clone the project.

```
git clone <repository-url>
```

or simply download `index.html`.

2. Open `index.html` in any modern browser.

No installation or server is required.

---

# 🖥️ User Interface

The application contains two major sections:

## 1. Appointment System

Allows users to:

* Enter patient details
* Validate information
* Book appointments
* View appointments
* Delete appointments

## 2. README Panel

Displays project documentation directly inside the application.

---

# 📋 Appointment Form Fields

| Field            | Required | Validation                       |
| ---------------- | -------- | -------------------------------- |
| Full Name        | Yes      | Starts with uppercase, no digits |
| Age              | Yes      | Integer between 1 and 130        |
| Gender           | Yes      | Must be selected                 |
| Mobile Number    | Yes      | Exactly 10 digits                |
| Appointment Date | Yes      | Cannot be in the past            |
| Department       | Yes      | Must be selected                 |
| Symptoms         | No       | Optional text                    |

---

# ✅ Validation Rules

## Name

Rules:

* Cannot be empty
* Cannot contain numbers
* Must start with an uppercase letter
* Allows:

  * Letters
  * Spaces
  * Hyphens (-)
  * Apostrophes (')

Example:

```
John Doe ✅
john Doe ❌
John123 ❌
```

Validation Regex:

```javascript
/^[A-Z][a-zA-Z\s\-']*$/
```

---

## Age

Rules:

* Required
* Whole number only
* Minimum: 1
* Maximum: 130

Examples:

```
45 ✅
0 ❌
-5 ❌
131 ❌
```

---

## Mobile Number

Rules:

* Exactly 10 digits
* Numbers only

Examples:

```
9876543210 ✅
98765 ❌
98765abcd1 ❌
```

Regex:

```javascript
/^\d{10}$/
```

---

## Appointment Date

Rules:

* Required
* Cannot be before today's date

Example:

```
Today ✅
Future date ✅
Yesterday ❌
```

---

## Department

User must choose one of:

* ❤️ Cardiology
* 🧠 Neurology
* 👶 Pediatrics
* 🦴 Orthopedics
* 🏥 General Medicine

---

# 📊 Appointment Object Structure

Every appointment is stored as:

```javascript
{
    id: "timestamp-random",
    name: "John Doe",
    age: 35,
    gender: "Male",
    phone: "9876543210",
    date: "2026-06-20",
    department: "Cardiology",
    symptoms: "Chest discomfort"
}
```

Appointments are stored inside:

```javascript
let appointments = [];
```

---

# ⚙️ Core JavaScript Functions

## generateId()

Creates a unique ID using timestamp and random characters.

---

## validateName()

Checks:

* Empty input
* Digits
* Uppercase first letter
* Allowed characters

Returns:

```javascript
{
    valid: true,
    message: ""
}
```

or

```javascript
{
    valid: false,
    message: "Error message"
}
```

---

## validateAge()

Ensures:

* Integer value
* Between 1 and 130

---

## validateGender()

Checks that a gender has been selected.

---

## validatePhone()

Ensures:

* Exactly 10 digits
* Numeric only

---

## validateAppointmentDate()

Checks that the selected date is today or later.

---

## validateDepartment()

Ensures a department is selected.

---

## validateForm()

Runs every validation function before allowing submission.

Returns:

```
true
```

or

```
false
```

---

## addAppointmentFromForm()

Creates a new appointment object and pushes it into:

```javascript
appointments
```

Then:

* Renders appointments
* Resets the form
* Displays success message

---

## renderAppointments()

Displays appointments sorted by date.

Each card shows:

* Name
* Gender
* Age
* Phone
* Appointment Date
* Department
* Symptoms (if available)

---

## deleteAppointmentById()

Removes one appointment from the array.

---

## clearAllAppointments()

Deletes all appointments after confirmation.

---

## resetFormFields()

Clears:

* Inputs
* Errors
* Validation styles

---

# 🎯 Event Listeners

## Form Submit

```javascript
form.addEventListener("submit")
```

Prevents page reload and books appointment.

---

## Phone Input

Automatically:

* Removes non-numeric characters
* Limits length to 10 digits

---

## Age Change

Automatically clamps:

```
Minimum = 1

Maximum = 130
```

---

## Name Blur

Runs validation when leaving the field.

---

## Phone Blur

Runs phone validation immediately.

---

## Reset Button

Clears the form.

---

## Clear All Button

Deletes every appointment after confirmation.

---

# 🎨 Styling Features

* Gradient background
* Rounded cards
* Responsive layout
* Animated tab switching
* Success notifications
* Error highlighting
* Clean typography
* Soft shadows

---

# 📱 Responsive Design

Optimized for:

* Desktop
* Tablet
* Mobile devices

Uses:

* Flexbox
* Media queries

---

# 📚 Technologies Used

* HTML5
* CSS3
* JavaScript (ES6)

No external frameworks.

---

# 🔮 Possible Future Improvements

* LocalStorage persistence
* Backend integration
* Database support
* Authentication
* Doctor scheduling
* Email notifications
* SMS reminders
* Appointment editing
* Search functionality
* Filtering by department
* Calendar view
* Dark mode

---

# 📄 License

MIT License

Free to use for educational and personal projects.

---

# ❤️ Developed For

**CareFlow Hospital**

Smart Appointment Booking and Management System

*Version 1.0*
