Meu primeiro laboratorio DevOps

# Curso de DevOps — Aulas 1 a 3

**Nível:** Iniciante
**Ambiente:** Ubuntu Linux
**Objetivo:** Aprender os fundamentos de Linux necessários para começar a estudar DevOps, utilizando um laboratório local, sem depender de AWS ou Azure.

---

# Aula 1 — Fundamentos e Linux

## 1. O que é DevOps?

DevOps é uma abordagem de trabalho que aproxima as equipes de desenvolvimento de software (*Development*) das equipes de operações e infraestrutura (*Operations*).

O objetivo é melhorar a colaboração, automatizar tarefas e tornar a entrega de software mais rápida, confiável e segura.

### Exemplo prático

Imagine uma empresa que desenvolve um sistema para controlar a produção de medidores elétricos.

Sem automação, uma pessoa pode precisar executar manualmente várias tarefas para publicar uma nova versão do sistema.

Com práticas DevOps, podemos automatizar etapas como:

1. Armazenar o código em um repositório.
2. Executar testes automaticamente.
3. Preparar a aplicação para execução.
4. Publicar uma nova versão.
5. Monitorar o funcionamento da aplicação.

## 2. O que aprender para trabalhar com DevOps?

Nossa trilha de aprendizado será:

1. Linux e terminal.
2. Arquivos, diretórios e permissões.
3. Processos, serviços e logs.
4. Redes e SSH.
5. Git e controle de versão.
6. Bash e automação.
7. Docker e containers.
8. CI/CD e pipelines.
9. Monitoramento.
10. Projeto prático integrando os conhecimentos.

## 3. Conhecendo o terminal Linux

O terminal permite interagir com o sistema operacional por meio de comandos.

No Ubuntu, pressione:

`Ctrl + Alt + T`

O terminal será aberto.

### Comando 1 — `pwd`

O comando `pwd` significa *Print Working Directory*.

Ele mostra o diretório atual.

```bash
pwd
```

Exemplo de resultado:

```text
/home/aurelio
```

O resultado depende do nome do usuário e do diretório atual.

### Comando 2 — `ls`

O comando `ls` lista os arquivos e diretórios do local atual.

```bash
ls
```

Para exibir também arquivos ocultos e informações detalhadas:

```bash
ls -la
```

Significado das opções:

* `-l`: exibe detalhes, como permissões, proprietário, tamanho e data.
* `-a`: inclui arquivos e diretórios ocultos.

### Comando 3 — `whoami`

Mostra o nome do usuário atualmente conectado.

```bash
whoami
```

### Comando 4 — `cat /etc/os-release`

Exibe informações sobre o sistema operacional instalado.

```bash
cat /etc/os-release
```

Esse comando apenas lê um arquivo de informações do sistema.

## 4. Conceitos importantes

| Conceito  | Significado                                                                |
| --------- | -------------------------------------------------------------------------- |
| Terminal  | Interface para executar comandos.                                          |
| Diretório | Local utilizado para organizar arquivos e outros diretórios.               |
| Comando   | Instrução enviada ao sistema operacional.                                  |
| Usuário   | Conta que executa comandos e possui determinadas permissões.               |
| Linux     | Sistema operacional amplamente utilizado em servidores e ambientes DevOps. |

## 5. Exercício da Aula 1

Execute os seguintes comandos no terminal:

```bash
pwd
ls
ls -la
whoami
cat /etc/os-release
```

### Objetivos

* Descobrir seu diretório atual.
* Listar arquivos.
* Identificar arquivos ocultos.
* Descobrir o usuário conectado.
* Identificar a distribuição e a versão do Linux.

---

# Aula 2 — Navegação, arquivos e diretórios

## 1. Conhecendo a estrutura de diretórios

No Linux, o diretório principal é `/`, chamado de raiz.

A partir dele, existem diversos diretórios com finalidades específicas.

| Diretório | Finalidade                                                     |
| --------- | -------------------------------------------------------------- |
| `/`       | Raiz do sistema de arquivos.                                   |
| `/home`   | Diretórios pessoais dos usuários.                              |
| `/etc`    | Arquivos de configuração do sistema e de serviços.             |
| `/var`    | Dados variáveis, incluindo muitos arquivos de log.             |
| `/tmp`    | Arquivos temporários.                                          |
| `/usr`    | Grande parte dos programas, bibliotecas e recursos instalados. |

Esses diretórios aparecem frequentemente no trabalho com servidores Linux.

## 2. Comandos fundamentais

### 2.1. `cd` — Navegar entre diretórios

O comando `cd` significa *Change Directory*.

Para acessar o diretório `/tmp`:

```bash
cd /tmp
```

Para voltar ao diretório pessoal:

```bash
cd ~
```

O símbolo `~` representa o diretório pessoal do usuário atual.

### 2.2. `pwd` — Descobrir o diretório atual

```bash
pwd
```

Se você estiver em `/tmp`, o resultado será:

```text
/tmp
```

