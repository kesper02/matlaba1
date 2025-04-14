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
    
    plt.figure(figsize=(8, 8))
    plt.pie(sizes, explode=explode, labels=labels, autopct='%1.1f%%',
            shadow=True, startangle=90, colors=['gold', 'lightcoral', 'lightskyblue', 'lightgreen'])
    plt.title('Приклад кругової діаграми')
    plt.axis('equal')
    plt.show()

homework_3()
```

## Комірка 6: Завдання 4 - Множинні графіки
```python
def homework_4():
    print(">>>>> Завдання 4: Створіть множинні графіки в одному вікні <<<<<")
    
    x = np.linspace(0, 2*np.pi, 100)
    
    plt.figure(figsize=(12, 6))
    
    # Перший підграфік
    plt.subplot(1, 2, 1)
    plt.plot(x, np.sin(x), 'b-', label='sin(x)')
    plt.title('Функція sin(x)')
    plt.legend()
    plt.grid(True)
    
    # Другий підграфік
    plt.subplot(1, 2, 2)
    plt.plot(x, np.cos(x), 'r--', label='cos(x)')
    plt.title('Функція cos(x)')
    plt.legend()
    plt.grid(True)
    
    plt.tight_layout()
    plt.show()

homework_4()
```

## Комірка 7: Завдання 5 - 3D графік (додаткове)
```python
def homework_5():
    print(">>>>> Завдання 5: Створіть 3D графік (додаткове) <<<<<")
    
    import matplotlib.pyplot as plt
    from mpl_toolkits.mplot3d import Axes3D
    import numpy as np
    
    fig = plt.figure(figsize=(10, 7))
    ax = fig.add_subplot(111, projection='3d')
    
    x = np.linspace(-5, 5, 100)
    y = np.linspace(-5, 5, 100)
    x, y = np.meshgrid(x, y)
    z = np.sin(np.sqrt(x**2 + y**2))
    
    surf = ax.plot_surface(x, y, z, cmap='viridis')
    fig.colorbar(surf)
    
    ax.set_title('3D графік функції sin(√(x²+y²))')
    ax.set_xlabel('Вісь X')
    ax.set_ylabel('Вісь Y')
    ax.set_zlabel('Вісь Z')
    
    plt.show()

homework_5()
```

## Як здати роботу:
1. Виконайте всі комірки по порядку
2. Збережіть Notebook (File → Save As...)
3. Завантажте файл `.ipynb` у ваш репозиторій
4. Відправте посилання на файл у Google Classroom
