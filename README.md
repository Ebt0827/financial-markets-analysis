# financial-markets-analysis

**Language: Python**  
**Tools: Jupyter Notebook, yFinance, Pandas, Matplotlib, Seaborn**  
**Goal: Data analysis practice for real-world financial markets (US Stocks)**

---

## Project Overview / Төслийн зорилго

This project is designed to help me build a strong understanding of **financial market analysis** using Python.  
It covers practical techniques such as stock price retrieval, visualization, returns calculation, moving averages, and correlation analysis.

Энэхүү төсөл нь **санхүүгийн зах зээлийн дата анализыг** Python ашиглан суралцах, практик дээр хэрэглэх зорилготой.  
Хувьцааны үнэ татах, график зурах, өгөөж тооцох, дундаж хөдөлгөөн болон хамаарлын шинжилгээ хийх зэрэг агуулгуудтай.

---

## Lessons / Хичээлүүд

| №   | Title (English)                         | Гарчиг (Монгол)                             
|-----|------------------------------------------|---------------------------------------------
| 1   | Getting Stock Price with yFinance       | yFinance ашиглан хувьцааны үнэ татах        
| 2   | Plotting Closing Price with Matplotlib  | Matplotlib ашиглан хаалтын үнэ зурах       
| 3   | Moving Averages (5, 20 days)            | 5, 20 өдрийн гулсмал дундаж                 
| 4   | Daily Returns & Standard Deviation      | Өдрийн өгөөж ба стандарт хазайлт           
| 5   | Correlation Analysis (Heatmap)          | Хамаарлын шинжилгээ (Heatmap)              
| ... | (Coming soon...)                        | (Үргэлжлэл байна...)                        

---

## ## What is Correlation? / Correlation гэж юу вэ?

Correlation is a statistical measure that indicates the degree to which two variables (such as stock prices) move in relation to each other. It helps investors understand how different assets behave together—whether they tend to rise or fall at the same time, or behave independently.

Correlation гэдэг нь хоёр хувьсагч (жишээ нь, хоёр компанийн хувьцааны үнэ) хооронд хэр зэрэг уялдаа хамааралтай хөдөлж байгааг илэрхийлдэг статистик хэмжигдэхүүн юм. Энэ нь хөрөнгө оруулагчдад хөрөнгийн үнэ хэр зэрэг хамт өсч буурдаг эсвэл тус тусдаа хөдлөдөгийг ойлгоход тусалдаг.

DataFrame.corr() ашиглаж, бүх хосуудын correlation-ыг нэг дор харж болно.

| Correlation | Meaning (English)            | Meaning (Монгол)                              |
|-------------|-------------------------------|------------------------------------------------|
| 1.0         | Strong positive correlation   | Маш хүчтэй эерэг хамаарал (хамт өсдөг)         |
| 0           | No correlation                | Хамаарал байхгүй                               |
| -1.0        | Strong negative correlation   | Маш хүчтэй сөрөг хамаарал (эсрэг чиглэлтэй)   |

**Example / Жишээ:**

- If the correlation between AAPL and MSFT is 0.95, it means their prices usually move together.
- Хэрэв AAPL ба MSFT-ийн хамаарал 0.95 байвал тэдний хувьцаа ихэвчлэн хамт өсч, хамт буурдаг гэсэн үг.

---

## What is a Heatmap? / Heatmap гэж юу вэ?

A heatmap is a graphical representation of data where individual values are represented by color. In the case of a correlation matrix, the heatmap helps quickly visualize how strong or weak the relationships are between each pair of stocks.

Heatmap гэдэг нь өгөгдлийг өнгөөр илэрхийлэн харуулдаг график дүрслэл юм. Correlation matrix буюу хамаарлын хүснэгтийг heatmap ашиглан дүрслэх нь хувьцаануудын хоорондын хамаарлыг хурдан бөгөөд ойлгомжтойгоор харуулахад тусалдаг.

- Heatmap (дүрслэл) ашиглан correlation ойлгох.
	- seaborn.heatmap() ашигласнаар хамаарлын хүчийг өнгөөр ойлгомжтой харуулдаг.
	- Улаан: өндөр эерэг хамаарал
    - Цэнхэр: өндөр сөрөг хамаарал
    - Цайвар: хамаарал сул

