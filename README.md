# Algoritmos Eficientes e Ineficientes: Como a Complexidade Impacta o Desempenho

A eficiência de um algoritmo está diretamente ligada à forma como ele utiliza os recursos computacionais, como **tempo de execução** e **memória**. Em ciência da computação, um dos principais critérios para avaliar essa eficiência é a chamada **complexidade de tempo**, expressa por meio da **notação Big-O**.


---

##  O que é um algoritmo eficiente?

Um algoritmo eficiente é aquele que **resolve o problema corretamente** com o **menor uso possível de recursos**, mesmo quando a entrada de dados cresce significativamente. Em geral, algoritmos com complexidade **O(1), O(log n), O(n)** e **O(n log n)** são considerados eficientes.

---

## É um algoritmo ineficiente?

Já os algoritmos ineficientes **consomem muitos recursos** para resolver um problema, principalmente tempo. Eles tendem a se tornar inviáveis para entradas grandes. Exemplos incluem algoritmos com complexidade **O(n²)**, **O(2ⁿ)** ou **O(n!)**.

---

## Entendendo as complexidades com exemplos

A seguir, veja os principais tipos de complexidade de tempo, com exemplos simples de algoritmos implementados em Python:

---

###  O(1) – Complexidade Constante

> O tempo de execução **não depende** do tamanho da entrada.

```python
def obter_primeiro_elemento(lista):
    return lista[0]


```
- Muito eficiente.

- Ideal sempre que possível

##  O(log n) – Complexidade Logarítmica  
O tempo cresce lentamente conforme a entrada aumenta.

```python
def busca_binaria(lista, alvo):
    inicio, fim = 0, len(lista) - 1
    while inicio <= fim:
        meio = (inicio + fim) // 2
        if lista[meio] == alvo:
            return True
        elif lista[meio] < alvo:
            inicio = meio + 1
        else:
            fim = meio - 1
    return False
```
##  O(n) – Complexidade Linear
O tempo cresce proporcionalmente ao tamanho da entrada.

```python
def encontrar_valor(lista, valor):
    for item in lista:
        if item == valor:
            return True
    return False
```

- Precisa verificar cada elemento uma vez.

- Razoavelmente eficiente.

##  O(n log n) – Complexidade Quase Linear
Tempo um pouco maior que O(n), mas ainda eficiente.

```python
def merge_sort(lista):
    if len(lista) <= 1:
        return lista
    meio = len(lista) // 2
    esquerda = merge_sort(lista[:meio])
    direita = merge_sort(lista[meio:])
    return merge(esquerda, direita)

def merge(esq, dir):
    resultado = []
    i = j = 0
    while i < len(esq) and j < len(dir):
        if esq[i] < dir[j]:
            resultado.append(esq[i])
            i += 1
        else:
            resultado.append(dir[j])
            j += 1
    resultado.extend(esq[i:])
    resultado.extend(dir[j:])
    return resultado
```
- Algoritmo de ordenação eficiente, mesmo para grandes listas.

##  O(n²) – Complexidade Quadrática
O tempo cresce de forma quadrática com o tamanho da entrada.

```python
def verificar_duplicados(lista):
    for i in range(len(lista)):
        for j in range(i + 1, len(lista)):
            if lista[i] == lista[j]:
                return True
    return False

```
- Muito lento para n > 30.

- Comum em algoritmos de força bruta ou recursão sem otimização.

##  O(n!) – Complexidade Fatorial
O tempo cresce de forma explosiva.
```python
import itertools

def gerar_permutacoes(lista):
    return list(itertools.permutations(lista))
```

- Para n = 10, já existem 3.628.800 permutações.

- Impraticável em grande escala.

  ---

Avaliar a complexidade de um algoritmo permite escolher a melhor solução para o seu problema, evitando atrasos, lentidão e consumo excessivo de recursos. Sempre que possível, opte por algoritmos com menor complexidade assintótica.

<img width="860" height="610" alt="image" src="https://github.com/user-attachments/assets/83f42015-b69e-4a38-9b03-1028e0156033" />