### 2.3. `mkdir` — Criar diretórios

Para criar um diretório chamado `devops-lab` na sua pasta pessoal:

```bash
mkdir -p ~/devops-lab
```

A opção `-p` permite criar diretórios intermediários quando necessário e não gera erro apenas porque o diretório já existe.

### 2.4. `ls` — Conferir o conteúdo

```bash
cd ~/devops-lab
ls -la
```

O comando mostra os arquivos e diretórios presentes no laboratório.

## 3. Criando a estrutura do laboratório DevOps

Vamos organizar os arquivos que utilizaremos durante o curso.

### Passo 1 — Criar os diretórios

```bash
mkdir -p ~/devops-lab/{scripts,logs,config}
```

Esse comando cria três diretórios:

* `scripts`: armazenará scripts de automação.
* `logs`: será utilizado para armazenar logs de exercícios.
* `config`: armazenará arquivos de configuração.

### Passo 2 — Entrar no laboratório

```bash
cd ~/devops-lab
```

### Passo 3 — Conferir a estrutura

```bash
ls -la
```

Você deverá encontrar os diretórios:

```text
config
logs
scripts
```

## 4. Criando seu primeiro arquivo

### Passo 1 — Criar o arquivo

Execute:

```bash
echo "Meu primeiro laboratorio DevOps" > README.txt
```

O comando cria o arquivo `README.txt` e grava o texto nele.

Entenda cada parte:

* `echo`: exibe um texto.
* `>`: redireciona a saída para um arquivo, substituindo seu conteúdo anterior caso ele já exista.
* `README.txt`: nome do arquivo de destino.

### Passo 2 — Ler o arquivo

```bash
cat README.txt
```

Resultado esperado:

```text
Meu primeiro laboratorio DevOps
```

### Diferença entre `>` e `>>`

O operador `>` substitui o conteúdo existente.

```bash
echo "Primeira linha" > README.txt
```

O operador `>>` acrescenta conteúdo ao final.

```bash
echo "Segunda linha" >> README.txt
```

Para conferir o resultado:

```bash
cat README.txt
```

Resultado:

```text
Primeira linha
Segunda linha
```

**Atenção:** o primeiro comando do exemplo substitui o conteúdo anterior do arquivo.

## 5. Exercício da Aula 2

**Pergunta:** qual comando cria um diretório chamado `backup` dentro de `~/devops-lab`?

A) `cd backup`

B) `mkdir ~/devops-lab/backup`

C) `cat backup`

D) `pwd backup`

**Resposta correta:** alternativa B.

O comando `mkdir` é utilizado para criar diretórios.

### Prática adicional

Execute:

```bash
mkdir ~/devops-lab/backup
```

Depois, confira:

```bash
ls -la ~/devops-lab
```

Verifique se o diretório `backup` foi criado.

---

# Aula 3 — Permissões, usuários e sudo

## 1. Entendendo as permissões no Linux

No Linux, os arquivos e diretórios possuem permissões que controlam quem pode ler, modificar ou executar cada item.

Execute:

```bash
cd ~/devops-lab
ls -l
```

Você poderá encontrar uma saída semelhante a:

```text
-rw-rw-r-- 1 aurelio aurelio 32 Oct 15 README.txt
```

O resultado exato depende das permissões, do usuário, do tamanho e da data do arquivo.

A parte mais importante para esta aula é:

```text
-rw-rw-r--
```

## 2. Interpretando as permissões

As permissões são organizadas em grupos:

```text
-rw-rw-r--
│││ │││ │││
│││ │││ └┴┴ Outros
│││ └┴┴─── Grupo
└┴┴─────── Proprietário
```

O primeiro caractere indica o tipo de item:

* `-`: arquivo comum.
* `d`: diretório.

As letras de permissão são:

| Letra | Significado | Efeito                                |
| ----- | ----------- | ------------------------------------- |
| `r`   | Read        | Ler o arquivo.                        |
| `w`   | Write       | Modificar o arquivo.                  |
| `x`   | Execute     | Executar o arquivo, quando aplicável. |

Em diretórios, as permissões têm particularidades:

* `r`: permite listar os nomes dos itens do diretório, conforme as demais permissões.
* `w`: permite alterar as entradas do diretório, normalmente em conjunto com `x`.
* `x`: permite acessar ou atravessar o diretório, conforme as permissões aplicáveis.

### Exemplo

Considere:

```text
-rw-rw-r--
```

A interpretação é:

* Proprietário (`rw-`): pode ler e escrever.
* Grupo (`rw-`): pode ler e escrever.
* Outros (`r--`): podem ler, mas não escrever.

## 3. Criando um script Bash

Um script é um arquivo que contém comandos que podem ser executados em sequência.

Vamos criar nosso primeiro script.

### Passo 1 — Abrir o editor

```bash
cd ~/devops-lab
nano scripts/ola.sh
```

O editor de texto `nano` será aberto.

### Passo 2 — Escrever o código

Digite:

