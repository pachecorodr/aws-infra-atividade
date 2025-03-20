# AWS Infraestrutura - Atividade Prática

## Descrição

Esta atividade prática tem como objetivo configurar uma infraestrutura básica na AWS, que inclui a criação de **Security Groups**, uma **instância EC2** e um **banco de dados PostgreSQL** via **RDS**. Durante este exercício, foi possível consolidar conhecimentos sobre os principais componentes da AWS e boas práticas de segurança.

### Passos Realizados

A seguir, estão os passos realizados para configurar a infraestrutura na AWS:


### 1. **Criação de Security Groups**

#### 1.1. Security Group para EC2
Foi criado um Security Group para a instância EC2 com as seguintes regras:
- **Acesso SSH (porta 22)** liberado apenas para o meu IP pessoal.
- **Acesso HTTP (porta 80)** liberado para qualquer IP (0.0.0.0/0).

#### 1.2. Security Group para RDS
Um segundo Security Group foi criado para o banco de dados RDS, com as seguintes configurações:
- **Acesso PostgreSQL (porta 5432)** liberado apenas para o Security Group da instância EC2.

**Captura de Tela: Security Groups**
![image](https://github.com/user-attachments/assets/f94cf16d-cb22-4582-9ca0-6e4da47ccb93)
![image](https://github.com/user-attachments/assets/c4c144f6-70ea-427a-aa96-e96c00c97388)


### 2. **Criação da Instância EC2**

- Utilizamos a **Amazon Linux AMI** para criar a instância EC2.
- A instância foi configurada com o tipo **t2.micro**, que é elegível para a camada gratuita da AWS.
- A instância foi associada ao **Security Group EC2** criado anteriormente.
- Um par de chaves `.pem` foi gerado e usado para acesso SSH à instância.

**Captura de Tela: Instância EC2**
![image](https://github.com/user-attachments/assets/7311756e-b365-4bdd-8d0c-7f4fc84a7690)



### 3. **Criação do Banco de Dados via RDS (PostgreSQL)**

- Foi criado um banco de dados gerenciado **PostgreSQL** via **RDS**.
- O **Security Group RDS** foi associado ao banco de dados, permitindo o acesso apenas pela instância EC2.
- As credenciais do banco foram configuradas com o nome de usuário **admin** e uma senha segura.
- O nome do banco de dados inicial foi definido como **meubanco**.
- O endpoint do banco de dados foi anotado para futuras conexões.

**Captura de Tela: RDS**
![image](https://github.com/user-attachments/assets/f78bf18f-ec00-4651-a669-b88a3c70cd17)



### 4. **Conexão ao Banco de Dados via SSH e psql**

- Após a instância EC2 ser criada, foi realizado o acesso via SSH à instância utilizando o arquivo `.pem` gerado.
- A conexão ao banco de dados PostgreSQL foi estabelecida utilizando o cliente **psql**, conectando-se ao endpoint do banco de dados RDS.

**Captura de Tela: Conexão com o Banco de Dados**
![image](https://github.com/user-attachments/assets/bd366677-3197-457c-9248-17544239a734)
![image](https://github.com/user-attachments/assets/d0e9ec4a-88cc-4c9d-9ddb-6d3457857629)
![image](https://github.com/user-attachments/assets/5e909cc8-3993-4684-a23b-7fb0e60079d4)


### 5. **Entrega**

- O repositório GitHub foi criado com o nome **aws-infra-atividade** e contém a documentação dos passos realizados.
- O vídeo de 30 segundos demonstrando a conexão SSH à instância EC2 e a conexão bem-sucedida ao banco RDS foi gravado e enviado ao Google Classroom.


### 6. **Conclusão**

Com a conclusão dessa atividade, foi possível configurar uma infraestrutura básica na AWS, implementando práticas de segurança como o uso de Security Groups para controlar o acesso à instância EC2 e ao banco de dados RDS. Além disso, a experiência com a conexão SSH e a integração com o banco de dados PostgreSQL através do RDS consolidou o aprendizado sobre as principais ferramentas da AWS.



