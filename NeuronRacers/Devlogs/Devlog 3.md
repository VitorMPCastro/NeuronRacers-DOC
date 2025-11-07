# Avanços avanços, mas e a documentação?

## Data

7-11-25

---
# Interinas:

Basicamente todos os problemas mencionados nos devlogs passados foram resolvidos. E em adição a isso, andei com o projeto até um ponto onde estou confortável em apresentá-lo como um MVP.
Ainda falta um requisito funcional bem grande, que é permitir que o usuário modificasse as entradas para o MLP, mas ainda não tive o tempo de pensar bonitinho em como vou fazer a UI para isso, e estava focado em otimizar a performance do jogo. Mas dito isso, os principais avanços desde o último devlog foram:

- API de Dados Interna - eu escrevi uma API que é capaz de puxar os dados para qualquer carro e servi-los onde eles foram requisitados. Todo elemento de UI que exibe informações dos carros ou da corrida é alimentado por ela. Além disso, fiz uma integração com a feature de definição da função de fitness.
- UI Mínima - fiz uma UI mínima que viabilizasse a edição de alguns parâmetros dos carros e a utilização de um menu de debug.
- Grafo de exibição da rede neural - Fiz uma representação gráfica da rede neural para o carro sendo observado pela câmera.

	![[Pasted image 20251107055331.png]]

- Grafo de visualização de inputs - Fiz uma representação gráfica de como

	![[Pasted image 20251107055425.png]]

- Painel informacional para o carro observado

	![[Pasted image 20251107055502.png]]

- Leaderboard de exibição dos carros classificados por fitness

	![[Pasted image 20251107055606.png]]

- Editor de fitness por texto

	![[Pasted image 20251107055701.png]]

- Menu de debug para visualização dos carros

	![[Pasted image 20251107055754.png]]

- Menu de debug geracional

	![[Pasted image 20251107055836.png]]

- Menu de debug para a pista

	![[Pasted image 20251107055945.png]]

- Menu de debug para o sistema de progressão dos carros

	![[Pasted image 20251107060036.png]]

- Visualização dos limites de pista e da linha central

	![[Pasted image 20251107060140.png]]

- Visualização dos setores de corrida da pista

	![[Pasted image 20251107060225.png]]

- Visualização dos checkpoints na pista

	![[Pasted image 20251107060301.png]]

- Visualização dos sensores do carro

	![[Pasted image 20251107060359.png]]

E isso mais ou menos resume o trabalho que fiz na UI neste tempo. Agora, também tive a chance de apresentar meu projeto durante a semana de tecnologia da fatec campinas, onde também coletei as opiniões das pessoas que interagiram com meu projeto.

Ao todo, obtive 20 respostas ao meu formulário. Todas as pessoas concordaram em participar da pesquisa.

A vasta maioria dos respondentes, 19 (95%), acredita que o projeto cumpre bem o objetivo de demonstrar o aprendizado de agentes neurais em um ambiente simulado. Apenas 1 respondente (5%), disse que o projeto cumpre parcialmente com este objetivo.

Houveram também diversas sugestões para melhoria. E aqui estão elas:

- Vários participantes sugeriram adicionar cenários mais realistas, como uma pista ou um ambiente mais "vivo", e incorporar colisão para os veículos, a fim de tornar o projeto mais parecido com uma corrida real.
- Houve sugestões para uma interação aprimorada com o usuário, incluindo a capacidade de os usuários competirem com a IA, implementar interação do usuário e um criador de pistas.
- Alguns participantes elogiaram o projeto, destacando sua complexidade e o fato de sua estrutura ter sido desenvolvida do zero, o que agrega "autoridade e notoriedade".
- Outras sugestões incluíram otimizar a interface, simplificar os menus, aumentar os tamanhos das fontes para melhor compreensão e fornecer um documento para esclarecer conceitos.
- Alguns participantes não tiveram sugestões, afirmando que o projeto era "muito bom" ou "ótimo".
- Uma sugestão bem-humorada incluiu "Ak-47, lasers e dinossauros".

Aqui estão as respostas anônimas coletadas via forms:

|                     |                                            |                                                                                                                         |                                                                                                                                                                                               |
| ------------------- | ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Timestamp           | Você concorda com os termos acima?         | Em sua opinião, o projeto cumpre bem o objetivo de demonstrar o aprendizado de agentes neurais em um ambiente simulado? | Quais melhorias ou sugestões você gostaria de deixar para o projeto?                                                                                                                          |
| 10/29/2025 10:01:59 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Adicionar um cenário como se fosse uma pista ou um cenário mais vivo                                                                                                                          |
| 10/29/2025 10:02:09 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Pra mim já ta muito bom :)                                                                                                                                                                    |
| 10/29/2025 10:18:15 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Está tudo muito bem elaborado!                                                                                                                                                                |
| 10/29/2025 10:45:21 | Li e concordo em participar desta pesquisa | Parcialmente                                                                                                            | Ak-47, lasers, e dinossauros                                                                                                                                                                  |
| 10/29/2025 10:45:28 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Como você disse, adicionar colisão nos carros e deixar realista como uma corrida.                                                                                                             |
| 10/29/2025 10:45:59 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | O projeto está ótimo! Uma sugestão seria adicionar colisão para os veículos.                                                                                                                  |
| 10/29/2025 11:08:12 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | A interface estar um pouco mais otimizada                                                                                                                                                     |
| 10/29/2025 11:52:16 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Só elogio                                                                                                                                                                                     |
| 10/30/2025 9:12:31  | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Não pensei em uma melhoria                                                                                                                                                                    |
| 10/30/2025 9:17:14  | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Não tenho sugestões, gostei bastante do projeto                                                                                                                                               |
| 10/30/2025 9:26:45  | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Dar a oportunidade do usuário de competir com as IA's                                                                                                                                         |
| 10/30/2025 9:43:05  | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Apenas um elogio: diferente de outros projetos que envolvem redes neurais, esse teve o desenvolvimento da estrutura feito do zero. Isso da uma autoridade e notoriedade tremenda! Parabéns 🚀 |
| 10/30/2025 9:43:54  | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | O jogo cumpre muito bem com o objetivo, talvez uma melhoria no cenário para dar mais destaque.                                                                                                |
| 10/30/2025 10:11:28 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | O projeto está incrível e bem complexo, acho que a única coisa que poderia melhorar seria ser um pouco mais explicativo ou com os termos traduzidos( ex o fitness)                            |
| 10/30/2025 10:17:04 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | simplificação dos menus (fórmulas e aumento em algumas fontes para melhor entendimento) do programa e seria legal a adição de um criador de pistas.                                           |
| 10/30/2025 10:33:10 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Multiplayer e esquema de apostas                                                                                                                                                              |
| 10/30/2025 10:44:21 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Achei bem legal a ideia, o ruim é que não tenho ideias de como melhorar.                                                                                                                      |
| 10/30/2025 11:14:04 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Implementar interação com o usuário                                                                                                                                                           |
| 10/30/2025 11:37:40 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Para um projeto individual feito em dois meses, isso já ta ótimo!                                                                                                                             |
| 10/31/2025 11:09:14 | Li e concordo em participar desta pesquisa | Sim                                                                                                                     | Parabéns pelo projeto, interessante observar que seria interessante ter um documento que esclareça os conceitos utilizados                                                                    |

Em geral, observa-se que o projeto foi extremamente bem recebido. Mesmo sendo um MVP ele provou que já é capaz de chamar a atenção do público e cumprir satisfatoriamente sua meta de auxiliar no entendimento de como funcionam redes neurais e o aprendizado por reforço.