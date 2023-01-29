
<div align="center">
<img src="images/clipart867608.png" width="150">

# Dashboard Comercial Hipotética Natural(readme em construção)

<div align="left">
Criação de um Dashboard Simples com Power BI, compondo uma consulta em SQL e criando um dashboard para a área comercial, mostrando a participação de seus vendedores . 


## Tecnologia

Os softwares  usados neste projeto foram:

* Microsoft Power BI
* MySQL WorkBench

## Serviços Usados

* Github
* Thispersondoesnotexist.com (todas imagens dos vededores foram criadas por inteligência artificial e não são pessoas reais)



## Como foi feito

Será descrito abaixo através de textos e imagens.

As tabelas estão disponíveis neste repositório, foram importados anteriormente.

Vamos em um primeiro momento focar na solicitação do cliente para elaborar uma consulta que vai nos trazer apenas os dados necessários para os visuais desejados.

O cliente possui 3 vendedores, e quer acompanhar o desenvolvimento individual das vendas destes vendedores.
O cliente quer saber:
* Quantidade vendida por mês no ano selecionado.
* Total vendido em reais no período.
* Total vendido por mês no ano selecionado.
* Participação das vendas por produto
* Participação das vendas por região

Para atender esta solicitação elaboramos a consulta abaixo:


use sucos_vendas;
select itens_notas_fiscais.numero, itens_notas_fiscais.quantidade, itens_notas_fiscais.preco, notas_fiscais.DATA_VENDA, tabela_de_clientes.estado, tabela_de_clientes.cidade, tabela_de_clientes.bairro, tabela_de_produtos.NOME_DO_PRODUTO, tabela_de_vendedores.nome , (itens_notas_fiscais.preco * itens_notas_fiscais.preco) as valor from itens_notas_fiscais
join notas_fiscais on itens_notas_fiscais.NUMERO = notas_fiscais.numero
left join tabela_de_clientes on notas_fiscais.cpf = tabela_de_clientes.cpf
left join tabela_de_produtos on itens_notas_fiscais.codigo_do_produto = tabela_de_produtos.CODIGO_DO_PRODUTO
left join tabela_de_vendedores on notas_fiscais.MATRICULA = tabela_de_vendedores.MATRICULA;


Assim ficamos com a tabela constando número da nota, quantidade vendida por nota, preço de venda unitário por nota, data da venda, bairro, cidade, estado do cliente, nome do produto, valor total vendido do produto.
  
<img src=images/pbdc_002.png>
  
Carregamos o bando de dados no Power BI e colocamos as credenciais de acesso ao banco.   

<img src=images/pbdc_001.png>
  
Selecionamos as opções avançadas e inserimos nossa consulta SQL.

  
<img src=images/pbdc_003.png>
  
Assim carregamos a tabela com a nossa consulta com apenas os dados necessários para os visuais que o cliente solicitou.

<img src=images/pbdc_004.png>

Como podemos verificar todos os campos necessários forram carregados no detalhe das colunas disponíveis de dados.
  
<img src=images/pbdc_005.png>

Elaboramos um template para comportar todos nosso visuais.
  
<img src=images/pbdc_007.jpg> 
  
Começamos criando nosso primeiro visual o gráfico de linhas de vendas por período.
  
<img src=images/pbdc_006.png>
  
  

Agora criamos o visual um gráfico de colunas indicando o número de unidades vendidas.
Optamos por este gráfico pois ao selecionar os dados separadamente podemos ver o destaque da fração selecionada x total.




<img src=images/pbdc_008.png>

Criamos um gráfico por bairro pois como atendemos apenas cidades de São Paulo e Rio de Janeiro, segregar por bairro pode ser interessante quando visualizarmos os vendedores individualmente.
  

<img src=images/pbdc_009.png>

Um gráfico de rosca para verificar a participação nas vendas de cada produto.  

<img src=images/pbdc_010.png>

Por último um cartão indicando o valor total em reais das vendas.
  
<img src=images/pbdc_011.png>

Criamos botões para os vendedores um botão para limpar os indicadores, e um menu suspenso para selecionar o ano desejado. Criamos um indicador para cada vendedor, e um indicador geral. Adicionamos a ação em cada botão.
  
<img src=images/pbdc_012.png>

Unimos todo com o template e ficamos com este resultado.
  
<img src=images/pbdc_013.png>

Agora no ambiente publicado temos a visualização tal como o usuário final, clicamos no botão e vimos que o indicador do vendedor é ativado.  

<img src=images/pbdc_014.png>

Ao Selecionar o ano desejado vimos que o relatório responde nos mostrando os dados do vendedor no ano selecionado. 
  
<img src=images/pbdc_015a.png>


## Recursos Usados

  - Construção de uma consulta SQL
  - Crianção de um template
  - Criação de botões personalizados
  - Criação de visuais
  - Criação de indicadores
  - Construção de um dashboard para atender as necessidades do cliente
  

## Links

  - Repositório: https://github.com/Alexandremsn/Dash_Comercial
  - Se for encontrado um bug, favor entrar em contato alexandremsneto1986@gmail.com


## Versão

1.0.0.0


## Autor

* **Alexandre Machado da Silva Neto**: @alexandremsn (https://github.com/alexandremsn)
