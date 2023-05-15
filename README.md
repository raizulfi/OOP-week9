# # Class Design and Implementation Case
1.(a) By making use of an example from the above scenario, distinguish between a class and an instantiation of a class. (3 points)
>> A class acts as a template, defining the shared characteristics and behaviors.
>
> > An instantiation represents a specific object created based on that class, with its own distinct attribute values. 
>  
>  >The class provides a standardized structure, and the instantiation represents a tangible instance of that structure with its unique properties.
>  
>  In the context of the examples above, we can consider a mangager class being defined. class will form attributes like their name, employee ID, job title, and base salary. an instantiation of the manger class named  Raihan Zulfi, Raihan Zulfi is a manager within the company. As an instantiation of the manager class, he would have his own unique values for the attributes defined in the class.

The different modules in the program each open a graphical user interface (GUI). Each GUI has a similar design but contains differences specific to each module.

(b) By giving two examples, explain how the principles of inheritance can be incorporated into the design of this administration program. (4 points)
 
> 1) A Manager class can be created, inheriting from the Employee class. The Employee class contains attributes and methods shared by all employees, such as name, address, and salary. By inheriting from the Employee class, the Manager class inherits these common attributes and methods. Additionally, the Manager class can add specific attributes and methods tailored to managers.

> 2) A CorporateSalesPerson class can be implemented, inheriting from the SalesPerson class. The SalesPerson class encompasses attributes and methods common to all salespeople, such as ID and sales history. By inheriting from the SalesPerson class, the CorporateSalesPerson class inherits these shared attributes and methods.

(c) Describe how the use of libraries can facilitate the development of programs like this company’s administration program. (3 points)

>Incorporating libraries into the administration program can enhance efficiency and productivity. Rather than writing custom code for each module, a GUI library can be employed to streamline the creation of various modules. Utilizing libraries can also offer a cost-efficient approach for companies, as it removes the requirement for extra expenses on development time or external resources.

Question 2
The company employs several sales personnel to sell its products to different retailers. Each branch of the company keeps track of its own sales with a suite of programs that include the two classes SalesPerson and Sales.

    public class SalesPerson {
    
    	// each object contains details of one salesperson
    
    	private String id;
    
    	private Sales[] salesHistory; // details of the different sales
    
    	private int count = 0; // number of sales made
    
    
    
    	//constructor for a new salesperson
    
    	public SalesPerson(String id){
    
    	// code missing
    
    	}
    
     
    
    	// constructor for a salesperson transferred (together with their sales details) from another branch
    
    	public SalesPerson(String id, Sales[] s, int c){
    
    	// code missing
    
    	}
    
     
    
    	public int getCount(){return count;}
    
    	public String getId() {return id;}
    
    	public void setSalesHistory(Sales s){
    
    	salesHistory[count] = s;
    
    	count = count +1;
    
    	}
    
     
    
    	public double calcTotalSales(){
    
    	// calculates total sales for the salesperson
    
    	// code missing
    
    	}
    
     
    
    	public Sales largestSale(){
    
    	// calculates the sale with the largest value
    
    	// code missing
    
    	}
    
    }



Each instance variable is initialized when a SalesPerson object is instantiated.

(a) Complete the constructor public SalesPerson(String id), from the SalesPerson class. (2 points)

    public SalesPerson(String id) {
        id = this.id;
        this.salesHistory = new Sales[100];
    }

(b) Explain why accessor methods are necessary for the SalesPerson class. (3 points)

In the SalesPerson class, accessor methods play a crucial role due to the private nature of the instance variables. As private variables cannot be directly accessed from external classes, accessor methods like getCount() and getSalesHistory() serve as a means to indirectly retrieve the values of these variables. By using accessor methods, the principle of encapsulation is preserved, allowing controlled access to the private variables while maintaining data integrity.


    public class Sales {
    
    	// each object contains details of one sale
    
    	private String itemId;     // id of the item
    	private double value;      // the price of one item
    	private int quantity;      // the number of the items sold
    
    	// constructor missing
    
    	public double getValue() {
            return value;
        }
    
    	public int getQuantity() {
            return quantity;
        }
    }

(c) (i) Construct unified modelling language (UML) diagrams to clearly show the relationship between the SalesPerson and Sales classes.

Note: There is no need to include mutator or accessor methods or a constructor. (4 points)

![image](https://github.com/raizulfi/OOP-week9/assets/114371959/329bb340-0ad9-4075-b049-b1e287defcff)

(c) (ii) Outline a negative effect that a future change in the design of the Sales object might have on this suite of programs. (2 points)

>   A potential drawback of making future changes to the Sales object's design is the risk of breaking dependent code within the program suite. For instance, if modifications are made to the Sales object, such as adding new attributes or methods, it could impact the functionality of code that directly interacts with the Sales object. Specifically, operations like the setSalesHistory() method in the SalesPerson class may no longer function correctly. Consequently, rectifying such issues could necessitate substantial program modifications.

(d) State the output after running this code. (4 points)
> 102
> 2  
> 2550.40  
> 5000.00

(h) Suggest changes that must be made to the SalesPerson class and/or the Sales class to allow these calculations to be made. (3 points)
> To enable the required calculations, certain adjustments are
> necessary. These include introducing a new variable to track the
> timing of sales and implementing a method capable of computing sales
> based on the time of each month.
> 
(i) Discuss the use of polymorphism that occurs in this suite of programs. (3 points)
>Polymorphism occurs in this suite of programs in the form of method overriding. For example, the SalesPerson class has a method called calcTotalSales() that calculates the total sales for a salesperson, while the Payroll class also has a method called calcTotalSales() that calculates the total sales for a salesperson, but for the purpose of calculating their salary. The two methods have different implementations, but share the same name and signature, allowing them to be used interchangeably in the program.
