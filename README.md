# FACULDADE DE PETROLINA (FACAPE)
### Equipe: Ariel Silva, Ianny Rabelo, Sigismundo Barbosa, Leonardo de Carvalho, Samuel Dias
## Projeto de avaliação II unidade - Sistemas distribuídos.

- Composto por 3 componentes:
  - src/main/java/com/leo/calc/WebService.java
  - src/main/java/com/leo/calc/ServidorBasico.java
  - src/main/java/com/leo/calc/ServidorEspecialista.java
- Um webservice rest encaminhará as operações via sockets para servidores especialistas.
- O ServidorBasico é responsável pelas operações básicas.
- O ServidorEspecialista é responsável pelas operações de porcentagem, raiz quadrada e potenciação.
- Tratamento de: operação inválida e divisão por zero.

## Como instalar

1) Instalar o Maven -> https://maven.apache.org/index.html
2) Na pasta do projeto: `mvn clean package && java -jar target/WebService-1.0.jar`
3) Em outra aba do terminal: `cd target/classes && java com.leo.calc.ServidorBasico`
4) Em uma terceira aba: `cd target/classes && java com.leo.calc.ServidorEspecialista`

## Endereçamento
Todos os servidores estão localizados no localhost (127.0.0.1).<br>
O WebService será levantado na porta 4567.

## Caminho da API
http://localhost:4567/{operacao}

### Operações
- /soma
- /subtracao
- /multiplicacao
- /divisao
- /porcentagem
- /raiz_quadrada
- /potencia

Sendo que para soma, subtração, multiplicação, divisão, porcentagem e potenciação, é necessário enviar os valores "x" e "y" no BODY.<br>

Já para a raiz quadrada, é necessário apenas o valor de "x".

## Exemplo

```
POST http://localhost:4567/soma
BODY
  {
    "x": 250,
    "y": 53
  }
RESPONSE
  Resultado: 303.0
```
