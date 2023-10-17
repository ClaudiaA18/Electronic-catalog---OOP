# Electronic Catalog - OOP

**Subject: OOP Project**

**Electronic Catalog**

**Name**: Gîrniță Alexandra-Claudia

**Group**: 322CC

**Difficulty Level**: Medium, with some challenges

**Time Allotted for Resolution**: 5 days (involving the exploration of several topics)

**Required Data**: Data reading is done from multiple files.

## Implementation Details

### Class Catalog
**Singleton Pattern**: To ensure that only one instance of the class exists. The class contains a private static instance of Catalog, which is created on the first call to the function that returns the catalog. Any subsequent calls will return the previously created catalog.

**Observer Pattern**: The catalog maintains a list of subscribers who receive notifications when the catalog is updated. When a notification arrives (i.e., a new grade is added), the list of subscribers (parents) is iterated through to find the parent whose child received the grade. Then, the notification is sent to that parent. Each parent maintains a list of grades, which is populated after receiving notifications.

### Class User
**Factory Pattern**: With several subclasses derived from the abstract User class, the FACTORY pattern facilitates the creation of different instances of the User class based on the name of the subclass whose instances are of interest.

### Class Course
**Builder Pattern**: As there are multiple fields to initialize when creating course instances, derived classes from the Course class (PartialCourse and FullCourse) implement an inner class to facilitate the instantiation process. This inner class contains methods that gradually populate the fields of the newly created instance.

**Strategy Pattern**: Since there are multiple ways to determine the grading hierarchy within a course, each course has a field of the interface that describes the student evaluation strategy. Depending on preference, the evaluation method can be flexibly modified by placing a particular implementation of the evaluation strategy in the general field.

**Visitor Pattern**: To keep track of individuals who assign a specific grade to a student (both the professor and the teaching assistant), the Catalog can also receive visitors who assign grades. For each visitor, it records that they were the ones who assigned the mentioned grade to the course, in a HashMap indexed by Teacher/Assistant.

**Memento Pattern**: To retain a snapshot of a course's past grades, an inner class is created within the course. This inner class keeps copies of the grades from a specific moment in time, allowing for the ability to set the current grades in the catalog to a past version.
