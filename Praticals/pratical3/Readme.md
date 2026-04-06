#  Automated Grading System

##  Class Diagram — System Blueprint
![alt text](<Screenshot from 2026-04-06 23-03-57.png>)
###  Key Question:
What are the components of the system and how are they related?

Think of this as a **blueprint of a house**  — it shows:
- Rooms → Classes  
- Furniture → Attributes & Methods  
- Doors/Connections → Relationships  

---

###  User (Base Class)
All system members inherit from `User`.

**Attributes:**
- name
- email
- password

**Capabilities:**
- login()
- logout()

---

###  Types of Users

####  Student
- Submit code
- View grades and feedback
- Resubmit multiple times

####  Professor
- Create assignments
- Review plagiarism
- Approve final grades

####  Admin
- Manage system rules
- Generate audit logs

---

###  Assignment
Created by Professor.

**Attributes:**
- title
- deadline
- grading criteria

**Rules:**
- Late submissions →  Automatically rejected
- On-time submissions →  Processed

---

###  Submission
Created by Student.

**Attributes:**
- file (e.g., `bubbleSort.py`)
- attempt number
- timestamp

**Features:**
- Multiple resubmissions allowed
- Each attempt is tracked

---

###  Submission Processing

Each submission generates:

####  Grade
- score
- feedback
- pass/fail status

####  Plagiarism Report
- similarity percentage
- flagged if too high
- sent to professor if suspicious

---

###  Workflow Summary

1. Professor creates assignment  
2. Student submits code  
3. System checks:
   - Deadline
   - Plagiarism
   - Auto-grading  
4. Grade generated  
5. Professor approves  
6. Synced to LMS  
7. Student views results  

---

##  Object Diagram — Real System Snapshot
![alt text](<Screenshot from 2026-04-06 23-04-45.png>)
###  Key Question:
What does the system look like at a specific moment?

Think of this as a **photo of the house with real people inside** 

---

###  Professor Instance
- Name: **Dr. Tshering**
- Department: SWE
- Status: Logged in

**Action:**
- Creates assignment:
  - Title: *Sorting Algorithm*
  - Deadline: *15 Oct 2024, 23:59*

---

###  Student Instance
- Name: **Karma Wangchuk**
- Year: 3

**Action:**
- Logs into system
- Views assignment
- Submits file:
  - `bubbleSort.py`
  - Time: *14 Oct, 18:30*
  - Attempt: 2nd

---

###  System Processing

####  Deadline Check
- Submission time:  Valid

####  Plagiarism Check
- Similarity: **12.5%**
- Result:  Acceptable

####  Auto-Grading
- Code executed against test cases

---

###  Grade Result

- **Score:** 85 / 100  
- **Feedback:** "Good logic, make your loops efficient"  
- **Status:**  Passed  

---

###  Final Steps

- Grade stored in system  
- Synced to LMS  
- Audit record created  

---

###  Student View

Karma logs in and sees:
- Score
- Feedback
- Code output

---

##  Summary

| Diagram Type   | Meaning |
|----------------|--------|
| Class Diagram  | Blueprint (structure of system) |
| Object Diagram | Snapshot (real instance at one time) |

---

 **In Simple Terms:**
- Class Diagram = Plan of the system  
- Object Diagram = Real example happening in the system  