## Conceitos inicias sobre BI

Processo de transformar dados em informações e informações em conhecimento - **Gartner**



### Propósito

Converter o volume de dados em informações relevantes para o negócio, por meio de relatórios analíticos

![image-20210920230750806](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920230750806.png)



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

![image-20210920232333685](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920232333685.png)



### Modelos: Relacional vs Dimensional

![image-20210920232459127](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920232459127.png)



### Arquitetura Básica

![image-20210920232550981](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920232550981.png)

- Coletar
- Extrair
- Tratar
- Armazenar dentro do DW junto com os seus Metadados para serem consultados pelos users.



### Staging Area

![image-20210920234539746](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920234539746.png)

Arquitetura mais possível de ser encontrada no mercado



### Data Marts

![image-20210920234625226](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920234625226.png)

* Os Data Marts são base de dados modelados por assuntos específicos
* Arquitetura comum vista no mercado
* A cada nova base de dados, aumenta-se a complexidade.
* A importância de um pipeline de dados para o processamento dessas informações



### ETL

(Extract, Transform, Load) é um processo automatizado que coleta dados brutos, extrai as informações necessárias para análise, transforma em um formato que atende às necessidades de negócios e carrega em um DW.

![image-20210920235118617](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920235118617.png)



![image-20210920235312133](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210920235312133.png)

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

![image-20210921074436221](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210921074436221.png)





![image-20210921074223252](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210921074223252.png)



#### DW e DM

* Utilizado para abranger todos assuntos da empresa
* Implementação e evolução dura mais que o **DM**
* Custo maior que o **DM**
* Quantidade de acesso a usuários é maior do que o **DM**
* A quantidade de dados tende a crescer muito mais que o **DM**





### Inmon vs Kimball



![image-20210921074831359](C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210921074831359.png)

#### Top-down design

* Toda sua origem de dados, coleta e armazenagem seja diretamente em um ambiente de DW;
* Em seguida transfere para as DMs específicas
* Ela considera a criação de um DW e sua modelagem
* DW -> DMs



<img src="C:\Users\Tiago\AppData\Roaming\Typora\typora-user-images\image-20210921075036250.png" alt="image-20210921075036250" style="zoom:67%;" />

#### Bottom-up design

* A primeira coisa que estabelece são os DMs;
* Empresas que possuem um porte menor, geralmente utilizam esse modelo
* Depois de coletada e armazenada nos DMs, elas são enviadas para o DW;
* Inicia por DMs menores -> DW



#### Qual abordagem utilizar?

* Para empresas onde **a informação consolidada é muito importante** como **estratégia de negócio**, **centralização das informações**, sugere-se a abordagem **<u>Top-down design</u>**

* Para tratamento de assuntos específicos em início de ambiente DW sugere-se a abordagem **<u>bottom-up design</u>**

