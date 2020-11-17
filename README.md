# PORTAL SEMÂNTICO
## Correlacionando fatores de saneamento básico com casos suspeitos e confirmados de COVID-19 no estado do Ceará

### Discentes
* Jussara Teixeira de Araújo Gonçalves
* Rôney Reis de Castro e Silva

### Professores
* Vânia Maria Ponte Vidal
* Angelo Brayner 

### Assistentes
* Caio Viktor da Silva Avila
* Tulio Vidal Rolim 


## Resumo
A pandemia de COVID-19 tem intrigado a comunidade científica que ainda busca respostas. Com acentuado número de infectados em todo o mundo, a busca por novas respostas e, consequentemente novos tratamentos, tem gerado uma corrida por novas descobertas. A análise de dados semânticos tem sido, durante os últimos anos, uma ferramenta muito poderosa para a descoberta de novos conhecimentos, aplicado em diversas áreas. Ferramenta essa já estudada no combate a COVID-19 através de diversos estudos [sermet2020semantic, guo2020cord19sts, alambo2020depressive]. O Ceará, um dos estados mais afetados pelo COVID-19, o cenário é ainda mais alarmante. Com PIB de apenas 2,11\%[pib], boa parte da população vive em situação socioeconômica precária, dificultando ainda mais métodos de prevenção que evitem a disseminação do coronavírus. 
Diante de tudo isso, esse trabalho tem como propósito investigar a relação dos casos suspeitos e confirmados de COVID-19 com a situação socioeconômica e de higiene da região onde vivem.


![Alt text](img/arquitetura.png?raw=true "Arquitetura")

## 1 - Fontes de dados
* Dados do IBGE sobre Pesquisa de Informações Básicas Municipais (MUNIC)
* Dados do SUS sobre Síndrome Gripal (SG)

## 2 - Questões de Competências
* QC1- Qual a relação entre os casos confirmados de COVID-19 e a situação de
saneamento básico dos municípios?
* QC 2 - Qual a relação entre os casos suspeitos e confirmados de COVID 19 e os fatores
gênero e renda?
* QC3- Quais municípios apresentaram maior fragilidade nos fatores de saneamento e
renda e qual relação com os casos confirmados de COVID 19?

## 3 - Tratamento dos Dados
* Importação dos dados a partir de CSVs
![Alt text](img/csv.jpeg?raw=true "Arquivos CSV")

* Transformação para dados relacionais

![Alt text](img/modelagem.png?raw=true "Modelagem")


## 4 - Modelagem da Ontologia

![Alt text](img/modelagem.jpeg?raw=true "Modelagem")

## 5 - Mapeamentos R2RML

* <a href="files/maps_ibge.ttl" download>Mapeamento IBGE</a>
* <a href="files/maps_sau.ttl" download>Mapeamento SUS</a>
* <a href="files/instances_ibge.ttl" download>Instâncias IBGE</a>
* <a href="files/instances_sau.ttl.zip" download>Instâncias SUS</a>
## 6 - Links sameAS

* silk-workbench-v3.2.0

![Alt text](img/linke1.jpeg?raw=true "Modelagem")

![Alt text](img/link2.jpeg?raw=true "Modelagem")

![Alt text](img/link3.jpeg?raw=true "Modelagem")

## 7 - GraphDB

* Importação das bases de dados
![Alt text](img/graph_imports.jpeg?raw=true "Modelagem")

* Execução das consultas SPARQL
![Alt text](img/graph.jpeg?raw=true "Modelagem")


## 8 - Resultados

* Resultado QC1
![Alt text](img/resultado1.jpg?raw=true "Resultado")

* Resultado QC1
![Alt text](img/resultado2.jpg?raw=true "Resultado")

* Resultado QC1
![Alt text](img/resultado3.jpg?raw=true "Resultado")

* Resultado QC2
![Alt text](img/resultado4.jpg?raw=true "Resultado")

