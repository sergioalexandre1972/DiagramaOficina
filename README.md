# 🛠 Sistema de Gerenciamento de Ordens de Serviço para Oficina Mecânica

## 📌 Visão Geral
Este projeto tem como objetivo modelar e desenvolver um **sistema de controle e gerenciamento de ordens de serviço** para uma **oficina mecânica**. O sistema permite o cadastro de clientes, veículos, mecânicos, ordens de serviço, serviços realizados e peças utilizadas.

---

## 🔗 Estrutura do Banco de Dados

### **1️⃣ Cliente**
Representa os clientes da oficina.
- `idCliente` (PK)
- `Nome`
- `Endereço`
- `Telefone`

### **2️⃣ Veículo**
Cada cliente pode possuir um ou mais veículos.
- `idVeiculo` (PK)
- `Placa`
- `Modelo`
- `Marca`
- `Ano`
- `idCliente (FK)`

### **3️⃣ Ordem de Serviço (OS)**
Cada veículo pode gerar uma ou mais ordens de serviço.
- `idOS` (PK)
- `DataEmissao`
- `ValorTotal`
- `Status`
- `DataConclusao`
- `idVeiculo (FK)`
- `idEquipe (FK)`

### **4️⃣ Equipe**
Cada OS é atribuída a uma equipe de mecânicos.
- `idEquipe` (PK)
- `NomeEquipe`

### **5️⃣ Mecânico**
Cada mecânico pertence a uma equipe e pode executar diferentes serviços.
- `idMecanico` (PK)
- `Nome`
- `Endereço`
- `Especialidade`
- `idEquipe (FK)`

### **6️⃣ Serviço**
Cada ordem de serviço pode conter diversos serviços.
- `idServico` (PK)
- `Descricao`
- `Valor`
- `idTabelaReferencia (FK)`

### **7️⃣ Peça**
Cada serviço pode necessitar de peças específicas.
- `idPeca` (PK)
- `Descricao`
- `Valor`

### **8️⃣ Tabela de Referência**
Define valores de mão de obra para cada serviço prestado.
- `idTabelaReferencia` (PK)
- `Descricao`
- `ValorMaoDeObra`

### **9️⃣ Relacionamentos**
- **Ordem de Serviço** pode conter **vários Serviços** (`OS_has_Servico`).
- **Ordem de Serviço** pode conter **várias Peças** (`OS_has_Peca`).

---

## 📊 Diagrama de Entidade-Relacionamento (DER)
📌 O diagrama foi modelado com base no **modelo EER (Extended Entity-Relationship)**, garantindo escalabilidade e melhor normalização do banco de dados.

![Diagrama de Entidade e Relacionamento](./diagrama-oficina.png) *(Substitua pelo caminho correto da imagem do DER se necessário.)*

---

## 🚀 Tecnologias Utilizadas
- **MySQL / PostgreSQL** (ou outro banco relacional)
- **MySQL Workbench / Draw.io** (para modelagem gráfica)

---

## 🔧 Funcionalidades Previstas
- Cadastro de clientes e veículos
- Geração e gerenciamento de ordens de serviço
- Acompanhamento de status de serviços
- Cálculo automático de valores de serviço e peças
- Relatórios sobre serviços realizados e faturamento

---

## 🛠 Como Usar
1. Clone este repositório:
   ```sh
   git clone https://github.com/seu-usuario/sistema-oficina.git
   ```
2. Importe o banco de dados no MySQL Workbench.
3. Execute as consultas SQL para criação das tabelas.
4. Inicie o desenvolvimento do backend e frontend conforme necessário.

---

## ✨ Contribuição
Caso queira contribuir com melhorias, sinta-se à vontade para sugerir alterações ou expandir o modelo conforme necessário.

---

## 📜 Licença
Este projeto é de livre uso para aprendizado e desenvolvimento de sistemas de gerenciamento de oficinas mecânicas.

---

📩 **Contato:** Caso tenha dúvidas ou sugestões, entre em contato!

