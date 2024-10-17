# resumo-do-lab
Este repositório contém um resumo dos conteúdos e das lições aprendidas durante os laboratórios práticos do bootcamp da DIO, sendo eles:
- Microsoft Azure - Localizando Serviços por Categoria
- Criando máquinas Virtuais na Azure
- Configurando uma instância de Banco de Dados na Azure

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
