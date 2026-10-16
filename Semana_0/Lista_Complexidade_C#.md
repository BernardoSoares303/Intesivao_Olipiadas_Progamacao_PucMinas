# Complexidade das Principais Estruturas e Algoritmos em C#

Lista de complexidade das Principais Estruturas e Algoritmos em C#, criada pelo chat gpt e gemini, não sei da veracidade das informações vou ver se meu professor da faculdade valida elas (Provavelmente isso não vai acontecer).

---

## 1. Complexidade das Principais Estruturas do C#

### `List<T>` — Lista Dinâmica

| Operação | Exemplo em C# | Complexidade |
| :--- | :--- | :--- |
| Acessar por índice | `lista[i]` | $O(1)$ |
| Alterar por índice | `lista[i] = x` | $O(1)$ |
| Adicionar ao final | `lista.Add(x)` | $O(1)^*$ |
| Inserir no início | `lista.Insert(0, x)` | $O(n)$ |
| Inserir no meio | `lista.Insert(i, x)` | $O(n)$ |
| Remover pelo índice | `lista.RemoveAt(i)` | $O(n)$ |
| Remover pelo valor | `lista.Remove(x)` | $O(n)$ |
| Buscar valor | `lista.Contains(x)` | $O(n)$ |
| Encontrar índice | `lista.IndexOf(x)` | $O(n)$ |
| Percorrer todos os elementos | `foreach` | $O(n)$ |
| Ordenar | `lista.Sort()` | $O(n \log n)$ |
| Inverter a ordem | `lista.Reverse()` | $O(n)$ |
| Copiar a lista | `lista.ToArray()` | $O(n)$ |

> `Add()` tem custo amortizado O(1), mas pode chegar a O(n) quando precisa redimensionar o array interno.

---

### `Dictionary<TKey, TValue>` — Tabela Hash

| Operação | Exemplo em C# | Média | Pior caso |
| :--- | :--- | :--- | :--- |
| Inserir ou atualizar | `dict[chave] = valor` | $O(1)$ | $O(n)$ |
| Consultar por chave | `dict[chave]` | $O(1)$ | $O(n)$ |
| Verificar chave | `dict.ContainsKey(chave)` | $O(1)$ | $O(n)$ |
| Verificar valor | `dict.ContainsValue(valor)` | $O(n)$ | $O(n)$ |
| Remover por chave | `dict.Remove(chave)` | $O(1)$ | $O(n)$ |
| Percorrer elementos | `foreach` | $O(n)$ | $O(n)$ |

> **Dica:** O `Dictionary` é especialmente útil para contar frequências, identificar duplicatas e resolver problemas que exigem buscas rápidas.

---

### `HashSet<T>` — Conjunto de Valores Únicos

| Operação | Exemplo em C# | Média | Pior caso |
| :--- | :--- | :--- | :--- |
| Adicionar | `set.Add(x)` | $O(1)$ | $O(n)$ |
| Verificar existência | `set.Contains(x)` | $O(1)$ | $O(n)$ |
| Remover | `set.Remove(x)` | $O(1)$ | $O(n)$ |
| União de conjuntos | `set.UnionWith(outro)` | $O(n+m)^*$ | $O(nm)^*$ |
| Interseção | `set.IntersectWith(outro)` | Depende da implementação e tamanhos | — |
| Percorrer | `foreach` | $O(n)$ | $O(n)$ |

*Os custos de união e interseção dependem do tamanho dos conjuntos, das operações de hash e de como os elementos são comparados. Para entrevistas, priorize as operações básicas.*

---

### `Queue<T>` — Fila FIFO
> **FIFO** (*First In, First Out*): o primeiro a entrar é o primeiro a sair.

| Operação | Exemplo em C# | Complexidade |
| :--- | :--- | :--- |
| Inserir no final | `fila.Enqueue(x)` | $O(1)$ amortizado |
| Consultar o primeiro | `fila.Peek()` | $O(1)$ |
| Remover o primeiro | `fila.Dequeue()` | $O(1)$ |
| Verificar se contém | `fila.Contains(x)` | $O(n)$ |
| Percorrer | `foreach` | $O(n)$ |

> **Uso comum:** BFS (Busca em Largura), simulações e processamento por ordem de chegada.

---

### `Stack<T>` — Pilha LIFO
> **LIFO** (*Last In, First Out*): o último a entrar é o primeiro a sair.

| Operação | Exemplo em C# | Complexidade |
| :--- | :--- | :--- |
| Inserir | `pilha.Push(x)` | $O(1)$ amortizado |
| Consultar o topo | `pilha.Peek()` | $O(1)$ |
| Remover o topo | `pilha.Pop()` | $O(1)$ |
| Verificar se contém | `pilha.Contains(x)` | $O(n)$ |
| Percorrer | `foreach` | $O(n)$ |

> **Uso comum:** Validação de parênteses, DFS, histórico de operações e expressões matemáticas.

---

## 2. Complexidade de Arrays e Strings

### Arrays (`T[]`)

| Operação | Exemplo | Complexidade |
| :--- | :--- | :--- |
| Acessar elemento | `arr[i]` | $O(1)$ |
| Alterar elemento | `arr[i] = x` | $O(1)$ |
| Percorrer | `foreach` | $O(n)$ |
| Buscar sem ordenação | `Array.IndexOf(arr, x)` | $O(n)$ |
| Ordenar | `Array.Sort(arr)` | $O(n \log n)$ |
| Copiar array | `Array.Copy(...)` | $O(n)$ |
| Criar array de tamanho $n$ | `new int[n]` | $O(n)$ |

