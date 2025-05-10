-- Employees Table
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FullName VARCHAR(100),
    Age INT,
    Gender VARCHAR(10),
    Department VARCHAR(50),
    Role VARCHAR(50),
    HireDate DATE,
    TerminationDate DATE,
    Salary DECIMAL(10, 2)
);

-- Attendance Table
CREATE TABLE Attendance (
    EmployeeID INT,
    AttendanceDate DATE,
    Status VARCHAR(10),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);

-- Performance Table
CREATE TABLE Performance (
    EmployeeID INT,
    ReviewDate DATE,
    Score INT,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);

-- Training Table
CREATE TABLE Training (
    EmployeeID INT,
    CourseName VARCHAR(100),
    CompletionStatus VARCHAR(20),
    CompletionDate DATE,
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);

-- Attrition Table
CREATE TABLE Attrition (
    EmployeeID INT,
    ExitDate DATE,
    Reason VARCHAR(100),
    FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
