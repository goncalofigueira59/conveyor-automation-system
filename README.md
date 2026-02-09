# Projeto de Automação de Máquina Transportadora de Peças

<p align="center">
  <img src="https://img.shields.io/badge/Categoria-Projeto%20Académico-blue" alt="Categoria: Projeto Académico">
  <img src="https://img.shields.io/badge/Área-Automação%20Industrial-orange" alt="Área: Automação Industrial">
  <img src="https://img.shields.io/badge/Software-AutoCAD%20Electrical-C81F2E?logo=autodesk" alt="Software: AutoCAD Electrical">
</p>

> [Projeto Académico] Elaboração do projeto elétrico e de automação de uma máquina transportadora de peças, incluindo análise de componentes (PLC, motores, sensores, atuadores pneumáticos ), modos de operação (manual/automático) e segurança industrial. Desenvolvido no âmbito do CTeSP em Instalações Elétricas e Automação Industrial.

---

## Índice

- Contextualização e Resumo
- Memória Descritiva e Funcionamento da Máquina
  - Funcionamento em Modo Manual e Automático
  - Painel de Comando
- Componentes da Máquina e Funcionalidades
  - PLC (Controlador Lógico Programável)
  - Fonte de Alimentação
  - Entradas e Saídas (Digitais)
  - Botões na Indústria de Automação
  - Disjuntores Magneto-Térmicos
  - Seccionador Geral (QS)
  - Eletroválvulas (YV)
  - Relés e Contactores
  - Fusíveis
  - Detetores de Presença (Foto-células) e Magnéticos
  - Motores Trifásicos
  - Bimanual
- Projeto Elétrico e Ferramentas
  - Programas Utilizados e Nota Técnica
  - Classificação das Instalações Industriais
  - Distribuição de Energia e Numeração de Linhas
  - Dimensionamento dos Condutores
- Considerações Finais e Aprendizagens
- Documentação do Projeto
- Licença

---

### 1. Contextualização e Resumo

Este projeto foi desenvolvido no âmbito da disciplina de **Desenho Assistido Por Computador para Instalações Elétricas**, pertencente ao curso **CTeSP em Instalações Elétricas e Automação Industrial** da ESTGA – Universidade de Aveiro. O trabalho consistiu na elaboração do projeto elétrico, na modalidade de automação, de uma máquina transportadora de peças.

O objetivo didático foi aplicar os conhecimentos lecionados em ambiente de aula, focando-se na conceção de um sistema de transporte de peças que integra três motores elétricos e dois cilindros pneumáticos de duplo efeito. Foram definidas as funcionalidades da máquina, incluindo modos de operação manual e automático, e a seleção detalhada de todos os componentes elétricos e de automação necessários.

### 2. Memória Descritiva e Funcionamento da Máquina

A máquina industrial projetada é um sistema de transporte de peças, caracterizado pela utilização de três motores elétricos e dois cilindros pneumáticos de duplo efeito para efetuar o movimento de mudança de transportador. A deteção de peças é realizada por detetores localizados na zona de carga, zona 2, zona 3 e zona de descarga. Adicionalmente, cada cilindro possui dois detetores magnéticos para identificar o seu avanço e recuo.

#### 2.1. Funcionamento em Modo Manual e Automático

A máquina foi concebida para operar em dois modos distintos, selecionáveis através de um seletor:

-   **Modo Manual:** Permite a atuação individual dos motores e cilindros através dos respetivos botões. É também possível criar um ciclo manual com tempos definidos pelo operador.
-   **Modo Automático:** Realiza ciclos contínuos de transporte de peças. O ciclo só se inicia após a verificação de todas as condições de segurança (paragem de emergência inativa, ausência de defeitos nos motores ou cilindros, e cilindros na posição inicial). A ativação da paragem de emergência durante o ciclo automático provoca a interrupção imediata do mesmo.

O início do ciclo (START) é acionado por um **bimanual**, garantindo que o operador utilize ambas as mãos e prevenindo acidentes de trabalho.

