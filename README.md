# resumo-do-lab
Este repositório contém um resumo dos conteúdos e das lições aprendidas durante os laboratórios práticos e algumas aulas teóricas do bootcamp da DIO.

## Resumos das lições aprendidas

*Utilizo da notação em tópicos para me guiar nos estudos futuros. Essa metodologia funciona bem para mim*

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
      -  Básico: seleção da assinatura, grupo de recursos, nome da VM, região, opção de disponibilidade (conjunto de dimensionamento de máquinas virtuais, optando por sua escalabilidade manual ou automática, entre outras configurações), imagem, tamanhos da VM (consultar tabela de tamanhos), nome e senha do usuário, 
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
        - **Azure Data Box** - serviço de migração física (até 80 TB), como se fosse um HD externo
          - ![image](https://github.com/user-attachments/assets/8ca69b98-85e5-44ba-9db3-ca950ef0094f)
        - **AzCopy** -  Utilitário para copiar Blobs/arquivos para conta de armazenamento, com sincronização unidirecional
      - Opções de Gerenciamento de Arquivos
        - Gerenciador de Armazenamento Azure - interface gráfica do usuário, como um navegador. Compatível com todos os sistemas operacionais. "AzCopy com uma tela bonitinha"
        - Sincronização de Arquivos do Azure - sincroniza arquivos do Azure e on-premises de forma bidirecional
