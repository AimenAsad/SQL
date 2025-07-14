
## 📊 ERD (Entity-Relationship Diagram) Design

The ERD forms the backbone of this database project, illustrating the relationships between various entities in the airplane and owner management system.

* **Owner (Superclass):** Considered a superclass, disjointly dividing into `Corporate` and `Person` subclasses, as an owner can be either.
* **Person (Subclass):** Further subdivided into `Employee` and `Pilot`, inheriting features from the `Person` class. Necessary attributes are identified for each.
* **Relationships:**
    * `Owns`: Links the `Owner` superclass to `Airplane` with a `purchase_date` attribute.
    * `Maintains`: Establishes a one-to-many relationship between `Employee` and `Service Record`.
    * `Plane Service`: Indicates that an `Airplane` can undergo maintenance multiple times.
    * `Airplane`, `Plane Type`, and `Hangar` information is stored in separate, linked classes.
* Primary and foreign keys are used throughout to establish robust links between all classes.

---

## 🔍 SQL Queries

**QUERY 01** - ERD Explanation
Description: This section provides a detailed textual explanation of the ERD diagram, outlining the superclass/subclass relationships, entity attributes, and the rationale behind the linkages (as described in the ERD section above).
![query1](images/query1.png)

**QUERY 02** - Table Content Display
Description: Displays the content saved in various tables, demonstrating basic SELECT * FROM TableName operations.
![query2](images/query2.png)
![query2](images/query2.0.png)

**QUERY 03** - Planes Never Maintained
Description: Uses a SQL nested query to find the registration numbers of airplanes that have never undergone maintenance.
![query3](images/query3.png)

**QUERY 04** - Corporate Owners of Large Planes
Description: Finds names and addresses of corporate owners who own planes with a capacity greater than 200, connecting Corporate, Owner, Owns, Airplane, and Plane Type tables using joins.
![query4](images/query4.1.png)
![query4](images/query4.2.png)

**QUERY 05** - Average Night Shift Salary
Description: Finds the average salary of employees who perform the night shift, utilizing the AVG() aggregate function.
![query5](images/query5.png)

**QUERY 06** - Top 5 Maintenance Hours Employees
Description: Displays the top 5 employees with the highest maintenance work hours, utilizing the SUM() aggregate function.
![query6](images/query6.png)
![query6](images/query6.1.png)

**QUERY 07** - Recent Maintenance
Description: Identifies the names and registration numbers of airplanes that have undergone maintenance in the past week, using date library functions like DATEADD and GETDATE(), alongside a nested query.
![query7](images/query7.1.png)
![query7](images/query7.2.png)

**QUERY 08** - Recent Plane Purchases
Description: Retrieves the names and phone numbers of all owners who have purchased a plane in the past month. Employs the LIKE operator for date filtering and LEFT JOIN for connecting multiple tables, ensuring distinct entries via primary and foreign keys.
![query8](images/query8.png)

**QUERY 09** - Total Pilots Per Plane Type
Description: Calculates the total number of pilots authorized to fly each type of plane, using GROUP BY and joining multiple tables.
![query9](images/query9.png)

**QUERY 10** - Hangars with Available Space
Description: Shows all data stored in hangars that have more available space, joining Hangar, Plane Type, and Airplane tables.
![query10](images/query10.1.png)
![query10](images/query10.2.png)

**QUERY 11** - Number of Airplanes Owned by Corporations
Description: Uses joins to show the number of airplanes owned by each corporation.
![query11](images/query11.png)

**QUERY 12** - Average Maintenance Hours Per Plane
Description: Calculates the average number of maintenance hours per plane using the AVG() aggregate function.
![query12](images/query12.png)

**QUERY 14** - Owners with Same Location as Corporation's Hangar
Description: Lists names and phone numbers of owners who bought a plane from a corporation with a hangar in the same location as the owner. Joins are performed based on location.
![query14](images/query14.png)

**QUERY 15** - Pilots of Planes Under Maintenance
Description: Identifies the names of pilots who can fly a plane that is currently undergoing maintenance, using nested queries, LIKE operator, and WHERE EXISTS.
![query15](images/query15.png)

**QUERY 16** - Employees by Maintenance Hours for a Corporation
Description: Finds employee names who have worked on planes owned by a specific corporation, sorted by total maintenance hours worked. Uses LEFT JOIN for data retrieval and GROUP BY for aggregation.
![query16](images/query16.png)

**QUERY 17** - Airplanes Never Owned by Corporation or Day Shift Maintained
Description: Lists names and registration numbers of airplanes that have never been owned by a corporation or maintained by a day-shift employee. Achieved through table joins, WHERE conditions, and a nested query.
![query17](images/query17.png)

**QUERY 18** - Corporations Purchasing Same Plane Type Recently
Description: Identifies names and addresses of owners who purchased a plane from a corporation that also purchased a plane of the same type in the past month. Employs INNER JOIN based on primary/foreign keys and the LIKE operator for string matching.
![query18](images/query18.png)

**QUERY 19** - Total Planes Per Hangar
Description: Counts the total number of planes in each hangar, joining the Hangar and Airplane tables with COUNT().
![query19](images/query19.png)

**QUERY 20** - Total Planes by Type
Description: Determines the total number of planes for each plane type, joining the Airplane and Plane Type tables.
![query20](images/query20.png)

**QUERY 21** - Number of Services Performed on Each Plane
Description: Finds the number of services performed on each plane, joining Airplane and Plane Service tables and using COUNT().
![query21](images/query21.png)

**QUERY 22** - Average Salary Per Shift
Description: Calculates the average salary for each shift (day and night).
![query22](images/query22.png)

**QUERY 23** - Total Planes Owned by Owners
Description: Finds the total number of planes owned by owners (both corporations and persons), joining Owner and Owns tables.
![query23](images/query23.png)

**QUERY 24** - Planes Authorized Per Pilot
Description: Figures out the number of planes each pilot is authorized to fly, using the Pilot and Flies tables with COUNT().
![query24](images/query24.png)

**QUERY 25** - Multi-Purpose Query Examples
Description: Contains a set of diverse query examples, including:
* Incrementing salary for specific employees working on a specific model.
* Identifying pilots who own and fly airplanes.
* Selecting hangar space based on availability.
* Selecting persons living in a specific region.
![query25](images/query25.png)
