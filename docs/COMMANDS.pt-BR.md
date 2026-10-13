# Comandos do SCC

🇬🇧 [English version](COMMANDS.md)

Todos os comandos `/scc` do SCC – Super Cool Calculator, gerados a partir dos textos de ajuda do próprio mod. No jogo, **`/scc help`** mostra a mesma lista (só os comandos que você pode usar; clique num deles para colocá-lo na linha do chat), **`/scc help <comando>`** os detalhes e **`/scc help settings`** todas as configurações do servidor com o valor atual.

_Válido para o SCC 1.4.1 ou mais novo (Minecraft 1.21.1 e 26.1.2). Gerado por `tools/make_commands_doc.py`._

## Permissões

**Todos** – qualquer jogador. **Dono da rede** – o jogador que colocou o Controlador de Rede (ou um operador); só importa com `/scc security on`. **Operador** – nível de permissão 2, como `/gamerule` (no single player: cheats ligados).

## Visão geral

| Comando | O que faz | Quem |
|---|---|---|
| [`/scc help [command\|settings]`](#scc-help) | Lista os comandos do SCC que você pode usar, ou explica um deles. | Todos |
| [`/scc guide [chapter] [heading]`](#scc-guide) | Abre o Manual do SCC, opcionalmente num capítulo. | Todos |
| [`/scc sky`](#scc-sky) | Mostra a conjunção celeste atual e a próxima. | Todos |
| [`/scc sky shower`](#scc-shower) | Informa quando vem a próxima noite de chuva de meteoros. | Todos |
| [`/scc order <item> [amount]`](#scc-order) | Pede um item da sua rede pelo chat. | Todos |
| [`/scc trust <player> [rights]`](#scc-trust) | Dá direitos a um jogador na sua rede. | Dono da rede |
| [`/scc untrust <player>`](#scc-untrust) | Remove todos os direitos de um jogador na sua rede. | Dono da rede |
| [`/scc rights`](#scc-rights) | Mostra o dono da rede e quem tem quais direitos. | Dono da rede |
| [`/scc <setting> [value\|on\|off]`](#scc-settings) | Mostra ou altera uma configuração do servidor. | Operador |
| [`/scc power [on\|off]`](#scc-power) | Liga ou desliga a necessidade de energia de todas as redes. | Operador |
| [`/scc list`](#scc-list) | Mostra todas as configurações do servidor com seus valores numa janela. | Operador |
| [`/scc reloadconfig`](#scc-reloadconfig) | Recarrega config/scc-server.json sem reiniciar. | Operador |
| [`/scc doctor`](#scc-doctor) | Relatório da rede: máquinas e tipos de receita da rede mais próxima. | Operador |
| [`/scc selftest`](#scc-selftest) | Executa o autoteste do SCC na sua posição. | Operador |
| [`/scc unstick`](#scc-unstick) | Libera todas as máquinas da rede mais próxima de filtros de etapa travados. | Operador |
| [`/scc drain [chunks]`](#scc-drain) | Remove a água dos blocos do SCC ao seu redor. | Operador |
| [`/scc profile [on\|off\|reset]`](#scc-profile) | Mede quanto tempo o SCC usa por tick. | Operador |
| [`/scc balance`](#scc-balance) | Mostra os valores de balanceamento em vigor agora. | Operador |
| [`/scc meteor [x y z]`](#scc-meteor) | Faz cair um meteoro. | Operador |
| [`/scc sky conjunction`](#scc-conjunction) | Pula para o auge da próxima conjunção celeste. | Operador |
| [`/scc sky shower jump`](#scc-showerjump) | Pula para o pôr do sol antes da próxima chuva de meteoros. | Operador |

## Comandos

<a id="scc-help"></a>
### /scc help

Sem argumento, lista todos os comandos que você pode usar; clique num deles para colocá-lo na linha do chat. Com o nome de um comando, mostra a sintaxe, uma descrição, um exemplo e quem pode usá-lo. Operadores também têm /scc help settings: todas as configurações do servidor com valor atual, padrão e significado.

- **Sintaxe:** `/scc help [command|settings]`
- **Exemplo:** `/scc help trust`
- **Quem:** todos

<a id="scc-guide"></a>
### /scc guide

Abre o manual do jogo, igual ao item Manual do SCC. Com um capítulo (por exemplo start, network, storage, autocraft, processing, sky, forge, quarry, cosmos, power) abre direto nele; uma segunda palavra pula para um título dentro desse capítulo. Links no chat usam este comando para apontar para a página certa.

- **Sintaxe:** `/scc guide [chapter] [heading]`
- **Exemplo:** `/scc guide quarry`
- **Quem:** todos

<a id="scc-sky"></a>
### /scc sky

Informa qual conjunção celeste está ativa agora, quanto tempo ainda dura e quando começa a próxima. Durante uma conjunção a Colheitadeira Celeste rende o dobro dos dois objetos celestes envolvidos (configuração conjunctions).

- **Sintaxe:** `/scc sky`
- **Exemplo:** `/scc sky`
- **Quem:** todos

<a id="scc-shower"></a>
### /scc sky shower

Mostra se há uma chuva de meteoros agora ou quanto falta para a próxima. As chuvas de meteoros acontecem em noites de lua nova (configurações meteorShowers, meteorShowerEvery, meteorShowerMeteors): estrelas cadentes a noite toda e alguns meteoros de verdade por jogador.

- **Sintaxe:** `/scc sky shower`
- **Exemplo:** `/scc sky shower`
- **Quem:** todos

<a id="scc-order"></a>
### /scc order

Precisa de um Terminal Sem Fio vinculado no inventário ou num slot do Curios, no alcance da antena, e do direito "pedir" nessa rede. Planeja como a janela de pedido: se faltarem ingredientes, o chat lista quais; senão o pedido começa e o chat mostra o tempo estimado. Tab completa os IDs de item, primeiro os itens da sua rede. Quantidade de 1 a 9999, padrão 1.

- **Sintaxe:** `/scc order <item> [amount]`
- **Exemplo:** `/scc order minecraft:iron_ingot 64`
- **Quem:** todos

<a id="scc-trust"></a>
### /scc trust

Fique perto da sua rede (até 12 blocos de um bloco do SCC). Os direitos são take, put, order e build, separados por vírgula; sem direitos, o jogador recebe todos. Só importa com a configuração security ligada. O Terminal de Segurança faz o mesmo numa janela.

- **Sintaxe:** `/scc trust <player> [rights]`
- **Exemplo:** `/scc trust Steve take,order`
- **Quem:** o dono da rede ou um operador (só importa com /scc security ligado)

<a id="scc-untrust"></a>
### /scc untrust

Fique perto da sua rede. Com security ligado, o jogador não pode mais usá-la.

- **Sintaxe:** `/scc untrust <player>`
- **Exemplo:** `/scc untrust Steve`
- **Quem:** o dono da rede ou um operador (só importa com /scc security ligado)

<a id="scc-rights"></a>
### /scc rights

Fique perto da sua rede. Só o dono (ou um operador) pode ver a lista.

- **Sintaxe:** `/scc rights`
- **Exemplo:** `/scc rights`
- **Quem:** o dono da rede ou um operador (só importa com /scc security ligado)

<a id="scc-settings"></a>
### /scc &lt;setting&gt;

/scc <configuração> mostra o valor atual, /scc <configuração> <valor> altera na hora para todos e salva em config/scc-server.json. Configurações liga/desliga aceitam on ou off, as outras um número dentro do intervalo permitido. /scc help settings lista todas com padrão e significado.

- **Sintaxe:** `/scc <setting> [value|on|off]`
- **Exemplo:** `/scc meteorChance 25`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-power"></a>
### /scc power

Sem on/off mostra o valor atual. Desligado: redes, máquinas e o Controlador de Rede funcionam sem FE. Padrão: on.

- **Sintaxe:** `/scc power [on|off]`
- **Exemplo:** `/scc power off`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-list"></a>
### /scc list

Abre uma janela com cada configuração, seu valor e uma explicação curta, com linha de busca. No console do servidor a lista vai para o chat.

- **Sintaxe:** `/scc list`
- **Exemplo:** `/scc list`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-reloadconfig"></a>
### /scc reloadconfig

Use depois de editar o arquivo à mão. Os novos valores são enviados a todos os jogadores na hora.

- **Sintaxe:** `/scc reloadconfig`
- **Exemplo:** `/scc reloadconfig`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-doctor"></a>
### /scc doctor

Fique perto da sua rede. Abre um relatório do que está conectado, quais tipos de receita as máquinas conseguem fazer e onde falta algum - a primeira coisa a ver quando um item parece impossível de fabricar. O relatório também vai para logs/scc.log.

- **Sintaxe:** `/scc doctor`
- **Exemplo:** `/scc doctor`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-selftest"></a>
### /scc selftest

Monta uma pequena rede de teste ao seu lado, verifica as funções básicas e a remove de novo. No chat aparecem só as falhas e o total; o resultado completo fica em logs/scc.log - útil para relatar bugs. Use num lugar com espaço livre.

- **Sintaxe:** `/scc selftest`
- **Exemplo:** `/scc selftest`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-unstick"></a>
### /scc unstick

Se os pedidos continuam dizendo que não há máquina adequada mesmo havendo uma, um filtro de etapa pode estar travado. Este comando limpa todos; o que ainda estiver nas máquinas volta para o armazenamento. Trabalhos em andamento no máximo repetem uma etapa iniciada.

- **Sintaxe:** `/scc unstick`
- **Exemplo:** `/scc unstick`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-drain"></a>
### /scc drain

Repara blocos do SCC que um bug antigo deixou alagados: todo bloco do SCC com água nos chunks carregados ao seu redor é secado (raio em chunks, padrão 8, 1-32). Cabos colocados debaixo d'água de propósito também são secados.

- **Sintaxe:** `/scc drain [chunks]`
- **Exemplo:** `/scc drain 4`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-profile"></a>
### /scc profile

/scc profile on começa a medir; jogue normalmente por alguns minutos e depois /scc profile mostra os resultados numa janela (e em logs/scc.log). /scc profile off para, /scc profile reset apaga as medições. Desligado por padrão e sem custo enquanto desligado.

- **Sintaxe:** `/scc profile [on|off|reset]`
- **Exemplo:** `/scc profile on`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-balance"></a>
### /scc balance

Lista os valores que criadores de modpacks podem alterar com data packs (data/scc/scc_balance/...). Use para conferir se o seu data pack funcionou.

- **Sintaxe:** `/scc balance`
- **Exemplo:** `/scc balance`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-meteor"></a>
### /scc meteor

Sem posição, cai a 24-48 blocos ao seu redor; com x y z, cai lá. Uma Colheitadeira Celeste próxima o captura; senão ele deixa uma cratera com um Meteorito - ou queima no ar onde os blocos são protegidos. No console do servidor a posição é obrigatória.

- **Sintaxe:** `/scc meteor [x y z]`
- **Exemplo:** `/scc meteor ~ ~ ~20`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-conjunction"></a>
### /scc sky conjunction

Ajusta o horário em todos os mundos para o momento mais próximo da próxima conjunção, como /time set. Serve para testar e para mostrar o efeito.

- **Sintaxe:** `/scc sky conjunction`
- **Exemplo:** `/scc sky conjunction`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="scc-showerjump"></a>
### /scc sky shower jump

Ajusta o horário em todos os mundos para pouco antes do pôr do sol da próxima noite de chuva de meteoros, como /time set. Serve para testar e para mostrar a chuva.

- **Sintaxe:** `/scc sky shower jump`
- **Exemplo:** `/scc sky shower jump`
- **Quem:** somente operadores (nível de permissão 2, como /gamerule)

<a id="settings"></a>
## Configurações do servidor

`/scc <configuração>` mostra um valor, `/scc <configuração> <valor>` altera na hora para todos (só operadores). Os valores ficam em `config/scc-server.json`; depois de editar esse arquivo à mão, use `/scc reloadconfig`. Maiúsculas e minúsculas não importam nos nomes.

| Configuração | Padrão | Permitido | Significado |
|---|---|---|---|
| `power` | `on` | on / off | A rede precisa de energia (FE)? |
| `requireController` | `on` | on / off | Toda rede precisa de um Controlador de Rede? |
| `controllerCapacity` | `4,000,000` | 1,000 – 100,000,000 | Quanto FE o controlador armazena. |
| `controllerTransfer` | `100,000` | 1 – 10,000,000 | Quanto FE pode entrar por tick. |
| `security` | `off` | on / off | Jogadores precisam de direitos numa rede que não é deles? |
| `powerFactor` | `100` | 0 – 10,000 | Todos os custos de energia em porcentagem (100 = normal, 0 = grátis). |
| `timeDilation` | `8` | 1 – 16 | A maior Dilatação Temporal que uma Calculadora de Processamento (Singularidade) pode usar (1 = desligado, 8 = até 8x). |
| `chrononCost2x` | `1` | 0 – 10,000 | Chronon por segundo para Dilatação Temporal 2x (0 = grátis). |
| `chrononCost4x` | `4` | 0 – 10,000 | Chronon por segundo para Dilatação Temporal 4x (0 = grátis). |
| `chrononCost8x` | `16` | 0 – 10,000 | Chronon por segundo para Dilatação Temporal 8x (0 = grátis). |
| `timeDilationEnabled` | `on` | on / off | Existe Dilatação Temporal (Calculadora de Processamento Singularidade)? Desligado: sem botão, nenhuma máquina é acelerada. |
| `dilationStep1` | `2` | 2 – 16 | Etapa 1 da Dilatação Temporal: quantas vezes mais rápido a máquina roda (padrão 2x; o custo é chrononCost2x). |
| `dilationStep2` | `4` | 2 – 16 | Etapa 2 da Dilatação Temporal: quantas vezes mais rápido a máquina roda (padrão 4x; o custo é chrononCost4x). |
| `dilationStep3` | `8` | 2 – 16 | Etapa 3 da Dilatação Temporal: quantas vezes mais rápido a máquina roda (padrão 8x; o custo é chrononCost8x). |
| `overdrive` | `on` | on / off | A Calculadora de Quebra (Singularidade) tem o Overdrive de Chronon? |
| `overdriveMax` | `128` | 1 – 100,000 | Overdrive de Chronon: blocos por segundo na etapa máxima. |
| `overdriveRampSeconds` | `15` | 0 – 3,600 | Overdrive de Chronon: segundos por etapa ao acelerar (4 etapas). |
| `overdriveCost1` | `1` | 0 – 10,000 | Overdrive de Chronon: Chronon por segundo na etapa 1 (0 = grátis). |
| `overdriveCost2` | `2` | 0 – 10,000 | Overdrive de Chronon: Chronon por segundo na etapa 2 (0 = grátis). |
| `overdriveCost3` | `4` | 0 – 10,000 | Overdrive de Chronon: Chronon por segundo na etapa 3 (0 = grátis). |
| `overdriveCost4` | `8` | 0 – 10,000 | Overdrive de Chronon: Chronon por segundo na etapa 4 (0 = grátis). |
| `breakBlocksBasic` | `1` | 1 – 1,024 | Calculadora de Quebra (Básico): blocos por operação. |
| `breakBlocksRedDwarf` | `1` | 1 – 1,024 | Calculadora de Quebra (Anã Vermelha): blocos por operação. |
| `breakBlocksYellowStar` | `1` | 1 – 1,024 | Calculadora de Quebra (Estrela Amarela): blocos por operação. |
| `breakBlocksBlueGiant` | `4` | 1 – 1,024 | Calculadora de Quebra (Gigante Azul): blocos por operação. |
| `breakBlocksNeutronStar` | `8` | 1 – 1,024 | Calculadora de Quebra (Estrela de Nêutrons): blocos por operação. |
| `breakBlocksSingularity` | `16` | 1 – 1,024 | Calculadora de Quebra (Singularidade): blocos por operação. |
| `breakTicksBasic` | `40` | 1 – 1,200 | Calculadora de Quebra (Básico): ticks entre duas operações (20 = 1 s). |
| `breakTicksRedDwarf` | `20` | 1 – 1,200 | Calculadora de Quebra (Anã Vermelha): ticks entre duas operações (20 = 1 s). |
| `breakTicksYellowStar` | `10` | 1 – 1,200 | Calculadora de Quebra (Estrela Amarela): ticks entre duas operações (20 = 1 s). |
| `breakTicksBlueGiant` | `10` | 1 – 1,200 | Calculadora de Quebra (Gigante Azul): ticks entre duas operações (20 = 1 s). |
| `breakTicksNeutronStar` | `10` | 1 – 1,200 | Calculadora de Quebra (Estrela de Nêutrons): ticks entre duas operações (20 = 1 s). |
| `breakTicksSingularity` | `10` | 1 – 1,200 | Calculadora de Quebra (Singularidade): ticks entre duas operações (20 = 1 s). |
| `quarryTicksBasic` | `10` | 1 – 1,200 | Pedreira Estelar (Básico): ticks por operação (menor = mais rápido). |
| `quarryTicksRedDwarf` | `5` | 1 – 1,200 | Pedreira Estelar (Anã Vermelha): ticks por operação (menor = mais rápido). |
| `quarryTicksYellowStar` | `2` | 1 – 1,200 | Pedreira Estelar (Estrela Amarela): ticks por operação (menor = mais rápido). |
| `quarryTicksBlueGiant` | `1` | 1 – 1,200 | Pedreira Estelar (Gigante Azul): ticks por operação (menor = mais rápido). |
| `quarryTicksNeutronStar` | `1` | 1 – 1,200 | Pedreira Estelar (Estrela de Nêutrons): ticks por operação (menor = mais rápido). |
| `quarryTicksSingularity` | `1` | 1 – 1,200 | Pedreira Estelar (Singularidade): ticks por operação (menor = mais rápido). |
| `quarryFeBasic` | `800` | 0 – 10,000,000 | Pedreira Estelar (Básico): FE por bloco antes de dureza e cartões. |
| `quarryFeRedDwarf` | `1,000` | 0 – 10,000,000 | Pedreira Estelar (Anã Vermelha): FE por bloco antes de dureza e cartões. |
| `quarryFeYellowStar` | `1,200` | 0 – 10,000,000 | Pedreira Estelar (Estrela Amarela): FE por bloco antes de dureza e cartões. |
| `quarryFeBlueGiant` | `1,500` | 0 – 10,000,000 | Pedreira Estelar (Gigante Azul): FE por bloco antes de dureza e cartões. |
| `quarryFeNeutronStar` | `2,000` | 0 – 10,000,000 | Pedreira Estelar (Estrela de Nêutrons): FE por bloco antes de dureza e cartões. |
| `quarryFeSingularity` | `2,500` | 0 – 10,000,000 | Pedreira Estelar (Singularidade): FE por bloco antes de dureza e cartões. |
| `quarryLoadsWorkChunk` | `on` | on / off | Star Quarry: ela mantém carregado o chunk que está minerando (no máx. 2 chunks, nunca o próprio)? Desligado: minera só chunks carregados e volta aos outros depois. |
| `harvestSpeed` | `100` | 1 – 10,000 | Velocidade da Colheitadeira Celeste em porcentagem (100 = normal). |
| `forgeEnergy` | `100` | 0 – 10,000 | Custo de energia da Forja Estelar em porcentagem (100 = normal, 0 = grátis). |
| `harvestEnergy` | `100` | 0 – 10,000 | Custo de energia da Colheitadeira Celeste em porcentagem (100 = normal, 0 = grátis). |
| `photonOutput` | `100` | 0 – 10,000 | Produção do modo fóton da Colheitadeira Celeste em porcentagem (100 = normal, 0 = modo fóton desligado). |
| `photonRange` | `16` | 0 – 256 | Distância em blocos na qual Colheitadeiras Celestes no modo fóton dividem o céu (0 = sem divisão). |
| `conjunctions` | `on` | on / off | Conjunções celestes dão à Colheitadeira Celeste o dobro dos dois objetos? |
| `wormholeCap` | `16,384` | 64 – 1,000,000 | Máximo de itens que uma Calculadora de Transferência (Singularidade) move por ciclo. |
| `instantCrafts` | `256` | 0 – 100,000 | Fabricações de uma etapa que um fabricador Singularidade conclui no mesmo tick em que chegam. |
| `parallelSteps` | `4` | 0 – 16 | Passos independentes de uma tarefa que rodam ao mesmo tempo como tarefas próprias (0 = um passo após o outro). |
| `wormholeBase` | `1,000` | 0 – 100,000,000 | Portal de Buraco de Minhoca: FE que cada salto custa, por mais curto que seja. |
| `wormholePerBlock` | `10` | 0 – 1,000,000 | Portal de Buraco de Minhoca: FE por bloco de distância dentro de uma dimensão. |
| `wormholeDimension` | `50,000` | 0 – 1,000,000,000 | Portal de Buraco de Minhoca: FE para um salto a outra dimensão (substitui base e distância). |
| `wormholeCooldown` | `5` | 0 – 3,600 | Portal de Buraco de Minhoca: segundos até um jogador poder saltar de novo. |
| `wormholeLeashed` | `on` | on / off | Portal de Buraco de Minhoca: animais na guia viajam junto? |
| `wormholeRemoteCost` | `150` | 0 – 10,000 | Controle de Buraco de Minhoca: preço em porcentagem do preço do portal para o mesmo salto. |
| `wormholeRemoteCooldown` | `30` | 0 – 3,600 | Controle de Buraco de Minhoca: segundos até um jogador poder abrir a próxima fenda de bolso. |
| `wormholeRemoteOpen` | `10` | 2 – 120 | Controle de Buraco de Minhoca: segundos que uma fenda de bolso fica aberta. |
| `wormholeRemoteShared` | `on` | on / off | Controle de Buraco de Minhoca: outros jogadores podem passar pela fenda de bolso de alguém? |
| `wormholePreview` | `on` | on / off | Portal/Controle de Buraco de Minhoca: enviar aos jogadores uma imagem ao vivo do destino dentro do portal? |
| `stockTooltips` | `on` | on / off | Dicas dos itens: mostrar aos jogadores com um Terminal Sem Fio vinculado quanto do item a rede deles guarda? |
| `stockHistory` | `on` | on / off | Dicas do terminal: registrar um histórico de estoque de 24 horas por item (só itens que mudam ou são consultados)? |
| `ae2Provider` | `on` | on / off | A Antena de Rede oferece o que o SCC sabe fabricar a uma rede AE2 que ela toca, para que trabalhos do AE2 possam usar? |
| `meteors` | `on` | on / off | Meteoros caem à noite (crateras, ou capturados por uma Colheitadeira Celeste)? |
| `meteorChance` | `12` | 0 – 100 | Chance por jogador e por noite de um meteoro cair por perto, em porcentagem. |
| `meteorShowers` | `on` | on / off | Toda noite de lua nova (veja meteorShowerEvery) é uma chuva de meteoros anunciada? |
| `meteorShowerEvery` | `1` | 1 – 100 | Chuvas de meteoros: a cada quantas noites de lua nova vem uma (1 = toda lua nova, a cada 8 dias). |
| `meteorShowerMeteors` | `4` | 0 – 20 | Chuvas de meteoros: meteoros de verdade por jogador numa noite de chuva (0 = só estrelas cadentes no céu). |
| `storageWarnings` | `on` | on / off | Avisar jogadores com acesso ao terminal quando o armazenamento da rede atingir storageWarnPercent e quando estiver cheio? |
| `storageWarnPercent` | `90` | 50 – 100 | Aviso de armazenamento: a partir de quantos por cento cheio (50-100). Avisa de novo depois que o armazenamento cair 5 pontos abaixo. |
| `orderTimeout` | `0` | 0 – 604,800 | Autofabricação: segundos que um pedido em espera pode ficar parado antes de desistir, para jogadores que escolheram Padrão no F7 e pedidos sem jogador (0 = embutido: 1 min, 6 min enquanto uma máquina ainda trabalha). |
| `orderTimeoutMax` | `0` | 0 – 604,800 | Autofabricação: a espera mais longa que jogadores (F7) e Calculadoras de Processamento podem escolher, em segundos (0 = sem limite, Nunca permitido). |
| `littleStarLightBlocks` | `off` | on / off | A Estrelinha coloca blocos de luz invisíveis em lugares escuros (como até a 1.4.0)? Desligado = só brilha no cliente. |
| `furnaceXp` | `on` | on / off | Uma Calculadora de Processamento envia a experiência de uma fornalha para a rede como experiência líquida? |
| `cradleSpeed` | `100` | 1 – 100,000,000 | Berço Estelar: velocidade da vida das estrelas, em porcentagem (100 = normal). |
| `cradleRange` | `64` | 0 – 1,024 | Berço Estelar: alcance da interferência gravitacional e da fusão de buracos negros, em blocos. |
| `cradleFoodPerChronon` | `40` | 0 – 1,000,000 | Berço Estelar: quantos itens de alimento devorados geram um Chronon num buraco negro (0 = nenhum). |
| `cradleBlast` | `off` | on / off | Berço Estelar: uma supernova fracassada explode e quebra blocos? |
| `distRateBasic` | `2,000` | 1 – 2,000,000,000 | Distribuidor Estelar (Básico): FE por tick para energia e carregamento juntos. |
| `distRateRedDwarf` | `8,000` | 1 – 2,000,000,000 | Distribuidor Estelar (Anã Vermelha): FE por tick para energia e carregamento juntos. |
| `distRateYellowStar` | `32,000` | 1 – 2,000,000,000 | Distribuidor Estelar (Estrela Amarela): FE por tick para energia e carregamento juntos. |
| `distRateBlueGiant` | `128,000` | 1 – 2,000,000,000 | Distribuidor Estelar (Gigante Azul): FE por tick para energia e carregamento juntos. |
| `distRateNeutronStar` | `512,000` | 1 – 2,000,000,000 | Distribuidor Estelar (Estrela de Nêutrons): FE por tick para energia e carregamento juntos. |
| `distRateSingularity` | `0` | 0 – 2,000,000,000 | Distribuidor Estelar (Singularidade): FE por tick para energia e carregamento juntos (0 = ilimitado). |
| `distTargetsBasic` | `16` | 1 – 1,024 | Distribuidor Estelar (Básico): máximo de blocos que ele abastece (1-1024). |
| `distTargetsRedDwarf` | `32` | 1 – 1,024 | Distribuidor Estelar (Anã Vermelha): máximo de blocos que ele abastece (1-1024). |
| `distTargetsYellowStar` | `64` | 1 – 1,024 | Distribuidor Estelar (Estrela Amarela): máximo de blocos que ele abastece (1-1024). |
| `distTargetsBlueGiant` | `128` | 1 – 1,024 | Distribuidor Estelar (Gigante Azul): máximo de blocos que ele abastece (1-1024). |
| `distTargetsNeutronStar` | `256` | 1 – 1,024 | Distribuidor Estelar (Estrela de Nêutrons): máximo de blocos que ele abastece (1-1024). |
| `distTargetsSingularity` | `1,024` | 1 – 1,024 | Distribuidor Estelar (Singularidade): máximo de blocos que ele abastece (1-1024). |
| `distBaseCost` | `400` | 0 – 1,000,000 | Custo base do Distribuidor Estelar em 1/100 FE por tick (400 = 4 FE/t). |
| `distTargetCost` | `10` | 0 – 100,000 | Custo do Distribuidor Estelar por bloco abastecido em 1/100 FE por tick (10 = 0,1 FE/t). |
| `distLossFree` | `16` | 0 – 100,000 | Distribuidor Estelar: sem perda de transferência até esta quantidade de blocos. |
| `distLossStep` | `16` | 1 – 100,000 | Distribuidor Estelar: +1 % de perda a cada tantos blocos além disso. |
| `distLossMax` | `10` | 0 – 90 | Distribuidor Estelar: perda máxima por distância em porcentagem. |
| `distInfiniteLoss` | `15` | 0 – 90 | Distribuidor Estelar: perda em porcentagem além de todo nível de alcance (Alcance Infinito). |
| `distDimensionalLoss` | `25` | 0 – 90 | Distribuidor Estelar: perda em porcentagem para outra dimensão (Dimensional). |
