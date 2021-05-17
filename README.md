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
2. 
3. Important commands:
    1. **cy.visit("/home")**: Go to a particular path specified.
    2. **cy.title()**: Yields the documents title as a string
    3. **cy.url()**: Yields the current URL as a string
    4. **cy.wait(500)/cy.wait(alias)**: Wait for some time or an alias to resolve. 
    5. **cy.fixture("users/admin.json").then((data) => {});**: Loads data from path to a file within fixtures folder.
    6. **cy.get(".class")**: Retrieve element using css selectors.(https://www.w3schools.com/cssref/css_selectors.asp)
       - **cy.get('header').parent()**: Yield parent el of `header`
       - **cy.get('header').find('ul')**: Yield ul within header element.
       - **cy.get('header').find('input').text()**: Find the text inside element.
       - **cy.get('nav a').first()**: Yield first link in nav
       - **cy.get('nav a').last()**: Yield last link in nav
       - **cy.get('ul>li').each(() => {...})**: Iterate through each 'li'
       - **cy.get('td').filter('.users')**: Yield all el's with class '.users'
       - **cy.get('tbody>tr').eq(0)**: Yield first 'tr' in 'tbody'
       - **cy.get('nav a:first').next()**: Yield next link in nav
       - **cy.get('nav a:first').prev()**: Yield prev link in nav
       - **cy.get('input').not('.required')**: Yield all inputs without class '.required'
       - Note: You cannot store the element in a variable as in selenium. Hence use promise: `cy.get(".class").then((elem) => {})`;
    7. **cy.get(".class").as("esh")**: Create an alias for the element
    8. **cy.contains("selector", "content")**: Find element by its css selector and also content.
    9. **cy.click()/dblClick()**: Click or double click an element.
    10. **cy.get('select').select('user-1')** Select the 'user-1' option
    11. **cy.get('form').submit()**: Submit a form
    12. **cy.get('[type="checkbox"]').check/uncheck()**: Check/uncheck a checkbox.
    13. **cy.get('[type="text"]').clear()**: Clear text input
    14. **cy.get('a').trigger('mousedown')**: Trigger mousedown event on link
    15. **cy.get('input').type('Hello, World')**: Type 'Hello, World' into the 'input'
    16. **cy.get('form').focus()/blur()**: Focus or blur on an element.
    17. **cy.get('form').should(chainers, value)**: Chainers are spy chainers
        - _cy.get('.error').should('be.empty')_ // Assert that '.error' is empty
        - _cy.contains('Login').should('be.visible')_ // Assert that el is visible
        - _cy.wrap({ foo: 'bar' }).its('foo').should('eq', 'bar')_ // Assert the 'foo' property equals 'bar'
        - _cy.get(':checkbox').should('be.disabled')_
        - _cy.get('form').should('have.class', 'form-horizontal')_
        - _cy.get('input').should('not.have.value', 'Jane')_
        - _cy.get('#header a').should('have.attr', 'href')_
        - _cy.get('#input-receives-focus').should('have.focus')_
        - `cy.get('.connectors-list > li').should(($lis) => {
          expect($lis).to.have.length(3)
          expect($lis.eq(0)).to.contain('Walk the dog')
          expect($lis.eq(1)).to.contain('Feed the cat')
          expect($lis.eq(2)).to.contain('Write JavaScript')
          })`
          
          
          
