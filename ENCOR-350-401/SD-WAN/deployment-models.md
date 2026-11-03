# CCNP Enterprise — ENCOR 350-401

## SD-WAN Deployment Models

> **Tema:** Software-Defined Wide Area Network (SD-WAN)  
> **Nível:** Introdução ao CCNP Enterprise  
> **Status:** Documentação teórica inicial — laboratório ainda não realizado

## 1. Objetivo

Compreender os modelos de implantação de SD-WAN, suas diferenças e os critérios para selecionar uma abordagem em redes corporativas.

## 2. Conceito de SD-WAN

SD-WAN (Software-Defined Wide Area Network) é uma abordagem de arquitetura WAN que utiliza controle centralizado por software, políticas e automação para conectar filiais, datacenters e aplicações em nuvem por diferentes meios de transporte.

Transportes possíveis incluem Internet banda larga, MPLS e redes móveis 4G/5G. A disponibilidade de cada transporte depende do ambiente e do projeto.

**Atenção:** SD-WAN não é sinônimo de Internet pública nem substitui, por definição, todos os circuitos MPLS.

## 3. Arquitetura Cisco SD-WAN: visão inicial

Na arquitetura Cisco Catalyst SD-WAN, as funções são separadas logicamente:

| Função | Papel | Nome tradicional em materiais de estudo |
|---|---|---|
| Gerenciamento | Interface central de administração e visibilidade | vManage |
| Controle | Distribuição de rotas e políticas por meio do OMP | vSmart |
| Orquestração | Auxilia no estabelecimento inicial de conectividade e autenticação | vBond |
| Data plane | Encaminha o tráfego entre os sites | WAN Edge (cEdge/vEdge) |

Os nomes e detalhes de implantação podem variar conforme a versão da solução Cisco.

## 4. Modelos de implantação

### 4.1 On-premises

Os componentes de gerenciamento e controle são hospedados na infraestrutura administrada pela própria organização.

**Vantagens potenciais:** maior controle sobre a hospedagem e integração com ambientes internos.

**Pontos de atenção:** capacidade computacional, disponibilidade, atualizações, backups e operação da plataforma.

### 4.2 Cloud-hosted

Os componentes de gerenciamento e/ou controle são hospedados em infraestrutura de nuvem, conforme o serviço e a arquitetura contratados.

**Vantagens potenciais:** menor necessidade de infraestrutura local para controladores e facilidade de expansão.

**Pontos de atenção:** conectividade, requisitos regulatórios, modelo de responsabilidade e dependências do provedor.

### 4.3 Híbrido

Combina componentes ou recursos hospedados localmente e na nuvem, conforme os recursos e versões suportados pela solução.

**Vantagens potenciais:** flexibilidade para requisitos específicos e transições arquiteturais.

**Pontos de atenção:** compatibilidade, desenho de alta disponibilidade, conectividade e complexidade operacional.

> **Distinção importante:** modelo de implantação dos controladores (on-premises/cloud/híbrido) não é a mesma coisa que topologia de conectividade WAN (hub-and-spoke, full mesh ou parcial).

## 5. Comparação resumida

| Critério | On-premises | Cloud-hosted | Híbrido |
|---|---|---|---|
| Hospedagem dos componentes | Ambiente próprio | Infraestrutura de nuvem | Combinada |
| Responsabilidade operacional | Predominantemente interna | Compartilhada, conforme contrato | Compartilhada e variável |
| Infraestrutura local necessária | Maior | Menor para controladores | Variável |
| Complexidade de integração | Dependente do ambiente | Dependente do serviço | Pode ser maior |

## 6. Exemplo de cenário corporativo

Uma empresa com matriz, filiais e aplicações em nuvem utiliza dois links WAN em uma filial: MPLS e Internet. Uma política SD-WAN pode selecionar o transporte conforme métricas de qualidade e requisitos da aplicação, desde que a solução e as políticas estejam corretamente configuradas.

**Perguntas para revisão:**

1. Qual é a diferença entre plano de controle e plano de dados?
2. Por que a escolha de cloud-hosted não define, sozinha, a topologia WAN?
3. Quais responsabilidades operacionais mudam entre on-premises e cloud-hosted?
4. Quais critérios orientariam a escolha para uma empresa com várias filiais?

## 7. Laboratório futuro

**Status: não executado.**

Planejamento preliminar:

1. Verificar requisitos de imagens, licenciamento e recursos da versão Cisco SD-WAN disponível.
2. Desenhar topologia com controladores, WAN Edges e transportes.
3. Validar conectividade e formação do plano de controle.
4. Observar políticas, rotas e seleção de caminhos.
5. Registrar comandos, capturas, falhas e correções no diretório `laboratorios/`.

Não há configurações ou resultados de laboratório a declarar nesta etapa.

## 8. Conclusão

A escolha do modelo de implantação depende de requisitos de governança, operação, conectividade, disponibilidade, custos e integração. O objetivo deste primeiro documento é estabelecer uma base conceitual antes da prática.

## 9. Referências para aprofundamento

- Cisco — documentação oficial do **Cisco Catalyst SD-WAN**: https://www.cisco.com/c/en/us/solutions/enterprise-networks/sd-wan/index.html
- Cisco — **ENCOR 350-401 Exam Topics** (conferir a versão vigente no site oficial): https://learningnetwork.cisco.com/

---

*Documento de estudo em evolução. Atualizar após leitura das referências oficiais e execução do laboratório.*
