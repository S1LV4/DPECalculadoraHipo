
# 📄 Cálculo de Hipossuficiência da Defensoria Pública

## 📌 Objetivo

Este projeto foi desenvolvido com finalidade avaliativa no âmbito do Processo Seletivo n.º 40 – CATE/RS – Defensoria Pública, tendo como propósito aplicar as diretrizes da Resolução nº 07/2018 do Conselho Superior da Defensoria Pública para aferir a hipossuficiência econômica de assistidos(as). O objetivo é verificar se a pessoa se enquadra nos critérios para obtenção de atendimento jurídico gratuito pela Defensoria Pública.

---

## ⚙️ Lógica do Algoritmo

O cálculo segue as seguintes etapas:

1. **Entrada de dados**:
   - 💰 Renda bruta familiar
   - 👪 Quantidade de dependentes ordinários
   - ♿ Quantidade de dependentes especiais
   - 💸 Valor atual do Salário Mínimo Nacional (SMN) - Consultado automaticamente via API do BACEN;

2. **Regras dos descontos**:
   - Cada dependente ordinário → desconto de **25% do SMN**
   - Cada dependente especial → desconto de **50% do SMN**
   - Soma total dos descontos = (dependentes ordinários × 25% SMN) + (dependentes especiais × 50% SMN)

3. **Renda ajustada**:
   - Renda Bruta Familiar - Descontos

4. **Comparação com o limite legal**:
   - Limite: **3 × Salário Mínimo Nacional** - Definido como critério de hipossuficiência pela Resolução 07/2018.
   - Se Renda Ajustada ≤ Limite: ✅ Hipossuficiente
   - Se Renda Ajustada > Limite: ❌ Não Hipossuficiente

5. **Geração do relatório estruturado** com todos os dados e justificativa final.

---

## 📊 Exemplo de Resultados Gerados

### ✅ Caso 1: Hipossuficiente
- Renda Bruta: R$ 5.000,00  
- 3 dependentes ordinários  
- SMN: R$ 1.518,00  
- Descontos: R$ 1.138,50  
- Renda Ajustada: R$ 3.861,50  
- Limite: R$ 4.554,00  
- **Resultado**: Hipossuficiente ✅

### ❌ Caso 2: Não Hipossuficiente
- Renda Bruta: R$ 8.000,00  
- 2 dependentes ordinários  
- Desconto: R$ 759,00  
- Renda Ajustada: R$ 7.241,00  
- Limite: R$ 4.554,00  
- **Resultado**: Não hipossuficiente ❌

---

## 🧮 Fórmulas Utilizadas

```python
desconto_dependentes = (dependentes_ordinarios * 0.25 + dependentes_especiais * 0.50) * salario_minimo
renda_ajustada = renda_bruta - desconto_dependentes
limite = salario_minimo * 3

if renda_ajustada <= limite:
    resultado = "Hipossuficiente"
else:
    resultado = "Não Hipossuficiente"
```

---

## 📁 Estrutura dos Arquivos

- `calc_hipo.ipynb`: Código principal em Jupyter Notebook para entrada, cálculo e geração do relatório.
- `relatorio_hipossuficiencia_*.txt`: Relatórios detalhados dos resultados.

---


