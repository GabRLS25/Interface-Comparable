<h1 align="center">
  🚀 Java Comparable: Ordenação de Funcionários
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/IntelliJ_IDEA-000000.svg?style=for-the-badge&logo=intellij-idea&logoColor=white" alt="IntelliJ IDEA"/>
  <img src="https://img.shields.io/badge/Clean_Code-222222?style=for-the-badge&logo=dev.to&logoColor=white" alt="Clean Code"/>
</p>

<p align="center">
  Um projeto prático demonstrando o poder da interface <b>Comparable</b> em Java para ordenação de coleções, aliado à manipulação de arquivos (I/O) de forma segura.
</p>

<hr>

## 📋 Sobre o Projeto

Este repositório contém um sistema simples, mas poderoso, de processamento de dados. Ele lê uma lista de funcionários e seus respectivos salários a partir de um arquivo CSV (Comma-Separated Values) e aplica uma regra de negócio específica: **ordenar todos os funcionários do maior para o menor salário**.

O projeto foi desenvolvido para consolidar os seguintes pilares do desenvolvimento em Java:
- Leitura e processamento de arquivos externos.
- Orientação a Objetos (Encapsulamento e Entidades).
- Uso de **Interfaces** para definir comportamentos (Contratos).
- Manipulação de **Collections**.

---

## ✨ Funcionalidades em Destaque

- 📂 **Leitura Segura de Arquivos:** Utilização do `try-with-resources` para garantir que o `BufferedReader` e o `FileReader` sejam fechados automaticamente, evitando vazamento de memória.
- ⚙️ **Processamento de Strings:** Separação inteligente de dados usando o método `.split(",")`.
- 🧠 **Ordenação Customizada:** Implementação nativa da interface `Comparable<T>` para inverter a ordem natural dos salários.

---

## 🏗️ Estrutura do Código

O projeto está dividido em dois pacotes principais, respeitando a separação de responsabilidades:

```text
📦 src
 ┣ 📂 application
 ┃ ┗ 📜 Program.java    # Ponto de entrada (Main), responsável pelo I/O e execução.
 ┗ 📂 entities
   ┗ 📜 Employee.java   # Entidade de domínio implementando a regra de ordenação.
```

---

## 🔍 Entendendo a Mágica (A Interface Comparable)

O grande diferencial deste projeto está na classe `Employee`. Para que a lista seja ordenada automaticamente pelo Java usando `Collections.sort(list)`, a classe precisa "ensinar" ao Java como comparar dois funcionários.

Fizemos isso implementando o método `compareTo`. Note o uso do **sinal de subtração (`-`)**; ele inverte a lógica padrão, forçando uma **ordem decrescente** (do maior para o menor salário):

```java
@Override
public int compareTo(Employee other) {
    // O sinal "-" inverte a ordem crescente padrão da classe Double
    return -salary.compareTo(other.getSalary());
}
```

---

## 🚀 Como Executar na Sua Máquina

Siga o passo a passo abaixo para rodar o projeto localmente:

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/Gabgosq25/Interface-Comparable.git
   ```

2. **Prepare o arquivo de dados:**
   - Crie uma pasta chamada `temp` no diretório raiz do seu disco `C:\`.
   - Dentro dela, crie um arquivo chamado `in.txt` (`C:\temp\in.txt`).
   - Adicione os dados no formato `Nome,Salário`. Exemplo:
     ```text
     Maria Brown,4300.00
     Alex Green,3100.00
     Bob Grey,3100.00
     Anna White,3500.00
     ```

3. **Rode a aplicação:**
   - Abra o projeto na sua IDE favorita (IntelliJ, Eclipse, VS Code).
   - Navegue até `application/Program.java`.
   - Execute o método `main`.
   - O resultado aparecerá ordenado diretamente no seu console! 🎉

---

<p align="center">
  <i>Desenvolvido com dedicação para aprofundamento em Arquitetura de Software e Boas Práticas em Java. ☕</i>
</p>