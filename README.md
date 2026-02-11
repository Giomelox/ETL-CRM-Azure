# ETL-CRM-Azure


# Criação e configuração de serviços

Primeiramente vamos criar um grupo de recursos no Azure, após inserir o nome escolhido para o grupo de recursos, clique em 'Review + Create'
<img width="996" height="380" alt="image" src="https://github.com/user-attachments/assets/0c9307ba-1444-48fa-b9f5-28429df563b4" />

Com o grupo de recursos criado, vamos criar um storage account para centralizar nosso modelo medalhão com camadas bronze, silver e gold com nosso star scheme

Vale considerar que para este exemplo, vamos nos basear nas configurações básicas das storages accounts, configure apenas estes tópicos (todos eles se encontram na primeira aba dos storage accounts):

Storage account name -> Nome desejado do storage account
Preferred storage type -> Azure blob storage or Azure data lake storage Gen 2
Primary workload -> Big data analytics
Redundancy -> LRS (Recomendado para projetos que não sejam críticos, vamos utilizar este por ser um ambiente de teste)

Após isso, clique em 'Review + Create'

<img width="1183" height="886" alt="image" src="https://github.com/user-attachments/assets/9dc55770-ac58-4367-9686-a698ef7a0cb4" />

Após isso, crie um container pra camada bronze, silver e gold

<img width="1635" height="889" alt="image" src="https://github.com/user-attachments/assets/89c4b181-42ff-4760-bb79-5573a160c85f" />

<img width="432" height="355" alt="image" src="https://github.com/user-attachments/assets/4246f0e2-903d-4013-8961-52475a67bb0b" />

Clique no container 'Bronze' criado e crie um repositório chamado 'parquet-files'

<img width="289" height="915" alt="image" src="https://github.com/user-attachments/assets/4dc4bf32-4321-4bae-a741-800544365b43" />

Selecione o diretório 'parquet-files' criado, e clique em 'upload' para fazer o upload do arquivo '0000.parquet' disponibilizado neste repositório

<img width="1651" height="348" alt="image" src="https://github.com/user-attachments/assets/c1a1bb5d-1375-48aa-9724-55743bc53e45" />

Agora vamos criar o nosso azure data factory, vamos focar nas configurações básicas também para este serviço:

Selecione o resource group criado anteriormente
escolha um nome para seu serviço

clique em 'Review + Create'
<img width="944" height="467" alt="image" src="https://github.com/user-attachments/assets/4db93814-d4b5-4a50-beec-4cf6134dcf0f" />

Agora vamos criar nosso Azure Synapse Analytics, configure assim:
<img width="1101" height="792" alt="image" src="https://github.com/user-attachments/assets/a1aadbaf-5eed-4db2-a7e7-4e995d687b14" />

<img width="1187" height="883" alt="image" src="https://github.com/user-attachments/assets/2b97c6c1-c4a8-4a10-8f30-db9d97d318e8" />

## Azure Databricks

Pesquise pelo serviço 'Azure Databricks' e crie um serviço com as seguintes configurações:

<img width="1650" height="662" alt="image" src="https://github.com/user-attachments/assets/1cd06d5a-15ce-47b7-862d-737dede184a7" />

<img width="913" height="755" alt="image" src="https://github.com/user-attachments/assets/b45831b3-1581-4d8d-9700-6b0d9791051a" />

Clique em 'Review + Create'



# Criando um ETL no ADF

Navegue até seu serviço do azure data factory criado e clique em 'launch studio', isso abrirá o serviço em outra página.

<img width="1649" height="637" alt="image" src="https://github.com/user-attachments/assets/4b4627e7-92ad-4b66-bb32-33cd1569e538" />

Na página aberta, você verá o Hub do ADF, clique em 'New' e 'Pipeline'

<img width="1875" height="626" alt="image" src="https://github.com/user-attachments/assets/9dc0d78e-fa0b-4b85-96f1-0ae51911d22f" />

Você verá uma tela de recursos disponíveis, clique nos 3 pontinhos do pipeline criado e clique em 'Rename' para alterar o nome para o desejado.

<img width="267" height="328" alt="image" src="https://github.com/user-attachments/assets/917e3365-b357-4be8-8beb-3b01803598ce" />
