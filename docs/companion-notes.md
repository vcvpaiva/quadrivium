

Recapitulação rápida (26 Out 2026)

Valeria apresentou um projeto colaborativo para criar um banco de dados de correspondências de Curry-Howard, conectando lógicas, teorias de tipos e categorias. 
Ela propôs começar com sistemas já estabelecidos como álgebras de Heyting, categorias cartesianamente fechadas, o lambda-cálculo tipado simples, e sub-sistemas de lógica intuicionista, trabalhando de forma sistemática para identificar critérios estruturais para quando a correspondência Curry-Howard existe. 

A equipe discutiu usar dois bancos de dados existentes:
* o de Peter Jipsen para álgebras [CAL](https://github.com/jipsen/Algebras-and-Logics/tree/main) e
* o sistema [EPS](https://proofsystem.github.io/Encyclopedia/) (Enciclopédia de Sistemas de Prova) para sistemas de prova 
como base para suas investigações. 
Willian e outros colaboradores expressaram interesse em participar do projeto, com Willian criando um grupo no WhatsApp para facilitar a comunicação contínua.

Próximas etapas:
Valeria
- reescrever os slides corrigindo os erros e adicionando os links dos dois bancos de dados (CAL do Peter Jipsen e Enciclopédia de Sistemas de Prova)
- ~~criar uma template inicial preliminar para a quádrupla (sistema lógico, teoria de tipos, versão categórica e versão algébrica)~~
- criar a entrada para o sistema LP (Lambek with Permutation)
- ~~enviar o vídeo da gravação e os links no grupo de WhatsApp~~
- ~~enviar o resumo da conversa gerado pelo Zoom Companion no grupo de WhatsApp~~
Willian
- criar um grupo de WhatsApp para o projeto e incluir Valeria e os demais colaboradores
- compartilhar o link do grupo de WhatsApp com outras pessoas interessadas em colaborar
- explorar o banco de dados de Peter Jipsen para identificar álgebras interessantes para iniciar o trabalho
Colaboração
- Valeria e Willian: se encontrar em duas ou três semanas para discutir a template e avançar nos sistemas (começando por Heyting algebras/lógica intuicionista e
  depois Lp ou lógica linear intuicionista)
Resumo

Valeria apresentou um projeto para criar um banco de dados de correspondências de Curry Howard que conectará álgebras, categorias e lógicas. 
Ela explicou que o foco será em lógicas intuicionistas e subestruturais, evitando a lógica clássica devido às limitações da teoria de Joyal que impede a 
interpretação direta da lógica clássica em categorias cartesianamente fechadas. 
O projeto visa fazer correspondências sistemáticas começando por sistemas que já funcionam bem, como lógica intuicionista, lógica linear intucionista e o 
Lambek calculus, interpretando componentes individuais desses sistemas de forma composicional.

Programa de Pesquisa em Lógica Algébrica
Valeria apresentou um programa de pesquisa abrangente sobre lógica algébrica e cálculos categóricos, focando em reticulados residuados, BCI e BC algebras, e sistemas de prova. Ela propôs desenvolver uma taxonomia que ligue álgebras, lógicas, cálculos e categorias, começando pelos cálculos de Lambek e progressivamente adicionando mais complexidade até chegar à lógica intuitionista. O objetivo principal é descobrir novos critérios estruturais para quando o Curry-Howard existe, começando sistematicamente dos cálculos de Lambek mais simples antes de generalizar para estruturas categóricas mais complexas.
Lab Notes e Lambek Calculus

Valeria propôs criar Lab Notes para documentar o progresso e erros do trabalho, sugerindo reuniões quinzenais para atualizar essas notas e começar pelo Lambek 
Calculus sem as três regras estruturais. Ela explicou que o Github manteria versões antigas dos documentos, permitindo rastrear mudanças e erros ao longo do tempo. 
Valeria também mencionou que consultou Claude sobre as linhas de pesquisa atuais sobre Lambek calculus e recebeu cinco linhas de pesquisa em andamento, 
propondo revisar o trabalho já realizado e as aplicações subsequentes do Lambek calculus em linguagem e programação.

Sistemas Matemáticos e Tensors
Valeria e Willian discutiram sobre sistemas matemáticos, especificamente sobre o sistema LP de Van Benthem e o cálculo de Lambek. 
Valeria explicou conceitos relacionados a categorias, tensors e axiomas, mencionando que o tensor não é comutativo e preferindo o sistema com apenas uma implicação. Eles revisaram documentos e tentaram localizar informações específicas em arquivos e enciclopédias durante a discussão.
Sistemas Algébricos LP de Lambek
Valeria e Willian discutiram sistemas algébricos, focando no sistema LP de Lambeck com permutação, que Valeria descreveu como o mais fácil de trabalhar devido à sua estrutura de monóide com residuação comutativa. Valeria explicou que estão considerando diferentes categorias de álgebras e sistemas, incluindo estruturas multiplicativas, aditivas e exponenciais. Ela mencionou que haveria aproximadamente 357 tipos diferentes de estruturas algébricas no sistema e que planeja corrigir os slides adicionando links relevantes antes de compartilhar com a equipe.
Sistematização de Sistemas de Prova
Valeria discutiu diferentes sistemas de prova, incluindo os trabalhos de Bruno Paleo e Peter Jipsen, observando que ambos carecem de sistematização consistente. 
Ela explicou que a equipe planeja criar uma template que combine elementos das abordagens de Bruno e Peter Jipsen, incluindo componentes lógicos, teoria de tipos, 
versão categórica e versão algébrica para cada sistema desenvolvido. Valeria mencionou que Gisele, uma colaboradora brasileira, está mantendo uma enciclopédia de 
sistemas de prova com uma template específica que limita cada sistema a duas páginas no Github, uma boa ideia.

Desenvolvimento de Sistema de Lógica
Valeria propôs desenvolver um sistema de lógica que inclui quatro componentes principais: álgebras, categorias, sistema de termos) e a lógica. 
Will sugeriu que seria mais fácil começar pelo desenvolvimento das álgebras de Heyting,  que tem três conectivos (\land, \lor, \to) e duas constantes (\top,  \bot), considerando que 
seria mais fácil de implementar do que o sistema LP. Valeria se comprometeu a reescrever os slides corrigindo os erros e criando um template inicial para o sistema LP, com planos de finalizar os três sistemas em duas a quatro semanas.
Categorias Cartesianamente Fechadas e Morfismos
Valeria e Willian discutiram conceitos de categorias cartesianamente fechadas e morfismos, com Valeria explicando como aplicar essas noções em um projeto.
Eles concordaram em criar um grupo no WhatsApp para continuar a colaboração, onde Willian compartilhará a transcrição e um resumo da conversa. Javier participou
brevemente da discussão e expressou interesse em acompanhar o projeto, embora tenha mencionado a necessidade de se contextualizar melhor nos tópicos discutidos.

