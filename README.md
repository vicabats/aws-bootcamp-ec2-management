# aws-bootcamp-ec2-management

Este repositório reúne meus estudos e práticas sobre **gerenciamento de instâncias EC2 na AWS**, desenvolvidos durante o **Santander Code Girls**.  
Aqui documento minhas anotações, prints de telas e principais aprendizados.

---

## 📌 Introdução

### Visão geral da AWS
**História:**  
A AWS (Amazon) foi fundada em 1994 somente com o propósito de ser uma loja de livros. Ela foi se tornar uma gigante da tecnologia com seu fundador, Jeff Bezos.  

O Amazon Web Services (AWS) foi lançado pela Amazon em 2006 como uma resposta à necessidade de oferecer serviços de infraestrutura em nuvem.  

---

## 🌍 Infraestrutura global

A infraestrutura global da AWS é a mais segura, abrangente e confiável plataforma de nuvem. Ela foi a pioneira de provisionamento de recursos em nuvem. Ela oferece mais de 200 serviços em todo o mundo.  

A AWS possui uma extensa rede global de datacenters, chamados de:  
- **Regiões** → áreas geográficas contendo várias Availability Zones.  
- **Availability Zones (AZs)** → datacenters independentes fisicamente, mas conectados logicamente para garantir alta disponibilidade.  

> Normalmente, uma região possui duas ou mais Availability Zones. Se um datacenter apresentar algum problema, o outro mantém os recursos.  

---

## ☁️ Conceitos básicos e modelo de negócio

O foco do modelo de negócio da AWS é o **pagamento por uso**, diferente dos modelos antigos como CAPEX.

- **OPEX** → não precisa de uma grande infraestrutura para iniciar um projeto.  
- **CAPEX** → modelo antigo; exigia infraestrutura física para cada POC.  

✅ O preço é flexível: pague apenas pelo uso.  
✅ Grande variedade de serviços.  

### Modelos de serviço
- **IaaS (Infrastructure as a Service)** → infraestrutura como serviço (ex.: sistema legado, servidor de arquivos).  
- **PaaS (Platform as a Service)** → plataforma como serviço (ex.: desenvolvimento de aplicações).  
- **SaaS (Software as a Service)** → software pronto para uso (ex.: Netflix, Spotify).  

---

## 🏗️ Conceitos fundamentais

**Região:** cada região é projetada para ser isolada das outras, garantindo tolerância a falhas e estabilidade.  
**Availability Zone:** datacenter independente, mas conectado logicamente.  

📌 Pontos para considerar ao escolher uma região:  
- Compliance (ex.: LGPD)  
- Disponibilidade do serviço  
- Custo  
- Latência  

---

## 🔐 Configuração da conta e segurança

Ao criar uma conta AWS, temos uma conta principal **root**, com super privilégios.  

**Boas práticas:**  
1. Criar conta root e guardar em lugar seguro.  
2. Não compartilhar dados da conta.  
3. Ficar atento a cobranças e e-mails suspeitos.  
4. Ativar autenticação **MFA**.  
5. Seguir o **princípio do menor privilégio**.  

---

## 👤 IAM (Identity and Access Management)

- Permite gerenciar perfis de acesso e permissões.  
- Podemos criar usuários, grupos e permissões.  
- Dá pra usar o **AWS CLI** para importar usuários via `.csv` e atribuí-los a grupos.  

---

## 💻 Instâncias EC2

**EC2 (Elastic Compute Cloud)**: máquinas virtuais na AWS.  

Componentes de uma instância:  
- CPU  
- Memória  
- Disco  
- Rede  
- Sistema Operacional  

📌 A EC2 faz parte do modelo **IaaS**.  

### Tipos de instâncias
- Famílias de instâncias com diferentes tamanhos e preços.  
- É possível fazer **upgrade/downgrade** de instância.  
- **On-demand**: uso sob demanda, cobradas por hora.  
- **Spot**: mais baratas, mas podem ser interrompidas.  
- **Reservadas**: mais baratas que on-demand, exigem compromisso (1–3 anos).  

---

## 📈 Operação e escalabilidade

- **Importante desligar instâncias não utilizadas** para economizar.  
- Se uma instância está ociosa, faça *stop*.  

### Escala de recursos
- **Vertical** → aumentar/reduzir recursos em uma mesma máquina (CPU, memória, storage).  
- **Horizontal** → adicionar mais instâncias para distribuir a carga.  

---

## 🗄️ Armazenamento

### Amazon EBS (Elastic Block Store)
- Volume em bloco anexado a instâncias EC2 (funciona como um HD).  
- Cada instância tem um volume raiz, mas é possível expandir.  

### Amazon S3 (Simple Storage Service)
- Armazenamento de objetos.  
- Classes de armazenamento:  
  - S3 Standard  
  - S3 Standard-IA (Infrequent Access)  
  - S3 One Zone-IA  
  - S3 Glacier (arquivamento, acesso menos frequente)  

📌 É possível definir **regras de lifecycle** para mover objetos automaticamente entre classes, reduzindo custos.  

---

## 📷 AMI (Amazon Machine Image)

- Imagem de máquina pré-configurada usada para iniciar instâncias.  
- Podem ser **públicas** ou **privadas**.  
- Possível personalizar uma instância e depois gerar uma **AMI**.  
- Facilita replicar ambientes.  

---

## 💾 Snapshots EBS

- Backup dos volumes EBS armazenados no S3.  
- Captura o estado do volume em um determinado momento.  
- É possível configurar frequência de snapshots.  

### Diferença entre AMI e Snapshot
- **AMI**: backup de toda a máquina (inclui volumes EBS anexados).  
- **Snapshot**: backup de um volume específico EBS.  

---

## 📚 Referências

- [Documentação oficial Amazon EC2](https://docs.aws.amazon.com/ec2/)  

---

✨ Esse guia é fruto da prática no bootcamp e servirá como material de consulta para futuros projetos na AWS.
