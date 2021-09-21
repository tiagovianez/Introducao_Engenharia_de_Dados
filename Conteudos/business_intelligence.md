## Conceitos inicias sobre BI

Processo de transformar dados em informações e informações em conhecimento - **Gartner**



### Propósito

Converter o volume de dados em informações relevantes para o negócio, por meio de relatórios analíticos

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163531-3250eedf-fe51-44f6-8193-58c428f4bed9.png" width="500px" />
</div>



#### Aplicações

* Query Report
* Data Mining
* Budget & Forecast
* KPI's
* Dashboards de gestão



#### Ferramentas

* MicroStrategy
* Google Data Studio
* Looker
* MS PBI
* Tableu
* QlikView
* Board
* Domo



## Data Warehouse

#### Antes do DW

* Falta de credibilidade dos dados, consequência de extrações
* Baixa produtividade
* Dificuldade em gerar informação a partir dos dados extraídos



#### Definição

É uma arquitetura de armazenamento projetada para conter dados extraídos de sistemas de transações, armazenamentos de dados operacionais e fontes externas.



Combinar esses dados em um formulário de resumo agregado adequado para análise de dados em toda a empresa  e relatórios para necessidades de negócios predefinidas.

 

### OLTP vs OLAP

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163604-d94c4d49-b860-4bac-b0f4-ba7c8e76834b.png" width="500px" />
</div>


### Modelos: Relacional vs Dimensional

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163685-fa08abc5-9052-4312-b087-b79c62e9c658.png" width="500px" />
</div>


### Arquitetura Básica

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163751-97fc2114-ccfe-4ecd-b536-b286fd5c9257.png" width="500px" />
</div>


- Coletar
- Extrair
- Tratar
- Armazenar dentro do DW junto com os seus Metadados para serem consultados pelos users.



### Staging Area

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163804-e8d4f8db-867d-4e0f-ba9b-a9f52b553149.png" width="500px" />
</div>


Arquitetura mais possível de ser encontrada no mercado



### Data Marts

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163841-1a4bc24f-52af-45c4-8a66-0255775f9d49.png" width="500px" />
</div>


* Os Data Marts são base de dados modelados por assuntos específicos
* Arquitetura comum vista no mercado
* A cada nova base de dados, aumenta-se a complexidade.
* A importância de um pipeline de dados para o processamento dessas informações



### ETL

(Extract, Transform, Load) é um processo automatizado que coleta dados brutos, extrai as informações necessárias para análise, transforma em um formato que atende às necessidades de negócios e carrega em um DW.

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163921-fb7c9a30-0b70-4ed2-81ba-0479ffd10d86.png" width="500px" />
</div>


<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163923-12f96238-9944-4498-9fe6-7265526b1255.png" width="500px" />
</div>


* **Malhas de ETL**



### ETL - Tipos de movimentação

#### Movimentação de volumes de dados

* Cargas completas - truncate & load
* Cargas incrementais - data / ID
* Frequência (diária, semanal, mensal): Qual o requisito do negócio que iremos atender?



#### Pode melhorar significativamente a qualidade dos dados 

* Qualidade e padronização/validação dos dados

* Metadados (descrevem os atributos dos dados - significado desses dados e a informação daquela tabela ou base de dados)





### Desafios do ETL

* **Escalabilidade** - É um dos recursos mais importantes em uma ferramenta ETL Moderna
* **Acurácia** - Garantir que os dados que você transformar sejam precisos e completos
* **Manusear fontes de dados diversas** - Lidar com diversos tipos de fontes de dados.



#### Considerações Finais

* DW é fundamental para um sistema de apoio à decisão
* Acesso simplificado a dados históricos
* Facilidade em consulta de informações
* Avalie as origens e tipos de dados
* Planeje a malha de ETLs
* Atenção a modelagem dos dados (Dimensional)
* Produção de relatórios





## Data Marts (DM)

É um subconjunto de um Data Warehouse

Orientado para uma linha de negócios específica

Contêm repositórios de dados resumidos coletados para análise em uma seão ou unidade específica dentro de uma organização

... Ex.: Departamento de Vendas

<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134163970-a955ad08-df65-4c3e-8d23-414ba6de843b.png" width="500px" />
</div>


<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134164049-8a4bfd7b-54ca-4737-8348-a2b8e21c2120.png" width="500px" />
</div>



#### DW e DM

* Utilizado para abranger todos assuntos da empresa
* Implementação e evolução dura mais que o **DM**
* Custo maior que o **DM**
* Quantidade de acesso a usuários é maior do que o **DM**
* A quantidade de dados tende a crescer muito mais que o **DM**





### Inmon vs Kimball



<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134164136-4e61a50f-5bdf-47df-9c1b-a0d7e10a4a9c.png" width="500px" />
</div>
#### Top-down design

* Toda sua origem de dados, coleta e armazenagem seja diretamente em um ambiente de DW;
* Em seguida transfere para as DMs específicas
* Ela considera a criação de um DW e sua modelagem
* DW -> DMs




<div align="left">
<img src="https://user-images.githubusercontent.com/78626907/134164203-ecd207e8-fc1c-4511-82d7-1af6912f5077.png" width="500px" />
</div>
#### Bottom-up design

* A primeira coisa que estabelece são os DMs;
* Empresas que possuem um porte menor, geralmente utilizam esse modelo
* Depois de coletada e armazenada nos DMs, elas são enviadas para o DW;
* Inicia por DMs menores -> DW



#### Qual abordagem utilizar?

* Para empresas onde **a informação consolidada é muito importante** como **estratégia de negócio**, **centralização das informações**, sugere-se a abordagem **<u>Top-down design</u>**

* Para tratamento de assuntos específicos em início de ambiente DW sugere-se a abordagem **<u>bottom-up design</u>**

