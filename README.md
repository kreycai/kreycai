## Guilherme Reale

Dev full stack. TypeScript dos dois lados — **NestJS** e **Next.js** na maior parte do tempo,
**React Native/Expo** quando o usuário está de pé com o celular na mão, **Prisma + PostgreSQL**
embaixo. Trabalho em monorepo (pnpm + Turborepo) porque quase todo sistema que eu construo
acaba tendo mais de uma cara: um painel, uma API e um app.

Fora do horário eu faço engenharia reversa de console antigo — patch de binário PowerPC,
tradução de ROM, formato de arquivo sem documentação. Parece hobby desconexo, e não é: é o
mesmo trabalho de ler um sistema que ninguém explicou e descobrir onde encostar a mão.

---

### Sistemas

**[esteticaautomotiva](https://github.com/kreycai/esteticaautomotiva)** — Micro-SaaS para
estúdio de estética automotiva. O operador mapeia os danos do carro tocando num SVG no celular,
**no pátio, com Wi-Fi ruim** — a fila de sincronização é offline, idempotente por `clientId`, e
classifica erro transitório (retenta) versus permanente (descarta, pra não travar a fila). O
cliente recebe o laudo por link público e o **aceite congela o checklist** com nome, IP e
horário. Multi-tenant desde o schema, JWT + guard por papel.

**[pastelaria_alemao](https://github.com/kreycai/pastelaria_alemao)** — Três apps (web, API,
mobile) sobre uma base. O que muda o jogo: **o sistema conhece a receita de cada pastel**, então
o estoque baixa por pedido e o lucro é calculado do custo real dos ingredientes, não estimado. O
alerta de estoque só dispara quando o item *cruza* o limiar — senão o celular do dono virava spam
e ele desligava a notificação.

### Engenharia reversa

**[vc64_240p](https://github.com/kreycai/vc64_240p)** — 240p real no Virtual Console de
Nintendo 64 do Wii. Patch no binário do emulador (PowerPC) pra sair em 240p progressivo em vez
de 480i, e remoção do filtro escuro que o VC aplica por cima do jogo. Confirmado em hardware
real, em quatro builds diferentes de emulador. Os dois patches existem porque **a via
convencional não existe**: o display copy do GX não sabe reduzir verticalmente.

**[gungnir-ptbr](https://github.com/kreycai/gungnir-ptbr)** — Tradução completa de um RPG de
PSP que nunca saiu do Japão em português: 17.550 strings, dentro da ISO e dentro do EBOOT
decriptado. A parte difícil não foi traduzir — foi que acento precisa de largura própria na
tabela de fonte, senão sai letra colada, e que texto em português estoura ponteiro e travava o
jogo.

**[sword-of-mana-ptbr](https://github.com/kreycai/sword-of-mana-ptbr)** — Diálogo inteiro de um
GBA em português: 4.335 falas. Texto em português é mais longo que em inglês, e em ROM isso
sobrescreve o vizinho. Em vez de cortar a tradução pra caber, **expandi a ROM de 16 para 32 MB e
reescrevi a tabela de ponteiros.**

---

### Como eu trabalho

Três coisas aparecem em tudo que eu escrevo, e são as que eu defendo numa revisão de código:

**Dinheiro não é `float`.** É `Decimal` no banco. Somar centavos em ponto flutuante acumula erro,
e num sistema que fecha caixa isso aparece na conta do dono.

**O histórico é imutável.** Item de pedido guarda o preço do dia da venda; movimento de estoque
guarda a entrada e a saída, não só o saldo. Mudar o preço amanhã não pode reescrever o
faturamento de ontem, e saldo errado sem histórico é discussão sem fim.

**O caso ruim é o caso normal.** Wi-Fi cai, o cliente contesta, o alerta vira spam. Isso não é
borda — é a terça-feira do usuário. Prefiro projetar pra ele.

---

📫 **guireale@hotmail.com** · [LinkedIn](https://www.linkedin.com/in/guilherme-reale-374615206/) · pronomes: ele/dele
