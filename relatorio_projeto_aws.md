# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 02/12/2025
Empresa: Abstergo Industries 
Responsável: Leandro Gomes

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries realizado por Leandro Gomes. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.

Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:

### Etapa 1: Hospedagem e Armazenamento

Amazon EC2 (Elastic Compute Cloud)
Foco: Servidor web para hospedar a aplicação da farmácia
Descrição de caso de uso: 
Uma instância EC2 hospeda o site da farmácia. 
O servidor roda uma aplicação simples que exibe o catálogo de medicamentos, buscas por nome e categoria, e processa pedidos. A instância fica em uma subnet pública para receber tráfego da internet.

Amazon S3 (Simple Storage Service)

Foco: Armazenamento de imagens de produtos e arquivos estáticos
Descrição de caso de uso: Bucket S3 armazena todas as fotos dos medicamentos (embalagens, bulas digitalizadas) e arquivos CSS/JavaScript do site. 

Amazon EBS (Elastic Block Store)
Disco persistente para o servidor EC2.
Volume EBS anexado à instância EC2 armazena o sistema operacional, código da aplicação e logs. 
Os dados persistem mesmo se a instância for reiniciada. 
Snapshots semanais automáticos garantem backup dos dados críticos da aplicação.


### Etapa 2: Banco de Dados

Amazon RDS (Relational Database Service)
Foco: Banco de dados gerenciado para dados estruturados
Descrição de caso de uso: 
Instância RDS (MySQL) armazena o catálogo de produtos (nome, preço, descrição, estoque), 
dados de clientes e histórico de pedidos. Tabelas incluem: produtos, categorias, clientes, pedidos e itens_pedido. 
O RDS elimina a necessidade de administrar manualmente o banco, fazendo backups automáticos diários e aplicando patches de segurança.

Amazon DynamoDB
Foco: Banco NoSQL para carrinho de compras temporário
Descrição de caso de uso: Tabela DynamoDB armazena carrinhos de compras ativos dos clientes. 

### Etapa 3: Rede / Escalabilidade 

Amazon VPC (Virtual Private Cloud)
Foco: Rede isolada e segura para os recursos
Descrição de caso de uso: VPC customizada contém toda a infraestrutura. 
Possui duas subnets: subnet pública onde fica o EC2 com acesso à internet via Internet Gateway, e subnet privad onde fica o RDS, protegido do acesso direto da internet. 
Security Groups funcionam como firewall, permitindo apenas tráfego para o EC2 e conexões MySQL apenas do EC2 para o RDS.

## Conclusão
A implementação de ferramentas na empresa Abstergo Industries tem como esperado a redução de custos com pessoas e infra estrutura, o que aumentará a eficiência e a produtividade da empresa. Recomenda-se a continuidade da utilização das ferramentas implementadas e a busca por novas tecnologias que possam melhorar ainda mais os processos da empresa.

## Anexos
![alt text](https://github.com/lgomessp-sp/Desafio_Santander_DIO_AWS/blob/main/image.png "Logo Title Text 1")



Assinatura do Responsável pelo Projeto:

Leandro Gomes