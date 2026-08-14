## Guilherme Reale

Desenvolvedor full stack sênior com foco em front-end. Estou há 3 anos na
[Liberta Investimentos](https://libertainvestimentos.com.br/), um dos maiores escritórios
credenciados à XP no Brasil: entrei terceirizado e fui efetivado depois de um ano e pouco.

Trabalho no **Liberta Play / TraderUp**, a plataforma de streaming do mercado financeiro do
grupo. É um produto com bastante coisa junta: catálogo de cursos e trilhas por perfil de
investidor, transmissões ao vivo com analistas, chat durante as lives, e a parte de venda com
carrinho e assinatura. O chat é nosso e os players são de terceiros (YouTube e Panda), então boa
parte do trabalho é manter e evoluir integrações sem quebrar quem está assistindo ao vivo.

Atuo da definição da estrutura do projeto até a entrega: escolha de arquitetura, padronização de
código, componentização reutilizável e revisão técnica. Quando o produto precisa, vou para o
back-end com Node.js, NestJS e banco relacional. Isso ajuda principalmente a decidir onde cada
responsabilidade deve ficar, em vez de empurrar complexidade para o outro lado do sistema.

Stack: React · Next.js · TypeScript · Angular · React Native · Expo · TailwindCSS · Node.js ·
NestJS · Express · Prisma · Zod · SQL · NoSQL · Azure DevOps

### Fora do trabalho

Engenharia reversa de formatos binários não documentados, quase sempre arquivos de jogo antigo:
mapeamento de containers proprietários, tabelas de ponteiros e edição de executáveis, com
ferramental próprio em Python. É de onde vem meu gosto por depurar o que não tem log e por
entender o sistema abaixo do framework.

Nos projetos pessoais uso NestJS na API, Next.js no web e React Native/Expo no mobile, com
Prisma e PostgreSQL, organizados como monorepo (pnpm + Turborepo).

### Projetos pessoais

[**esteticaautomotiva**](https://github.com/kreycai/esteticaautomotiva) — Micro-SaaS para
estúdio de estética automotiva. O operador registra os danos do carro tocando num mapa na tela
do celular, ainda no pátio. O Wi-Fi de galpão é ruim, então os danos entram numa fila local e
sincronizam quando a conexão volta: cada item leva um `clientId` para o reenvio não duplicar, e
erro 4xx é descartado em vez de retentado, senão um item travaria a fila inteira. O cliente
recebe o laudo por link e, quando aceita, o checklist é congelado com nome, IP e horário. Os
dados são separados por empresa desde o schema, com JWT e guard por papel.

[**pastelaria_alemao**](https://github.com/kreycai/pastelaria_alemao) — Web, API e mobile sobre
a mesma base. Cada pastel tem uma receita em gramas e cada matéria-prima tem preço por quilo,
então o sistema calcula o custo e a margem de cada produto, dá o lucro real do dia e monta a
lista de compras do que passou do mínimo, com estimativa de quanto vai custar. O alerta de
estoque só dispara quando o item cruza o limiar, e não a cada pedido — do outro jeito o dono
recebia notificação demais e desligava.

### Engenharia reversa

[**vc64_240p**](https://github.com/kreycai/vc64_240p) — 240p no Virtual Console de Nintendo 64
do Wii. É um patch no binário do emulador (PowerPC) para a saída ser 240p progressivo em vez de
480i, mais a remoção do filtro escuro que o VC aplica sobre o jogo. Testado em hardware real,
em quatro builds diferentes de emulador. Precisou ser no binário porque o display copy do GX não
reduz verticalmente, então não existe caminho pela API.

[**gungnir-ptbr**](https://github.com/kreycai/gungnir-ptbr) — Tradução completa de um RPG de PSP
que nunca saiu do Japão em português: 17.550 strings, parte na ISO e parte no EBOOT decriptado.
O trabalho difícil não foi traduzir. Foi descobrir que cada caractere acentuado precisa de
largura própria na tabela da fonte, senão as letras saem coladas, e que texto em português
estoura um limite de ponteiro e travava o jogo.

[**sword-of-mana-ptbr**](https://github.com/kreycai/sword-of-mana-ptbr) — Diálogo inteiro de um
jogo de GBA em português, 4.335 falas. Texto em português é mais longo que em inglês, e numa ROM
isso sobrescreve o dado seguinte. Em vez de encurtar a tradução para caber, expandi a ROM de 16
para 32 MB e reescrevi a tabela de ponteiros.

---

guireale@hotmail.com · [LinkedIn](https://www.linkedin.com/in/guilherme-reale-374615206/) · pronomes: ele/dele