---

## Summary / Дүгнэлт

Correlation and heatmap are essential tools for financial analysis.  
Correlation болон heatmap нь санхүүгийн зах зээлийн өгөгдлийг шинжлэхэд чухал үүрэгтэй ба хөрөнгө оруулалтын шийдвэр гаргалтад ашиглагддаг.

---

## 🔍 What is a Moving Average? / Хөдөлгөөнт дундаж гэж юу вэ?

A **moving average** is a tool used in time series analysis that smooths out short-term fluctuations and highlights longer-term trends or cycles.  
Хөдөлгөөнт дундаж нь үнийн хэлбэлзлийг жигдэлж, нийт хандлагыг тодорхойлдог өгөгдлийн шинжилгээний арга юм.

| Name | Meaning (English) | Meaning (Монгол) |
|------|-------------------|------------------|
| SMA (Simple Moving Average) | Average of prices over a set period | Тухайн хугацааны үнийн энгийн дундаж |
| EMA (Exponential Moving Average) | Weighted average giving more importance to recent prices | Сүүлийн үнийн мэдээлэлд илүү жин өгсөн жинтэй дундаж |

---

## How to Interpret / Яаж ойлгох вэ?

When the short-term SMA crosses above the long-term EMA → Buy Signal
    - Богино хугацааны дундаж (SMA) уртыг давах үед → Худалдан авах дохио
When the short-term SMA crosses below the long-term EMA → Sell Signal
    - Богино хугацааны дундаж уртаас доош гарвал → Зарах дохио

---

## Хураангуй

plot()
     Draws line graph, Шугаман график зурна
legend()
    Shows labels for each line
    Шугам бүрийн нэр харуулна
window
    Number of periods in average
    Хэдэн хоногийн дундаж тооцох
ewm(span=)
    Weighted average favoring recent data
    Сүүлийн өдрүүдэд илүү жин өгнө
figure()
    Sets plot size
    Зургийн хэмжээг тогтооно
xlabel() / ylabel()
    Axis labels
    Тэнхлэгийн тайлбар
title()
    Title of plot
    Графикийн гарчиг
grid()
    Background grid
    Арын тор нэмнэ

---

## Lesson 7: Trading Signals from Moving Averages  

# Хөдөлгөөнт дундаж ашиглан худалдах/авах дохио олох.

---

## Зорилго / Objective

- SMA ба EMA-г хослуулан **арилжааны дохио (trading signal)** үүсгэх
- `Buy` болон `Sell` дохио үүсгэх үндсэн логикийг ойлгох
- Мөнхүү дохиог график дээр тэмдэглэх

---

## 🔍 Trading Signals гэж юу вэ?

**trading signal** is an indicator or event suggesting a potential buying or selling opportunity in the market.
**Худалдах/авах дохио** гэдэг нь зах зээл дээрх арилжааны боломжийг илтгэх дохио юм.

---

## 📌 Golden Cross vs. Death Cross

| Signal Name | Description (EN) | Description (MN) |
|-------------|------------------|------------------|
| Golden Cross | Short-term MA crosses **above** long-term MA → **Buy** | Богино хугацааны дундаж уртаас дээш гарвал → **Авах** |
| Death Cross  | Short-term MA crosses **below** long-term MA → **Sell** | Богино хугацааны дундаж уртаас доош гарвал → **Зарах** |

---

## NumPy түгээмэл ашиглагддаг функцууд:

## 1. Array үүсгэх (Creating Arrays)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.array([1,2,3])` | Create array from list | Жагсаалтаас массив үүсгэнэ |
| `np.zeros((2,3))` | 2x3 array of zeros | 0-оор дүүрсэн массив |
| `np.ones((2,3))` | 2x3 array of ones | 1-ээр дүүрсэн массив |
| `np.full((2,3), 7)` | 2x3 array of 7s | 7-оор дүүрсэн массив |
| `np.eye(3)` | Identity matrix | Identity матриц (диагональ нь 1) |
| `np.arange(0, 10, 2)` | Values from 0 to 10 (step 2) | Утгуудыг интервалтайгаар үүсгэнэ |
| `np.linspace(0, 1, 5)` | 5 evenly spaced numbers | Жигд хуваагдсан 5 утга |

