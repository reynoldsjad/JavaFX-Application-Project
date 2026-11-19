# JavaFX-Application-Project
# Inventory and Equipment Checkout Manager 
A JavaFX desktop application for tracking equipment, borrower limits, item conditions, and item dates. 

# Project Overview
The Inventory and Equipment Checkout Manager tracks equipment availability and loan history while enforcing the following:
- Preventing items in 'NEEDS_REPAIR' from being checked out by borrowers.
- Preventing borrowers with overdue items or borrowers who have reached their maximum active item limit from borrowing more items.
- Tracking checkout dates, due dates, return dates, and overdue status for borrowed items.

Core domain logic is separated from the JavaFX user interface so business rules can be developed with unit tests and Test-Driven Development using JUnit and Maven.

# Starting UML Design
The initial domain class design is defined in ['diagram.puml'] and includes:
- **'InventoryService'**: Manages items, borrowers, and checkout records, while coordinating checkouts, returns, searches, and overdue payments.
- **'EquipmentItem'**: Represents item details ('item_Id', 'name', 'category', 'condition', 'available') and checkout eligibility ('canBeCheckedOut()').
- **'Borrower'**: Tracks borrower details and borrowing limits ('canBorrowMore()').
- **'CheckoutRecord'**: Tracks loan dates and return status ('isOverdue()', 'getDaysOverdue()', 'closeRecord()').
- **'ItemCondition'**: States the quality of an item ('EXCELLENT', 'GOOD', 'NEEDS_REPAIR').