* Resultado QC3
![Alt text](img/resultado5.jpg?raw=true "Resultado")

* Resultados
![Alt text](img/resultado6.jpg?raw=true "Resultado")

* Resultados
![Alt text](img/resultado7.jpg?raw=true "Resultado")


* Resultados
![Alt text](img/resultado8.jpg?raw=true "Resultado")


* Resultados
![Alt text](img/resultado9.jpg?raw=true "Resultado")

* Resultados
![Alt text](img/resultado10.jpg?raw=true "Resultado")

* Resultados
![Alt text](img/resultado11.jpg?raw=true "Resultado")



## Vocabulário

* sau: http://datasus.gov.br/owl 
* ibge: https://www.ibge.gov.br/owl
* loc: https://www.localizacao.com/owl 

**sau:Doenca**
A classe Doenca é a classe que representa as doenças, por exemplo, diabetes, doenças respiratórias, Covid-19, etc.
<br>**Propriedades:** rdsf:label

**sau:Paciente**
Subclasse de foaf:Agent, a classe Paciente representada o estado do Agent.
<br>**Propriedades**: sau:id_paciente

**sau:Profissional_da_Saude**
S****ubclasse de Paciente, representa os pacientes que também são profissionais
<br>**Propriedades**: sau:tipo_profissional

**sau:Condicao**
Classe que representa o estado de um Paciente, por exemplo, se apresenta fatores de risco como gravidez, idade avançada, etc.
<br>**Propriedades**: rdsf:label


**sau:Sintomas**
<br>**Propriedades**: rdsf:label, sau:data_inicio_sintomas

**sau:Sindrome_Gripal**
<br>**Propriedades**: rdsf:label

**sau:Teste**
<br>**Propriedades**: sau:data_teste

**sau:Tipo_Teste**
<br>**Propriedades**: rdsf:label

**sau:Resultado**
<br>**Propriedades**: rdsf:label

**sau:tipo_profissional**
Propriedade que representa a especialidade do profissional de saúde

**sau:data_teste**
Data de realização do teste, representado na forma de string dd-mm-yyyy

**sau:data_inicio_sintomas**
Data do início dos sintomas relatados pelo paciente, representado na forma de string dd-mm-yyyy

**sau:id_paciente**
Número inteiro representando a identificação única do paciente

sau:hasSintomas

sau:hasCondição

sau:hasDoenca 

sau:fezTeste

sau:fazParteDe





**ibge:Saneamento_Basico** 
<br>**Propriedades**: rdsf:label

**ibge:Domicilio** 
<br>**Propriedades**: ibge:quantidade_de_domicilios

**ibge:Serviço**
<br>**Propriedades**: rdsf:label

**ibge:Registro_de_serviço** 
<br>**Propriedades**: ibge: número_de_entidades_executoras, ibge: cobrança_de_serviço, ibge:orgão_municipal_gestor_do_serviço

**ibge:Abastecimento_de_Agua** 
<br>**Propriedades**: rdsf:label

**ibge:Esgoto** 
<br>**Propriedades**: rdsf:label

**ibge:Urbana** 
<br>**Propriedades**: rdsf:label

**ibge:Area_de_abrangencia**
<br>**Propriedades**: rdsf:label

**ibge:Rural**
<br>**Propriedades**: rdsf:label

ibge:quantidade_de_domicilios

ibge: número_de_entidades_executoras

ibge: cobrança_de_serviço

ibge:orgão_municipal_gestor_do_serviço

ibge:fornece serviço

ibge:tem_abrangencia_municipal

ibge:hasLocalização



**loc:Localização**
<br>**Propriedades**: rdsf:label

**loc:Municipio**
<br>**Propriedades**: rdfs:label, loc:código, cep

**loc:Bairro**
<br>**Propriedades**: rdsf:label

**loc:Microregiao**
<br>**Propriedades**: rdsf:label, loc:código

