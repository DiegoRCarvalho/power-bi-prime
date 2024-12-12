# Power BI

[Clique aqui](https://www.youtube.com/playlist?list=PLFKhhNd35zq90tdc3PYpx4IA-SoxSNlmN) para acessar a playlist do curso **Curso de Power BI - Do Básico ao Profissional** fornecido pelo canal **Prime Cursos do Brasil** do Youtube.

## Materiais utilizados no curso

├── Materiais

│ └── Dimensão

│   └── Canal.xlsx

│   └── Categoria.xlsx

│   └── Cidade.xlsx

│   └── Clientes.txt

│   └── Marca.xlsx

│   └── Produto.xlsx

│   └── Subcategoria.xlsx

│ └── Fato

│   └── vendas - 2010_2013.xlsx

│   └── vendas - 2014_2017.xlsx

│   └── vendas - 2018_2021.xlsx



## Importar fontes de dados

Vamos importar os dados fornecidos no diretório Materiais.

### Importar Planilhas

- No diretório **Dimensão** Temos planilhas e um arquivo de texto, vamos importá-los utilizando o botão *Página Inicial / Obter Dados* e o tipo de arquivo desejado, por exemplo Excel, Texto, pasta, etc.

- Ao importar uma planilha, recebemos o seguinte questionamento:

    ![alt](images/001.png)

    a. A primeira opção que podemos ver na imagem, é para importar no formato de **tabela**.

    b. A segunda opção, é para importar no formato de **planilha**.

        A melhor opção é importar como tabela, diferença entre as duas é que a tabela só importa as linhas e colunas que contém dados. Já no formato de planilha irá importar as 1.048.576 linhas e 16.384 colunas do Excel, deixando a tudo mais lento.

- Clicar em **Carregar**, a pasta *Dimensão* possui várias planilhas para importar, então é mais prático apenas carregar todas elas e transformar os dados em uma etapa posterior, mas também é possível clicar em **Transformar Dados** e realizar cada transformaçãos nessa etapa.
Após carregar todas as planilhas deste diretório, teremos a seguinte estrutura:
  
    ![alt](images/002.png)

### Importar arquivos de texto

- Atenção ao arquivo *Clientes.txt*, ele não é uma planilha, é um arquivo de texto com dados separados por tabulações, nesses casos, sempre devemos avaliar o arquivo para descobrir qual o seu delimitador, é tabulação, é vírgula, é ponto e vírgula, etc.

    ![alt](images/003a.png)
    ![alt](images/003b.png)


- Clicar em *Página Inicial / Transformar dados*

    ![alt](images/004.png)

- Na tela aberta, vamos editar os nomes das tabelas e os tipos de dados.

    ![alt](images/005.png)

    1. Nos nomes de arquivos iremos remover acentos, espaços e caracterés especiais. Além disso, é interessante adicionar um prefíxo *dim_*, pois todos os arquivos são referentes a dimenções.
      
      ![alt](images/006.png)
    
    2. Nos tipos de dados iremos verificar em cada tabela se o tipo está correto, para alterar basta seguir o exemplo da imagem abaixo.
    
        ![alt](images/007.png)

    3. Na tabela dim_cliente iremos mesclar as colunas nome e sobrenome.
      
        ![alt](images/008a.png)
        ![alt](images/008b.png)

    4. Ainda na tabela dim_cliente iremos corrigir a coluna Data de nascimento, o tipo está como texto, com aspas e no formato americano (M-D-YYYY). As imagens a seguir irão mostrar o passo a passo e o resultado das transformações.
      
        ![alt](images/009a.png)
        ![alt](images/009b.png)
        ![alt](images/009c.png)
        ![alt](images/009d.png)
        ![alt](images/009e.png)
        ![alt](images/009f.png)

    5. Em seguida basta clicar em fechar e aplicar para salvar as transformações nas tabelas.

### Criar Pastas

É interessante organizar os arquivos em pastas, para criar uma pasta, clique com o botão direito e em seguida em *Novo Grupo*, digite o nome desejado e depois arraste os arquivos para dentro da pasta.

  ![alt](images/010.png)

### Importar arquivos semelhantes automaticamente

- Agora vamos adicionar os arquivos do diretório Fato, onde temos 3 planilhas com a mesma estrutura, porém cada uma possui dados relativos a um período de tempo. Vamos entender como automatizar essa importação.

  ![alt](images/011a.png)
  ![alt](images/011b.png)

- Vamos clicar em Transformar dados porque existem transformações necessárias antes de podermos combinar os arquivos.

  ![alt](images/011c.png)

- Conforme formos adicionando novas planilhas nessa pasta, se elas seguirem o padrão de nomeclatura e possuir as mesmas colunas, então elas serão importadas automaticamente.

    ![alt](images/011d.png)

- A única coluna necessária para mesclarmos as 3 planilhas e outras que podem ser adicionadas no futuro, é a coluna Content, então podemos excluir as demais.

    ![alt](images/011e.png)

- Em seguida, iremos clicar no ícone de 2 setas para baixo ao lado do nome da coluna. Repare que na visualização existem tratativas necessárias nos arquivos.

    ![alt](images/011f.png)

- No arquivo exemplo iremos remover os cabeçarios promovidos automaticamente e excluir as 4 primeiras linhas. Essa remoção não afeta o arquivo original, altera apenas o arquivo concatenado presente no Power BI.

    ![alt](images/011g.png)

- Como os arquivos importados são planilhas e não tabelas, devemos remover as linhas vazias.

  ![alt](images/011h.png)   

- Em seguida iremos promover a primeira linha como cabeçalho.

    ![alt](images/011i.png)

- A tabela concatenada irá apresentar erros porque ela está tentando procurar as linhas e colunas que excluímos, para solucionar, basta remover a etapa de tipo alterado, como na imagem abaixo.

    ![alt](images/011j.png)

- Ficará assim: 

    ![alt](images/011k.png)
    ![alt](images/011l.png)


## Modelagem de Dados

A modelagem de dados é igual a modelagem de um banco de dados. Não tenho muito o que explicar, vou colocar a imagem abaixo caso eu queira lembrar de algum detalhe no futuro.

  ![alt](images/012.png)


## Criar Tabela Calendário

- Para criar uma nova tabela, faça: 

  ![alt](images/014a.png)

- A função CALENDARAUTO() descobre a menor e a maior data entre todas as planilhas e recupera todas as datas entre elas. Essa função se autoincrementa sozinha, então se for adicionada uma nova data, ela será reconhecida e a função recalculada automaticamente.

  ![alt](images/014b.png)

- Criar outras colunas.

  ![alt](images/014c.png)

- Função YEAR() recupera o ano de uma data
  
  ![alt](images/014d.png)

- Função MONTH() recupera o número do mês de uma data. Repare que a data está na mesma tabela que a coluna criada, então ela pode ser chamada apenas utilizando [nome da coluna], sem precisar indicar em qual tabela a coluna está.
  
  ![alt](images/014e.png)

- Função FORMAT() Converte um texto em um formato especificado. No exemplo recupera o nome do mês.
  
  ![alt](images/014f.png)

- Função DAY() recupera o número do dia de uma data.
  
  ![alt](images/014g.png)

- Função FORMAT() Converte um texto em um formato especificado. No exemplo recupera o nome do dia.
  
  ![alt](images/014h.png)

- Por questões de boa prática é recomendável marcar a tabela como tabela de data.
  
  ![alt](images/014i.png)

- Por útimo, criamos um relacionamento entre a tabela fato (data venda) e a tabela calendário(data).
  
  ![alt](images/014j.png)

## Medidas

Para fazer cálculos, sempre devemos utilizar medidas, mesmo que existam colunas com valor total, por questões de performace é melhor usar uma medida.

  ![alt](images/015a.png)


### Medida de soma

  ![alt](images/015b.png)
  ![alt](images/015c.png)

### Medida de contar linhas da tabela

  ![alt](images/015d.png)

### Medida de média de qtde. vendidas

  ![alt](images/015e.png)

## Função Related

Se parece com o procx do Excel, mas no Power BI, é necessário que as duas tabelas tenha um relacionamento para poder utilizar essa função.

  ![alt](images/016.png)

## Função Iteradora

Permite obter o total através de um cálculo sobre outras colunas, **realizando o cálculo linha a linha**. As funções iteradoras terminam com um X no final do nome.

- Neste exemplo vemos porque não podemos apenas multiplicar uma coluna pela outra.
  ![alt](images/017a.png)

- O mesmo exemplo anterior, mas agora usando a função iteradora SUMX.
  ![alt](images/017b.png)

- O mesmo exemplo anterior, mas agora obtendo a média através da função iteradora AVERAGEX.
  ![alt](images/017c.png)

## Mínimo e Máximo

- No exemplo abaixo vemos que as funções MIN e MAX retornaram apenas o menor e o maior valor da tabela e não o mínimo e máximo de cada marca.

  ![alt](images/018a.png)

- A solução para esse caso é aplicar uma segmentação de dados.
  ![alt](images/018b.png)


## Descobrir Lucro / Margem

1. Vamos descobrir o valor bruto vendido e se existem descontos nas vendas

  - Para descobrir o valor bruto vendido, criamos uma medida combinando as funções SUMX e RELATED, para obtermos a Qtde que está na fato_vendas e multiplicar esse valor por Preco_Unitario que está na tabela dim_produto. Lembrando que a função RELATED só funciona se existir um relacionamento entre as duas tabelas.

    ![alt](images/019a.png)

  - A tabela fato vendas já possui um campo valor total, então teoricamente chegaríamos ao mesmo resultado anterior, apenas somando os valores dessa coluna.

    ![alt](images/019b.png)

  - Quando comparamos as colunas Faturamento Bruto e Venda Total, percebemos que existem diferenças de valores, isso aconteceu propositalmente, apenas para exemplificar uma situação que costuma acontecer na vida real, onde responsável pela planilha não informou que a coluna Valor Total na verdade utiliza o valor com o desconto da venda e não o valor real do produto.

    ![alt](images/019c.png)

  - Agora que já sabemos o valor bruto e o valor com o desconto, conseguimos exibir o desconto.

    ![alt](images/019d.png)

2. Descontar tributos e custos

  - Essa informação está presente na tabela dim_produto.

    ![alt](images/019e.png)

  - Para trazermos essas duas medidas para o nosso exemplo iremos utilizar a combinação das funções SUMX e RELATED igual fizemos para descobrir o valor bruto vendido.

    ![alt](images/019f.png)

    ![alt](images/019g.png)

3. Resultado

    ![alt](images/019h.png)

  - Quantida: Qtd. de produtos vendidos.

  - Faturamento Bruto: Qtd de produtos vendidos multiplicado pelo preço unitário dos produtos.

  - Desconto: Desconto fornecido ao cliente durante a venda.

  - Receita Bruta: Qtd de produtos vendidos multiplicado pelo preço unitário com os descontos dos produtos. Nesse exemplo esse dado está contido na coluna Venda Total da tabela fato_vendas.

  - Tributos: Total pago em impostos

  - Receita Líquida: É obtida através da subtração da Receita Bruta pelos tributos.

  - Custos: Valor gasto com insumos, etc.

  - Lucro / Margem:  É obtida através da subtração da Receita Líquida pelos Custos.