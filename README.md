# Projeto SSC0904

> Trabalho final de Sistemas Computacionais Distribuídos - SSC0904

O projeto se baseia no framework de comunicação com protocolo IRC desenvolvido no trabalho final da disciplina _SSC0142 - Redes de Computadores_, em 2022, pelos mesmos alunos. O objetivo deste projeto, então, é transformar o framework desenvolvido em uma plataforma distribuída robusta, com enfoque nas características importantes desse tipo de sistema, como discutido em aula:
- Alto desempenho
- Confiabilidade
- Escalabilidade
- Consistência
- Segurança

Assim, foi implementada criptografia no chat dos servidores, garantindo **segurança**, ferramentas para remediar falhas de conexão ao servidor, garantindo **confiabilidade**, processamento paralelizado a fim de trazer **alto desempenho** e logs de execução garantindo a análise posterior de quaisquer problemas de execução.

## Autores

| Nome                            | RA       |
|:-------------------------------:|:--------:|
| Lourenço de Salles Roselino     | 11796805 |
| Marco Antônio Ribeiro de Toledo | 11796419 |

> O código foi compilado utilizando `clang++ versão 11.0.0`, com `target = Linux GNU x86_64` e desenvolvido em `C++17` com padrão GNU, usando a flag `-std=gnu++17` durante a compilação.

## Aspectos técnicos

### Execução
Para testar o código, compile-o com o comando `make` (ou em modo de debug, garantindo um log de informações, com `make debug`).
O servidor será iniciado na porta `6667` (essa configuração está contida na variável `static string PORT{}` no arquivo [`Conn.hpp`](src/Utils/Conn.hpp)). O programa cliente também será iniciado.

### Uso

**Comandos comuns a todos os usuários:**<br>
`/connect` - Estabelece a conexão com o servidor;<br>
`/quit` - O cliente fecha a conexão e fecha a aplicação;<br>
`/ping` - O servidor retorna "pong" assim que receber a mensagem.<br>
`/join nomeCanal` - Entra no canal;<br>
`/nickname apelidoDesejado` - O cliente passa a ser reconhecido pelo apelido especificado;<br>
`/ping` - O servidor retorna "pong" assim que receber a mensagem.<br>

<br>**Comandos apenas para administradores de canais:**<br>
`/kick nomeUsurio` - Fecha a conexão de um usuário especificado;<br>
`/mute nomeUsurio` - Faz com que um usuário não possa enviar mensagens neste canal;<br>
`/unmute nomeUsurio` - Retira o mute de um usuário;<br>
`/whois nomeUsurio` - Retorna o endereço IP do usuário apenas para o administrador.

> Para mandar mensagens no servidor, apenas digite normalmente no terminal e aperte **ENTER**.

