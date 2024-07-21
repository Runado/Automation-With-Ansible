# Ansible_Codes
 Neste repositório irei explorar a ferramenta Ansible para automação de tarefas voltada a administração de sistemas operacionais e redes de computadores.

#O que é o Ansible?
Ansible® é um mecanismo open source de automação. Ele ajuda a automatizar o provisionamento, o gerenciamento de configurações, a implantação de aplicações, a orquestração e muitos outros processos de TI.
É possível usar o Ansible para instalar software, automatizar tarefas do dia a dia, provisionar componentes de infraestrutura e rede, melhorar a segurança e a conformidade, aplicar patches em sistemas e orquestrar fluxos de trabalho complexos.


# Módulos

O Ansible se conecta aos nós (ou hosts) e envia a eles pequenos programas chamados módulos. Os nós são os endpoints de destino (servidores, dispositivos de rede ou qualquer computador) que você quer gerenciar com o Ansible. Os módulos são utilizados para realizar tarefas de automação no Ansible. Esses programas foram desenvolvidos para serem modelos de recursos do estado desejado do sistema. Em seguida, o Ansible executa os módulos e os remove ao terminar.

Sem eles, você dependeria de comandos ad hoc e scripts para realizar suas tarefas. Você pode usar os módulos integrados do Ansible para automatizar tarefas ou escrever os seus próprios módulos novos. Os módulos do Ansible podem ser escritos em qualquer linguagem que retorne JSON, como Ruby, Python ou bash. Os módulos de automação do Windows podem ser escritos até mesmo em Powershell. 

# Automação sem agentes 

O Ansible é uma ferramenta sem agentes, ou seja, não requer instalação de software para gerenciamento dos nós. Ele acessa seu inventário e lê as informações sobre quais máquinas você deseja gerenciar. O Ansible tem um arquivo de inventário padrão, mas você pode criar o seu próprio arquivo e definir quais servidores quer que sejam gerenciados. 

Ele usa o protocolo SSH para se conectar aos servidores e executar as tarefas. Por padrão, o Ansible usa chaves SSH com o ssh-agent e seu nome de usuário atual para se conectar a máquinas remotas. Não é preciso ter login de raiz. Acesse com qualquer usuário e execute os comandos su ou sudo.

Após se conectar, o Ansible transfere os módulos exigidos pelo comando ou pelo Ansible Playbook para serem executados na(s) máquina(s) remota(s). Ele usa templates YAML legíveis para os usuários programarem a automação de tarefas repetitivas sem precisar aprender uma linguagem de programação avançada.

# Como utilizar o Ansible para comandos ad-hoc 

Você também pode usar o Ansible para executar comandos ad-hoc, automatizando uma única tarefa em um ou mais nós gerenciados. Para isso, execute um comando ou chame um módulo usando a linha de comando. Nesse caso, nenhum playbook é usado e os comandos ad-hoc não são reutilizáveis. Essa é uma opção viável para tarefas pontuais. Já para tarefas frequentes ou complexas, é necessário usar um Ansible Playbook.

# Ansible Playbooks
Os Ansible Playbooks são usados para orquestrar processos de TI. Um playbook é um arquivo YAML que usa uma extensão .yml ou .yaml contendo uma ou mais plays. Ele é usado para definir o estado desejado de um sistema. Um módulo do Ansible, por sua vez, é um script autônomo que pode ser utilizado dentro do Ansible Playbook. 

As plays consistem em um conjunto ordenado de tarefas a serem executadas em hosts selecionados no arquivo de inventário do Ansible. As tarefas são os componentes da play que chamam os módulos do Ansible. Em uma play, as tarefas são executadas na ordem em que são escritas.

Quando o Ansible é executado, ele consegue controlar o estado do sistema. Se examinar o sistema e concluir que a descrição do playbook é incompatível com o estado real do sistema, o Ansible fará as mudanças necessárias para que o sistema corresponda ao playbook. 

O Ansible inclui um modo de verificação que permite a validação de playbooks e comandos ad-hoc antes de realizar mudanças de estado em um sistema. Essa função mostra o que o Ansible faria, mas sem efetivamente mudar nada. No Ansible, os manipuladoressó são utilizados para executar uma tarefa específica após uma modificação no sistema. Eles são disparados pelas tarefas e executados uma vez, no final de todas as outras plays do playbook.

As variáveis permitem alterar como os playbooks são executados para gerenciar diferenças entre sistemas, como versões de pacotes ou caminhos de arquivos. Com o Ansible, você pode executar playbooks em sistemas diferentes com um único comando. As variáveis dão conta das variações entre os sistemas. Elas podem ser definidas nos playbooks, no inventário, em arquivos ou funções reutilizáveis ou na linha de comando. Elas seguem a precedência de variáveis, que define a ordem em que uma substituirá a outra.

# Ansible Roles
são funções que formam um tipo especial de playbook portátil e totalmente autossuficiente, com grupos de tarefas, variáveis, templates de configuração e outros arquivos complementares que são necessários para concluir uma orquestração complexa. Uma coleção pode conter múltiplas funções. Isso facilita o compartilhamento de conteúdo via automation hub e Ansible Galaxy.

As coleções são um formato utilizado para distribuir conteúdo do Ansible. Elas podem incluir playbooks, funções, módulos, plug-ins e documentação agrupados em um pacote. Assim, criadores podem compartilhar e usar outros conteúdos de automação com mais facilidade. Essas coleções são classificadas por domínio de conteúdo e exigem menos preparação prévia para encontrar e montar diferentes funções e módulos.

O Ansible Content Collections funciona da mesma forma, mas foi desenvolvido especificamente para que usuários do Ansible Automation Platform acelerem a automação com conteúdo pronto criado pela Red Hat e nossos parceiros certificados. Essas coleções, que incluem Red Hat Ansible Certified Content e conteúdo validado do Ansible, foram desenvolvidas e testadas com a colaboração de parceiros para termos certeza de que são confiáveis, que priorizam a segurança e são adequadas ao uso empresarial.

