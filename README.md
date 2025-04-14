# Лабораторна робота з візуалізації даних

## Інструкція з використання
1. Відкрийте Jupyter Notebook
2. Створіть новий файл з розширенням `.ipynb`
3. Копіюйте комірки з цього документа
4. Виконуйте комірки по черзі

## Комірка 1: Імпорт бібліотек
```python
import matplotlib.pyplot as plt
import numpy as np
print(">>>>> Бібліотеки успішно імпортовано <<<<<")
```

## Комірка 2: Базовий приклад графіка
```python
def basic_example():
    x = np.linspace(0, 10, 100)
    y = np.sin(x)
    
    plt.figure(figsize=(10, 5))
    plt.plot(x, y, label='sin(x)', color='blue', linewidth=2)
    plt.title('Базовий графік функції sin(x)')
    plt.xlabel('Вісь X')
    plt.ylabel('Вісь Y')
    plt.legend()
    plt.grid(True)
    plt.show()

basic_example()
print(">>>>> Базовий приклад виконано <<<<<")
```

## Комірка 3: Завдання 1 - Графік cos(x)
```python
def homework_1():
    print(">>>>> Завдання 1: Створіть графік cos(x) <<<<<")
    
    x = np.linspace(-np.pi, np.pi, 200)
    y = np.cos(x)
    
    plt.figure(figsize=(10, 5))
    plt.plot(x, y, label='cos(x)', color='red', linestyle='--')
    plt.title('Графік функції cos(x) на інтервалі [-π, π]')
    plt.xlabel('x')
    plt.ylabel('cos(x)')
    plt.legend()
    plt.grid(True)
    plt.show()

homework_1()
```

## Комірка 4: Завдання 2 - Стовпчаста діаграма
```python
def homework_2():
    print(">>>>> Завдання 2: Створіть стовпчасту діаграму <<<<<")
    
    categories = ['Категорія A', 'Категорія B', 'Категорія C', 'Категорія D']
    values = [15, 24, 18, 30]
    
    plt.figure(figsize=(8, 5))
    bars = plt.bar(categories, values, color=['skyblue', 'lightgreen', 'orange', 'pink'])
    
    # Додаємо значення над стовпцями
    for bar in bars:
        height = bar.get_height()
        plt.text(bar.get_x() + bar.get_width()/2., height,
                 f'{height}', ha='center', va='bottom')
    
    plt.title('Приклад стовпчастої діаграми')
    plt.xlabel('Категорії')
    plt.ylabel('Значення')
    plt.grid(axis='y')
    plt.show()

homework_2()
```

## Комірка 5: Завдання 3 - Кругова діаграма
```python
def homework_3():
    print(">>>>> Завдання 3: Створіть кругову діаграму <<<<<")
    
    labels = ['Частина A', 'Частина B', 'Частина C', 'Частина D']
    sizes = [25, 35, 20, 20]
    explode = (0.1, 0, 0, 0)  # Виділяємо перший сектор
    
    plt.figure(figsize
