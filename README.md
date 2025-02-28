
### **📌 Explicação do Modelo Conceitual**  

## **🔧 Contexto do Projeto**  
Este projeto tem como objetivo desenvolver um **sistema de controle e gerenciamento de ordens de serviço** para uma oficina mecânica. O sistema deve permitir o registro de clientes, veículos, mecânicos, ordens de serviço (OS), peças e serviços realizados, garantindo uma gestão eficiente e organizada.  

A modelagem conceitual foi baseada na seguinte narrativa:  

> Os clientes levam seus veículos à oficina para consertos ou revisões periódicas.  
> Cada veículo é atribuído a uma equipe de mecânicos, que identifica os serviços necessários e registra uma Ordem de Serviço (OS) com data de entrega prevista.  
> O valor total da OS é composto pelo custo dos serviços prestados e das peças utilizadas.  
> O cliente deve autorizar a execução dos serviços antes do início do trabalho.  
> A equipe designada avalia e executa os serviços necessários.  
> Os mecânicos possuem um código identificador, nome, endereço e especialidade.  
> Cada OS possui um número único, data de emissão, valor total, status e data de conclusão dos trabalhos.  

---

## **📌 Modelo Conceitual**  

O **modelo conceitual** define as principais **entidades**, **atributos** e **relacionamentos** do sistema. Ele representa de forma abstrata como os dados são organizados.  

### **🛠️ Entidades Identificadas**  

1. **Cliente**: Representa os clientes da oficina, responsáveis pelos veículos.  
   - Atributos: `ID`, `Nome`, `Telefone`, `Email`, `Endereço`  

2. **Veículo**: São os automóveis levados pelos clientes para manutenção.  
   - Atributos: `ID`, `ID_Cliente`, `Modelo`, `Placa`, `Ano`  
   - Relacionamento: Cada veículo pertence a **um único cliente**, mas um cliente pode possuir **vários veículos**.  

3. **Mecânico**: Funcionários responsáveis por executar os serviços.  
   - Atributos: `ID`, `Nome`, `Endereço`, `Especialidade`  

4. **Equipe**: Um grupo de mecânicos designado para uma Ordem de Serviço.  
   - Atributos: `ID_Equipe`  
   - Relacionamento: Cada **equipe** pode ter **vários mecânicos**, e um **mecânico pode fazer parte de várias equipes** ao longo do tempo.  

5. **Ordem de Serviço (OS)**: Representa o serviço prestado para um veículo.  
   - Atributos: `ID`, `ID_Veiculo`, `ID_Equipe`, `Data de Emissão`, `Data de Conclusão`, `Valor Total`, `Status`  
   - Relacionamento: Cada OS pertence a **um veículo** e é executada por **uma equipe de mecânicos**.  

6. **Serviço**: Representa os serviços prestados na oficina (exemplo: troca de óleo, alinhamento, balanceamento).  
   - Atributos: `ID`, `Descrição`, `Valor`  
   - Relacionamento: Cada OS pode ter **vários serviços**, e cada serviço pode estar em **várias OS**.  

7. **Peça**: Representa as peças utilizadas na manutenção dos veículos.  
   - Atributos: `ID`, `Descrição`, `Preço`  
   - Relacionamento: Cada OS pode conter **várias peças**, e cada peça pode estar associada a **várias OS**.  

---

## **📌 Relacionamentos no Modelo Conceitual**  

- **Cliente possui Veículo** (*1:N*) → Um cliente pode ter vários veículos, mas cada veículo pertence a apenas um cliente.  
- **Veículo recebe Ordem de Serviço (OS)** (*1:1*) → Um veículo pode ter uma OS em um determinado período e cada OS é associada a apenas um veículo.  
- **Ordem de Serviço (OS) é realizada por uma Equipe** (*N:1*) → Uma OS é sempre executada por uma equipe, mas uma equipe pode trabalhar em várias OS.  
- **Equipe é composta por Mecânicos** (*N:M*) → Uma equipe pode ter vários mecânicos, e um mecânico pode participar de várias equipes.  
- **Ordem de Serviço (OS) inclui Serviços** (*N:M*) → Uma OS pode conter vários serviços, e um serviço pode estar presente em várias OS.  
- **Ordem de Serviço (OS) inclui Peças** (*N:M*) → Uma OS pode conter várias peças, e uma peça pode estar em várias OS.  

---


## **📌 Conclusão**  
O modelo conceitual aqui apresentado estabelece uma estrutura organizada para a gestão de ordens de serviço em uma oficina mecânica. Ele permite:  

✅ **Gerenciar clientes e veículos** vinculados a ordens de serviço  
✅ **Controlar mecânicos e equipes**, garantindo organização na execução dos serviços  
✅ **Registrar serviços e peças utilizadas**, possibilitando um cálculo exato do valor da OS  
✅ **Monitorar o status das OS**, permitindo melhor gestão dos trabalhos na oficina  

A próxima etapa do projeto consiste na implementação do **modelo lógico**, convertendo essa estrutura conceitual em um banco de dados relacional no MySQL. 🚀  

---

### **📢 Quer Contribuir?**  
Se você quiser contribuir com melhorias para o projeto, sinta-se à vontade para abrir um Pull Request! 💡  

📌 **Desenvolvido com ❤️ por [BeckyLabhar]**  
