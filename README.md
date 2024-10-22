# resumo-do-lab
Este repositório contém um resumo dos conteúdos e das lições aprendidas durante os laboratórios práticos e algumas aulas teóricas do bootcamp da DIO.

## Resumos das lições aprendidas

*Utilizo da notação em tópicos para me guiar nos estudos futuros. Essa metodologia funciona bem para mim*
*Não utilizar ferramentas/recursos em versão prévia para ambientes de produção*

## Módulo 1 | Conceitos Iniciais de Cloud com Azure

### Microsoft Azure - Localizando Serviços por Categoria

  - Configuração do idioma no Portal Microsoft Azure
  - Configuração da aparência do Portal Microsoft Azure
  - Introdução aos recursos oferecidos no Portal Microsoft Azure
  - Entendimento das ferramentas oferecidas separadas por categorias
  - Introdução a como navegar e utilizar dos recursos do Portal Microsoft Azure

### Criando máquinas Virtuais na Azure

  - Entendimento de todos os benefícios da computação: alta disponibilidade, escalabilidade, elasticidade, confiabilidade, previsibilidade, segurança, governança e gerenciabilidade
  - Categorização do tempo de inatividade de acordo com o % de SLA cotratado (quanto maior o número de 9's, menor o tempo de indisponibilidade)
  - Configuração das opções de disponibilidade para criação de máquinas virtuais na Azure
  - Utilização do botão "Saiba mais" para acessar a documentação dos tópicos
  - Criação de contas de armazenamento - replicação de dados entre data centers e/ou regiões
  - Pontos importantes para avaliação antes das configurações dos itens acima, levando em consideração contextos financeiros e estruturais da empresa em questão

### Configurando uma instância de Banco de Dados na Azure

  - Como criar máquinas virtuais no Portal Microsoft Azure
  - Configuração do sistema operacional da VM e seu valor de cobrança
  - Adição de discos além da VM padrão
  - Configurações de rede e gerenciamento (proteção, desligamento automático)
  - Importância do entendimento das necessidades e configurações necessárias de acordo com o contexto e a estratégia da empresa em questão
  - Introdução às configurações da criação de um banco de dados SQL

## Módulo 2 | Arquitetura e Serviços Azure

### Construindo Arquiteturas no Azure

  - Não consegui realizar na prática, pois minha conta gratuita na azure já expirou. Estou acompanhando com bastante atenção e visualizando as etapas com calma.
  - Criação de grupos de recursos para exemplificar seu uso e configuração do mesmo
  - Inclusão de uma rede virtual de uma outra região no grupo de recursos, para comprovar que é possível ter recursos de diferentes regiões no mesmo grupo

### Computação e Rede

  - Tipos de computação
    - Computação do Azure - serviço sob demanda que fornece inúmeros recursos
    - Máquinas virtuais (VM's) - emulação de um software físico. Dono possui controle total.
    - Conjunto de dimensionamento de VM's - balanceamento de cargas, garante dimensionamento automático dos recursos
    - Conjuntos de disponibilidade de VM's - diferentes domínios de falha com diferentes VM's em diferentes domínios de atualização, garantia contra indisponibilidade física/virtual.
      - Menor número de hosts disponíveis: sempre o menor número de VM's em um domínio de falha.
    - Área de trabalho virtual do Azure - execução completa de aplicativo pela nuvem, como um desktop personalizado
      - Redução de perda de recursos físicos
      - Gerenciamento de acessos e licenças
    - Serviçoes de Contêineres do Azure (PaaS) - ambiente leve e virtualizado **sem necessidade de gerenciamento do sistema operacional** e responde sob demanda a atualizações/alterações
        - Instâncias de um contêiner: Oferta de PaaS executa um contêiner no Azure
        - Aplicativos de contêiner: balanceamento de carga e escalabilidade
        - Kubernetes do Azure: orquestração para contêineres - arquiteturas distribuídas com grandes números de contêineres (gerenciamento do ciclo de vida)
    - Azure Functions - oferta PaaS que suporta operações de computação sem servidor, baseado em eventos/ocorrências
  
    - **Comparação das opções de computação do Azure**
      - VM's - útil para migrações lift-and-shift com pacote de sistema operacional completo
      - Área de trabalho cirtual - experiência de desktop com aplicativos definidos e selecionados. Recursos limitados de acordo com o acesos
      - Contêineres - ambiente leve e em miniatura para microsserviçoes. Garante escalabilidade e resiliência pela orquestração (AKS)
  
    - Serviços de Aplicativo da Azure - plataforma para criação, implementação e dimensionamento de aplicativos Web e API. Oferta PaaS.
    - Serviços de Rede do Azure - VNET permite comunicações entre os recursos do Azure, extremidades públicas e privadas. Permite criação de sub-redes virtuais. Atenção para não criar na mesma faixa de IP das redes on-premises (OVERLAP)
    - Gateaway de VPN - envio de tráfego criptografado entre rede virtual e local
      - ExpressRoute - "Gateway" físico feito por cabos de fibra ótica
    - DNS (Domain Name Service) do Azure - gerenciamento de recursos externos e do azure com um único serviço de DNS (possibilidade de apontar conjuntos de registros para um único DNS)
 
 ### Configurando Recursos e Dimensionamentos em Máquinas Virtuais na Azure

  - Criação de VM's
    -  Possibildiade: Seleção do ambiente de trabalho e da carga de trabalho, configurações e recursos já pré-definidos de acordo com as seleções
      -  Básico: seleção da assinatura, grupo de recursos, nome da VM, região, opção de disponibilidade (conjunto de dimensionamento de máquinas virtuais, optando por sua escalabilidade manual ou automática, entre outras onfigurações), imagem, tamanhos da VM (consultar tabela de tamanhos), nome e senha do usuário, 
      -  Discos: portas de entrada, tamanho de disco, checkar "excluir com VM" (apagar o disco junto com a exclusão da VM, evitar discos órfãos).
      -  Rede: Seleção da rede virtual, "Excluir o IP público e a NIC quando a VM for excluída"
      -  Gerenciamento: Identidade, Azure AD, desligamento automático (mas não tem ligamento automático), email de notificação para usuário definido, habilitar backup.
      -  Monitoramento: definir alertas para receber notificações, diagnóstico
      -  Avançado: seleção de extensões para ser instalada na VM, apliativos da VM
      -  Marcas: importante para governança
      -  Revisar + criar: finalização do processo, apresentação do preço e termo de autorização

    - Área de Trabalho Virtual
      - Modelos de host: Pessoal (casos específicos com softwares específicos) ou Em pool (para várias instâncias com balanceamento de carga)
      - Adição de VM's

    - Aplicativos de Funções - necessário ter uma conta de armazenamento
      -  Nomear
      -  Código ou imagem de contêiner
      -  Pilha de runtime (linguagem)
      -  Versão da linguagem
      -  Região
      -  Opções de hospedagem
      -  Sistema operacional

### Armazenamento

  - Serviços de armazenamento
     - Contas de armazenamento
      - Precisa ter um nome GLOBALMENTE exclusivo
      - Fornece acesso à internet em todo o globo
      - Seleção de serviços de armazenamento e opções de redundância
        - Redundância - quanto de disponibilidade vou ter da informação. Quanto maior o número de 9's na durabilidade, maior a disponibilidade do armazenamento
          - LRS - modelo não indicado para ambientes de produção (3 cópias no mesmo datacenter)
          - ZRS - modelo indicado para ambientes de produção (3 cópias em 3 datacenters diferentes)
            - ![image](https://github.com/user-attachments/assets/d5f1995f-8da9-4250-9525-f88fba109ca3)
        - Tipos de Armazenamento
          - Blob - otimizado para armazenamento massivo de **dados não estruturados** ( [...] <storage-account-name>.blob [...] )
            - Pode receber diversos tipos e categorias de dados, funciona como uma caixa
          - Disco - fornecimento de discos para VM's, apps e outros serviços ( [...] <storage-account-name>.dfs [...] )
          - Fila - armazenamento de mensagens ( [...] <storage-account-name>.queue [...] )
          - Arquivos - compartilhamento de arquivos de rede altamente disponível, "pasta na nuvem" ( [...] <storage-account-name>.file [...] )
          - Tabelas - opção de chave para dados estruturados não relacionais em designs sem esquema ( [...] <storage-account-name>.table [...] )
    - Camadas de acesso
      - Frequente - otimizada para dados acessados com frequência
        - Esporádico - otimizada para dados acessados com pouca frequência e armazenado por pelo menos 30 dias
        - Frio - otimizada para dados acessados com pouca frequência e armazenado por pelo menos 90 dias
          - Arquivo morto - otimizada para dados acessados raramente e armazenado por pelo menos 180 dias
    - Migrações para o Azure
      - Plataforma unificada para migração
      - Intervalo de ferramentas integradas e autônomas
      - Avaliação e migração
      - **Azure Data Box** - serviço de migração física (**até 80 TB**), como se fosse um HD externo
        - ![image](https://github.com/user-attachments/assets/8ca69b98-85e5-44ba-9db3-ca950ef0094f)
      - **AzCopy** -  Utilitário para copiar Blobs/arquivos para conta de armazenamento, com sincronização unidirecional
    - Opções de Gerenciamento de Arquivos
      - Gerenciador de Armazenamento Azure - interface gráfica do usuário, como um navegador. Compatível com todos os sistemas operacionais. "AzCopy com uma tela bonitinha"
      - Sincronização de Arquivos do Azure - sincroniza arquivos do Azure e on-premises de forma bidirecional

#### Laboratório - Armazenamento

  - Contas de armazenamento
    - Assinatura, grupo de recursos, nome da conta (GLOBALMENTE exclusivo, 3 a 24 caracteres, sem caracteres especiais e com letas minúsculas apenas), região, desempenho (standard - maioria dos cenários; premium - cenários com baixa latência) e redundância (LRS, ZRS, GRS ou GZRS)
      - Armazenamento de blobs (quente ou frio), acesso a rede (privado ou público)
      - Habilitar ou não a exclusão automática de blobs
- Contêiners (mais usados) - Blobs
- Compartilhamento de Arquivos (mais usados)
  - Gera o script completo para configurar uma máquina e utilizar dos arquivos dentros do compartilhamente de arquivos criado
  - Modelo de replicação
  - Modelo de camada (quente ou frio)
- Fila
  - Utilizada para aplicações
- Tabela

  - Migrações para Azure
    - Criação de um projeto e seleção de sua geografia
    - Dentro do Portal, existem ferramentas de avaliação para entendimento da estratégia de migração mais recomendada
    - DataBox - selecionar tipo de transferência (importação ou exportação do azure), assinatura, grupo de recursos, região de origem e de destino
      - Comparação dos preços de acordo com o tamanho (DataBox disk, DataBox, DataBox Heavy)
      - Volumes muito grandes de informações

  - AzCopy
    - Funciona para todos os sistemas operacionais
    - Download do AzCopy
    - Criação de um novo contêinere - alterar as permissões e checkar todas elas e copiar o token SaaS gerado
    - Copiar um código presente na documentação de criação do AzCopy
    - Utilizar o prompt de comando para realizar a cópia, indicando a pasta correta e colando o token com as alterações necessárias
    - Os dados são copiados a partir do AzCoy e salvos na nuvem Azure

  - Gerenciador de Armazenamento do Azure
    - Seleção de recurso e ambiente do Azure
    - Visualmente mais "fácil"


    ### Identidade, Acesso e Segurança

    -  Serviços de Diretório
      -  Microsoft Entra ID - antigo Azure Active Directory
        - Serviço de gerenciamento de identidades e acesso em nuvem
          - Autenticação
          - Logon único (SSO) - evitar diversos usuários e senhas
          - Gerenciamento de aplicativos
          - B2B
          - Gerenciamneto de dispositivos
![image](https://github.com/user-attachments/assets/c967f2a6-7ff7-44ab-8a93-d1b38d5fb41d)
        - Benefícios dos serviços de domínio baseados em nuvem, sem gerenciar os controladores de domínio
        - Execução de aplicatvios herdados na nuvem
        - Sincronização automática pelo Microsoft Entra ID

    - Diferença entre Autenticação e Autorização
      - Autenticação (liberação no prédio)
        - Identificação de pessoa/serviço para acesso a um recurso
        - Solicitação de credenciais legítimas
        - Controle de acessos seguros, princípios de identidade
      - Autorização (liberação à áreas específicas)
        - Nível de acesso a uma pessoa/serviço autenticada(o)
        - Quais dados podem ser acessados

    - Métodos de Autenticação
      - Autenticação Multifator (MFA)
        - Fornece segurança adicional, exigindo dois ou mais elementos de autenticação
        - Fatores
          - Algo que você sabe (login e senha)
          - Algo que você possui (chave, cartão)
          - Algo que você é (validação facial)
      - B2B do Microsoft Entra External  ID
        - Colaboração B2B de usuários externos
        - Parceiros, fornecedores, outros colaboradores
      - B2C de identidades Externas do Azure AD
        - Compartilhamento de pequenas % de meus recursos para utilização do usuário
        - "Login" a partir do email em sites de e-commerce

    - Modelos de Segurança
      - Acesso Condicional
        - Associação de usuário/grupo
        - Local do IP
        - Dispositivo
        - Aplicativo
        - Detecção de risco
      - Controle de Acesso Baseado em Função (ou RBAC: Role Based Access Control)
        - Gerenciamento dos acessos por granularidade fina
        - Apenas acessos necessários para o desempenho das funções do colaborador
        - ![image](https://github.com/user-attachments/assets/ba0a5e98-5373-47ab-a932-05e5dfd4d62c)
      - Confiança Zero / Proteção Completa
        - Proteção dos recursos através do pressuposto de que algo foi violado
        - Proteção dos ativos em qualquer lugar com uma política central
        - ![image](https://github.com/user-attachments/assets/416e6067-a906-4840-9f8c-56652ab32c4e)
      - Microsoft Defender para Nuvem
        - Serviço de monitoramento contra ameaças nos datacentes da Microsoft e outras nuvens
        - ![image](https://github.com/user-attachments/assets/16be232d-9198-45fc-b4f7-ffaf78f833d4)
        - Recomendações de segurança e controles de acesso just-in-time

#### Laboratório - Identidade, Acesso e Segurança

  - Microsof Entra ID
    - Responsável por represar e administrar os usuários
    - Introdução ao menu do recurso
      - Ponto de atenção para as regras (Roles and administrators) - o que o usuário pode fazer com relação a outras contas
        - Para criar "roles" personalizados, é necessário de uma licença mínima das MS Entra ID Premium P1 ou P2
        - Add role assignement - dar acesso necessário para os colaboradores de acordo com o contexto da função
      - Usuário - Contas dos usuários, nome principal, tipo de membro, sincronizando de uma conta on-premise
        - Ao excluir um usuário do Entra ID, é possível restaurar o usuário por até 30 dias depois de sua exclusão automática - Alternativa para recuperar arquivos relacionados ao usuário inativado
      - Possibilidade de Self-Service Password Reset (SSPR) - ao esquecer a senha, o próprio usuário pode alterar sua senha
        - Caso contrário, alguém com o role HelpDesk deve alterar para a pessoa
      - Possibilidade de upar um .csv para criar "bateladas" de usuários
    - O acesso "free" é muito limitado para uma organização, não é o indicado
    - Health - Report do SLA
  
  - Microsof Defender for Cloud
    - "Termômetro" - indica a qualidade da segurança a partir de um Secure Score
    - Recomendações no quesito segurança e o quanto isso impacta no Secure Score
    - Traz recomendações de outros cloud providers também (GCP, AWS,..)
    - Central de alertas - possibilidade de configuração de alertas a serem recebidos por email ou outras ferramentas
    - Attack path analysis - possíveis "portas abertas" para a internet
    - 
  - 
 


    
