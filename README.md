# Guia de Configuração e Execução de Script Python em Ambiente Virtual

Este guia oferece instruções detalhadas sobre como configurar e executar um script Python em um ambiente virtual isolado. Testado no Windows 11 com Python 3.12.

## Índice

- [Guia de Configuração e Execução de Script Python em Ambiente Virtual](#guia-de-configuração-e-execução-de-script-python-em-ambiente-virtual)
  - [Índice](#índice)
  - [Configuração do Ambiente](#configuração-do-ambiente)
    - [Criar o Ambiente Virtual](#criar-o-ambiente-virtual)
    - [Ativar o Ambiente Virtual](#ativar-o-ambiente-virtual)
    - [Instalar Dependências](#instalar-dependências)
    - [Preparar o ChromeDriver](#preparar-o-chromedriver)
  - [Execução do Script](#execução-do-script)
  - [Desativar o Ambiente Virtual](#desativar-o-ambiente-virtual)
  - [Detalhes do Teste Automatizado](#detalhes-do-teste-automatizado)

## Configuração do Ambiente

### Criar o Ambiente Virtual

Execute o seguinte comando para criar um ambiente virtual:

```bash
python -m venv venv
```

### Ativar o Ambiente Virtual

Ative o ambiente virtual com o comando:

```bash
.\venv\Scripts\activate
```

### Instalar Dependências

Com o ambiente virtual ativado, instale as dependências listadas no arquivo requirements.txt:

```bash
pip install -r .\requirements.txt
```

### Preparar o ChromeDriver

Faça o download do ChromeDriver e coloque-o no mesmo diretório que seu script. Use o seguinte link para download:

[ChromeDriver Download](https://googlechromelabs.github.io/chrome-for-testing/known-good-versions-with-downloads.json)

## Execução do Script

Com o ambiente virtual ativado e as dependências instaladas, execute o script usando o seguinte comando:

```bash
python pratica-automacao-de-testes.py
```

## Desativar o Ambiente Virtual

Após a execução do script, desative o ambiente virtual com o comando:

```bash
deactivate
```
## Detalhes do Teste Automatizado

O script de teste automatizado utiliza o Selenium WebDriver para interagir com uma página HTML local (sample-exercise.html). A seguir, os passos do teste:

1.  Abertura da Página: Verifica se a página foi aberta corretamente comparando o título da página com "Sample page".
2.  Geração de Código:
  - Clica no botão "generate".
  - Aguarda que um código seja gerado e exibido no elemento com ID my-value.
3.  Teste do Código Gerado:
  - Insere o código gerado no campo de entrada com ID input.
  - Clica no botão "Test" para verificar o código.
4.  Verificação de Alerta:
  - Aguarda um alerta aparecer.
  - Verifica se o texto do alerta é "Done!" e fecha o alerta.
5.  Validação da Mensagem:
  - Verifica se uma mensagem de resultado contendo o código gerado é exibida corretamente na página.
  - O script finaliza fechando o navegador após a execução dos testes.