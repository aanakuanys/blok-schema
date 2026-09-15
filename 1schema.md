```markdown
```mermaid
graph TD
    Start([Бастау]) --> Init[a = [5, 2, 9, 9, 7, 3, 8, 7, 1] <br/> birinshi = None <br/> ekinshi = None <br/> ushinshi = None]
    
    Init --> Loop{for x in a}
    
    Loop -- "Элемент бар" --> CheckDup{x == birinshi or x == ekinshi or x == ushinshi?}
    CheckDup -- "Иә" --> Continue[continue] --> Loop
    CheckDup -- "Жоқ" --> Check1{birinshi is None or x > birinshi?}
    
    Check1 -- "Иә" --> Up1[ushinshi = ekinshi <br/> ekinshi = birinshi <br/> birinshi = x] --> Loop
    Check1 -- "Жоқ" --> Check2{ekinshi is None or x > ekinshi?}
    
    Check2 -- "Иә" --> Up2[ushinshi = ekinshi <br/> ekinshi = x] --> Loop
    Check2 -- "Жоқ" --> Check3{ushinshi is None or x > ushinshi?}
    
    Check3 -- "Иә" --> Up3[ushinshi = x] --> Loop
    Check3 -- "Жоқ" --> Loop
    
    Loop -- "Тізім бітті" --> CheckFinal{ushinshi is not None?}
    CheckFinal -- "Иә" --> PrintYes[/print: Үшінші ең үлкен элемент, ushinshi/]
    CheckFinal -- "Жоқ" --> PrintNo[/print: Үш түрлі элемент жоқ/]
    
    PrintYes --> End([Соңы])
    PrintNo --> End([Соңы])
```
