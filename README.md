
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



<img src=images/pbdc_002.png>

<img src=images/pbdc_001.png>
  
<img src=images/pbdc_003.png>

<img src=images/pbdc_004.png>

<img src=images/pbdc_005.png>


<img src=images/pbdc_006.png>

<img src=images/pbdc_007.png>

<img src=images/pbdc_008.png>


<img src=images/pbdc_009.png>


<img src=images/pbdc_010.png>


<img src=images/pbdc_011.png>


<img src=images/pbdc_012.png>


<img src=images/pbdc_013.png>


<img src=images/pbdc_014.png>

<img src=images/pbdc_015.png>


## Recursos Usados

  - Importação de Database
  - Limpeza de dados
  - Criação de um DataFrame
  - Análise de parâmetros estatísticos
  - Análise de gráficos
  - Construção de um modelo de regressão linear
  - Teste e validação deste modelo
  

## Links

  - Repositório: https://github.com/Alexandremsn/Ricks_Diamonds
  - Se for encontrado um bug, favor entrar em contato alexandremsneto1986@gmail.com


## Versão

1.0.0.0


## Autor

* **Alexandre Machado da Silva Neto**: @alexandremsn (https://github.com/alexandremsn)
