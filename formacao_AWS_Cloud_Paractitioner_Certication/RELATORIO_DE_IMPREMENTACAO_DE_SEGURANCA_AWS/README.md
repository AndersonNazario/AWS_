# RELATORIO DE IMPLEMENTAÇÃO DE MEDIDAS DE MEDIDAS DE SEGURANÇA 
Data: 29/10/2025
Empresa: Abstergo Industries
Responsável: Anderson Angelo Nazario

## Introdução 
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Anderson Angelo Nazario. O objetivo do ´projeto foi elencar 3 medidas de segurança em conjunto dos serviços da AWS, com a finalidade de aumentar a segurança ne empresa.

## Descrição do projeto 
O projeto de implementação de ferramentas foi desenvolvido em 3 medias de segurança. A seguir, serão descritas as etapas da implementação:

### Medida 1:
- Gerenciamento de Acesso e Credenciais (IAM)
- Princípio do Menor Privilégio e MFA
- Para proteger o Portal de Pedidos e o Sistema de Inventário (que rodam em EC2), implementamos IAM Roles para as aplicações e IAM Users individuais para os funcionários. Melhoria: As aplicações acessam o banco de dados usando Roles temporárias (sem chaves de acesso de longo prazo, seguindo as melhores práticas). Todos os usuários IAM com privilégios de gestão foram obrigados a configurar o MFA (Multi-Factor Authentication), bloqueando acessos não autorizados por roubo de senha.

### Medida 2:
- Criptografia Centralizada de Dados em Repouso
- AWS KMS (Key Management Service)
- Todos os dados sensíveis da Abstergo (incluindo o armazenamento S3 de documentos e os volumes EBS dos servidores EC2) foram configurados para usar criptografia em repouso. Melhoria: Utilizamos o AWS KMS para criar e gerenciar as chaves criptográficas (CMKs - Customer Master Keys). Isso garante que, mesmo que o armazenamento físico seja comprometido, os dados permaneçam ilegíveis, e o controle das chaves esteja sob estrita política de auditoria da Abstergo (cumprindo a necessidade de proteção da LGPD).



### Medida 3:
- Visibilidade e Auditoria de Segurança
- AWS CloudTrail e Amazon Macie
- Para cumprir as exigências de rastreabilidade e conformidade, o AWS CloudTrail foi habilitado para registrar todas as ações de API, permitindo auditorias detalhadas (quem alterou um Security Group ou quem tentou acessar um recurso). Melhoria: Integrado a isso, o Amazon Macie foi configurado para fazer a descoberta automatizada de dados confidenciais (PII, CPF, etc.) no Amazon S3, alertando a equipe se algum documento sigiloso for armazenado sem a devida criptografia ou política de acesso.

## Conclusão 
Conclusão sobre as Ferramentas de Segurança Implementadas
A escolha das ferramentas IAM Roles, AWS KMS e AWS CloudTrail/Macie representa uma abordagem de segurança em camadas e proativa para a Abstergo Industries, fundamental para a conformidade com a LGPD.
IAM Roles (Controle de Acesso): Estabeleceu a base de segurança, garantindo que as aplicações usem permissões temporárias em vez de credenciais permanentes de alto risco. Isso é o cerne do Princípio do Menor Privilégio.
AWS KMS (Proteção de Dados): Centralizou o controle sobre a criptografia dos dados mais sensíveis da empresa (em S3 e EBS). Ao gerenciar as próprias chaves, a Abstergo atendeu a requisitos rigorosos de privacidade de dados em repouso.
CloudTrail & Macie (Visibilidade e Descoberta): Proporcionou o mecanismo de auditoria (CloudTrail) necessário para a conformidade legal e adicionou uma camada de inteligência de dados (Macie) para detectar automaticamente onde os dados sigilosos (PII) podem estar desprotegidos.
Em resumo, as ferramentas implementadas criaram um ambiente onde a segurança é inerente à arquitetura, e não um complemento. Isso eleva a postura de segurança da Abstergo a um padrão de excelência na nuvem, minimizando o risco de vazamentos e simplificando futuras auditorias.