> **Nota:** Arrays têm tamanho fixo. O acesso por índice constante os torna ideais para programação competitiva.

---

### `string`
Em C#, strings são **imutáveis**: operações que modificam seu conteúdo criam uma nova string em memória.

| Operação | Exemplo | Complexidade |
| :--- | :--- | :--- |
| Acessar caractere | `texto[i]` | $O(1)$ |
| Consultar tamanho | `texto.Length` | $O(1)$ |
| Buscar caractere ou trecho | `texto.Contains("abc")` | $O(n \cdot m)^*$ |
| Encontrar índice | `texto.IndexOf("abc")` | Até $O(n \cdot m)^*$ |
| Concatenar duas strings | `a + b` | $O(n+m)$ |
| Criar substring | `texto.Substring(i, tam)` | $O(tam)$ |
| Converter para array de chars | `texto.ToCharArray()` | $O(n)$ |
| Comparar strings | `a == b` | Até $O(n)$ |
| Dividir em partes | `texto.Split(' ')` | Geralmente $O(n)$ (+ alocações) |

*Onde $n$ é o tamanho do texto e $m$ é o tamanho do trecho buscado.*

> **Dica de competição:** Para concatenar muitos fragmentos dentro de um loop, prefira `StringBuilder` para evitar o custo de alocações excessivas.

---

## 3. Métodos Comuns do LINQ

O LINQ é expressivo, mas é importante estar atento ao custo implícito de cada chamada.

| Método | Exemplo | Complexidade Típica |
| :--- | :--- | :--- |
| `Any()` | `lista.Any()` | $O(1)$ |
| `Any(condição)` | `lista.Any(x => x > 5)` | $O(n)$ |
| `Count()` (coleção conhecida) | `lista.Count()` | $O(1)$ |
| `Count(condição)` | `lista.Count(x => x > 5)` | $O(n)$ |
| `First()` | `lista.First()` | $O(1)$ |
| `First(condição)` | `lista.First(x => x > 5)` | $O(n)$ |
| `Where()` | `lista.Where(x => x > 5)` | Execução adiada; $O(n)$ ao percorrer |
| `Select()` | `lista.Select(x => x * 2)` | Execução adiada; $O(n)$ ao percorrer |
| `Distinct()` | `lista.Distinct()` | Geralmente $O(n)$ |
| `GroupBy()` | `lista.GroupBy(x => x)` | Geralmente $O(n)$ |
| `OrderBy()` | `lista.OrderBy(x => x)` | $O(n \log n)$ |
| `ToList()` | `consulta.ToList()` | $O(n)$ para materializar |
| `Sum()` | `lista.Sum()` | $O(n)$ |

> **Atenção:** `Where()` e `Select()` utilizam **execução adiada** (*deferred execution*). O processamento só ocorre ao iterar sobre o resultado. Percorrer a mesma consulta múltiplas vezes recalcula todos os passos.

---

## 4. Complexidade de Operações Matemáticas e Algoritmos

| Operação / Algoritmo | Complexidade Típica |
| :--- | :--- |
| Soma, subtração e multiplicação (tamanho fixo) | $O(1)$ |
| Divisão inteira (tamanho fixo) | $O(1)$ |
| Percorrer os dígitos de um número | $O(\log n)$ |
| Busca linear | $O(n)$ |
| Busca binária (dados ordenados) | $O(\log n)$ |
| Dois loops independentes de tamanho $n$ | $O(n^2)$ |
| Dois loops aninhados de tamanho $n$ | $O(n^2)$ |
| Três loops aninhados de tamanho $n$ | $O(n^3)$ |
| Merge Sort | $O(n \log n)$ |
| Quick Sort | Média $O(n \log n)$, Pior caso $O(n^2)$ |
| BFS / DFS em grafos (lista de adjacência) | $O(V + E)$ |
| Percorrer árvore binária | $O(n)$ |
| Busca em árvore binária balanceada | $O(\log n)$ |
| Busca em árvore binária degenerada | $O(n)$ |

**Convenções:**
- $n$: quantidade de elementos.
- $V$: quantidade de vértices em um grafo.
- $E$: quantidade de arestas em um grafo.
- $\log n$: logaritmo na base 2 (padrão em computação).

---

## 5. Como Reconhecer Cada Complexidade

- **$O(1)$ — Constante:** O custo não cresce com o tamanho dos dados.
  ```csharp
  int x = lista[0];
  ```
- **$O(\log n)$ — Logarítmica:** O espaço de busca reduz por um fator a cada passo.
  ```csharp
  while (n > 1) n /= 2;
  ```
- **$O(n)$ — Linear:** Os elementos são processados uma única vez.
  ```csharp
  foreach (int x in lista) Console.WriteLine(x);
  ```
- **$O(n \log n)$ — Linearítmica:** Comum em algoritmos eficientes de ordenação baseados em comparação.
  ```csharp
  lista.Sort();
  ```
- **$O(n^2)$ — Quadrática:** Cada elemento é comparado ou processado em relação a todos os outros.
  ```csharp
  for (int i = 0; i < n; i++)
      for (int j = 0; j < n; j++)
          Console.WriteLine(i + j);
  ```

---

## 6. Ordem de Crescimento para Memorizar

Disposto do menor para o maior crescimento assintótico:

$$O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(n^3) < O(2^n) < O(n!)$$

Essa hierarquia é essencial para estimar a viabilidade de uma abordagem dentro dos limites de tempo impostos em maratonas de programação e testes técnicos.
