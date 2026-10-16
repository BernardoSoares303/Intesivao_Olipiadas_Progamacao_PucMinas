# Fudeu!
Acabei de descobrir que a olimpíada que me inscrevi começa semana que vem, o que mata meu tempo de preparação tendo isso em mente o objetivo do repositorio mudou agora não é uma preparação mas sim um estudo em geral, vou tentar estudar ao maximo nessa semana que vem pela frente porem como tenho que dar 2 aulas por semana devido ao projeto de extensão da faculdade terei menos dias para estudo.

O foco agora é tentar o metodo Juscelino Kubitschek, Deus tenha misericórdia deste que vos escreve.

Independentemente não vou deixar a peteca cair, se não der bom esse semestre (2° de 2026), estarei mais preparado para a competição do primeiro semestre de 2027. O foco se mantem os estudo tambem e estou começando a achar meio esquizofrenicos esses textos, entretanto toda via contunuarei os escrevendo para servir de registro para mim mesmo de qual imbecil eu era e provavelmente aindo sou.

# Estudo do dia 1
Como ao invez de semanas terei dias para me preparar hoje vou tentar fazer alguns leetcodes que são atividades da minha faculdade, um abraço pro meu professor Humberto Nigriri (espero que seu nome esteja escrito corretamente) que além de me fornecer materias para o estudo desse dia é a pessoa que organiza a compentição que irei participar, além disso é um eximio flautista e nadador.

## Meta do dia 1:
Fazer pelo menos 3 das atividades do humberto vou colar nesse Markdown as perguntas é a minha solução.

## Atividade 1: Implemente uma função recursiva que busca um valor num vetor a partir de um índice, retornando a posição onde foi encontrado ou -1 caso não exista.

### Solução

```csharp
static int BuscarRec(int[] vetor, int indice, int alvo)
{
    if(indice>=vetor.Length)
        return -1;
    if(vetor[indice] == alvo)
        return indice;
    
    return BuscarRec(vetor, indice + 1, alvo);
}
```

### Explicação da Solução

```csharp
    if(indice>=vetor.Length)
            return -1;
```
A linha acima é o caso base. O caso base determina quando a função deve parar de chamar a si mesma. Sem essa condição, se o alvo não fosse encontrado, a função continuaria aumentando o índice até tentar acessar uma posição fora dos limites do vetor, causando um erro de execução.

```csharp
    if(vetor[indice] == alvo)
            return indice;
```
Essa linha serve para verificar se o alvo é igual ao item armazenado na posição atual do indice do vetor.

```csharp
    return BuscarRec(vetor, indice + 1, alvo);
```
Essa é a chamada recursiva, que é o que faz a função chamar a si mesma. Para quem não sabe, uma função recursiva é uma função que resolve um problema por meio de chamadas a si mesma, dividindo-o em etapas menores.

Neste caso, a função chama a si mesma para verificar a próxima posição do vetor, criando uma pilha de execução em que cada chamada verifica um elemento. Quando o alvo é encontrado ou o caso base é atingido, as chamadas começam a ser encerradas.

O **indice + 1** é o que faz a busca avançar pelo vetor, passando para a próxima posição a cada chamada recursiva.