# Cypress Web automation

- To open cypress ui: npx cypress open
- Clone repo for examples: https://github.com/Postavshik/ngx-cypress-test.git

## Cypress Folder structure
1. **Fixtures**: Contains the test/mock data to be passed to tests.**
cy.visit**
2. **Integrations**: Contains all the specs.
3. **Plugins**: Contains any cypress overidden files for custom implementation.
4. **Support**: Contains index.js which is the first file which runs when cypress loads.
5. **cypress.json**: Cypress configuration file.(baseURL and others) https://docs.cypress.io/guides/references/configuration#cypress-json


## Cypress Commands
1. CheatSheet: https://docs.cypress.io/api/table-of-contents
2. Important commands:
    1. **cy.visit("/home")**: Go to a particular path specified.
    2. **cy.get(".class")**: Retrieve element using css selectors.(https://www.w3schools.com/cssref/css_selectors.asp)
       - **cy.get('header').parent()**: Yield parent el of `header`
       - **cy.get('header').find('ul')**: Yield ul within header element.
       - **cy.get('nav a').first()**: Yield first link in nav
       - **cy.get('ul>li').each(() => {...})**: Iterate through each 'li'
       - **cy.get('td').filter('.users')**: Yield all el's with class '.users'
    4. **cy.fixture("users/admin.json").then((data) => {});**: Loads data from path to a file within fixtures folder.
    5. **cy.contains("selector", "content")**: Find element by its css selector and also content.
    6. **cy.click()/dblClick()**: Click or double click an element.
    7. 
