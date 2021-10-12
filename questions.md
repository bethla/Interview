1. What each of these console statements will print?

```
let a = 8 
let b = '8' 

console.log(a == b)
console.log(a === b) 
```

2. Write code to print the words with more than 3 letters

```
// Return the words with more than 3 letters
const words = ['one', 'apple', 'red', 'javascript', 'at', 'blueberries']
```

3. Write code to sum an array of numbers

```
const a = [1, 2, 3, 4, 5];
```

4. What will this code print?

```
function printVar() {
  console.log(a);
  var a = 'tree';
}

printVar(); 
```

5. What is this test checking?

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


6. What is the difference between these 2 tests?
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

  
 7. Please explain what intercept and wait do in this test
 ```
 cy.intercept({
    url: 'http://example.com/search*',
    query: { q: 'expected terms' },
  }).as('search')
  // some other code in here
  cy.wait('@search');
  ```
  
  8. Is there anything wrong with this test? How can it be improved?
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