**loc:Mesoregiao**
<br>**Propriedades**: loc:código

**loc:Unidade_Federativa**
<br>**Propriedades**: rdsf:label, loc:código

**loc:Pais**
<br>**Propriedades**: rdsf:label, loc:código


loc:código

loc:fazParteDe

loc:cep


## Modelagem

## Ontologia de Domínio

## Integração Semântica (IS)

## Resultados

## Referências

[1]Y. Sermet and I. Demir, “A semantic web framework for automated smart assistants:Covid-19 case study,” arXiv preprint arXiv:2007.00747, 2020.

[2] X. Guo, H. Mirzaalian, E. Sabir, A. Jaiswal, and W. Abd-Almageed, “Cord19sts: Covid19 semantic textual similarity dataset,” arXiv preprint arXiv:2007.02461, 2020.

[3] A. Alambo, M. Gaur, and K. Thirunarayan, “Depressive, drug abusive, or informative:Knowledge-aware study of news exposure during covid-19 outbreak,” arXiv preprint arXiv:2007.15209, 2020.

[4] (2019) Pib cearense cresce 2,11% em 2019 e supera a média nacional. [Online]. Available: https://www.seplag.ce.gov.br/2020/04/14/pib-cearense-cresce-211-em-2019-e-supera-a-media-nacional/

[5] A. Badawi and S. G. Ryoo, “Prevalence of comorbidities in the middle east respiratorysyndrome coronavirus (mers-cov): a systematic review and meta-analysis,” International Journal of Infectious Diseases, vol. 49, pp. 129–133, 2016.

[6] F. Wu, S. Zhao, B. Yu, Y.-M. Chen, W. Wang, Z.-G. Song, Y. Hu, Z.-W. Tao, J.-H. Tian,Y.-Y. Pei et al., “A new coronavirus associated with human respiratory disease in china,” Nature, vol. 579, no. 7798, pp. 265–269, 2020.

[7] (2020) Ministério da saúde: Sobre a doença. [Online]. Available: https://coronavirus.saude.gov.br/sobre-a-doenca#diagnostico

[8] (2020) Coronavirus disease (covid-19) pandemic. [Online]. Available: https://www.who.int/emergencies/diseases/novel-coronavirus-2019

[9] (2020) Sobre a doença covid-19. [Online]. Available: https://coronavirus.saude.gov.br/sobre-a-doenca

[10] (2020) The world wide web consortium. [Online]. Available: https://www.w3.org/

[11] J. F. Sequeda and D. P. Miranker, “A pay-as-you-go methodology for ontology-based data access,” IEEE Internet Computing, vol. 21, no. 2, pp. 92–96, 2017.

[12] J. Z. Pan, G. Vetere, J. M. Gomez-Perez, and H. Wu, Exploiting linked data and knowledge graphs in large organisations. Springer, 2017.

[13] (2020) A free, open-source ontology editor and framework for building intelligent systems. [Online]. Available: https://protege.stanford.edu/

[14] P. Cristofaro, “Virtuoso rdf triple store analysis benchmark & mapping tools rdf/oo, 2013.”

[15] (2020) Virtuoso sparql. [Online]. Available: http://vos.openlinksw.com/owiki/wiki/VOS/VOSSPARQL

[16] M. Achichi, Z. Bellahsene, and K. Todorov, “A survey on web data linking,” Revue des Sciences et Technologies de l’Information-Série ISI: Ingénierie des Systèmes d’Information, 2016.

[17] J. Volz, C. Bizer, M. Gaedke, and G. Kobilarov, “Silk-a link discovery framework for the web of data.” Ldow, vol. 538, p. 53, 2009.

[18] L. P. Branquinho, R. M. A. Baracho, and M. B. Almeida, “Modelo para suporte à descoberta de conhecimento em base de dados (kdd): Aplicação em estratégias no mercado de medicina diagnóstica,” vol. 10, pp. 251–264, 2015.
