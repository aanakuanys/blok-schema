```mermaid
flowchart TD
    A([Басы]) --> B[/text = input()/]
    B --> C[words = text.split()]
    C --> D[best_word = ""<br/>best_count = 0]
    D --> E[for word in words]
    E --> F[different = ""]
    F --> G[for symbol in word]
    G --> H{symbol not in different?}
    H -->|Иә| I[different += symbol]
    H -->|Жоқ| G
    I --> G
    G --> J[count = len(different)]
    J --> K{count > best_count?}
    K -->|Иә| L[best_count = count<br/>best_word = word]
    K -->|Жоқ| M{count == best_count<br/>and len(word) > len(best_word)?}
    L --> E
    M -->|Иә| N[best_word = word]
    M -->|Жоқ| E
    N --> E
    E --> O[/print(best_word)<br/>print(best_count)/]
    O --> P([Соңы])
```


```mermaid
graph TD
    Start([Бастау]) --> Input["text = input()"]
    
    Input --> Split["words = text.split()"]
    Split --> Init["best_word = '' <br/> best_count = 0"]
    
    Init --> LoopWord["for word in words"]
    
    LoopWord -- "Сөз бар" --> InitDiff["different = ''"]
    InitDiff --> LoopSym["for symbol in word"]
    
    LoopSym -- "Символ бар" --> CheckSym{"symbol not in different?"}
    
    CheckSym -- "Иә" --> AddSym["different += symbol"] --> LoopSym
    CheckSym -- "Жоқ" --> LoopSym
    
    LoopSym -- "Символ бітті" --> Calc["count = len(different)"]
    
    Calc --> CheckCount{"count > best_count?"}
    
    CheckCount -- "Иә" --> Upd1["best_count = count <br/> best_word = word"] --> LoopWord
    CheckCount -- "Жоқ" --> CheckLen{"count == best_count and len(word) > len(best_word)?"}
    
    CheckLen -- "Иә" --> Upd2["best_word = word"] --> LoopWord
    CheckLen -- "Жоқ" --> LoopWord
    
    LoopWord -- "Цикл бітті" --> Print1[/print: best_word/]
    
    Print1 --> Print2[/print: best_count/]
    
    Print2 --> End([Соңы])
```



```mermaid
   graph TD
    Start([Бастау]) --> Input["N = int(...) <br/> M = int(...) <br/> A = []"]
    
    Input --> LoopN["for i in range(N)"]
    LoopN -- "Жол бар" --> LoopM["for j in range(M)"]
    LoopM -- "Элемент бар" --> ReadX["x = int(...) <br/> row.append(x)"] --> LoopM
    
    LoopM -- "Жол бітті" --> AppA["A.append(row)"] --> LoopN
    
    LoopN -- "Матрица бітті" --> Trans["AT = [] <br/> for j in range(M) <br/> for i in range(N) <br/> AT[j][i] = A[i][j]"]
    
    Trans --> PrintA[/print: A/]
    PrintA --> PrintAT[/print: AT/]
    
    PrintAT --> CheckM{"M < N?"}
    CheckM -- "Иә" --> SetM["diagonal_count = M"] --> DiagLoop
    CheckM -- "Жоқ" --> SetN["diagonal_count = N"] --> DiagLoop
    
    DiagLoop["for i in range(diagonal_count)"] -- "Элемент бар" --> CheckEq{"A[i][i] == AT[i][i]?"}
    
    CheckEq -- "Иә" --> PrintEq[/print: тең/] --> DiagLoop
    CheckEq -- "Жоқ" --> PrintNotEq[/print: тең емес/] --> DiagLoop
    
    DiagLoop -- "Цикл бітті" --> End([Соңы])
```
