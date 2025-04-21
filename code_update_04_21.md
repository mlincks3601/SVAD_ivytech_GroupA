// Group project module 6 code update 04-21-25
//PLEASE READ NOTES TO UNDERSTAND THIS PROGRAM
// Notes for loop usage: The statement "FOR i FROM 1 TO 10 DO" is a loop in pseudocode that is used to repeat a block of code 10 times, once for each value of i from 1 to 10. 
//Breakdown: FOR → This initiates a loop.
 //i → This is a loop variable (or counter), which keeps track of the number of iterations. 
//FROM 1 TO 10 = This means i starts at 1 and increases by 1 each time (by default), stopping at 10. 
//DO = Indicates the beginning of the loop's code block. 
//END FOR = Marks the end of the loop.
//Example Execution: 
//If i starts at 1, the loop executes the statements inside it, then i increases to 2, and the loop runs again. 
//This continues until i = 10, at which point the loop stops.
//-------------------------------------------------------------------------------------------- 

Tatiana Aguilar: Variables and 1st loop (Add notes for what each line of code is doing) 
BEGIN VARIABLES
// Define variables for employee input (info we need from the user to calculate)
// Employee variables
	 ID = INTEGER	//Unique employee identifier (Primary Key)
 	Name = STRING	//Employee’s full name (first and last name)
 	hourly_rate = FLOAT(x)	//Rate of pay per hour for the employee
 	hours_worked = FLOAT(x)	//Total # of hours worked in the pay period
//Below variables will be used at the end of the program
         	state_tax = FLOAT(5.6%)  	// Calculated as gross_pay * 0.056 (5.6%)
        	federal_tax = FLOAT (7.9%)  // Calculated as gross_pay * 0.079 (7.9%)
tax _deduction = FLOAT(x)	// Total tax withheld (state_tax + federal_tax)
        	net_pay = FLOAT(x)  // Take-home pay after deductions(gross_pay-tax_deduction)
END VARIABLES
//------------------------------------------------------------------------------------------ 
// Declare a list aka ARRAY of 10 employees that we will use in a loop later
 Employees = [10] AS ARRAY OF Employee	// Make an array of 10 Employee records
//-----------------------------------------------------------------------------------------
//Start a loop for user to input employee details and then use our variables from above to help calculate payroll
 
FOR i FROM 1 TO 10 DO
	PRINT "Enter Employee ID: "		//Prompt the user to enter the Employee’s ID
	INPUT Employees[i].ID	
	PRINT "Enter Employee Name: "	//Prompt the user to enter the Employee’s full name
	INPUT Employees[i].Name
	PRINT "Enter Hourly Rate: "		//Prompt user to enter hourly wage for employee
	INPUT Employees[i].hourly_rate
	PRINT "Enter hours_worked: "	//Prompt user to enter hours worked
	INPUT Employees[i].hours_worked
PRINT “------------------------------------------------------”
	PRINT “Thank you for your input, you're finished.”
END FOR

//NOTES: index i during each iteration of the loop.
  //NOTES: Employees[i] → This accesses the i-th employee in the Employees array (aka a list) during each loop iteration.


Andrew Duffield section below: Calculation loop 2 (Add notes for what each line of code is doing)
//Start the calculations loop
 FOR i FROM 1 TO 10 DO
  IF Employees[i].gross_pay = Employees[i].hourly_rate * Employees[i].hours_worked THEN
// state tax is 5.6% 
// Federal tax is 7.9%
// Total tax is 13.5%
    Employees[i].tax_deduction = Employees[i].gross_pay * .135
    Employees[i].net_pay = Employees[i].gross_pay - Employees[i].tax_deduction
// Print results from calculations
    PRINT “---------------RESULTS—-------------”
    PRINT "Employees[i].gross_pay"
    PRINT "Employees[i].tax_deduction"
    PRINT "Employees[i].net_pay"
  END IF
END FOR

// Display calculated payroll info to the user when finished
PRINT "Payroll Summary"
PRINT "-------------------------------------------"
Trey section: Final output loop from previous data collected and loops ran
//Start the last loop to display the above calculated info for every employee by calling in the loop variables from the 1st loop next to text

 FOR i FROM 1 TO 10 DO PRINT 
"Employee ID: ", Employees[i].ID PRINT 		//Print Employee ID
"Employee Name: ", Employees[i].Name PRINT	//Print Employee Name
 "Gross Pay: ", Employees[i].gross_payPRINT	//Print Gross Pay
"TaxDeduction:", Employees[i].tax_deduction PRINT "Net Pay: $", Employees[i].net_pay 
PRINT "-------------------------------------------"		//Print Tax deduction and Net Pay
 //end the loop 
END FOR
END

 //-----------------------------------------------------------------------------------------



















////////////////////////PYTHON CODE BELOW TAKEN FROM PSEUDOCODE ABOVE ////////////////////

 //employees will be an array for the loop to go through employees = []
for i in range(1, 11):

 Print (f"\nEnter details for Employee {i}:")
 ID = input("Enter Employee ID: ") 
Name = input("Enter Employee Name: ") 
hourly_rate = float(input("Enter Hourly Rate: ")) 
hours_worked = float(input("Enter Hours Worked: "))
payroll = hourly_rate * hours_worked
employees.append({
	"ID": ID,
	"Name": Name,
	"Hourly Rate": hourly_rate,
	"Hours Worked": hours_worked,
    "Payroll": payroll
})
print("\nPayroll Details:") for emp in employees: print(f"ID: {emp['ID']}, Name: {emp['Name']}, Payroll: ${emp['Payroll']:.2f}") 
////////////////////////////////////////////////////////////////////////////////////////////
	// After user has inputted the needed info, make sure to call [i] to continue to go through the loop, then calculate payroll
   //NOTES: [i] is used to reference a specific employee in the Employees array (aka a list) at index i during each iteration of the loop.
  //NOTES: Employees[i] → This accesses the i-th employee in the Employees array (aka a list) during each loop iteration.
 
    Employees[i].gross_pay = Employees[i].hourly_rate * Employees[i].hours_worked
    Employees[i].tax_deduction = Employees[i].gross_pay * 0.2 
 // Assume 20% tax
    Employees[i].net_pay = Employees[i].gross_pay - Employees[i].tax_deduction
//end the loop
 END FOR //-----------------------------------------------------------------------------------------
// Display calculated payroll info to the user when finished
PRINT "Payroll Summary"
PRINT
 "-------------------------------------------"
//Start the last loop to display the above calculated info for every employee by calling in the loop variables from the 1st loop next to text

 FOR i FROM 1 TO 10 DO PRINT 
"Employee ID: ", Employees[i].ID PRINT 
"Employee Name: ", Employees[i].Name PRINT
 "Gross Pay: ",Employees[i].gross_payPRINT
"TaxDeduction:", Employees[i].tax_deduction PRINT "Net Pay: $",
 Employees[i].net_pay PRINT 
"-------------------------------------------"
 //end the loop 
END FOR
END
 