#### 2.2. Painel de Comando

O painel de comando é um elemento central para a interação com a máquina, composto por:

-   **Botões de Pressão com Iluminação:** Para colocação em serviço e seleção de movimentos (avançar/recuar cilindros).
-   **Botão para Retirar de Serviço:** Desativação da máquina.
-   **Botão de Paragem de Emergência (BPE):** Com encravamento mecânico, para paragem imediata e segura.
-   **Seletores:**
    -   Duas posições para seleção do modo de operação (Manual/Automático).
    -   Três posições para seleção do Cilindro 1, Cilindro 2 ou ponto 0.
    -   Quatro posições para seleção do Motor 1, Motor 2, Motor 3 ou ponto 0 (para funcionamento manual).
-   **Sinalizadores:**
    -   Três sinalizadores vermelhos para indicação de defeito em cada motor.
    -   Dois sinalizadores para defeitos nos cilindros.
    -   Dois sinalizadores verdes para sinalizar o recuo de cada cilindro.
-   **Botão de Anulação/Reteste:** Para anular defeitos ou verificar a sua persistência.

### 3. Componentes da Máquina e Funcionalidades

#### 3.1. PLC (Controlador Lógico Programável)

O PLC é o componente eletrónico especializado responsável pelo controlo e monitorização da máquina. Através de programas específicos, gere toda a lógica de funcionamento, incluindo os modos manual e automático, e a interação com as entradas e saídas.

#### 3.2. Fonte de Alimentação

Para alimentar o autómato com 24V DC, foi utilizado um transformador. A proteção da fonte é assegurada por fusíveis (F1 e F2) nas saídas (24V e 0V) para prevenir danos em caso de curto-circuito, e na entrada para proteção contra picos ou defeitos na linha. A fonte de alimentação foi designada com a nomenclatura **GB**.

#### 3.3. Entradas e Saídas (Digitais)

Todas as entradas e saídas do autómato foram consideradas como **digitais** neste projeto. Os sinais digitais caracterizam bits (0 ou 1), indicando a presença ou ausência de sinal.

-   **Entradas:** Botões de pressão (simples e iluminados), seletores, contactos de disjuntores magneto-térmicos, foto-células e sensores eletromagnéticos.
-   **Saídas:** Eletroválvulas, sinalizadores (lâmpadas) de defeito e recuo de cilindros, e bobinas de contactores para acionamento de motores.

#### 3.4. Botões na Indústria de Automação

Na automação industrial, os botões de pressão funcionam sem encravamento, transmitindo sinal apenas enquanto premidos. Para funcionalidades que exigem um sinal contínuo (semelhante a um interruptor), é necessário criar um **circuito de memória**. Exceções são botões com encravamento mecânico, como a **Botoneira de Paragem de Emergência (BPE)**, que mantém o sinal após ser premida até ser desativada manualmente. Os botões foram representados como **SBs**.

#### 3.5. Disjuntores Magneto-Térmicos

Estes disjuntores combinam proteção térmica (contra sobreaquecimento por sobrecarga) e magnética (contra curtos-circuitos). São essenciais para proteger o equipamento e a rede elétrica. Foram utilizados em diversos pontos do projeto para proteção de componentes como tomadas e iluminação do quadro elétrico, e nos circuitos de potência. A nomenclatura para disjuntores magneto-térmicos gerais foi **QF**, e para disjuntores magneto-térmicos de motor foi **Q**.

#### 3.6. Seccionador Geral (QS)

Posicionado na alimentação geral da máquina, o seccionador geral (**QS**) permite cortar toda a energia elétrica para intervenções de segurança. Funciona com encravamento, exigindo rearme manual após desativação, protegendo todas as linhas, incluindo o neutro.

#### 3.7. Eletroválvulas (YV)

