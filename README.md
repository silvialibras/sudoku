# 📝 Construção do Jogo Sudoku em Java 

## 🎯 Objetivo do Projeto  
Desenvolver um jogo Sudoku em Java, aplicando conceitos de:  
✔ **POO (Programação Orientada a Objetos)**  
✔ **Swing (Interface Gráfica)**  
✔ **Lógica de Matrizes**  
✔ **Validação de Regras do Sudoku**  

---

## 🔧 Passo a Passo da Construção  

### **1️⃣ Estrutura Básica do Projeto**  
- **Organização de Pacotes:**  
  ```
  br.com.dio.model      # Classes de modelo (Space, Board)  
  br.com.dio.service   # Lógica do jogo (BoardService)  
  br.com.dio.ui        # Interface gráfica (MainScreen, botões, painéis)  
  ```

### **2️⃣ Classe `Space` (Célula do Sudoku)**  
- **Atributos:**  
  ```java
  public class Space {
      private int expected;  // Valor correto (fixo)  
      private Integer actual; // Valor digitado pelo jogador  
      private boolean fixed;  // Se é um número pré-definido  
  }
  ```
- **Métodos:**  
  - `setActual()`, `getExpected()`, `isFixed()`  

### **3️⃣ Classe `BoardService` (Lógica do Jogo)**  
- **Responsabilidades:**  
  - Gerar tabuleiro válido  
  - Validar regras do Sudoku  
  - Verificar vitória  
  ```java
  public class BoardService {
      private List<List<Space>> spaces;
      
      public boolean hasErrors() { /* ... */ }  
      public void reset() { /* ... */ }  
  }
  ```

### **4️⃣ Interface Gráfica (Swing)**  
- **`MainScreen` - Tela Principal:**  
  ```java
  public class MainScreen {
      private BoardService boardService;
      private JFrame mainFrame;
      
      public void buildMainScreen() {
          // Cria tabuleiro 9x9 com setores 3x3
      }
  }
  ```

- **Componentes UI:**  
  - `SudokuSector`: Painel 3x3 com células (`NumberText`)  
  - `FinishGameButton`: Botão para verificar solução  
  - `ResetButton`: Reinicia o jogo  

### **5️⃣ Lógica de Validação**  
- **Método `getSpaceFromSector` (Exemplo corrigido):**  
  ```java
  private List<Space> getSpaceFromSector(List<List<Space>> spaces, int initCol, int endCol, int initRow, int endRow) {
      List<Space> sector = new ArrayList<>();
      for (int r = initRow; r <= endRow; r++) {
          for (int c = initCol; c <= endCol; c++) {
              sector.add(spaces.get(r).get(c));  // Correto: linha primeiro!
          }
      }
      return sector;
  }
  ```

---

## 🛠️ Como Executar  
1. Clone o repositório;  
2. Compile e execute `MainScreen.java`;  
3. Preencha o tabuleiro e clique em **"Verificar"** para testar sua solução.  

---

## 📚 Aprendizados  
✅ **Matrizes e Lógica de Grid:** Manipulação de índices para divisão em setores 3x3.  
✅ **Swing:** Criação de interfaces interativas com botões e painéis.  
✅ **Clean Code:** Separação clara entre modelo, serviço e UI.  

---
IDE Utilizada: Intellij IDEA

---

## 🔗 Link Útil  
- [Regras do Sudoku](https://www.sudokuonline.io/pt/regras-sudoku)  

--- 
