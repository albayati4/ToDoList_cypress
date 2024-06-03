![Image](https://www.cypress.io/cypress_logo_social.png)

## Date: 06/04/2024

### By: Abdullah Albayati

### Testing Front end project-06

#### Validating 5 test cases for all the components of a To Do list form.

#### Creator Linkedin page

[Abdullah Albayati](https://www.linkedin.com/in/albayati-abdullah/)

---

#### This project was creatated and executed with the use of JaveScript, Node.js, Cypress, CSS selectors and POM.

---

### _Getting Started_

- In all test cases we are required to visit this page [project-6](https://www.techglobal-training.com/frontend/project-6)
- So I used `beforeEach` from Mocha framework with `cy.visit()` to handel visiting this website before each test case.
- I Created a separate folder called Pages with a TODOList.js file inside to be able to use POM (Page Object Model)
- In my TODOList.js I created a class called TODOList and I added all my locators and methods then I exported this class with
  ```JavaScript
  export default TODOList
  ```
- In order to use this page I had to imported in my 03-project.cy.js and create a new instance of this object to use it.
  ```JavaScript
  import TODOList from "../../../pages/TODOList";
  const toDoList = new TODOList();
  ```
- I created a method inside my page to get click on remove completed tasks button

  ```JavaScript
  // Methods
  /**
   * This function clicks on Remove Completed Tasks Button
   * @returns {click}
   */
  ClickOnRemoveCompletedTasksButton() {
    return this.getRemoveCompletedTasksButton().click();
  }
  ```

- I created an array that I would use few times so I made it global

  ```JavaScript
  const arr = ["New Task 1 {enter}", "New Task 2 {enter}", "New Task 3 {enter}", "New Task 4 {enter}", "New Task 5 {enter}"];
  ```

- I used each to handel validating multiple detalis with their text from an array

  ```JavaScript
  arr.forEach((value) => {
      toDoList.getNewToDoInputBox().clear().type(`${value}{enter}`);
    });
  ```

- I used `toDoList.getAddButton().should("not.be.disabled")` to check if a button is clickable.

- I used `toDoList.getExpectedLocator.type('expected input') `to type anything in the input fields.

### _Screenshots_

![Image](https://i.ibb.co/CWLcXhB/Screenshot-2024-06-03-at-3-43-56-PM.png)