As eletroválvulas (**YV**) controlam o avanço e recuo dos cilindros pneumáticos. São ativadas como saídas do autómato, garantindo que os cilindros atuem no momento certo para cumprir o ciclo de transporte, evitando que peças fiquem presas. O esquema pneumático foi fornecido pelo professor.

#### 3.8. Relés e Contactores

-   **Relés:** Componentes com contactos internos que abrem ou fecham através da magnetização de uma bobina, permitindo a passagem de energia.
-   **Contactores:** Funcionam de forma semelhante aos relés, mas são geralmente mais robustos e utilizados para acionar cargas de maior potência, como os motores. Foram utilizados no circuito de alimentação dos motores.

#### 3.9. Fusíveis

Utilizados para proteção contra sobrecargas e curtos-circuitos, garantindo a segurança dos circuitos e componentes. Foram aplicados na proteção da fonte de alimentação e em outros pontos críticos.

#### 3.10. Detetores de Presença (Foto-células) e Magnéticos

-   **Foto-células:** Detetam a presença de peças nas zonas de carga, transporte e descarga.
-   **Sensores Magnéticos:** Utilizados nos cilindros pneumáticos para identificar as posições de avanço e recuo.

#### 3.11. Motores Trifásicos

Três motores trifásicos são responsáveis pelo movimento da máquina transportadora. A sua proteção é assegurada por disjuntores magneto-térmicos de motor.

#### 3.12. Bimanual

Um comando bimanual é utilizado para o início do ciclo (START), exigindo que o operador use ambas as mãos simultaneamente. Esta medida de segurança previne que as mãos do operador estejam em zonas de risco durante o arranque da máquina.

### 4. Projeto Elétrico e Ferramentas

#### 4.1. Programas Utilizados e Nota Técnica

O projeto elétrico, o esquema de funcionamento e o circuito pneumático foram originalmente desenvolvidos utilizando o **AutoCAD Electrical 2021**.

> **Nota Importante:** Atualmente, os ficheiros editáveis (.dwg) do AutoCAD não se encontram disponíveis neste repositório. Toda a informação técnica, lógica de funcionamento e detalhes dos esquemas estão preservados e detalhados no relatório/memória descritiva presente na pasta `project-files/`.

#### 4.2. Classificação das Instalações Industriais

A alimentação industrial é tipicamente um sistema trifásico de 380V, acompanhado por um neutro dimensionado para a potência contratada e um ou mais aterramentos essenciais para a proteção de pessoas e equipamentos. O cálculo da potência aparente, com base na potência ativa e reativa, é uma consideração padrão.

#### 4.3. Distribuição de Energia e Numeração de Linhas

O projeto seguiu as práticas de distribuição de energia, incluindo a numeração de linhas e a identificação por colunas nos esquemas elétricos, para garantir clareza e facilidade de manutenção.

#### 4.4. Dimensionamento dos Condutores

O dimensionamento dos condutores foi realizado para assegurar que a instalação cumpre as normas de segurança e operacionais, suportando as correntes nominais e de curto-circuito sem sobreaquecimento ou quedas de tensão excessivas.

### 5. Considerações Finais e Aprendizagens

Este projeto representou uma aplicação prática e abrangente dos conhecimentos adquiridos no CTeSP em Instalações Elétricas e Automação Industrial. Permitiu consolidar a compreensão sobre a seleção e dimensionamento de componentes elétricos e de automação, a conceção de painéis de comando, a implementação de lógicas de segurança e a elaboração de documentação técnica detalhada. A experiência com o AutoCAD Electrical foi fundamental para a criação dos esquemas, reforçando a importância das ferramentas CAD na engenharia moderna.

### 6. Documentação do Projeto

O relatório completo/memória descritiva e justificativa do projeto está disponível em formato PDF na pasta `project-files/`. Este documento constitui a prova de conceito e o registo detalhado de todo o trabalho de engenharia realizado, suprindo a ausência dos ficheiros originais de CAD.

### 7. Licença

Este projeto está licenciado sob a **MIT License**. Veja o ficheiro `LICENSE` para mais detalhes.
