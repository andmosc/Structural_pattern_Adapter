# Задача Калькулятор

## Описание
В этом задании попрактикуемся с шаблоном *Adapter* (*Адаптер*). Ниже вам дан готовый класс калькулятора:

```java
public class Calculator {
  public Formula newFormula() {
    return new Formula();
  }
  --------------------
```

Пример использования этого класса:
```java
Calculator calc = new Calculator();
System.out.println(
  calc.newFormula()
    .addOperand(5)
    .addOperand(15)
    .calculate(Calculator.Operation.MULT)
    .result()
);
```

Пользователю же нужен другой интерфейс для работы с калькулятором:
```java
public interface Ints {
  int sum(int arg0, int arg1);
  int mult(int arg0, int arg1);
  int pow(int a, int b);
}
``` 

Вам надо написать класс `IntsCalculator`, который будет имплементировать интерфейс `Ints`, "под капотом" делая вычисления через класс `Calculator`.