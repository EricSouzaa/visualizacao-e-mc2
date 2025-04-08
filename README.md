# ⚛️ Visualização da Equação E = mc² com Matplotlib

Este projeto tem como objetivo representar graficamente a famosa equação da física moderna **E = mc²**, de Albert Einstein, utilizando a biblioteca **Matplotlib** com Python.

A ideia é visualizar como a energia cresce em função da massa, e também explorar diferentes tipos de escalas no gráfico (linear e logarítmica).

---

## 📊 Descrição do projeto

Foram criados dois gráficos lado a lado:

1. **Escala linear** no eixo Y
2. **Escala logarítmica** no eixo Y

Isso permite comparar visualmente como a energia aumenta de forma **não-linear** à medida que a massa cresce.

---

## 🔢 Fórmulas e dados utilizados

A fórmula utilizada foi:

\[
E = mc²
\]

Onde:
- `m` é a massa (variando de 0 a 10 kg)
- `c` é a velocidade da luz no vácuo (aproximadamente \(3 \times 10^8\) m/s)
- `E` é a energia resultante, em joules (J)

---

## 🧪 Código em Python (Matplotlib)

```python
import matplotlib.pyplot as plt
import numpy as np

# Valores de massa de 0 a 10 kg
m = np.linspace(0, 10, 11)
c = 3 * (10**8)
e = m * (c**2)

# Criar dois subplots (lado a lado)
fig, axes = plt.subplots(nrows=1, ncols=2)

# Gráfico com escala normal
axes[0].plot(m, e, color='blue')
axes[0].set_xlabel('Mass (kg)')
axes[0].set_ylabel('Energy (J)')
axes[0].set_title('E=mc² (normal scale)')
axes[0].grid(True)

# Gráfico com escala logarítmica no eixo Y
axes[1].plot(m, e, color='red')
axes[1].set_xlabel('Mass (kg)')
axes[1].set_ylabel('Energy (J)')
axes[1].set_title('E=mc² (log scale)')
axes[1].set_yscale('log')
axes[1].grid(True, which='both', axis='y')

# Ajustar layout para evitar sobreposição
plt.tight_layout()
plt.show()
