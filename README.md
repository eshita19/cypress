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
    2. **cy.title()**: Yields the documents title as a string
    3. **cy.get(".class")**: Retrieve element using css selectors.(https://www.w3schools.com/cssref/css_selectors.asp)
       - **cy.get('header').parent()**: Yield parent el of `header`
       - **cy.get('header').find('ul')**: Yield ul within header element.
       - **cy.get('nav a').first()**: Yield first link in nav
       - **cy.get('nav a').last()**: Yield last link in nav
       - **cy.get('ul>li').each(() => {...})**: Iterate through each 'li'
       - **cy.get('td').filter('.users')**: Yield all el's with class '.users'
       - **cy.get('tbody>tr').eq(0)**: Yield first 'tr' in 'tbody'
       - **cy.get('nav a:first').next()**: Yield next link in nav
       - **cy.get('nav a:first').prev()**: Yield prev link in nav
       - **cy.get('input').not('.required')**: Yield all inputs without class '.required'
    4. **cy.fixture("users/admin.json").then((data) => {});**: Loads data from path to a file within fixtures folder.
    5. **cy.contains("selector", "content")**: Find element by its css selector and also content.
    6. **cy.click()/dblClick()**: Click or double click an element.
    7. **cy.get('select').select('user-1')** Select the 'user-1' option
    8. **cy.get('form').submit()**: Submit a form
    9. **cy.get('[type="checkbox"]').check/uncheck()**: Check/uncheck a checkbox.
    10. **cy.get('[type="text"]').clear()**: Clear text input
    11. **cy.get('a').trigger('mousedown')**: Trigger mousedown event on link
    12. **cy.get('input').type('Hello, World')**: Type 'Hello, World' into the 'input'
