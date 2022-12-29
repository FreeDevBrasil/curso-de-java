# Parte 4 — Maven: Repositórios, bibliotecas, build e distribuição de dependências

Introdução
----------

Para gerenciar a parte técnico dos projetos escrito em Java, existem duas ferramentas principais, que são usadas que são Maven e Gradle. Também existem muitas outras, mas as outras ferramentas também dependem do Maven internamente, por isso é bom entender como funciona, mesmo utilizando uma ferramenta alternativa.

Gradle também é uma boa opção, mas não é tão popular quanto o Maven, a principal diferencia é que dentro do Gradle pode utilizar Kotlin ou Java, para configurar, e por isso é considerado mais complexo do que Maven, mas ao mesmo tempo se torna mais flexível. Gradle não existiria se não fosse o Maven, por que O GRADLE depende do Maven para buscar dependências e extensões para funcionar. Pode parecer que o Gradle é uma opção inferior por que Gradle traz as limitações do Maven além das suas próprias, mas tem seus casos de uso, mas o Gradle não faz parte do Curso, mas eu recomendo aprender o básico por que você vai encontrar de vez em quando em outros projetos de Java

Muitas outras ferramentas são utilizadas também, mas nenhuma delas é tão completa como o Maven, e uma delas, por exemplo ANT, era muito popular, mas é raro ver em projetos modernos.

Maven é projeto de código fonte aberto escrito em Java, e faz parte da fundação Apache. Maven é uma ferramenta com muita funcionalidade e pode aparecer muito complexo, mas isso é normal já que automatiza muitas tarefas do início ao final do seu projeto. Mesmo que você não utilize ele completamente, e raramente projetos utilizam todas as funcionalidades, O Maven sempre será útil para qualquer projeto de Java, e já é considerado o padrão da indústria.

Instalação
----------

Maven vem incluído em alguns IDEs como IntelliJ e também vem incluído em alguns projetos online para ser utilizado sem instalação nenhuma. Mesmo sendo incluído, no seu IDE ou no projeto que você está utilizando do momento, eu recomendo instalá-lo manualmente, pois vai ser bem útil no futuro. A instrução sore a instalação estão aqui e são três etapas mais importantes que vale a pena lembrar se for instalar:

1. Extrair o arquivo .zip em lugar accessível. Eu utilizo C:\apache-maven-3.8.6 por exemplo
2. Após instalação é importante configurar essas variáveis do sistema:
   * **M2_HOME**
   * **JAVA_HOME** (se não estiver configurado já)
   * E adicionar a pasta bin (No meu caso seria “C:\apache-maven-3.8.6“ ao seu PATH.
Fazendo isso traz o benéfico de pode utilizar o Maven fora do projeto e IDE.

Embora o Maven seja principalmente usado para projetos em Java, ele pode ser utilizado com qualquer linguagem, e isso é comum quando a maior parte do projeto é Java com módulos pequenos escritor em outras linguagens junto.

Passos de processamento do Maven
--------------------------------

Como mencionado, Maven cuida de gerenciamento técnico do início ao final (inclusive a própria entrega e instalação em servidores remotos):

1. **CLEAN**: *Limpeza da compilação anterior*
2. **VALIDATE**: *Validação do projeto, se está tudo certo como por exemplo se as dependências estão corretas*
3. **COMPILE**: *Compilação do código, de acordo com a configuração do projeto*
4. **TEST**: *Execução de testes automáticos*
5. **PACKAGE**: *Empacota seu projeto, dependendo da configuração, em bibliotecas, arquivos para servir em servidores e com extensões pode até preparar o seu projeto para instalação em maquinas comuns como executáveis e instalador, além de auto atualização. Normalmente vai produzir um JAR nesse passo* 
6. **VERIFY**: *Após de gerar os pacotes (packages) - Maven pode instalar esses pacotes para distribuição em repositórios globais, ou somente local para você utilizar em projetos separado na mesma maquina.*
7. **INSTALL**: *Além dos pacotes para ser executados ele prepara documentação automática (Javadoc ou outras), relatórios e qualquer coisa extra que seja necessário.*
8. **DEPLOY**: *E no final ele pode instalar o e configurar o projeto em servidor ou serviço de cloud remoto. 
