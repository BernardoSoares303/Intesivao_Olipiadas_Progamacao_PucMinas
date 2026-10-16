# Plano de Estudos — Competição de Programação em C#

**Objetivo:** preparar-se para uma competição interna com problemas no estilo LeetCode, usando C#.

**Duração sugerida:** 4 semanas  
**Ritmo sugerido:** 1 hora por dia, 5 dias por semana  
**Estratégia:** aprender padrões de algoritmos, resolver problemas sem consultar soluções de imediato, analisar erros e treinar com tempo limitado.

> Adapte o ritmo ao seu prazo e ao seu nível atual. É melhor consolidar uma técnica do que avançar sem compreendê-la.

---

## 1. Método de treinamento

1. **Estude por padrões, não aleatoriamente.** Aprenda uma técnica e resolva vários problemas que a utilizem.
2. **Tente resolver antes de consultar a solução.** Reserve de 20 a 30 minutos para pensar. Se travar, estude a ideia e depois implemente novamente sem copiar.
3. **Treine com tempo limitado.** Depois de aprender um assunto, pratique em sessões cronometradas.
4. **Mantenha um caderno de erros.** Registre o problema, a técnica, onde travou, a solução correta e os casos extremos que esqueceu.
5. **Revise os problemas.** Refaça os que errou alguns dias depois, sem consultar a resposta anterior.

## 2. Calendário de preparação

### Semana 1 — Fundamentos que dão pontos

**Assuntos**
- Arrays e strings
- `Dictionary<TKey, TValue>`
- `HashSet<T>`
- Complexidade Big O
- Percorrer arrays, contar elementos e encontrar valores

**Meta:** resolver problemas Easy sem depender de dicas.

### Semana 2 — Reconhecimento de padrões

**Assuntos**
- Two Pointers
- Sliding Window
- Prefix Sum
- Busca binária (Binary Search)

**Meta:** reconhecer qual padrão pode ser usado antes de começar a codificar.

### Semana 3 — Estruturas de dados

**Assuntos**
- `Stack<T>` e `Queue<T>`
- Listas ligadas
- Árvores
- Recursão
- Introdução a BFS e DFS

**Meta:** saber quando cada estrutura ou algoritmo simplifica o problema.

### Semana 4 — Velocidade e simulação

**Assuntos**
- Problemas mistos
- Otimização de soluções
- Revisão dos padrões anteriores
- Simulados cronometrados

**Meta:** resolver problemas novos sem dicas e administrar o tempo.

> As semanas são metas, não prazos rígidos. Se uma técnica ainda não estiver clara, revise-a antes de avançar.

---

## 3. Lista de exercícios

Resolva os problemas no site oficial do LeetCode. Tente implementar cada solução em C#.

