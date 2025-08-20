# Metrics & Static Review – calculator-java

## 1) Dimensiune (LOC)
- Tool: cloc 2.06
- Total LOC Java: **148**

## 2) Complexitate
- Tool: Lizard
- `evaluateExpression(...)` – Cyclomatic Complexity: **12**; Cognitive Complexity (estimativ): **≈16**
- `Calculate(...)` – Cyclomatic Complexity: **12**; Cognitive Complexity (estimativ): **≈17**

## 3) Revizuire informală (fără rulare)
_Format: fișier – linia – observație_
- `Calculator.java` – linia 28–72 – Metoda `evaluateExpression`: if-uri imbricate → crește complexitatea; recomandat refactorizare în metode mai mici.
- `Calculator.java` – linia 74–186 – Metoda `Calculate`: cod duplicat pentru operatori; recomandat Strategy/Command.
- `Calculator.java` – valori numerice „magic numbers” pentru priorități; recomandat extragere în constante/enum.
- `Calculator.java` – lipsă validare împărțire la zero și input invalid.
- `Start.java` – metoda `main`: prea multă logică directă; recomandat delegare către clase auxiliare.

## 4) Analiză statică – sinteză
- Checkstyle/SonarLint: ar semnala nume metode generice, complexitate peste prag, duplicări.
- Code Smells: if-uri imbricate, metode lungi, lipsă validări.

## 5) Recomandări
1. Reduce nesting (spargere în metode mici).
2. Elimină duplicarea prin Strategy/Command.
3. Adaugă validări input (ex.: divide-by-zero).
4. Introdu constante/enum pentru priorități/operatori.
5. Creează teste unitare pentru cazuri limită și ordine de evaluare.
