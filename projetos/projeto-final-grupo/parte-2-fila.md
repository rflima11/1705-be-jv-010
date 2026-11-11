# Projeto final, parte 2: a fila

Uma sugestão para a hora do projeto nesta aula: fazer os dois serviços conversarem por uma fila.

## O que fazer

1. **O primeiro serviço publica** a mensagem no RabbitMQ.
2. **O segundo serviço escuta** a fila e grava no banco dele.
3. **Não duplique.** Antes de gravar, o segundo serviço confere se aquele id já existe. Se já existe, não grava de novo.
4. **Teste a repetição.** Publique a mesma mensagem duas vezes pelo painel do RabbitMQ (http://localhost:15672) e confira que ficou uma linha só no banco.
5. **Escreva o ADR-002:** por que fila, e não HTTP. Diga a garantia de entrega: "pelo menos uma vez" (a mensagem pode chegar repetida, mas não se perde).
6. **Faça commit e push.**

## Onde olhar

O código da aula do RabbitMQ no `comprovantes-pix`, branch `aula-05-gabarito`: o `FilasConfig`, o `GravacaoAdapter` e o `ConsumidorDeGravacao`.

## Pronto quando

- A mensagem sai do primeiro serviço, passa pela fila e chega no segundo.
- A mensagem repetida não duplica nada.

## Se quiser ir além

Use um tópico no Kafka, no lugar da fila ou junto com ela.
