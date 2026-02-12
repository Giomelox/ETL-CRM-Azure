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

A criação do workspace pode levar alguns minutos. Após a criação, clique em 'Properties' e copie a 'Workspace URL' do seu databricks, cole-a em outra aba do navegador

<img width="1625" height="587" alt="image" src="https://github.com/user-attachments/assets/cb682e93-ad84-4213-a191-3477b4f1c88f" />

Feito isso, vá no canto superior direito e clique em 'Settings'

<img width="238" height="399" alt="image" src="https://github.com/user-attachments/assets/f8170eed-2ed2-4132-8542-b54c2e66c6e4" />

E então navegue até a área 'Developer'

<img width="1604" height="519" alt="image" src="https://github.com/user-attachments/assets/b9c1cbd5-4914-4c36-8e7b-d40c27963bf9" />

Clique em 'Manage' na parte de 'Access Token' e clique em 'Generate new token'

<img width="1626" height="515" alt="image" src="https://github.com/user-attachments/assets/ec91774c-74e4-4fdf-854c-f0d7f401c43e" />

## Copie o token gerado, pois ele será usado na etapa posterior, e você não poderá pegar este token novamente!!

# Criando um ETL no ADF

Navegue até seu serviço do azure data factory criado e clique em 'launch studio', isso abrirá o serviço em outra página.

<img width="1649" height="637" alt="image" src="https://github.com/user-attachments/assets/4b4627e7-92ad-4b66-bb32-33cd1569e538" />

Na página aberta, você verá o Hub do ADF, clique em 'New' e 'Pipeline'

<img width="1843" height="373" alt="image" src="https://github.com/user-attachments/assets/f050c199-8d91-4053-9619-ca50dd7bf9d4" />


Você verá uma tela de recursos disponíveis, clique nos 3 pontinhos do pipeline criado e clique em 'Rename' para alterar o nome para o desejado.

<img width="293" height="286" alt="image" src="https://github.com/user-attachments/assets/62508f72-f07a-4805-8405-f99304f635aa" />

Na janela de 'Activities', expanda a seção 'databricks' e mova o componente 'notebook' para a área de edição

<img width="1821" height="688" alt="image" src="https://github.com/user-attachments/assets/590cc18c-74d4-4dc7-b232-47a8e5f1d3d5" />

Clique no componente adicionado, e na seção de configurações do componente, altere o nome para o desejado

<img width="1206" height="836" alt="image" src="https://github.com/user-attachments/assets/5ed48e4f-cf56-4f0b-b882-fbedbdcf695a" />

Feito isso, vamos para a aba 'Azure Databricks' e na opção de 'databricks linked services', clicar no botão de '+ New', configure de acordo com as imagens abaixo:

<img width="625" height="915" alt="image" src="https://github.com/user-attachments/assets/a255ea42-e82d-47ac-8f05-4ca40675df65" />

<img width="581" height="204" alt="image" src="https://github.com/user-attachments/assets/6aec4481-c85f-4e1d-8bb9-deda0f2d3aa6" />

Clique em 'Create'

Feito isso, abra sua janela que está o databricks (ou abra novamente caso tenha fechado) e clique na seção 'Compute' e crie um com as mesmas configurações abaixo:

<img width="1661" height="907" alt="image" src="https://github.com/user-attachments/assets/0891ef24-52ec-4341-9226-f0d2458b714a" />


Após isso, clique na seção 'Workspace', em seguida, Clique em 'Create' e depois 'Notebook' no canto superior direito, e após a criação, altere o nome do notebook para o desejado.

<img width="1861" height="667" alt="image" src="https://github.com/user-attachments/assets/7e7766af-bd35-4cfb-9f2c-33ade1422a94" />


Com o notebook criado, vamos clicar na seção 'Connect' e selecionar o cluster criado no passo anterior

<img width="1674" height="439" alt="image" src="https://github.com/user-attachments/assets/dfe95540-e2fd-4435-b0b0-8f9777f27250" />


Com o cluster conectado ao nosso notebook, vamos rodar um código simples em pyspark para conferir a funcionalidade do sistema

A estrutura do código é simples, adapte para seu ambiente do azure:

`````

token_storage_account = 'SEU STORAGE ACCOUNT TOKEN!!'

nome_storage_account = 'stfilescrm'
nome_container = 'bronze'
nome_subpasta = 'parquet-files'

bronze_path = f'abfss://{nome_container}@{nome_storage_account}.dfs.core.windows.net/{nome_subpasta}/'

spark.conf.set(
    'fs.azure.account.key.stfilescrm.dfs.core.windows.net',
    token_storage_account
)

df = spark.read.parquet(
    bronze_path
).dropna()

df.show()

`````

<img width="1647" height="890" alt="image" src="https://github.com/user-attachments/assets/af303464-d499-450e-904d-0ee1c13e2acc" />


Agora voltaremos à nossa aba do navegador onde está o Azure DataFactory, vamos clicar na aba 'Settings' e selecionar nosso notebook criado no passo anterior

<img width="1520" height="851" alt="image" src="https://github.com/user-attachments/assets/c1387321-1c06-4427-adee-e1462c7985d7" />

Feito isso, clique em 'Publish All' para publicar e salvar as alterações feitas, e para testar se está tudo funcionando corretamente, após salvar clique em 'Add Trigger' -> 'Trigger Now'

<img width="1828" height="355" alt="image" src="https://github.com/user-attachments/assets/6e02f952-4cba-45cd-bd1a-5c08cc7b875f" />
