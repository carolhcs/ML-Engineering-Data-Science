
![DALL·E 2024-06-16 09 52 43 - Create a horizontal black and white noir-style comic strip banner in an 8_9 format that represents Machine Learning  The scene should feature a detect](https://github.com/carolhcs/ML-Engineering-Data-Science/assets/14095834/cc78d52b-01ac-419a-a0fa-363f66de0e79)

# Machine Learning Engineering and Data Science
Exercicios e Desfios do Bootcamp da DIO de Python Data Analytics - Machine Learning Engineering e Data Science
### Desafio de Projeto criado durante o bootcamp de Python Data Analytics da DIO
#### por Hellen Caroline Salvato
💻 [carolsalvato.com](https://carolsalvato.com) | [Linkedin](www.linkedin.com/in/hellencarolinesalvato) | [Perfil DIO](https://www.dio.me/users/carol_lgl) 

Os desafios originais foram feitos usando o Power BI da Microsoft, que é bem mais imples e amigavel. Porém como existem varias limitações relacionadas a ele, resolvi refazer meu desafio em python, como uma forma de me desafiar.



![DALL·E 2024-06-16 09 53 25 - Create a horizontal black and white noir-style comic strip banner in an 8_9 format that represents Machine Learning  The scene should feature a detect](https://github.com/carolhcs/ML-Engineering-Data-Science/assets/14095834/ffc133d8-bc43-42c4-af03-eab23b349f1f)

## Algoritmos Basicos de Machine Learning
[Exemplo de uso do MATPLOT LIB DIO](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/Projeto_ML_01_DIO.ipynb)

[Rede Neural do Zero DIO](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/Rede_Neural_do_Zero_DIO.ipynb)

### Algoritmo Genético (GA)
[Algoritmo Genético Simples em Python](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/Basic_GA.ipynb)

<details>
    <summary><h3>Algoritmo Genético Simples em Python</h3></summary>
Claro! Vou criar um algoritmo genético simples em Python, utilizando o formato do Google Colab, com blocos de código separados e explicações detalhadas. Vamos adicionar emojis para tornar as explicações mais atraentes e claras. 

### Algoritmo Genético Simples em Python

#### 🧬 Introdução aos Algoritmos Genéticos
Um algoritmo genético (AG) é uma técnica de busca heurística inspirada no processo de evolução natural. Ele é usado para encontrar soluções aproximadas para problemas de otimização e pesquisa.

#### 🛠️ Instalação de Bibliotecas Necessárias

```python
# 📦 Instalando bibliotecas necessárias
!pip install numpy
```

#### 🧩 Importação de Bibliotecas

```python
# 📚 Importando bibliotecas necessárias
import numpy as np
import random
```

#### 🧬 Funções de Auxílio

```python
# 🛠️ Funções de auxílio

# Função de fitness para avaliar a adequação de uma solução
def fitness_function(individual):
    return sum(individual)  # Exemplo simples: soma dos elementos do indivíduo

# Função para criar um indivíduo
def create_individual(length):
    return [random.randint(0, 1) for _ in range(length)]

# Função para criar uma população inicial
def create_population(size, length):
    return [create_individual(length) for _ in range(size)]
```

#### 👫 Seleção Natural

```python
# 👫 Seleção natural

# Função para selecionar indivíduos com base em sua aptidão (fitness)
def select(population, fitnesses, num_to_select):
    fitnesses = np.array(fitnesses)
    probabilities = fitnesses / fitnesses.sum()
    selected_indices = np.random.choice(len(population), size=num_to_select, p=probabilities)
    return [population[i] for i in selected_indices]
```

#### 🔄 Crossover e Mutação

```python
# 🔄 Crossover e mutação

# Função de crossover (cruzamento) de dois indivíduos
def crossover(parent1, parent2):
    crossover_point = random.randint(1, len(parent1) - 1)
    child1 = parent1[:crossover_point] + parent2[crossover_point:]
    child2 = parent2[:crossover_point] + parent1[crossover_point:]
    return child1, child2

# Função de mutação de um indivíduo
def mutate(individual, mutation_rate=0.01):
    for i in range(len(individual)):
        if random.random() < mutation_rate:
            individual[i] = 1 - individual[i]  # Inverte o bit
    return individual
```

#### 🌱 Evolução da População

```python
# 🌱 Evolução da população

# Função principal para evoluir a população
def genetic_algorithm(pop_size, ind_length, generations, mutation_rate):
    population = create_population(pop_size, ind_length)
    
    for generation in range(generations):
        # Calculando a aptidão (fitness) de cada indivíduo
        fitnesses = [fitness_function(individual) for individual in population]
        
        # Seleção natural
        selected = select(population, fitnesses, pop_size // 2)
        
        # Criando a próxima geração
        next_generation = []
        while len(next_generation) < pop_size:
            parent1, parent2 = random.sample(selected, 2)
            child1, child2 = crossover(parent1, parent2)
            next_generation.append(mutate(child1, mutation_rate))
            if len(next_generation) < pop_size:
                next_generation.append(mutate(child2, mutation_rate))
        
        population = next_generation
        
        # Melhor indivíduo da geração atual
        best_individual = max(population, key=fitness_function)
        print(f'Geração {generation + 1}: Melhor Fitness = {fitness_function(best_individual)}')
    
    return best_individual
```

#### 🚀 Executando o Algoritmo

```python
# 🚀 Executando o algoritmo genético

pop_size = 100  # Tamanho da população
ind_length = 10  # Tamanho de cada indivíduo (número de genes)
generations = 50  # Número de gerações
mutation_rate = 0.01  # Taxa de mutação

best_solution = genetic_algorithm(pop_size, ind_length, generations, mutation_rate)
print('Melhor solução encontrada:', best_solution)
```

### 📊 Conclusão
Este código implementa um algoritmo genético simples que pode ser adaptado para diversos tipos de problemas de otimização. Modificando a função de fitness e ajustando os parâmetros, você pode aplicar este algoritmo a problemas específicos em diferentes áreas.

</details>

### Algoritmo de colonia de formigas


### Rede Neural Artificial (RNA)


### Deep Learning




![DALL·E 2024-06-16 09 52 05 - Create a horizontal black and white noir-style comic strip banner in an 8_9 format that represents data science  The scene should include elements suc](https://github.com/carolhcs/ML-Engineering-Data-Science/assets/14095834/9fa620c5-d7cb-42f4-b712-59a1190fa45f)

## Desafios de Data Science / Python Data Analytics
O Power BI é uma ferramenta de Business Intelligence (BI) da Microsoft que permite a coleta, processamento, visualização e compartilhamento de dados. Ele é utilizado para transformar dados brutos em informações visuais e interativas, facilitando a tomada de decisões baseada em dados. 

### Power BI em Python
[Conexão e criação de um sistema base para análise de dados e geração de relatórios e gráficos](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/PowerBI_Python.ipynb)

### Criando Um Relatório Gerencial de Vendas com Power BI
[Criando Um Relatório Gerencial de Vendas com Power BI (com Python)](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/PowerBI_Python_01.ipynb)

### Criando um Dashboard corporativo com integração com MySQL e Azure

[Criando um Dashboard corporativo com integração com MySQL e Azure (com Python)](https://github.com/carolhcs/ML-Engineering-Data-Science/blob/main/PowerBI_Python_02.ipynb)

<details>
    <summary><h3>Criando um Dashboard corporativo em Python</h3></summary>
As ferramentas principais utilizadas são:

- **MySQL**: Para o banco de dados.
- **SQLAlchemy**: Para conexão ao banco de dados MySQL.
- **Pandas**: Para manipulação de dados.
- **Dash**: Para criar o dashboard web interativo.
- **Plotly**: Para visualização de dados.

### 1. Criando uma Instância do MySQL na Azure

Primeiro, é necessário criar uma instância do MySQL no Azure. Este passo envolve configurações no portal do Azure e não pode ser feito diretamente por código Python. Consulte a [documentação oficial](https://docs.microsoft.com/en-us/azure/mysql/quickstart-create-mysql-server-database-portal) para instruções detalhadas.

### 2. Explorando o Recurso - Instância do MySQL

Depois de criar a instância, você deve configurar os detalhes de conexão (host, user, password, database).

### 3. Se Conectando ao Banco de Dados com Cloud Shell

Para testar a conexão ao banco de dados, utilize o Azure Cloud Shell com comandos como:

```shell
mysql -h your-server.mysql.database.azure.com -u your-username@your-server -p
```

### 4. Criando Regra no Firewall na Azure para Acesso ao Banco de Dados

Configure uma regra no firewall para permitir conexões do seu IP. Isso pode ser feito através do portal do Azure na seção de configurações do banco de dados MySQL.

### 5. Conectando ao MySQL no Azure Utilizando Workbench

Teste a conexão utilizando o MySQL Workbench ou outro cliente de banco de dados para garantir que está tudo funcionando.

### 6. Integrando Power BI com MySQL na Azure

Vamos traduzir esta etapa para Python, integrando nosso banco de dados MySQL com um dashboard criado com Dash.

### Passo a Passo em Python

#### Conectando ao Banco de Dados MySQL

Instale as bibliotecas necessárias:
```bash
pip install pandas sqlalchemy dash plotly
```

```python
import pandas as pd
from sqlalchemy import create_engine

# Configurar a string de conexão ao MySQL no Azure
db_user = 'your-username@your-server'
db_password = 'your-password'
db_host = 'your-server.mysql.database.azure.com'
db_name = 'your-database-name'

connection_string = f'mysql+pymysql://{db_user}:{db_password}@{db_host}/{db_name}'
engine = create_engine(connection_string)

# Ler dados do banco de dados
query = "SELECT * FROM your_table"
df = pd.read_sql(query, engine)
```

#### Criando o Dashboard com Dash

```python
import dash
import dash_core_components as dcc
import dash_html_components as html
from dash.dependencies import Input, Output
import plotly.express as px

app = dash.Dash(__name__)

# Layout do dashboard
app.layout = html.Div([
    html.H1("Dashboard Corporativo"),
    dcc.Dropdown(
        id='filter-dropdown',
        options=[{'label': item, 'value': item} for item in df['your_column'].unique()],
        value=df['your_column'].unique()[0]
    ),
    dcc.Graph(id='example-graph')
])

# Callback para atualizar o gráfico com base no filtro selecionado
@app.callback(
    Output('example-graph', 'figure'),
    [Input('filter-dropdown', 'value')]
)
def update_graph(selected_value):
    filtered_df = df[df['your_column'] == selected_value]
    fig = px.bar(filtered_df, x='x_column', y='y_column', title='Seu Gráfico')
    return fig

if __name__ == '__main__':
    app.run_server(debug=True)
```

### Considerações Finais

Para um deployment em produção, considere utilizar serviços de hospedagem que suportem aplicações Python, como Heroku, AWS, ou Azure App Service. Certifique-se de proteger suas credenciais e seguir boas práticas de segurança ao configurar sua aplicação e banco de dados.

</details>

----------------------------------------------------------------

![image](https://github.com/carolhcs/ML-Engineering-Data-Science/assets/14095834/56963b32-0d4d-44fc-b58d-a77387ee3e55)


