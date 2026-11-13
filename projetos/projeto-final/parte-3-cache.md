# Projeto final, parte 3: o cache

Uma sugestão para a hora do projeto nesta aula: guardar uma cópia da leitura no cache.

## O que fazer

1. **Crie um endpoint de leitura:** um `GET` que busca pelo id.
2. **Ponha o cache:** `@Cacheable` com o Redis, e a validade (o TTL) no `application.yml`.
3. **Não guarde o "não achei".** Quem procurar de novo daqui a pouco precisa achar.
4. **Decida quando apagar.** Se o dado muda, apague a cópia (`@CacheEvict`). Se ele nunca muda, explique por que a validade basta.
5. **Escreva o ADR-003:** o que o cache guarda, por quanto tempo e quando apaga.
6. **Faça commit e push.**

## Onde olhar

O código da aula de cache no `comprovantes-pix`, branch `aula-04-gabarito`: o `ConsultaService`, com o `@Cacheable(value = "comprovantes", unless = "#result == null")`, e o `CacheConfig`.

## Pronto quando

- A segunda leitura do mesmo id vem do cache, sem ir ao banco.

## Se quiser ir além

Ligue o retry com backoff e a DLQ no serviço que escuta a fila. Copie o bloco `retry` do `application.yml` do gravador e a DLQ do `FilasConfig` do gravador (branch `aula-05-gabarito`).
