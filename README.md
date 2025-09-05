# Explorando evolução de código

Neste exercício, iremos explorar a evolução de código em sistemas reais.

Iremos utilizar a ferramenta [GitEvo](https://github.com/andrehora/gitevo).
Essa ferramenta analisa a evolução de código em repositórios Git nas linguagens Python, JavaScript, TypeScript e Java, e gera relatórios `HTML` como [este](https://andrehora.github.io/gitevo-examples/python/pandas.html).

Mais exemplos de relatórios podem ser podem ser encontrados em https://github.com/andrehora/gitevo-examples.

# Passo 1: Selecionar repositório a ser analisado

Selecione um repositório relevante na linguagem de sua preferência (Python, JavaScript, TypeScript ou Java).
Você pode encontrar projetos interessantes nos links abaixo:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

# Passo 2: Instalar e rodar a ferramenta GitEvo

> [!NOTE]
> Antes de instalar a ferramenta, é recomendado criar e ativar um [ambiente virtual Python](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments).

Instale a ferramenta [GitEvo](https://github.com/andrehora/gitevo) com o comando:

```
$ pip install gitevo
```

Execute a ferramenta no repositório selecionado utilizando o comando abaixo (ajuste conforme a linguagem do repositório).
Substitua `<git_url>` pela URL do repositório que será analisado:

```shell
# Python
$ gitevo -r python <git_url>

# JavaScript
$ gitevo -r javascript <git_url>

# TypeScript
$ gitevo -r typescript <git_url>

# Java
$ gitevo -r java <git_url>
```

Por exemplo, para analisar o projeto Flask escrito em Python:

```
$ gitevo -r python https://github.com/pallets/flask
```

> [!NOTE]
> Essa etapa pode demorar alguns minutos pois o projeto será clonado e analisado localmente.

# Passo 3: Explorar o relatório de evolução de código

Após executar a ferramenta [GitEvo](https://github.com/andrehora/gitevo), é gerado um relatório `HTML` contendo diversos gráficos sobre a evolução do código.

Abra o relatório `HTML` e observe com atenção os gráficos.

# Passo 4: Explicar um gráfico de evolução de código

Selecione um dos gráficos de evolução e explique-o com suas palavras.
Por exemplo, você pode:

- Detalhar a evolução ao longo do tempo
- Detalhar se as curvas estão de acordo com boas práticas
- Explicar grandes alterações nas curvas
- Explorar a documentação do repositório em busca de explicações para grandes alterações
- etc.

Seja criativo!

# Instruções para o exercício

1. Crie um `fork` deste repositório (mais informações sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Adicione o relatório `HTML` no seu fork.
3. No Moodle, submeta apenas a URL do seu `fork`.

Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork:

1. Repositório selecionado: https://github.com/axios/axios
2. Gráfico selecionado:

<img width="500" alt="Variable_declarations" src="https://github.com/user-attachments/assets/eef767e3-3379-4a41-ae11-a385bd3329e9" />

4. Explicação: 

O gráfico é relativo à biblioteca Axios, escrita em JavaScript, que permite fazer requisições HTTP no lado do cliente e do servidor, auxiliando no desenvolvimento de sistemas web.

O gráfico mostra a clara evolução e manutenção da ferramenta com o passar do tempo. O aumento no número total de declarações de variáveis demonstra um crescimento do código, o que muito provavelmente está relacionado com o surgimento ou melhoria de funcionalidades da biblioteca, um indicador positivo de que o projeto é bem mantido, já que cresce constantemente. 

Além disso, existe um ponto de virada muito chave nas curvas de cada tipo de variável declarada. Entre 2022 e 2023, houve um crescimento muito grande no número de chamadas do tipo `const`, e o decréscimo de chamadas do tipo `var`.
Esse comportamento provavelmente indica que nesse momento houveram muitos esforços para refatoração ou reestruturação do código da biblioteca, já que variáveis `const` são mais seguras, pois são limitadas a um escopo e não podem ser reescritas, tornando o código mais legível e com menos comportamentos inesperados.

Ao pesquisar sobre o contexto dessas mudanças, existe um evento bem significativo na linha do tempo, que pode ter incentivado essa reestruturação da biblioteca.
A biblioteca Axios sempre foi bastante popular no desenvolvimento Web pois fornecia uma interface simples, mas também bastante completa para lidar com requisições HTTP.
Em 2022, a API `fetch`, nativa do JavaScript, se tornou bastante popular, pois passou a ser adotada por todos os navegadores, e em principal, passou a ser suportada pelo ambiente de desenvolvimento Node.js. 
Ela surgiu como uma opção bastante simples e de interface clara e concisa, e é uma opção bastante utilizada para requisições HTTP.
Nesse contexto, acredito que houve uma necessidade da ferramenta Axios de se modernizar, de oferecer ainda mais capacidades que vão além das funcionalidades mais simples, para que ainda existam casos de uso para a ferramenta e se diferenciar da opção nativa da linguagem, por isso, os desenvolvedores tiveram de reestruturar o projeto para que a biblioteca pudesse expandir de forma mais robusta e segura, em termos de código.
