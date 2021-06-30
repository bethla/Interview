1. What is this test checking?

```
it('loads 3 elements', () => {
  cy.visit('index.html')
  cy.get('#app div')
    .should(($div) => {
      expect($div.eq(0)).to.contain('first child')
      expect($div.eq(1)).to.contain('second child')
      expect($div.eq(2)).to.contain('third child')
    })
})
```


2. What is the difference between these 2 tests?
```
it('check header - 1', () => {
  cy.get('.docs-header')
    .find('div')
    .should(($div) => {
      expect($div).to.have.length(1);
      expect($div).to.have.text('Introduction');
    });
 });

it('check header - 2', () => {
  cy.get('.docs-header')
    .find('div')
    .then(($div) => {
      expect($div).to.have.length(1);
      expect($div).to.have.text('Introduction');
    });
});
```

  
 3. Please explain what intercept and wait do in this test
 ```
 cy.intercept({
    url: 'http://example.com/search*',
    query: { q: 'expected terms' },
  }).as('search')
  // some other code in here
  cy.wait('@search');
  ```
  
  4. Is there anything wrong with this test? How can it be improved?
  ```
  describe('my form', () => {
    before(() => {
      cy.visit('/users/new')
    })

    it('check first name field', () => {
      cy.get('#first')
        .type('johnny');
    })
  })
  ```

