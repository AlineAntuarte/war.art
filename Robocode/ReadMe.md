## ReadMe para Robocode

Atualizado em 29-Jul-2021 por Flemming N. Larsen

[Página Inicial do Robocode](https://robocode.sourceforge.io/)

### ÍNDICE

- [ReadMe para Robocode](#readme-para-robocode)
  - [ÍNDICE](#índice)
  - [O QUE É ROBOCODE?](#o-que-é-robocode)
  - [HISTÓRIA DO ROBOCODE](#história-do-robocode)
  - [REQUISITOS DO SISTEMA](#requisitos-do-sistema)
  - [PRIMEIROS PASSOS](#primeiros-passos)
  - [API DO ROBOCODE](#api-do-robocode)
  - [REPOSITÓRIO DO ROBOCODE](#repositório-do-robocode)
  - [COMUNIDADE](#comunidade)
  - [DESAFIOS](#desafios)
  - [ENTRE NA COMPETIÇÃO](#entre-na-competição)
  - [LINHA DE COMANDO](#linha-de-comando)
  - [RELATAR PROBLEMAS / BUGS](#relatar-problemas--bugs)
  - [SOLICITAÇÕES DE FUNCIONALIDADES](#solicitações-de-funcionalidades)
  - [NOTÍCIAS](#notícias)
  - [COMO CONTRIBUIR](#como-contribuir)

### O QUE É ROBOCODE?

Robocode é um jogo de programação onde o objetivo é programar um tanque de batalha robótico para competir contra outros robôs em uma arena de batalha. O nome Robocode vem de "código de robô". O jogador é o programador do robô, que não terá influência direta no jogo. Em vez disso, o jogador deve escrever a IA do robô dizendo como ele deve se comportar e reagir aos eventos que ocorrem na arena. As batalhas acontecem em tempo real e são exibidas na tela.

O lema do Robocode é: *Construa o melhor, destrua o resto!*

Além de ser um jogo de programação, Robocode é usado para aprender a programar principalmente na linguagem Java, mas outras linguagens como Kotlin e Scala também são possíveis.

Escolas e universidades usam o Robocode como parte do ensino de programação e também para estudar inteligência artificial (IA). O conceito do Robocode é fácil de entender e uma maneira divertida de aprender a programar.

Robocode oferece um ambiente de desenvolvimento completo e vem com um instalador, editor de robôs embutido e compilador Java. Robocode só requer que um JRE (Java Runtime Environment) já esteja instalado no sistema. Assim, tudo que um desenvolvedor de Robocode (Robocoder) precisa para começar já está incluído no arquivo de distribuição principal (`robocode-xxx-setup.jar`). Robocode também suporta o desenvolvimento de robôs usando IDEs externas como:

- [IntelliJ IDEA](https://www.jetbrains.com/idea/)
- [Eclipse](https://www.eclipse.org/downloads/)
- [NetBeans](https://netbeans.apache.org/)
- [Visual Studio Code](https://code.visualstudio.com/)

Uma IDE externa auxilia muito mais o desenvolvedor do que o editor embutido do Robocode, que serve apenas para pequenos ajustes rápidos.

O fato de o Robocode rodar na plataforma Java permite que ele seja executado na maioria dos sistemas operacionais que suportam Java, como Windows, Linux, macOS e outros UNIX. Note que o Java 8 é a versão mínima exigida, mas versões mais recentes podem ser usadas. Veja os [Requisitos do Sistema](#requisitos-do-sistema) para mais informações.

Fique atento: muitos usuários do Robocode (também chamados de Robocoders) acham o Robocode muito divertido, mas também bastante viciante. :-)

Robocode é gratuito e desenvolvido como um projeto de lazer, sem fins lucrativos. Os desenvolvedores trabalham no Robocode porque acham divertido.

Robocode é um projeto [Open Source](https://pt.wikipedia.org/wiki/C%C3%B3digo_aberto), ou seja, todo o código-fonte é aberto para todos.

Robocode é fornecido sob os termos da [EPL](https://www.eclipse.org/legal/epl-v10.html) (Eclipse Public License).

### HISTÓRIA DO ROBOCODE

O jogo Robocode foi iniciado por Mathew A. Nelson como um projeto pessoal no final de 2000 e se tornou profissional quando ele o levou para seu trabalho na IBM, como um download do AlphaWorks, em julho de 2001.

A IBM se interessou pelo Robocode como uma forma divertida de aprender Java e promover a linguagem.

A inspiração para criar o Robocode veio do [Robot Battle](https://en.wikipedia.org/wiki/Robot_Battle), um jogo de programação criado por Brad Schick em 1994, que por sua vez foi inspirado pelo [RobotWar](https://en.wikipedia.org/wiki/RobotWar), um jogo para Apple II+ dos anos 1980.

Artigos da IBM e a comunidade do RoboWiki tornaram o Robocode muito popular como jogo de programação, sendo usado por anos em escolas e universidades ao redor do mundo.

No início de 2005, Mathew convenceu a IBM a liberar o Robocode como [Open Source](https://pt.wikipedia.org/wiki/C%C3%B3digo_aberto) no SourceForge. A comunidade começou a desenvolver suas próprias versões, como "Contributions for Open Source Robocode", RobocodeNG e Robocode 2006, por Flemming N. Larsen.

Eventualmente, Flemming assumiu o projeto Robocode no SourceForge em julho de 2006, continuando o desenvolvimento do jogo original. O projeto RobocodeNG foi abandonado e o Robocode 2006 foi fundido na nova versão oficial 1.1, com muitas melhorias. Desde então, várias versões foram lançadas com mais recursos e contribuições da comunidade.

Em maio de 2007, o cliente [RoboRumble](https://robowiki.net/wiki/RoboRumble) foi integrado ao Robocode, sendo amplamente usado para criar rankings de robôs nas competições 1-vs-1, Melee, Team e Twin Dual.

Em 2012, Julian ("Skilgannon") criou o [LiteRumble](https://robowiki.net/wiki/LiteRumble), um sistema leve de RoboRumble para rodar no Google App Engine.

Em maio de 2010, um **plugin .Net** foi disponibilizado, permitindo desenvolver robôs para o [.Net Framework](https://dotnet.microsoft.com/download/dotnet-framework/) 3.5 além do Java, graças a Pavel Savara.

Em abril de 2021, o plugin .Net foi descontinuado devido a problemas na ferramenta de build e documentação.

### REQUISITOS DO SISTEMA

Para rodar o Robocode, é necessário ter Java 8 ou superior instalado. Tanto o JRE quanto o JDK podem ser usados. O JRE não inclui o compilador padrão (javac), mas o Robocode vem com o compilador ECJ (Eclipse Compiler for Java), então o JRE é suficiente.

É importante configurar as seguintes variáveis de ambiente antes de rodar o Robocode:

- **JAVA_HOME** deve apontar para o diretório do Java (JDK ou JRE).  
  Exemplo Windows: `JAVA_HOME=C:\Program Files\AdoptOpenJDK\jdk-16.0.0.36-hotspot`  
  Exemplo Linux/macOS: `JAVA_HOME=/usr/lib/jvm/adoptopenjdk-16-hotspot-amd64`

- **PATH** deve incluir o caminho para o `bin` do Java (`JAVA_HOME`), onde está o executável `java`.  
  Exemplo Windows: `PATH=%PATH%;%JAVA_HOME%`  
  Exemplo Linux/macOS: `PATH=${PATH}:${JAVA_HOME}/bin`

Mais detalhes em:

- [Requisitos do Sistema](https://robowiki.net/wiki/Robocode/System_Requirements)

### PRIMEIROS PASSOS

A maior parte da documentação do Robocode está no [RoboWiki](https://robowiki.net/), mantido por Julian ("Skilgannon"). O RoboWiki é uma excelente fonte de informações sobre desenvolvimento no Robocode.

Recomenda-se ler os artigos do [RoboWiki](https://robowiki.net/) para começar. O primeiro artigo sugerido é:

- [Primeiros Passos](https://robowiki.net/wiki/Robocode/Getting_Started)

Leia sobre a anatomia de um robô, física do jogo, pontuação, etc.

### API DO ROBOCODE

A API do Robocode está disponível em:

- [Java Robot API](https://robocode.sourceforge.io/docs/robocode/)
- [Java Control API](https://robocode.sourceforge.io/docs/robocode/index.html?robocode/control/package-summary.htm)

A API do Robocode consiste em várias APIs:

- **Robot API**: No pacote Java `robocode`. Usada para desenvolver robôs, sendo a única parte acessível aos robôs.
- **Robot Interfaces**: No pacote `robocode.robotinterfaces`. Usada para criar novos tipos de robôs com APIs diferentes. **Nota:** As regras do jogo e comportamentos dos robôs não podem ser alterados.
- **Control API**: No pacote `robocode.control`. Usada para permitir que outra aplicação inicie batalhas com robôs selecionados e recupere resultados, além de snapshots de robôs e balas em momentos específicos.

### REPOSITÓRIO DO ROBOCODE

Para experimentar novos robôs além dos exemplos que vêm com o Robocode, visite o [LiteRumble home](https://literumble.appspot.com/) que contém muitos bots.

### COMUNIDADE

A comunidade do Robocode utiliza o [RoboWiki](https://robowiki.net/) como canal de comunicação. Lá, compartilham ideias, trechos de código, algoritmos, estratégias e muito mais. Documentação oficial dos desenvolvedores também é publicada lá.

No [RoboWiki](https://robowiki.net/), você encontra estratégias como:

- [Radar](https://robowiki.net/wiki/Radarr)
- [Movimentação](https://robowiki.net/wiki/Category:Movement)
- [Mira](https://robowiki.net/wiki/Category:Targeting)

E também trechos de código:

- [Code Snippets](https://robowiki.net/wiki/Category:Code_Snippets)

Você pode interagir com outros Robocoders em:

- O grupo [Robocode](https://groups.google.com/g/robocode) no Google.
- O grupo no [Facebook](https://www.facebook.com/groups/129627130234).

### DESAFIOS

Uma boa forma de evoluir como desenvolvedor de robôs é encarar desafios reais. No [RoboWiki](https://robowiki.net/), existem desafios famosos para testar movimentação, mira e armas dos robôs:

- [Desafios de Movimentação](https://robowiki.net/wiki/Category:Movement_Challenges)
- [Desafios de Mira](https://robowiki.net/wiki/Category:Targeting_Challenges)
- [RoboRumble Gun Challenge](https://robowiki.net/wiki/RoboRumble_Gun_Challenge)

Há muitos outros desafios disponíveis no RoboWiki além destes.

### ENTRE NA COMPETIÇÃO

Se quiser desafiar seu(s) robô(s) e a si mesmo como Robocoder, o [LiteRumble](https://robowiki.net/wiki/LiteRumble) é o melhor caminho. O LiteRumble mantém um [ranking atualizado](https://literumble.appspot.com/) dos bots do Robocode.

Não hesite em [entrar na competição RoboRumble](https://robowiki.net/wiki/RoboRumble/Enter_The_Competition).

### LINHA DE COMANDO

É possível especificar opções e propriedades predefinidas pela linha de comando ao rodar o Robocode. Para ver as opções, execute:

    robocode -help

Por exemplo, é possível:

- Desabilitar a interface gráfica (GUI).
- Desabilitar a segurança específica do Robocode (não substitui a segurança do JVM).
- Ativar/desativar o modo de depuração, útil para debugar robôs.
- Executar uma batalha baseada em um arquivo .battle existente.
- Repetir uma batalha gravada visualmente.
- Salvar os resultados das batalhas em um arquivo CSV.

Mais detalhes em:

- [Uso no Console](https://robowiki.net/w/index.php?title=Robocode/Console_Usage)

### RELATAR PROBLEMAS / BUGS

Se encontrar um problema no Robocode, reporte assim que possível.

O bug deve ser reportado na página de [Bugs](https://sourceforge.net/p/robocode/bugs/) no SourceForge. Cada bug será priorizado conforme seu impacto.

Ajuda muito descrever os passos para reproduzir o problema. Envie prints, código-fonte ou qualquer coisa que ajude a mostrar o bug. Informe também o sistema operacional, versão do Robocode e do Java.

Se for usuário registrado no SourceForge (registre-se [aqui](https://sourceforge.net/user/registration)), poderá adicionar um "monitor" ao seu relatório para receber notificações e acompanhar o status do bug.

Se você for desenvolvedor e souber como corrigir o bug, pode enviar um [pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) no [GitHub](https://github.com/robo-code/robocode). Assim, você se torna um contribuidor do Robocode. Saiba mais sobre como contribuir [aqui](#como-contribuir). Aceitamos correções sob os termos da [EPL](https://www.eclipse.org/legal/epl-v10.html).

### SOLICITAÇÕES DE FUNCIONALIDADES

Se tiver uma ideia para uma nova funcionalidade ou melhoria, compartilhe enviando uma solicitação ou iniciando uma discussão no grupo [Robocode Application Developers](https://groups.google.com/g/robocode-developers).

Solicitações devem ser feitas na página de [Feature Requests](https://sourceforge.net/p/robocode/feature-requests/) no SourceForge. Cada solicitação será priorizada conforme o impacto.

Se a funcionalidade for uma grande mudança, como alterar o comportamento dos robôs, pode não ser aceita, pois o Robocode é usado em competições como o [LiteRumble](https://literumble.appspot.com/).

Descreva sua ideia em detalhes e como ela pode ser implementada. Por exemplo, é possível estender uma funcionalidade existente?

Se for usuário registrado no SourceForge (registre-se [aqui](https://sourceforge.net/user/registration)), poderá adicionar um "monitor" à sua solicitação para receber notificações e acompanhar o status.

Se você for desenvolvedor e souber como implementar a funcionalidade, pode fazê-lo se ela for aceita. Assim, você se torna um contribuidor do Robocode. Saiba mais sobre como contribuir [aqui](#como-contribuir). Aceitamos implementações sob os termos da [EPL](https://www.eclipse.org/legal/epl-v10.html).

### NOTÍCIAS

Notícias sobre o Robocode são publicadas no blog do projeto. É possível assinar o feed RSS para receber novidades.

- [Notícias do Robocode](https://robo-code.blogspot.com/)

Você também pode seguir o Robocode no Twitter e Facebook:

- [Twitter do Robocode](https://twitter.com/robocode)
- [Robocode no Facebook](https://www.facebook.com/group.php?gid=129627130234)

O RoboWiki também está no Twitter:

- [Twitter do RoboRumble](https://twitter.com/robowiki)

### COMO CONTRIBUIR

Se quiser contribuir com o Robocode, por exemplo, com uma nova funcionalidade ou correção de bug, comece lendo o [Guia do Desenvolvedor para construir o Robocode](https://robowiki.net/wiki/Robocode/Developers_Guide_for_building_Robocode).

Aceitamos mudanças de código sob os termos da [EPL](https://www.eclipse.org/legal/epl-v10.html).

Existe pouca ou nenhuma documentação sobre o funcionamento interno do Robocode, então o código-fonte precisará ser analisado para entender como tudo funciona. É necessário ser um desenvolvedor Java experiente.

O Robocode é dividido em vários módulos. Veja o post do Pavel Savara para uma boa visão geral:

- [Módulos do Robocode](https://zamboch.blogspot.com/2009/06/robocode-modules-as-in-version-17.html)

Ajuda sobre o funcionamento interno pode ser obtida no grupo [Robocode Application Developers](https://groups.google.com/g/robocode-developers), onde você pode se registrar e iniciar um novo tópico.

Se a contribuição envolver menos de 10 arquivos, o preferido é enviar um [pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests) no [GitHub](https://github.com/robo-code/robocode).

Seu pull request será revisado e testado antes de ser aceito e mesclado ao Robocode. Mudanças adicionais podem ser feitas por outros desenvolvedores para finalizar ou ajustar o trabalho.
