Download Link: https://assignmentchef.com/product/solved-bbm-104-assignment-3-pizza-delivery-system
<br>
The aim of this experiment is to introduce you object-oriented programming and design with Java. You will learn the structure of a class, how classes interact, inheritance and polymorphism and basic input-output operations in Java. There will be two main parts to this assignment. One part consists of creating the system’s input-output interface and implementing the logic for this interaction. The other part is defining (and implementing) the persistence backend (i.e. how we store and retrieve the information our system uses). You should also use decorator design pattern in first part of the experiment. Your homework will take commands from an input file then it will print the results of these commands to an output file. You should use Data Access Objects (DAO) to manage your data.




<strong>Decorator Pattern: </strong>

The Java language provides the keyword extends for subclassing a class. Those with enough knowledge of object-oriented programming know how powerful subclassing, or extending a class. By extending a class, you can change its behavior. The Decorator Pattern is used for adding additional functionality to a particular object as opposed to a class of objects. With the Decorator Pattern, you can add functionality to a single object and leave others like it unmodified. Any calls that the decorator gets, it relays to the object that it contains, and adds its own functionality along the way, either before or after the call. This gives you a lot of flexibility since you can change what the decorator does at runtime, as opposed to having the change be static and determined at compile time by subclassing. Since a Decorator complies with the interface that the object that it contains, the Decorator is indistinguishable from the object that it contains. That is, a Decorator is a concrete instance of the abstract class, and thus is indistinguishable from any other concrete instance, including other decorators. This can be used to great advantage, as you can recursively nest decorators without any other objects being able to tell the difference, allowing a near infinite amount of customization.

Decorators add the ability to dynamically alter the behavior of an object because a decorator can be added or removed from an object without the client realizing that anything changed. It is a good idea to use a Decorator in a situation where you want to change the behavior of an object repeatedly (by adding and subtracting functionality) during runtime.




The dynamic behavior modification capability also means that decorators are useful for adapting objects to new situations without re-writing the original object’s code.




The code for a decorator would something like this:




<strong>void operation { </strong>

<strong>// any pre-processing code goes here </strong> <strong>component.operation() // delegate to the decor </strong>

<strong>// any post-processing code goes here </strong>

<strong>} </strong>




Note that the decorator can opt to not delegate to the decor, if, for instance, some condition was not met.

<strong> </strong>

<strong>Data Access Object </strong>

The Data Access Object (DAO) layer is an essential part of good application architecture. Business applications almost always need access to data from databases or data files. The Data Access Object design pattern provides a technique for separating object persistence (stored data) and data access logic from any particular persistence mechanism (writing to files or accessing a real database). There are clear benefits to this approach from an architectural perspective. The Data Access Object approach provides flexibility to change an application’s persistence mechanism over time without the need to re-engineer application logic that interacts with the Data Access Object tier. The Data Access Object design pattern also provides a simple, consistent API for data access that does not require knowledge of sub mechanism. A typical Data Access Object interface is shown below. (This is an example, your interface should look like different )

<strong>public interface CustomerDAO { public void add(Customer customer);  </strong>

<strong> </strong>

<strong>public void update(int id, Customer customer); </strong>

<strong> </strong>

<strong>public void delete(int id);  </strong>

<strong> </strong>

<strong>public Customer[] getAll(); </strong>

<strong> </strong>

<strong>……………..  </strong>

<strong>}  </strong>

<strong>Experiment: </strong>

In this experiment, you are expected to develop a simple Pizza <em>Restaurant System. </em>Your application should support the following features:




<u>New Customer:</u>

Create a new customer. Attributes of a customer are:

<ul>

 <li>Customer id (Unique)</li>

 <li>Customer Surname</li>

 <li>Customer Name</li>

 <li>Customer Address</li>

 <li>Customer Phone Number</li>

</ul>




<u>Remove Customer:</u>

Remove a customer from the database by using its identification number.




<u>List Customers:</u>

Print the list of customers ordered by name.

<u>Create Order</u><u>:</u>

Create a new order for an existing customer and append it to order data file. Each order has a unique order id.




<u>Add Pizza:</u>

Add a pizza to a given order with given toppings. A pizza can include 3 toppings at most. There are 2 types of pizzas. These are:

<ul>

 <li>American Pan Pizza 5 $</li>

 <li>Neapolitan Pizza 10 $</li>

</ul>




A pizza can include 3 toppings at most. There are 4 types of toppings.              Soudjouk 3 $

<ul>

 <li>Salami 3 $</li>

 <li>Pepper 1 $</li>

 <li>Onion 2 $</li>

</ul>




<u>Add Drink:</u>

Add a soft drink to an order (2$). There is the only cola in this restaurant.

<u>Pay Check</u>

Calculate the paycheck of an order. List all pizzas and drinks in the order then calculate the total cost of an order.




Customer information and order information will be stored in text files (lists or arrays will also be accepted). The format of the files for persistence are shown below. Names of these files will be taken as arguments in your application. You can reach sample customer file, order data file and sample input-output files from the page of piazza site of the experiment.

