# Teste Automatizado com Cypress

Este repositório contém um exemplo de teste automatizado utilizando [Cypress](https://www.cypress.io/). Este teste foi desenvolvido após assistir a uma aula sobre QA de software que utilizou o site [OrangeHRM Live](https://opensource-demo.orangehrmlive.com) como exemplo.

## Descrição

A aula focou em ensinar os fundamentos de testes automatizados para qualidade de software, utilizando a ferramenta Cypress. O objetivo do teste é verificar o processo de login no sistema OrangeHRM e confirmar se o usuário é redirecionado para a página de dashboard após o login bem-sucedido.

## Teste de Login com Cypress

O seguinte código Cypress realiza um teste simples de login:

```javascript
describe('Teste de Login', () => {
  it('Deve fazer login e verificar a página de dashboard', () => {
    // Visita a página de login
    cy.visit('https://opensource-demo.orangehrmlive.com/web/index.php/auth/login')
    
    // Digita o usuário
    cy.get(':nth-child(2) > .oxd-input-group > :nth-child(2) > .oxd-input').type('Admin')
    
    // Digita a senha
    cy.get(':nth-child(3) > .oxd-input-group > :nth-child(2) > .oxd-input').type('admin123')
    
    // Clica no botão de login
    cy.get('.oxd-button').click()
    
    // Verifica se a página de dashboard foi carregada
    cy.get('.oxd-topbar-header-breadcrumb > .oxd-text').contains('Dashboard')
  })
})
```



## Como Executar
Para executar o teste, siga os passos abaixo:

1- Instale o Cypress:

    npm install cypress --save-dev

2- Abra o Cypress:

    npx cypress open

Execute o teste:

Coloque o código de teste no arquivo 'cypress/e2e/login.cy.js'.


No painel do Cypress, selecione o arquivo 'login.cy.js' para executar o teste.


## Conclusão
Esta experiência foi muito valiosa para entender como testes automatizados podem garantir a qualidade do software. Utilizando Cypress, conseguimos escrever testes claros e eficientes para validar funcionalidades essenciais, como o login do usuário.

### Links Úteis
* [Cypress Documentation](https://www.cypress.io/)
* [OrangeHRM Live Demo](https://opensource-demo.orangehrmlive.com)

