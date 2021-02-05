# Boas vindas ao repositório do projeto Restaurant Orders!

## O que foi desenvolvido

A lanchonete Pão na Chapa, atualmente possui um sistema de faturamento dos pedidos dos clientes, que salva o nome da pessoa, o pedido realizado, e dia do atendimento (dia da semana). O projeto consiste em ajudar a lanchonete a melhorar esse sistema para que ele possibilite extração de relatórios e num segundo momento, a controlar seu estoque.

O projeto está estruturado em duas etapas obrigatórias, e a tarefa bônus, também em duas etapas, totalizando 4 requisitos. Foco nas etapas obrigatórias e com o mesmo cuidado que teria com um cliente real: código limpo, com boa manutenção e legibilidade.

---

## Desenvolvimento e testes

**Estrutura do repositório**

- No diretório `src/` você vai encontrar os arquivos onde foram implementadas todas as classes e métodos que considerei importantes para resolver cada etapa do projeto;

- No diretório `data/` você vai encontrar os arquivos de _log_ que foram utilizados em cada etapa;

- Os testes foram implementados nos arquivos do diretório `tests/`.

**Testes**

Para executar os testes, lembre-se de primeiro **criar e ativar o ambiente virtual**, além de também instalar as dependências do projeto. Isso pode ser feito através dos comandos:

```bash
$ python3 -m venv .venv

$ source .venv/bin/activate

$ python3 -m pip install -r requirements.txt
```

**Instalação de dependências**

O arquivo `requirements.txt` contém todos as dependências que serão utilizadas no projeto

Se quiser saber mais sobre a instalação de dependências com `pip`, veja esse [artigo.](https://medium.com/python-pandemonium/better-python-dependency-and-package-management-b5d8ea29dff1)

**Estilo**

Para verificar se você está seguindo o guia de estilo do Python corretamente, execute o comando:

```bash
$ python3 -m flake8
```

---

## Requisitos obrigatórios:

### 1 - Campanha de publicidade

A lanchonete quer promover ações de marketing e, para isso, a agência de publicidade precisa exatamente das informações abaixo:

- Qual o prato mais pedido por 'maria'?

- Quantas vezes 'arnaldo' pediu 'hamburguer'?

- Quais pratos 'joao' nunca pediu?

- Quais dias 'joao' nunca foi na lanchonete?

#### Dados

O atual sistema guarda os `logs` de todos os pedidos feitos em um arquivo _csv_, contendo o formato `cliente, pedido, dia`, um por linha e sem nome das colunas (a primeira linha já é um pedido).

O `log` a ser utilizado é o arquivo `data/orders_1.csv`. Todas as informações são _strings_ com letras minúsculas. O histórico contém pedidos feitos em todos os dias da semana e de todos os pratos que a lanchonete oferece. Ou seja, é possível saber o cardápio completo. Os dias da semana estão no formato `"...-feira", "sabado" ou "domingo"`.

#### Implementação

No arquivo `analyse_log.py`, escrevi uma função que responde às seguintes perguntas abaixo:

- Qual o prato mais pedido por 'maria'?

- Quantas vezes 'arnaldo' pediu 'hamburguer'?

- Quais pratos 'joao' nunca pediu?

- Quais dias 'joao' nunca foi na lanchonete?

A função não retornará nada! A função apenas salva as respostas no arquivo `data/mkt_campaign.txt`, na mesma ordem que acima.

**Assinatura da função:**

```python
def analyse_log(path_to_file):
    # Código vem aqui
```

### 2 - Teste do método `analyse_log()`

No arquivo `tests/test_analyse_log.py`, implementei um teste que verifica se a saída da função, escrita no arquivo `txt`, está correta.

**Saída correta:**

- hamburguer;

- 0;

- {'pizza', 'coxinha', 'misto-quente'};

- {'sabado', 'segunda-feira'}

### 3 - Análises contínuas

A campanha de marketing foi um sucesso! A gerência agora deseja um sistema que mantenha um registro contínuo dessas informações. Mais especificamente, desejam que o sistema permita a extração das seguintes informações a qualquer momento:

- Prato favorito por cliente;

- Quanto de cada prato cada cliente já pediu;

- Pratos nunca pedidos por cada cliente;

- Dia mais movimentado;

- Dia menos movimentado.

Para isso, implementei uma classe que entregue as informações acima.

### 4 - Teste da classe `TrackOrders`

##### As seguintes verificações serão feitas:

- Elaborado uma suíte de testes que garante, no mínimo, 90% de cobertura das classes;

- Implementado os testes no arquivo `test_track_orders.py`.

---