<strong> </strong>

<h1>Customer Data File Format</h1>




&lt;customerID&gt; &lt;customerName&gt; &lt;customerSurname&gt; &lt;phone number&gt; Address: &lt;address&gt;

Customer name, surname, and phone number consist of one string. The address can be made up of one or more strings. Entries in customer data file should be ordered by ID.

<strong> </strong>

<h1>Order Data File Format</h1>




Order: &lt;orderID&gt; &lt;customerID&gt;

&lt;pizza type&gt; (Neapolitan or American Pan) &lt;topping [1-3]&gt; (There can be 3 toppings at most)

&lt;drink&gt;




Entries in order data file should be ordered by ID. After add and remove operations, all changes should be reflected data files.

<strong> </strong>

<strong>Input File Format (</strong>Note: Number of topping can vary from 1 to 3.)




<ul>

 <li>AddCustomer &lt;cutomerID&gt; &lt;name&gt; &lt;surname&gt; &lt;phone number&gt; &lt;address&gt;</li>

</ul>




<ul>

 <li>RemoveCustomer &lt;cutomer ID&gt;</li>

</ul>




<ul>

 <li>CreateOrder &lt;OrderID&gt; &lt;CustomerID&gt;</li>

</ul>




<ul>

 <li>RemoveOrder &lt;OrderID&gt;</li>

</ul>




<ul>

 <li>AddPizza &lt;OrderID&gt; &lt;pizza type&gt; &lt;topping&gt;</li>

</ul>




<ul>

 <li>AddDrink &lt;OrderID&gt;</li>

</ul>




<ul>

 <li>PayCheck &lt;OrderID&gt;</li>

</ul>




<ul>

 <li>ListCustomers</li>

</ul>

<strong> </strong>

<h1>Output File Format</h1>




<ul>

 <li>Customer &lt;CustomerID &gt; &lt;name&gt; added</li>

</ul>




<ul>

 <li>Customer &lt;CustomerID&gt; &lt;name&gt; removed</li>

</ul>




<ul>

 <li>Order &lt;OrderID&gt; created</li>

</ul>




<ul>

 <li>&lt;pizza type&gt; pizza added to order &lt;OrderID&gt;</li>

</ul>




<ul>

 <li>Drink added to order &lt;OrderID&gt;</li>

</ul>




<ul>

 <li>PayCheck for order &lt;OrderID&gt;

  <ul>

   <li>&lt;pizza type&gt; &lt;topping[1-4]&gt; &lt;cost&gt; $</li>

  </ul></li>

</ul>




<ul>

 <li>&lt;pizza type&gt; &lt;topping[1-4]&gt; &lt;cost &gt; $</li>

</ul>




<ul>

 <li>SoftDrink &lt;cost&gt; $</li>

</ul>




<ul>

 <li>Total: &lt;total_cost&gt; $</li>

</ul>

<strong> </strong>

<strong>Implementation Details: </strong>

You should use decorator pattern <strong>(20points) </strong>for add topping mechanism. Add topping code should look like this:




<strong> </strong>

<strong>pizza.addTopping(new Salami(new HotPepper(new Soudjuk())); </strong> This a pizza with salami, hot pepper, and soudjouk.

<strong> </strong>

<strong>pizza.printToppings(); </strong>Output of this method call should be <strong><em>Soudjuk HotPepper Salami </em></strong>

<strong> </strong>

<strong>pizza.cost(); </strong>Output of this method call should return the costs of pizza and its toppings




The advantage of using data access objects is the relatively simple and rigorous separation between two important parts of an application which can and should know almost nothing of each other, and which can be expected to evolve frequently and independently. Changing business logic can rely on the same DAO interface, while changes to persistence logic do not affect DAO clients as long as the interface remains correctly implemented. In the specific context of the Java programming language, Data Access Objects as a design concept can be implemented in a number of ways. This can range from a fairly simple interface that separates the data access parts from the application logic to frameworks and commercial products. DAO coding paradigms can require some skill.

For our system, we will store the data inside the individual files (one for order and one for customer class), and use Data Access Objects (DAO) to manage them <strong>(10points)</strong>. Each DAO will have the basic operations to manage the data (defined by the DAO interface provided with the assignment). So basically what you need to do is implementing following abstract methods:<strong><em>  </em></strong>

<strong><em> </em></strong>

<strong><em>Object </em>getByID(int ID) </strong>// read a single entry from the file  <strong><em>Object </em>deleteByID(int ID) </strong>// delete a single entry from file  <strong><em>void </em>add(Object object) </strong>// add or update an entry  <strong><em>void </em>update(Object object) </strong>// add or update an entry

<strong><em>ArrayList </em>getALL() </strong>// get all entries

You could add additional methods to your DAOs and you can also make changes in DAO interface. Your application should terminate and save the files automatically when finish to reading input file.








