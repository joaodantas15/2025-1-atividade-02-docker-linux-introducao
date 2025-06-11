Relatório:
# Relatório da Atividade 02 - Introdução a Linux com Docker

- **Aluno:** João Pedro Dantas Magalhães
- **Disciplina:** Sistemas Operacionais (TADS 2025.1)
- **Professor:** Leonardo A. Minora
- **Data:** 10 de junho de 2025

## 1. Introdução

O objetivo desta atividade foi aplicar e consolidar conhecimentos básicos sobre o sistema operacional Linux, utilizando um ambiente prático e isolado fornecido por um contêiner Docker. Por meio de uma imagem da distribuição Fedora, foram executados comandos fundamentais de navegação, manipulação de arquivos, gerenciamento de pacotes e processos, simulando um cenário de uso real de um terminal Linux.

## 2. Relato das Atividades Práticas

A seguir, são apresentados os resultados e as evidências da execução dos passos solicitados no roteiro da atividade.

### 2.1. Início do Contêiner Fedora
O ambiente de trabalho foi inicializado com sucesso utilizando o comando `docker run -it`. O terminal passou a operar dentro do contêiner, como evidenciado pelo novo prompt de comando.

![Inicialização do Contêiner Fedora]

### 2.2. Navegação Básica
Foram praticados os comandos essenciais de navegação no sistema de arquivos, como `pwd` para verificar o diretório atual, `cd` para navegar entre diretórios (`~`, `..`, `atividades`) e `mkdir` para criar uma nova pasta.

![Navegação entre diretórios

### 2.3. Manipulação de Arquivos
Nesta etapa, foram utilizados os comandos `touch`, `mv`, `cp` e `rm` para criar, renomear, copiar um arquivo entre diretórios distintos e, por fim, remover o arquivo original, validando a persistência da cópia de segurança.

![Criação, cópia e remoção de arquivos](imagens/print-03-manipulacao.png)

### 2.4. Gerenciamento de Pacotes com DNF
O gerenciador de pacotes `dnf` do Fedora foi utilizado para atualizar o sistema e para instalar e posteriormente remover um pacote de software (o editor de texto `nano`).

**Instalação do pacote `nano`:**
![Instalação do pacote nano

**Remoção do pacote `nano`:**
![Remoção do pacote nano

### 2.5. Gerenciamento de Permissões de Arquivos
As permissões de um arquivo de script (`script.sh`) foram modificadas com o comando `chmod u+x` para conceder ao usuário proprietário a permissão de execução. O comando `ls -l` foi usado para verificar o estado antes e depois da alteração.

**Permissões antes da alteração:**
![Permissões antes do chmod

**Permissões após a alteração:**
![Permissões após o chmod

### 2.6. Gerenciamento de Processos
Para esta etapa, um processo (`sleep 60`) foi executado em segundo plano. Durante a tentativa de listagem de processos, foi identificado que a imagem mínima do Fedora não continha as ferramentas necessárias, resultando no erro `ps: command not found`. O problema foi solucionado com a instalação do pacote `procps-ng`. Após a instalação, foi possível listar o processo com `ps aux`, identificar seu PID e finalizá-lo com o comando `kill`.

![Execução, identificação e encerramento do processo]

### 2.7. Encerramento e Limpeza do Ambiente
Ao final de todas as atividades, o contêiner foi encerrado com o comando `exit`, e posteriormente removido do sistema host com `docker rm fedora-tutorial` para liberar os recursos.

![Saída e remoção do contêiner]

## 3. Conclusão

Esta atividade prática foi de grande valor para a fixação dos comandos essenciais do Linux. A utilização do Docker como ferramenta de ambiente se mostrou extremamente eficiente, permitindo iniciar um sistema limpo e isolado em segundos.

A principal dificuldade encontrada foi a ausência do comando `ps` na imagem mínima do Fedora. No entanto, essa dificuldade se transformou em uma importante oportunidade de aprendizado, exigindo a pesquisa e a instalação do pacote `procps-ng` para solucionar o problema. Isso demonstrou na prática a natureza modular do Linux e a importância do gerenciamento de pacotes para customizar um ambiente. A atividade reforçou não apenas a sintaxe dos comandos, mas também a lógica por trás da estrutura e do gerenciamento de um sistema operacional baseado em Unix.
