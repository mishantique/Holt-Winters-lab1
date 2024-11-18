# **README**

## **Цель работы**
Изучение и реализация модели Хольта-Уинтерса для прогнозирования временных рядов с сезонностью. Тюнинг гиперпараметров модели (\( $\alpha$,  $\beta$, $\gamma$\) и длины сезона \(L\)) с использованием методов оптимизации. Исследование точности прогноза и визуализация результатов.

---

## **Постановка задачи**
1. Реализовать модель Хольта-Уинтерса с аддитивным компонентным разложением временного ряда.
2. Выполнить прогноз временного ряда на заданный горизонт (\(  $\tau$ \)).
3. Автоматизировать тюнинг гиперпараметров сглаживания (\($\alpha$,  $\beta$, $\gamma$\)) и длины сезона (\(L\)).
4. Провести оценку качества модели с использованием метрик MAE (средняя абсолютная ошибка) и MSE (среднеквадратичная ошибка).
5. Визуализировать исторические данные, прогнозные значения и ошибки.
6. Подготовить аудиоотчёт (подкаст) с описанием хода работы и полученных результатов.

---
## **Описание датасета**
AirPassengers Dataset — это классический временной ряд, содержащий ежемесячные данные о количестве пассажиров международных авиалиний за период с января 1949 года по декабрь 1960 года. Датасет демонстрирует выраженную сезонность, линейный тренд и шумовые колебания, что делает его идеальным для тестирования моделей прогнозирования, таких как Хольта-Уинтерса.

---
## **Расширенный блок**
### **Реализованные улучшения**
1. Добавлен **тюнинг длины сезона** (\(L\)) в дополнение к сглаживающим параметрам (\($\alpha$,  $\beta$, $\gamma$\)).
2. Использована функция оптимизации `scipy.optimize.minimize` для подбора всех гиперпараметров модели.
3. Проведено исследование зависимости ошибки прогноза от длины сезона.

### **Результаты расширенного анализа**
1. **Оптимальные параметры сглаживания**: 
   - Alpha ($\alpha$)): от 0.01 до 1.
   - Beta (\($\beta$)): от 0.01 до 1.
   - Gamma (\($\gamma$\)): от 0.01 до 1.
2. **Оптимальная длина сезона (\(L\))**: Автоматически подобрана в диапазоне 4–24.

### **Пример визуализации ошибки от длины сезона**
![image](https://github.com/user-attachments/assets/5be18db8-46ac-467c-bbe7-a34122e018cf)

---

## **Краткое описание модели**
Модель Хольта-Уинтерса позволяет прогнозировать временные ряды с выраженной сезонностью. Она включает три основные компоненты:
1. **Уровень (\(a_t\))**: отвечает за текущее значение ряда.
2. **Тренд (\(b_t\))**: отражает скорость изменения ряда во времени.
3. **Сезонность (\(F_t\))**: описывает регулярные колебания с заданным периодом (\(L\)).

Алгоритм использует сглаживающие параметры:
- **\($\alpha$)** для уровня,
- **\($\beta$)** для тренда,
- **\(\$\gamma$\)** для сезонности.

Прогнозное значение на горизонт \( $\tau$):
![image](https://github.com/user-attachments/assets/bed2ddca-820e-4b05-aaf3-6cea23886fa8)


---

## **Экраны работы программы**
### **1. Визуализация исходного временного ряда**
![image](https://github.com/user-attachments/assets/0a13c822-f9dd-4c57-91ab-c9f5fdaa61a3)


### **2. Результат прогноза**
![image](https://github.com/user-attachments/assets/0409a9a1-1a1f-48d9-9024-055bd131b865)


### **3. Ошибки прогноза**
![image](https://github.com/user-attachments/assets/bdc902f0-da37-4ee3-bdce-b3b53f5a4d4b)


### **4. Зависимость ошибки от длины сезона**
![image](https://github.com/user-attachments/assets/c42acda3-b51e-4b39-870d-a75d3027c68a)


---

### Краткий вывод

1. **Исходный временной ряд (AirPassengers Dataset):**
   Данные демонстрируют выраженную сезонность и линейный рост количества пассажиров в период с 1949 по 1960 годы. Сезонные пики соответствуют летним месяцам, когда наблюдается высокий спрос на авиаперелёты.

2. **Прогноз модели Хольта-Уинтерса:**
   Модель успешно уловила тренд и сезонные колебания временного ряда. Прогнозные значения следуют за историческими данными, демонстрируя хорошее соответствие с общей динамикой.

3. **Ошибки прогноза:**
   На горизонте прогноза наблюдаются некоторые расхождения между фактическими и прогнозными значениями. Максимальные ошибки приходятся на пики и спады сезонных циклов, что связано с высокой амплитудой колебаний.

4. **Результаты оптимизации:**
   Автоматический подбор гиперпараметров (\( \alpha, \beta, \gamma, L \)) улучшил качество модели, что видно по корректной идентификации длины сезона и сглаживанию данных.

5. **Заключение:**
   Реализованная модель Хольта-Уинтерса продемонстрировала высокую точность в прогнозировании временных рядов с трендом и сезонностью. Этот подход может быть эффективно применён для задач прогнозирования в реальных данных, таких как пассажиропотоки, продажи или энергопотребление.


---
## **Запуск программы**
1. Установите необходимые библиотеки:
   ```bash
   pip install pandas matplotlib scipy
2. Запустите .ipynb-файл