---

## 2. Array хэлбэр өөрчлөх (Reshaping)

| Функц | Description |  Тайлбар |
|-------|----------------|-------------|
| `a.reshape((3,2))` | Change shape | Хэлбэрийг өөрчлөх |
| `a.flatten()` | Flatten to 1D | 1 хэмжээст болгох |
| `a.ravel()` | Flatten (view) | 1D хэлбэрт үзэх |
| `a.T` | Transpose | Транспоуз (row ↔ column) |

---

## 3. Статистик функцүүд (Statistics)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.mean(a)` | Mean (average) | Дундаж утга |
| `np.median(a)` | Median value | Медиан (дунд утга) |
| `np.std(a)` | Standard deviation | Стандарт хазайлт |
| `np.var(a)` | Variance | Дисперс |
| `np.sum(a)` | Sum of elements | Нийлбэр |
| `np.min(a)` | Minimum value | Хамгийн бага утга |
| `np.max(a)` | Maximum value | Хамгийн их утга |
| `np.percentile(a, 50)` | 50th percentile | Процентиль утга |

---

## 4. Нөхцөлт функцүүд (Conditional Selection)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.where(condition, x, y)` | Return x or y based on condition | Нөхцөлөөр утга сонгох |
| `np.nonzero(a)` | Indices of non-zero elements | Тэгээс ялгаатай утгуудын индекс |

---

## 5. Утга боловсруулах (Manipulating Values)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.sort(a)` | Sort elements | Элементийг эрэмбэлэх |
| `np.argsort(a)` | Indices that sort array | Эрэмбэлэх индексүүд |
| `np.unique(a)` | Unique elements | Давтагдаагүй утгууд |
| `np.clip(a, min, max)` | Limit values | Утгыг хязгаарлах |

---

## 6. Математик функцүүд (Math)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.add(a, b)` | Add arrays | Хоёр массив нэмэх |
| `np.subtract(a, b)` | Subtract arrays | Хасах |
| `np.multiply(a, b)` | Multiply arrays | Үржих |
| `np.divide(a, b)` | Divide arrays | Хуваах |
| `np.exp(a)` | Exponential | Экспонент |
| `np.sqrt(a)` | Square root | Квадрат язгуур |
| `np.power(a, 2)` | Power of each element | Зэрэгтэлэх |

---

## 7. Вектор ба матриц тооцоолол (Linear Algebra)

| Функц |  Description |  Тайлбар |
|-------|----------------|-------------|
| `np.dot(a, b)` | Dot product | Вектор үржвэр |
| `np.matmul(a, b)` | Matrix multiplication | Матриц үржүүлэлт |
| `np.linalg.inv(a)` | Inverse matrix | Эргүүлэх матриц |
| `np.linalg.det(a)` | Determinant | Матрицын детерминант |
| `np.linalg.eig(a)` | Eigenvalues | Өөрийн утгууд |
| `np.linalg.solve(A, b)` | Solve Ax = b | Тэгшитгэл шийдэх |

---

## 8. Санамсаргүй тоо (Random)

| Функц |  Description | Тайлбар |
|-------|----------------|-------------|
| `np.random.rand(3)` | Random floats (0–1) | Санамсаргүй float тоо |
| `np.random.randn(3)` | Normal dist. floats | Normal тархалттай тоо |
| `np.random.randint(1, 10, 5)` | Random integers | Санамсаргүй integer |
| `np.random.seed(0)` | Fix random results | Санамсаргүй үр дүнг тогтмолжуулах |

---

## 9. Массив нэгтгэх, тусгаарлах (Join / Split)

| Функц | Description |  Тайлбар |
|-------|----------------|-------------|
| `np.concatenate((a, b))` | Join arrays | Массив нэгтгэх |
| `np.stack((a, b))` | Stack arrays | Массив давхарлан нэгтгэх |
| `np.split(a, 3)` | Split array | Хэсэг хэсгээр хуваах |

---

