background-image: url(figures/outra-capa.png)

---

# Relembrando...

<blockquote>É inviável documentar a arquitetura em um único artefato.</blockquote>
<b>Documentação é comunicação.</b>
<br>
<img align="center" style="width: 100%;margin-left: 5px;margin-top: 18px" src="figures/visoes.png"/>
<p style="font-size:8px;position:absolute;left:80%">Copyright @ 2008 by Bredmeyer Consulting</p>

---

# Visões Arquiteturais

Viewpoints, Views, and Perspectives.

<img class="img-center" src="figures/livro-texto.jpg"/>

---

# Visões e Pontos de Vista

Uma <b>visão arquitetural</b> é a descrição de um aspecto do sistema.

<b>Ponto de vista</b> é uma coleção de padrões, templates e convenções que servem de guia para a construção das visões.

<img class="img-center" style="width: 60%;" src="figures/visao.jpg"/>

???

Aqui é importante frisar o conceito de divisão e conquista. As visões são criadas porque diminuem o problema. Juntas elas são capazes de descrever a arquitetura.

Pontos de vista agregam conhecimento legado para a construção de descrições arquiteturais. Há sim formalismos envolvidos, por exemplo, UML como linguagem de descrição pode uniformizar a maneira de descrever determinados aspectos da arquitetura. Contudo, na prática há uma heterogeneidade na maneira de descrever aspectos arquiteturais.

---

# Pontos de vista

- <b>Funcional</b>, <b>Informação</b> e <b>Concorrência</b> caracterizam a organização fundamental do sistema;
<br>
<br>
- <b>Desenvolvimento</b> existe para apoiar a construção do sistema; e
<br>
<br>
- <b>Implantação</b> e <b>Operação</b> caracterizam o sistema uma vez implantado em seu ambiente de execução.

???

O modelo de visões/pontos de vista é flexível o suficiente para você não precisar descrever usar todos os pontos de vista, por exemplo. Essa é a vantagem de ter um modelo com visões independentes. Além disso, cabe ao arquiteto decidir, em conjunto com stakeholders, o que e quanto descrever.

---
class: middle, center

# Funcional

---

# Funcional

<blockquote>Descreve os elementos funcionais do sistema, suas responsabilidades, interfaces e relacionamentos. Tipicamente é o primeiro aspectos que stakeholders estão interessados.</blockquote>

<img class="img-center" style="width: 80%;" src="figures/funcional.jpg"/>

---

# Funcional: visão geral

<b>Preocupações:</b> interfaces externas, organização interna e conceitos de projeto.

<b>Modelos:</b> Funcionais.

<b>Problemas e armadilhas:</b> interfaces e responsabilidades mal definidas, infraestrutura modelada como elementos funcionais, muitas dependências, *"god" elements* etc.

<b>Stakeholders:</b> todos.

<b>Aplicabilidade:</b> todos os sistemas.

---

# Funcional: elementos

<b>Elementos funcionais:</b> parte bem definida do sistema com uma responsabilidade particular e interface bem definida. Exemplo: módulo responsável por login, módulo reponsável por log etc, monitor etc.

<b>Interfaces:</b> definem as funções que podem ser acessadas por outros elementos. Definem entrada, saída e semântica das funções.

<b>Conectores:</b> pedaços da arquitetura que permitem a conexão entre dois elementos. A diferença para a interfaces é que conectores são complexos o suficiente para demandarem uma especificação mais detalhada. 

<b>Entidades externas:</b> outros sistemas, programas, dispositivos, serviços que estão além da fronteira do sistema.

<b>Exemplo de Notação formal:</b> diagrama de componentes.

---

# Funcional: Monitor

Importante: nem todos os exemplos são bons exemplos de descrição funcional. Vamos discutí-los um a um.

<img class="img-center" style="width: 80%;" src="figures/componentes.png"/>
<p style="font-size:10px;text-align:center">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Funcional: Webshop

<img class="img-center" style="width: 80%;" src="figures/componentes-2.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Funcional: Webshop

UML não é a única forma. Na verdade, vamos trabalhar com Sketches Arquiteturais. Lembre-se: o objetivo é <b>comunicar</b>. Notação é meio, não fim.

<img class="img-center"  src="figures/sketch.png"/>

???

- Uma crítica a esse modelo é que ele não isola visualmente os elementos externos. Usa esteriótipos para isso. É importante, mas do ponto de vista de disposição dos elementos, vale a pena deixar os elementos internos dentro de um retângulo que delimita as fronteiras.

---

# Funcional: Bash


<img class="img-center" style="width: 60%;" src="figures/bash.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Funcional: Eclipse

Este é um bom modelo funcional?

<img class="img-center" style="width: 60%;" src="figures/eclipse.png"/>
<p style="font-size:10px;text-align:center;">Copyright - http://aosabook.org/en/eclipse.html</p>

---

# Diretrizes para descrição da visão funcional

- Componente não é atividade. Por isso, não usamos verbos para declará-los.

- Identifique os componentes -- elementos de alto-nível com responsabilidades claras.

- Identifique os relacionamentos desses elementos -- dependência, generalização, composição, uso, chamada etc.

- Diferencie grupos de componentes com diferentes formas.

- Especifique protocolos de comunicação, quando possível/preciso.  

- Seja consistente na notação. Componentes e relacionamentos similares devem ter a mesma forma.

- Evite modelar infraestrutura na visão funcional.

- Cuidado para não tornar essa visão a visão de todas as outras.

---

# Por que esta não é uma boa descrição?

<img class="img-center" style="width: 80%;" src="figures/modelo-ruim.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>
???

O que esse modelo comunica?

Não sabemos que componentes existem no servidor.