| # | Problema | Padrão principal | Dificuldade |
|---:|---|---|---|
| 1 | [Two Sum](https://leetcode.com/problems/two-sum/) | `Dictionary` / hashing | Easy |
| 2 | [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) | `HashSet` | Easy |
| 3 | [Valid Anagram](https://leetcode.com/problems/valid-anagram/) | Frequência de caracteres | Easy |
| 4 | [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) | Varredura de array | Easy |
| 5 | [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) | Two Pointers | Easy |
| 6 | [Two Sum II](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) | Two Pointers em array ordenado | Medium |
| 7 | [Binary Search](https://leetcode.com/problems/binary-search/) | Busca binária | Easy |
| 8 | [Maximum Average Subarray I](https://leetcode.com/problems/maximum-average-subarray-i/) | Sliding Window | Easy |
| 9 | [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) | Stack | Easy |
| 10 | [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/) | Lista ligada | Easy |
| 11 | [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/) | DFS / recursão | Easy |
| 12 | [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) | Programação dinâmica básica | Easy |

### Quando considerar um problema dominado?

Marque-o como dominado quando conseguir:
- Explicar a lógica com suas próprias palavras.
- Implementar sem copiar a solução.
- Analisar a complexidade de tempo e memória.
- Testar casos extremos e explicar por que a solução funciona.

---

## 4. Rotina diária de 60 minutos

| Tempo | Atividade |
|---|---|
| 10 minutos | Revisar um padrão já estudado |
| 30 minutos | Tentar resolver um problema novo |
| 10 minutos | Analisar uma solução melhor, se necessário |
| 10 minutos | Reimplementar ou registrar o aprendizado |

No início, compreender profundamente alguns problemas é mais valioso do que copiar muitas soluções. Com a evolução, aumente a dificuldade e reduza gradualmente o tempo de resolução.

## 5. C# para programação competitiva

| Necessidade | Estrutura ou recurso |
|---|---|
| Procurar valores rapidamente | `Dictionary<TKey, TValue>` ou `HashSet<T>` |
| Ordenar elementos | `Array.Sort()` |
| Pilha | `Stack<T>` |
| Fila | `Queue<T>` |
| Lista de tamanho variável | `List<T>` |
| Percorrer caracteres | `char` e `string` |
| Acumular valores | Variáveis e arrays auxiliares |

### Exemplo: Two Sum com Dictionary

A solução ingênua testa todos os pares e custa `O(n²)`. Com um `Dictionary<int, int>`, podemos guardar os valores já vistos e procurar o complemento em tempo esperado constante por consulta, alcançando `O(n)` de tempo esperado.

```csharp
public int[] TwoSum(int[] nums, int target)
{
    var vistos = new Dictionary<int, int>();

    for (int i = 0; i < nums.Length; i++)
    {
        int complemento = target - nums[i];

        if (vistos.TryGetValue(complemento, out int indice))
            return new int[] { indice, i };

        vistos[nums[i]] = i;
    }

    return Array.Empty<int>();
}
```

**Observação:** no LeetCode, normalmente você implementa o método solicitado dentro da classe fornecida pela plataforma. Não adicione `Main()` quando o editor já fornece a assinatura e a classe necessárias.

`Dictionary` e `HashSet` oferecem desempenho esperado próximo de `O(1)` por consulta, mas isso não é uma garantia absoluta para todos os casos.

---

## 6. Estratégia para o dia da competição

### Antes de programar
- Leia os enunciados e identifique os que parecem familiares, se as regras permitirem.
- Comece pelos problemas que consegue resolver com maior confiança.
- Observe as restrições de entrada e o formato esperado da resposta.

### Durante a prova
- Se ficar 10–15 minutos sem encontrar um caminho viável, anote sua ideia e passe para outro problema, se a plataforma permitir.
- Não gaste todo o tempo em uma única questão.
- Faça submissões cuidadosas e respeite as regras de penalidade e pontuação da competição.

### Antes de submeter
- Teste arrays vazios, quando permitidos, e arrays com um único elemento.
- Considere valores repetidos, números negativos e limites máximos.
- Verifique situações em que a resposta não existe.
- Analise se a complexidade é adequada para as restrições do enunciado.
- Confira índices, tipos numéricos e o formato de saída.

---

## 7. Checklist de prontidão

- [ ] Resolver pelo menos 8 dos 12 exercícios sem consultar soluções.
- [ ] Explicar a diferença entre `O(n)`, `O(n log n)` e `O(n²)`.
- [ ] Reconhecer quando usar `Dictionary`, `HashSet`, `Stack` e `Queue`.
- [ ] Resolver três problemas Easy inéditos em uma sessão cronometrada.
- [ ] Fazer pelo menos dois simulados com problemas misturados.
- [ ] Revisar os erros cometidos nos simulados.
- [ ] Conseguir explicar a lógica e a complexidade das soluções submetidas.

## 8. Recursos úteis

- [LeetCode Study Plans](https://leetcode.com/studyplan/)
- [LeetCode Contests](https://leetcode.com/contest/)
- [Two Sum](https://leetcode.com/problems/two-sum/)
- [Binary Search](https://leetcode.com/problems/binary-search/)
- [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

---

## Princípio principal

**Priorize consistência, reconhecimento de padrões e revisão de erros.** Não é necessário dominar todos os algoritmos avançados para começar a competir. Primeiro, resolva problemas fáceis com segurança e aprenda a reconhecer problemas médios em que já conhece a técnica.
