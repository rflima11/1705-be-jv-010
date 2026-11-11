# Projeto final

| | |
|---|---|
| **Formato** | individual: cada pessoa faz o seu |
| **Tema** | livre: você escolhe |
| **Apresentação** | banca de uns 20 minutos por pessoa. O último dia é **23/11/2026** |

---

## 1. O que fazer

Escolha um problema e monte um sistema pequeno que use o que vimos no módulo.

A API de Comprovantes PIX das aulas é só um exemplo. Não copie: leve as mesmas ideias para o seu problema.

Se precisar de uma ideia:

- **Central de boletos:** emite o boleto e manda registrar por uma fila.
- **Antifraude:** as transações chegam por uma fila, e o resultado da análise fica em cache.
- **Um problema do seu trabalho.** É a melhor opção, porque fica perto do dia a dia.

---

## 2. O obrigatório

- [ ] **2 serviços**, cada um com **o seu banco**, como o emissor e o gravador do PIX.
- [ ] **1 fila** entre eles: um serviço manda a mensagem e o outro recebe. Se a mesma mensagem chegar duas vezes, quem recebe grava uma vez só.
- [ ] **1 cache**: o que ele guarda, por quanto tempo e quando apaga.
- [ ] **ADRs** na pasta `docs/adr/`: um arquivo curto para cada decisão importante, com o que você escolheu, o que mais considerou e por quê.
- [ ] **1 README** com o que o sistema faz, um desenho dos serviços e como rodar, dizendo o perfil (A, B ou C).

Se sobrar tempo, você pode ir além: retry e DLQ, Kafka, SAGA ou teste de contrato. Nada disso é obrigatório.

### Os perfis de execução

Cada máquina tem as suas limitações. Por isso, você escolhe como o projeto vai rodar:

| Perfil | Como roda |
|---|---|
| **A** | com Docker |
| **B** | sem Docker, só com Java |
| **C** | conceitual: desenhado e explicado, sem rodar tudo |

**Ninguém perde nota por causa do ambiente.**

---

## 3. Como entregar

Entregue um repositório no GitHub (ou um zip) com o código, os ADRs e o README.

Faça commits aos poucos, não tudo no último dia.

---

## 4. A nota

| O que vale | Pontos |
|---|:---:|
| Os serviços estão separados, cada um com o seu banco | 25 |
| A fila: quem manda, quem recebe, e a mensagem repetida não duplica nada | 25 |
| O cache: o que guarda, por quanto tempo e quando apaga | 25 |
| As escolhas explicadas nos ADRs: por que assim e o que mais você considerou | 25 |

---

## 5. A banca

Em uns 20 minutos:

1. Mostre o projeto rodando, dizendo o perfil (A, B ou C). No perfil C, mostre o desenho.
2. Explique por que fez assim.
3. Responda às perguntas.
4. Conte se usou IA e o que conferiu à mão.