O que significa as linhas pontilhadas?

Elementos de hardware que não cabem como funcionais.

Aparentemente há uma decomposição em APPServer. Não sabemos qual, nem quais foram as decisões de projeto.

Muito importante: atente-se para as descrições funcionais.

---

# Decisões ruins

Por que este modelo denuncia decisões ruins?

<img class="img-center" style="width: 90%;" src="figures/god.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

--

Vamos discutir um pouco sobre "god components/packages/classes", acoplamento e coesão.

---

# Desafio

Vamos representar a visão funcional do Google Docs?

---
class: middle, center

# Informação
---

# Informação

<blockquote>Descreve o modo como a arquitetura armazena, manipula, gerencia e distribui informação.</blockquote>

<img class="img-center" style="width: 80%;" src="figures/information.png"/>

---
# Informação: visão geral

<b>Preocupações:</b> estrutura, fluxo, controle de acesso, ciclo de vida, transações, qualidade, volume etc.

<b>Modelos:</b> diagrama de classes, diagrama de entidades e relacionamentos, diagrama de fluxo de dados, modelos estáticos de estruturas de dados, modelos de qualidade de dados etc.

<b>Problemas e armadilhas:</b> incompatibilidade, má qualidade, más definições de volume e esquemas.

<b>Stakeholders:</b> usuários, desenvolvedores, DBAs, entre outros.

<b>Aplicabilidade:</b> todo sistema que possui requisitos não-triviais de gerenciamento de informação.

---

# Informação: modelos estáticos de estruturas de dados

- Entidades
- Atributos
- Relacionamentos (associações)
- Cardinalidade

<img class="img-center" style="width: 70%;" src="figures/entidade-relacionamento.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Informação: modelos estáticos de estruturas de dados

<img class="img-center" style="width: 90%;" src="figures/classe.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Informação: Twitter

Como seria?

---

# Informação: fluxo

Foco no movimento da informação. Quais são os principais elementos arquiteturais e como a informação flui entre eles.

Muito adequado para sistemas *data-intensive*.


---

# Informação: Diagrama de fluxo de dados

Notação: Setas, Retângulos, Retângulos abertos e Elipses.

<img class="img-center" style="width: 70%;" src="figures/data-flow.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>


---

# Informação: Diagrama de máquina de estados

<img class="img-center" style="width: 90%;" src="figures/maquina-de-estados-uml.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>


---

# Informação: ePol

<img class="img-center" style="width: 90%;" src="figures/epol.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2020 by João Brunet</p>


???

Este diagrama tem relação forte com as regras de negócio do sistema. No caso do ePol, foi alvo de longas e profundas discussões até ser especificado em sua forma final. 

Hoje o diagrama serve de referência concreta para comunicar o ciclo de vida de um inquérito policial.

---

# Diretrizes para descrição da visão de informação

- Indentificar as entidades centrais em um sistema.

- Não é necessário detalhar toda e qualquer informação. Se seu modelo tem mais de 20 entidades e não cabe em uma página, ele não irá servir para o seu propósito, isto é, não irá comunicar.

- Você até pode, mas deve evitar diagramas de baixo-nível.

- Detalhes como acesso podem ser expressados como tabelas e comentários.

- Evitar detalhes desnecessários.

---

# Desafio

Vamos criar a máquina de estados de um post no instagram?

---
class: middle, center

# Concorrência
---

# Concorrência

<blockquote>Descreve a estrutura de concorrência do sistema. Identifica partes do sistema que são executadas concorrentemente e apresenta o controle dessa concorrência.</blockquote>

<img class="img-center" style="width: 40%;" src="figures/concorrencia.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Benjamin D. Esham</p>

---

# Concorrência: visão geral

<b>Preocupações:</b> organização das tarefas, mapeamento de elementos funcionais às tarefas, comunicação entre processos, gerenciamento de estado, sincronização, tolerância à falhas etc.

<b>Modelos:</b> modelos de estados e concorrência.

<b>Problemas e armadilhas:</b> complexidade, deadlock e condições de corrida.

<b>Stakeholders:</b> desenvolvedores, testadores e administradores.

<b>Aplicabilidade:</b> sistemas concorrentes.

---

# Concorrência

<img class="img-center" style="width: 75%;" src="figures/diagrama-concorrente.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

???

Não há uma notação padrão em UML. O que se faz é reusar componentes e pacotes e anotar identificando processos e threads, além da comunicação entre esses elementos.

---

# Concorrência

<img class="img-center" style="width: 50%;" src="figures/threads.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

---

# Concorrência


<img class="img-center" style="width: 50%;" src="figures/statechart.png"/>
<p style="font-size:10px;text-align:center;">Copyright - 2005 by Eoin Woods and Nick Rozanski</p>

???

Não é incomum o uso de diagrama de atividades.

---

# Diretrizes para descrição da visão de concorrência

- Seja consistente na notação.

- Identifique os estados.

- Identifique as transições e guardas.

- Se precisar detalhes, separe o ciclo de vida de algumas threads em outro modelo.

???

---

# Até aqui...

<img class="img-center" style="width: 75%;" src="figures/sofar.jpg"/>

???

É inviável documentar a arquitetura em um único artefato. Precisamos criar visões específicas para cada aspecto a ser documentado.

A visão funcional é provavelmente o cartão de visita da descrição arquitetural de um sistema.

Diagramas de entidades e relacionamentos e diagramas de classe são apropriados para descrever as entidades centrais de um sistema.

Máquinas de estados são excelentes para descrever o ciclo de vida de uma entidade. 

Máquinas de estados são excelentes referências para a implementação e testes das regras de negócio.

---
# Próxima aula

### Desenvolvimento, Implantação e Operação.