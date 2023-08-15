# `Prog. Orientada a Objetos - Desafio Final`

> ####  módulo [ADA 1011 POO]
> `Participantes:`
> *Celice | João | Juan | Ivan | Rafael* 

## Implementar uma aplicação para uma Farmácia que vende produtos através de e-commerce.
  
>`Requisitos:`
_A farmácia precisa dos seguintes serviços (que devem ser disponibilizados para escolha do usuário através de um menu feito no console). 
 *Não é necessário implementar interface gráfica*_

+ Deverá conter um cadastro de clientes, no qual a busca se dará por CPF (sem pontuação)
+ Deverá conter um cadastro de medicamentos, no qual a busca se dará pelo nome, fabricante ou descrição parcial de acordo com o tipo de medicamento. Os medicamentos poderão ser Quimioterápicos ou Fitoterápicos. Os medicamentos Quimioterápicos deverão ter a informação sobre se são vendidos apenas mediante receita ou não (Ex: remédios tarja preta e antibióticos).
+ Através do sistema deverá ser possível efetuar vendas, e estas serão realizadas apenas para clientes cadastrados no sistema.
+ Durante a venda, haverá 20% de desconto para clientes idosos (acima de 65 anos), e 10% de desconto nas compras acima de 150 reais. Os descontos não são cumulativos, e deve ser dado sempre o desconto mais alto caso haja conflito.
+ Durante a venda de remédios Quimioterápicos, se um dos remédios for do tipo controlado (que exige apresentação de receita para a compra), o sistema deverá emitir um alerta ao atendente questionando se o mesmo verificou a receita do respectivo remédio. Deverá ser informado no alerta o nome do remédio controlado.

>`Deverá ser possível emitir relatórios:`
* De listagem de clientes, cadastrados por nome, em ordem alfabética crescrente (A-Z), especificando os dados do cliente
* De listagem de medicamentos, por ordem alfabética
* De listagem de medicamentos Quimioterápicos ou Fitoterápicos
* Estatísticas dos atendimentos realizados no dia (considere o dia como o tempo que o menu está em execução. Quando for sair do programa, deve ser emitido este relatório) contendo:
* Remédio mais vendido, contendo a quantidade e o valor total
* Quantidade de pessoas atendidas
* Número de remédios Quimioterápicos vendidos no dia, contendo a quantidade e o valor
* Número de remédios Fitoterápicos vendidos no dia, contendo a quantidade e o valor

>`Requisitos mínimos a serem observados na modelagem:`
* Existem 5 classes obrigatórias no seu projeto: 
    * *Clientes, Medicamentos Quimioterápicos, Medicamentos Fitoterápicos, Laboratórios e Vendas.* 
    * Elas devem ser usadas para organizar o projeto, e devem conter no mínimo os detalhes abaixo:
        + Clientes
            * Identificador (CPF)
            * Nome
            * Data de nascimento
        + Medicamentos Quimioterápicos
            * Nome
            * Principal composto
            * Laboratório
            * Descrição
            * Necessita receita
        + Medicamentos Fitoterápicos
            * Nome
            * Principal composto
            * Laboratório
            * Descrição
        + Laboratório
            * Nome
            * Endereço
            * Telefone para contato
            * Cidade
            * Estado
        + Vendas
            * Data e hora da venda
            * Produtos vendidos
            * Cliente
            * Valor total
            * Status

**_Importante:
Como "banco de dados" temporário para armazenar os dados sugerimos listas ou dicionários (o que for mais simpĺes de implementar). Não recomendamos bancos de dados (relacionais ou não relacionais) ou arquivos, visto que estas estruturas não são o foco deste módulo._**

>`Estrutura do projeto:`
````
C:.
│   README.md                           --> Detalhes do projeto
│   requirements.txt                    --> Bibliotecas obrigatórias
├─── docs                                    
│        Projeto Final - POO.ipynb      --> Projeto em formato notebook (#todo)
└─── e_farmacia                              
    │    __init__.py                    --> Inicialização do pacote
    │    e_farmacia.py                  --> Programa principal
    ├─── modulo_farmacia                                
    │       __init__.py                 --> Inicialização do pacote
    │       modulo_farmacia.py          --> Módulo principal
    │       modulo_auxiliar.py          --> Módulo auxiliar
    │       e_farmacia.db.json          --> Arquivo de banco persistente
    │       e_farmacia.log              --> Arquivo de log
````

>`Estrutura do banco de dados:`
````
{
    "Clientes":[
       {
          "Identificador":"",
          "Nome":"",
          "Data de nascimento":"",
          "Receitas Médicas":[
             {
                "Nome":"",
                "Principal composto":"",
                "Validade":""
             }
          ],
          "Status":true,
          "Data Criação":""
       }
    ],
    "Laboratórios":[
       {
          "Nome":"",
          "Telefone":"",
          "Endereço":"",
          "Cidade":"",
          "Estado":"",
          "Data Criação":""
       },
       {
          "Nome":"",
          "Telefone":"",
          "Endereço":"",
          "Cidade":"",
          "Estado":"",
          "Data Criação":""
       }
    ],
    "Medicamentos Quimioterápicos":[
       {
          "Nome":"",
          "Principal composto":"",
          "Laboratório":"",
          "Descrição":"",
          "Valor":0.00,
          "Necessita receita":true,
          "Data Criação":""
       },
       {
          "Nome":"",
          "Principal composto":"",
          "Laboratório":"",
          "Valor":0.00,
          "Descrição":"",
          "Necessita receita":true,
          "Data Criação":""
       }
    ],
    "Medicamentos Fitoterápicos":[
       {
          "Nome":"",
          "Principal composto":"",
          "Laboratório":"",
          "Valor":0.00,
          "Descrição":"",
          "Necessita receita":false,
          "Data Criação":""
       }
    ],
    "Vendas":[
       {
          "Cliente":"",
          "Valor total":0.00,
          "Produtos vendidos":[
             {
                "Nome":"",
                "Tipo":"",
                "Valor":0.00
             }
          ],
          "Status":"",
          "Data da Venda":""
       },
       {
          "Cliente":"",
          "Valor total":0.00,
          "Produtos vendidos":[
             {
                "Nome":"",
                "Tipo":""
             }
          ],
          "Status":"",
          "Data da venda":""
       }
    ]
}
````