```bash
#!/bin/bash

echo "Ola! Meu laboratorio DevOps esta funcionando."
```

Explicação:

* `#!/bin/bash`: indica que o script deve ser interpretado pelo Bash.
* `echo`: exibe uma mensagem no terminal.
* `ola.sh`: é o nome do arquivo de script.

### Passo 3 — Salvar o arquivo

No Nano:

1. Pressione `Ctrl + O` para salvar.
2. Pressione `Enter` para confirmar o nome.
3. Pressione `Ctrl + X` para sair.

## 4. Executando o script

Tente executar:

```bash
./scripts/ola.sh
```

Se aparecer uma mensagem como:

```text
Permission denied
```

isso pode significar que o arquivo não possui permissão de execução.

## 5. Utilizando `chmod`

O comando `chmod` permite alterar as permissões de arquivos e diretórios.

Execute:

```bash
chmod +x scripts/ola.sh
```

A opção `+x` adiciona a permissão de execução, respeitando as regras de permissão aplicáveis.

Agora execute novamente:

```bash
./scripts/ola.sh
```

Resultado esperado:

```text
Ola! Meu laboratorio DevOps esta funcionando.
```

**O que você aprendeu?**

Criar um arquivo não significa que ele possui permissão para ser executado. O comando `chmod +x` permite adicionar essa permissão.

## 6. Conferindo as permissões

Execute:

```bash
ls -l scripts/ola.sh
```

Você deverá encontrar a letra `x` nas permissões do arquivo.

Por exemplo:

```text
-rwxr-xr-x 1 aurelio aurelio 65 Oct 15 scripts/ola.sh
```

Esse é apenas um exemplo. As permissões exatas podem variar conforme o usuário e a configuração do sistema.

## 7. Entendendo o comando `sudo`

O comando `sudo` permite executar comandos com privilégios administrativos, desde que o usuário esteja autorizado.

Por exemplo:

```bash
sudo systemctl status ssh
```

Esse comando consulta o estado de um serviço chamado `ssh`.

Dependendo da instalação e da configuração do Ubuntu, o serviço pode não existir ou ter outro nome. Isso não significa necessariamente que há um problema no sistema.

### Quando utilizar `sudo`?

Ele é normalmente utilizado em tarefas como:

* Instalar ou remover programas.
* Administrar serviços do sistema.
* Alterar arquivos protegidos.
* Executar operações administrativas autorizadas.

**Importante:** não utilize `sudo` indiscriminadamente. Comandos executados com privilégios administrativos podem alterar ou danificar o sistema.

Para trabalhar nos arquivos do seu laboratório pessoal, normalmente não precisamos de `sudo`.

## 8. Exercício da Aula 3

**Pergunta:** para que serve o comando abaixo?

```bash
chmod +x scripts/ola.sh
```

A) Apaga o arquivo `ola.sh`.

B) Adiciona permissão de execução ao arquivo.

C) Cria um novo usuário Linux.

D) Executa o arquivo como administrador.

**Resposta correta:** alternativa B.

O comando modifica as permissões do arquivo, adicionando a permissão de execução.

## 9. Prática final da Aula 3

Execute os comandos:

```bash
cd ~/devops-lab
```

```bash
ls -l scripts/ola.sh
```

```bash
./scripts/ola.sh
```

Confira se:

* O arquivo existe.
* A permissão de execução está presente.
* O script é executado sem erros.
* A mensagem esperada aparece no terminal.

---

# Resumo das Aulas 1 a 3

| Comando  | Finalidade                                                           |
| -------- | -------------------------------------------------------------------- |
| `pwd`    | Mostrar o diretório atual.                                           |
| `ls`     | Listar arquivos e diretórios.                                        |
| `ls -la` | Listar também itens ocultos, com detalhes.                           |
| `whoami` | Mostrar o usuário atual.                                             |
| `cat`    | Exibir o conteúdo de um arquivo.                                     |
| `cd`     | Navegar entre diretórios.                                            |
| `mkdir`  | Criar diretórios.                                                    |
| `echo`   | Exibir ou gerar texto.                                               |
| `>`      | Redirecionar a saída, substituindo o conteúdo do arquivo de destino. |
| `>>`     | Acrescentar a saída ao final de um arquivo.                          |
| `nano`   | Editar arquivos de texto no terminal.                                |
| `chmod`  | Alterar permissões.                                                  |
| `sudo`   | Executar comandos com privilégios administrativos autorizados.       |

# Próxima etapa — Aula 4

Na próxima aula, estudaremos **processos, serviços e logs no Linux**.

Você aprenderá a:

1. Identificar processos em execução.
2. Consultar o consumo de recursos.
3. Entender o que são serviços.
4. Verificar se um serviço está funcionando.
5. Consultar logs para investigar falhas.
6. Começar a diagnosticar problemas como um profissional DevOps.

Esses conhecimentos são fundamentais para administrar aplicações e servidores Linux.

---

**Fim do material — Aulas 1 a 3**

