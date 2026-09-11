# Bugs encontrados - DemoQA Practice Form

Testes exploratórios realizados em: https://demoqa.com/automation-practice-form

---

## Bug #1 - Feedback visual de validação inconsistente em campos vazios

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Deixar os campos Email, Picture e Current Address vazios
2. Preencher os demais campos obrigatórios visíveis
3. Observar o estado visual dos campos vazios

**Resultado esperado:** Campos vazios sem indicação, ou com indicação de erro se forem obrigatórios
**Resultado obtido:** Email, Picture e Current Address aparecem com check verde mesmo vazios; o campo Subjects (também vazio) não recebe indicação nenhuma
**Severidade:** Baixa (cosmético/UX)

---

## Bug #2 - Nome de 1 caractere aceito sem validação de tamanho mínimo

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Preencher First Name e Last Name com apenas 1 caractere (ex: "v")
2. Submeter o formulário

**Resultado esperado:** Nome de 1 caractere deveria ser rejeitado ou sinalizado
**Resultado obtido:** Formulário aceita sem nenhum aviso, exibindo "Student Name: v v" no resultado
**Severidade:** Baixa

---

## Bug #3 - Campo Address sem limite de caracteres, quebra o layout da tabela de resultado

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Preencher Current Address com uma string extremamente longa (100+ caracteres repetidos)
2. Submeter o formulário

**Resultado esperado:** Limite razoável de caracteres (maxlength), ou quebra de linha/truncamento no resultado
**Resultado obtido:** Texto aceito sem limite; a tabela de resultado exige scroll horizontal, quebrando o layout responsivo
**Severidade:** Baixa/Média

---

## Bug #4 - Date of Birth aceita data futura/atual sem validação lógica

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Selecionar a data atual ou uma data futura no campo Date of Birth
2. Submeter o formulário

**Resultado esperado:** Campo de data de nascimento deveria rejeitar hoje ou datas futuras
**Resultado obtido:** Aceito sem aviso; resultado exibe a data futura normalmente
**Severidade:** Média (falha de regra de negócio)

---

## Bug #5 - Validação de e-mail inconsistente (rejeita formato errado, mas aceita vazio)

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Digitar um e-mail sem "@" (ex: "teste") → observar rejeição
2. Limpar o campo, deixando-o vazio → submeter o formulário

**Resultado esperado:** Comportamento consistente — se o campo valida formato quando preenchido, deveria também exigir preenchimento
**Resultado obtido:** Formato inválido é bloqueado, mas campo vazio passa direto no submit
**Severidade:** Baixa

---

## Teste #6 - Validação de campo Mobile (PASSOU )

**Página:** /automation-practice-form
**Passos para reproduzir:**
1. Inserir letras no campo Mobile
2. Inserir menos de 10 dígitos

**Resultado esperado:** Campo deve recusar ambos os casos
**Resultado obtido:** Recusado corretamente em ambos os cenários
**Resultado:**  Passou
