# ETL-CRM-Azure

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

 
<img width="1652" height="388" alt="image" src="https://github.com/user-attachments/assets/294da60c-dbe3-4562-b674-9cb9e5617d9e" />




Agora vamos criar o nosso azure data factory, vamos focar nas configurações básicas também para este serviço:

Selecione o resource group criado anteriormente
escolha um nome para seu serviço

clique em 'Review + Create'
<img width="944" height="467" alt="image" src="https://github.com/user-attachments/assets/4db93814-d4b5-4a50-beec-4cf6134dcf0f" />

Agora vamos criar nosso Azure Synapse Analytics, configure assim:
<img width="1101" height="792" alt="image" src="https://github.com/user-attachments/assets/a1aadbaf-5eed-4db2-a7e7-4e995d687b14" />

<img width="1187" height="883" alt="image" src="https://github.com/user-attachments/assets/2b97c6c1-c4a8-4a10-8f30-db9d97d318e8" />


