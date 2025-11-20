# RELATORIOS DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

DATA: 19/10/2025
EMPRESA: Abstergo Industries 
RESPONSÁVEL: Anderson Angelo Nazario

## Introdução 
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Anderson Angelo Nazario. O objetivo do projeto foi *elencar 3 serviços AWS, com a finalidade *realizar dimunição de custo imediatos.

## Descrição do projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada um com seus objetivos especificos. A seguir serão descritas as estapas do projeto:

### Etapa 1: Base de Computação e Elasticidade
A primeira etapa é substituir os servidores físicos por uma solução de computação elástica e escalável.

- Nome da ferramenta: 
Amazon EC2 (Elastic Compute Cloud)

- Foco da ferramenta: 
Provisionamento de Servidores e IaaS

- Descrição da ferramenta: 
Será utilizado para hospedar a API de Processamento de Pedidos e o Sistema de Inventário da Abstergo. Em vez de comprar e manter servidores físicos, a Abstergo provisionará instâncias virtuais (IaaS) sob demanda, pagando apenas pelo tempo de uso. Isso elimina o CapEx inicial e oferece a flexibilidade de escolher a capacidade ideal para cada função


### Etapa 2: Alta Disponibilidade e Otimização de Custos
A segunda etapa é garantir que o sistema não saia do ar durante os picos de pedidos e introduzir um modelo de custo mais eficiente.

- Nome da ferramenta: 
Amazon EC2 Auto Scaling

- Foco da ferramenta: 
Escalabilidade Horizontal e Elasticidade

- Descrição da ferramenta: 
Será configurado junto ao EC2 e ao Elastic Load Balancing (ELB) para monitorar a demanda de pedidos. Durante os picos de acesso (ex: promoções ou início do dia útil), o serviço adicionará instâncias automaticamente (scale out) e as removerá durante a baixa demanda (scale in). Objetivo de Custo: Garante que a Abstergo pague somente pela capacidade que está ativamente utilizando, alinhando perfeitamente a infraestrutura ao fluxo de receita variável.



### Etapa 3: Armazenamento Escalável e Durável
A terceira etapa foca na substituição dos servidores de arquivos e na base para o armazenamento de dados não estruturados (documentos, relatórios, backups).

- Nome da ferramenta: 
Amazon S3 (Simple Storage Service)

- Foco da ferramenta: 
Armazenamento de Objetos Altamente Durável

- Descrição da ferramenta: 
Será usado como o repositório central para todos os dados não estruturados da empresa, como cópias digitais de receitas (documentos), relatórios de vendas (logs) e backups do banco de dados (snapshots). O S3 é virtualmente ilimitado em escala e oferece durabilidade de 99.999999999%, substituindo caros e limitados servidores de arquivos locais. Objetivo de Custo: Utilizar as classes de armazenamento S3 Intelligent-Tiering e Glacier para transferir automaticamente dados raramente acessados para camadas de custo muito mais baixo.


## Conclusão: Benefícios e Melhorias Estratégicas para a Abstergo Indústria
A implementação dos serviços-chave da AWS na Abstergo marca uma transformação fundamental no modelo operacional e financeiro da empresa, permitindo uma entrada ágil e segura no mercado de revenda farmacêutica.

Melhoria Financeira e Operacional
O benefício mais imediato é a completa eliminação do investimento pesado de capital (CapEx) em servidores, datacenters e hardware de armazenamento. A Abstergo agora opera com custos variáveis (OpEx), pagando somente pelo consumo real dos recursos, o que é crucial para uma empresa em fase de crescimento.

O uso combinado do Amazon EC2 e Amazon EC2 Auto Scaling traduz-se diretamente em elasticidade de negócio. O sistema de pedidos e inventário pode escalar horizontalmente para absorver picos de alta demanda (como promoções ou horários de pico) sem falhas de performance. Igualmente importante, a capacidade é reduzida automaticamente em períodos de baixa atividade, garantindo que a Abstergo nunca pague por recursos ociosos, otimizando a economia de custos.

Confiabilidade e Segurança de Dados
Com a adoção do Amazon S3 para armazenamento de objetos, a Abstergo garante uma durabilidade de dados inigualável para documentos críticos, como receitas digitalizadas e relatórios de vendas. Além disso, o S3 facilita a implementação de uma estratégia de backup de baixo custo.

Em suma, a nova arquitetura fornece uma plataforma altamente disponível e resiliente que permite à Abstergo focar integralmente no seu objetivo principal — a revenda e a logística farmacêutica — enquanto a AWS gerencia a segurança e a infraestrutura subjacente em escala global!