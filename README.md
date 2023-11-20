// Employee class
public class Employee {
    private String firstName;
    private String lastName;
    private int employeeID;
    private double salary;

    // Constructor
    public Employee() {
        this.salary = 0.0;
    }

    // Setters and getters
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    public String getFirstName() {
        return firstName;
    }

    public void setLastName(String lastName) {
        this.lastName = lastName;
    }

    public String getLastName() {
        return lastName;
    }

    public void setEmployeeID(int employeeID) {
        this.employeeID = employeeID;
    }

    public int getEmployeeID() {
        return employeeID;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }

    // Method to print employee summary
    public String toString() {
        return "Employee ID: " + employeeID + "\nName: " + firstName + " " + lastName + "\nSalary: $" + salary;
    }
}
// Manager class (inherits from Employee)
public class Manager extends Employee {
    private String department;

    // Constructor
    public Manager() {
        // Call the superclass constructor
        super();
    }

    // Getter and setter for department
    public String getDepartment() {
        return department;
    }

    public void setDepartment(String department) {
        this.department = department;
    }

    // Overridden method to print both superclass and subclass attributes
    @Override
    public String toString() {
        // Call the superclass toString method to print superclass attributes
        return super.toString() + "\nDepartment: " + department;
    }
}
import java.util.Scanner;

// TestEmployee class
public class Test {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input for Employee
        System.out.println("Enter Employee Information:");
        System.out.print("First Name: ");
        String empFirstName = scanner.nextLine();

        System.out.print("Last Name: ");
        String empLastName = scanner.nextLine();

        System.out.print("Employee ID: ");
        int empEmployeeID = scanner.nextInt();

        System.out.print("Salary: ");
        double empSalary = scanner.nextDouble();

        // Creating an Employee object
        Employee employee = new Employee();
        employee.setFirstName(empFirstName);
        employee.setLastName(empLastName);
        employee.setEmployeeID(empEmployeeID);
        employee.setSalary(empSalary);

        System.out.println("\nEmployee Summary:");
        System.out.println(employee);

        // Input for Manager
        scanner.nextLine(); // Consume the newline character left by nextDouble()

        System.out.println("\nEnter Manager Information:");
        System.out.print("First Name: ");
        String mgrFirstName = scanner.nextLine();

        System.out.print("Last Name: ");
        String mgrLastName = scanner.nextLine();

        System.out.print("Employee ID: ");
        int mgrEmployeeID = scanner.nextInt();

        System.out.print("Salary: ");
        double mgrSalary = scanner.nextDouble();

        scanner.nextLine(); // Consume the newline character left by nextDouble()

        System.out.print("Department: ");
        String mgrDepartment = scanner.nextLine();

        // Creating a Manager object
        Manager manager = new Manager();
        manager.setFirstName(mgrFirstName);
        manager.setLastName(mgrLastName);
        manager.setEmployeeID(mgrEmployeeID);
        manager.setSalary(mgrSalary);
        manager.setDepartment(mgrDepartment);

        System.out.println("\nManager Summary:");
        System.out.println(manager);

        // Close the scanner
        scanner.close();
    }
}
