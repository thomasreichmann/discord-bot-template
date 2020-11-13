# Info

 Esse repo tem como intuito:
 * Disponibilizar uma maneira rapida de prototipar e criar bots completos
 * Ser uma base completa com todos os sistemas basicos esperados de um bot como:
   * Indexação automatica de comandos novos sem ser necessario codigo novo
   * Sistema de eventos modular e automatico
   * Sistema de `!Help` Automatico
   * Sistema de permissoes por comando, permitindo:
      * Permissoes basicas do discord
      * Exclusividade por guild
      * Exclusividade por usuario
 
 # Comandos
 
Para criar um comando novo, utilize como base o `templateCommand.js` como base e crie um arquivo na pasta comandos com o nome principal do comando

Todo comando tem uma quantidade de  metadata que pode ser atribuida a ele:


|     Nome    | Necessario |    Value   |                                                         Descricao                                                        |               Exemplo               |
|:-----------:|:----------:|:----------:|:------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------:|
|     name    |    `sim`   |  `string`  |                                                      Nome do comando                                                     |             `name: help`            |
| description |    `sim`   |  `string`  |                                              Descricao do comando para !help                                             |   `description: 'comando basico'`   |
|   aliases   |    `nao`   | `string[]` |                                                Alternativas para o comando                                               | `aliases: ['template', 'templote']` |
|    usage    |    `nao`   |  `string`  |                                               Como o comando deve ser usado                                              |         `usage: play [link]`        |
|   cooldown  |    `nao`   |  `number`  |                                                    Cooldown do comando                                                   |            `cooldown: 5`            |
| permissions |    `nao`   |  `number`  | [Permission integer](https://discordapi.com/permissions.html) indicando as permissoes necessarias para usar esse comando |         `permissions: 8192`         |
|     ids     |    `nao`   | `string[]` |                                       IDs dos usuarios que podem usar esse comando                                       |    `ids: ['181270590672338944']`    |
|   hideHelp  |    `nao`   |  `boolean` |                                         Se o comando deve ser escondido do !help                                         |           `hideHelp: true`          |
# Eventos

Para adicionar mais eventos ao `Event Handler`, use como base o `templateEvent.js` e crie um arquivo na pasta events com o nome exato do [evento](https://discord.js.org/#/docs/main/stable/class/Client?scrollTo=e-channelCreate)