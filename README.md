Download Link: https://assignmentchef.com/product/solved-csci3110-project-2-gasoline-pump
<br>
File(s) to be submitted: gaspump.h, gaspump.cpp, proj2.cpp, makefileObjectives: 1) Use classes; 2) Split interface and implementation into files; 3) Use an array of pointers to objects;4) Instantiate objects using parameterized constructors; 5) Use objects in a client/driver function.Project description:In this assignment you will create a class representing a gasoline pump. The pump will maintain a running total of theamount of fuel dispensed and revenues collected. The driver program will simulate fuel demand for a number ofvehicles.Requirements:1. Your program must be split into three files, the requirements for which are specified below:a) The class interface, or declaration, file Must be named gaspump.h Must contain #include guards for GASPUMP_H Class must be named GasPump Will have these private membersi. A string containing the type of gas the gas pump holdsii. A double representing the amount of fuel on hand (in gallons)iii. A double representing the fuel pump’s capacity (in gallons)iv. A double that holds the price per gallonv. A double representing the total amount of fuel dispensed (all purchases)vi. A double that stores the total amount of money collected (all purchases)vii. A bool that indicates whether the next customer should be turned away as fuel is replenishedviii. A void function that replenishes the fuel pump’s tank when it runs out of fuel Must have these public membersi. A single constructor with three parameters (in order): a standard string (std::string) that holds thetype of gasoline in the pump, a double representing the maximum capacity of the tank in gallons,and a double for the price per gallon.ii. An inline accessor function that returns a standard string for the pump’s fuel typeiii. An inline accessor function that returns a double for the pump’s fuel price per galloniv. An inline accessor function that returns a double for the pump’s fuel on handv. An inline accessor function that returns the total amount of fuel dispensed (all purchases)vi. An inline accessor function that returns the total amount of revenue collected (all purchases)vii. A void function dispenseFuel, that controls the fueling of vehiclesb) A class implementation, or definition, file Must be named gaspump.cpp Will have the implementation for the following functionsi. Constructor – This function has three parameters that map directly to data members; it should alsoinitialize the fuel quantity on hand to the maximum tank capacity (i.e., start at full capacity)ii. replenish – This function resets the fuel tank level to the maximum capacity.iii. dispenseFuel – This function is the heart of the class, and controls the fueling of a single vehicle. Itaccepts a pointer to a double (to the fueling outcome array), and a double that indicates thepurchase amount desired by the vehicle. It uses the pointer to set the values in the 2-element array:actual purchase amount (element 0) and actual quantity of fuel dispensed to the vehicle (element1). The amount of fuel a vehicle gets is one of the following: 1) the full amount requested by thevehicle (if it is available); or 2) the remaining amount in the tank (if the tank has less than therequested amount); or 3) Zero, if the vehicle is being turned away so the tank can be replenished.It does this byA. Converting the purchase amount to gallons of fuel.B. Ensuring that it only dispenses fuel if the tank is not being replenished (in which case thecustomer is turned away)C. Ensuring that the pump dispenses no more than the amount of fuel on hand. If the vehicle’sfuel demand exceeds the amount of fuel on hand, the vehicle gets all of the fuel on hand,and the next customer is turned away as the fuel is replenished.D. Keeping track of fuel total dispensedE. Keeping track of total revenue collectedc) A driver, or client, file Must be named proj2.cpp Reads input data from a file named gas.txt, that will be formatted as follows:o The first line is a random number seed (integer)o The second line is the number of vehicles to be run through the simulationo The 3rd through 5th lines represent individual gas pumps (one per line), composed of: Gasoline type (string) Tank capacity (double) Cost per gallon (double) Percentage of vehicles requiring this type of gas (double between 0 and 1) – Note: this fieldmust sum to 1 across the three gas pump lines Example line: Unleaded 100.0 2.00 0. 5 – Note that in this case, the percentage values in theother two lines must sum to 0.5 Instantiates an array of pointers to 3 GasPump objects, using data read from the input file. Declares a 2-element double array that is passed to the dispenseFuel function to get the outcome of fueling Sets the random number generator seed [using srand()] to the value read from the input file: Creates a loop for the number of vehicles to be simulated – one vehicle per iteration:o Determine which pump the vehicle will fuel from, by drawing a random number between 0 and 1,[use ((double) rand() + 1) / RAND_MAX to prevent a divide by zero error] and comparing it againstthe “stacked” percentages read from the file, to select the pump pointer array index. Example:Index 1.00 Fuel Type 1 Percentage (line 3): 0.30.71 Fuel Type 2 Percentage (line 4): 0.6

0.1Random draw 0.64 resultsin selection of index 1 forthe fuel type2 Fuel Type 3 Percentage (line 5): 0.10.0o Determine the amount of money the vehicle wants to spend on fuel Select random values from $30 to $55 in increments of $5, by drawing a random integerwith rand, modding it by 6, multiplying the result by 5, and adding 30 to it.o Use the pointer at the index to invoke the dispenseFuel function in the appropriate pumpo Output a single line containing the following (in order): Vehicle #, fuel type, price per gallon, desired purchase amount, actual purchase amount,gallons dispensed, gallons remaining Upon exiting the loop, output the total fuel dispensed and total revenue collected for each pump (in order)2. Sample Output (with explanation) – This is the output from running with the provided sample input file. The formatof your output MUST MATCH EXACTLY the output in this specification. DO NOT add any verbiage or information beyondwhat is called for.3. Test your program – Use different random number seeds, numbers of vehicles, prices, and tank capacities.4. Code comments – Add the following comments to your code: A section at the top of the source file(s) with the following identifying information:Your NameCSCI 3110-00X (your section #)Project #XDue: mm/dd/yy Below your name add comments in each file that gives an overview of the program or class. Place a one or two line comment above each function that summarizes the workings of the function.

5. RubricRequirement Points Offmain: Input filename -5main: Data correctly read from file -10main: GasPump pointer array declaration and initialization -10main: Declaration of fueling outcome array -5main: Random number seeding -5main: Fuel pump selection -5main: Fuel purchase amount selection -5main: Invocation of functions through object -5main: All required output per vehicle -10main: Required final totals output -5GasPump: Constructor properly initializes objects -5GasPump: Accessors declared/defined per the specifications -5GasPump:dispenseFuel: Dispenses fuel and updates fueling outcome and totals -10GasPump:dispenseFuel: Sets up and invokes tank replenishment -10GasPump: Maintains totals for fuel dispensed and revenue collected -5 (each)GasPump:replenish: Correctly replenishes pump -10general: Does not compile (on ranger using Linux g++ compiler, and the provided makefile) -25general: Runtime crash -25general: Other TBD