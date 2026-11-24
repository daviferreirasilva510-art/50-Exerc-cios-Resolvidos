# 50 Exercícios Práticos Resolvidos — Estruturas de Dados em Python

Repositório com soluções práticas em Python sobre **Listas**, **Pilhas**, **Filas**, **Árvores de Processos** (simulação didática) e **Integração**.

> **Nota didática:** Os exemplos de árvores de processos representam relações pai-filho de forma didática; não criam nem encerram processos reais do sistema operacional.

---

## Sumário

- [Listas (01 a 12)](#listas-01-a-12)
- [Pilhas (13 a 24)](#pilhas-13-a-24)
- [Filas (25 a 36)](#filas-25-a-36)
- [Árvore de Processos (37 a 48)](#árvore-de-processos-37-a-48)
- [Integração (49 a 50)](#integração-49-a-50)
- [Referências Bibliográficas](#referências-bibliográficas)

---

## Listas (01 a 12)

### 01. Criar e percorrer uma lista
**Pergunta / Enunciado:** Crie uma lista de cinco números e imprima cada elemento.

**Resposta (Código):**
```python
numeros = [4, 7, 2, 9, 5]

for numero in numeros:
    print(numero)
```
**Explicação:** O laço `for` visita os elementos na ordem em que aparecem na lista.

---

### 02. Inserir elementos
**Pergunta / Enunciado:** Crie uma lista vazia e cadastre três nomes digitados pelo usuário.

**Resposta (Código):**
```python
nomes = []

for i in range(3):
    nome = input(f"Nome {i + 1}: ")
    nomes.append(nome)

print(nomes)
```
**Explicação:** O método `append()` acrescenta cada novo elemento ao final da lista.

---

### 03. Remover uma ocorrência
**Pergunta / Enunciado:** Remova o valor 20 de uma lista somente se ele existir.

**Resposta (Código):**
```python
valores = [10, 20, 30, 20]

if 20 in valores:
    valores.remove(20)

print(valores)
```
**Explicação:** A verificação `20 in valores` evita erro caso o elemento não exista, e `remove()` elimina apenas a primeira ocorrência encontrada.

---

### 04. Soma sem sum
**Pergunta / Enunciado:** Calcule a soma dos elementos sem usar `sum()`.

**Resposta (Código):**
```python
valores = [3, 5, 8, 2]
total = 0

for valor in valores:
    total += valor

print("Soma:", total)
```
**Explicação:** A variável `total` acumula o valor de cada elemento percorrido na lista.

---

### 05. Média de uma lista
**Pergunta / Enunciado:** Calcule a média de cinco notas armazenadas em uma lista.

**Resposta (Código):**
```python
notas = [7.0, 8.5, 6.0, 9.0, 7.5]
soma = 0

for nota in notas:
    soma += nota

media = soma / len(notas)
print(f"Média: {media:.2f}")
```
**Explicação:** A soma das notas é dividida pela quantidade de elementos obtida com `len(notas)`.

---

### 06. Maior elemento sem max
**Pergunta / Enunciado:** Identifique o maior número de uma lista não vazia.

**Resposta (Código):**
```python
valores = [12, 5, 27, 9]
maior = valores[0]

for valor in valores[1:]:
    if valor > maior:
        maior = valor

print("Maior:", maior)
```
**Explicação:** O primeiro elemento inicia a comparação e `maior` é atualizado sempre que surge um valor superior.

---

### 07. Menor elemento e posição
**Pergunta / Enunciado:** Encontre o menor valor e seu índice.

**Resposta (Código):**
```python
valores = [8, 3, 6, 1, 4]
indice = 0

for i in range(1, len(valores)):
    if valores[i] < valores[indice]:
        indice = i

print(valores[indice], "no índice", indice)
```
**Explicação:** A variável `indice` acompanha a posição do menor valor encontrado durante a varredura.

---

### 08. Contar pares
**Pergunta / Enunciado:** Conte quantos elementos são pares.

**Resposta (Código):**
```python
valores = [1, 4, 6, 9, 10, 13]
quantidade = 0

for valor in valores:
    if valor % 2 == 0:
        quantidade += 1

print("Pares:", quantidade)
```
**Explicação:** O operador de módulo `%` verifica se o resto da divisão por 2 é igual a zero.

---

### 09. Busca linear
**Pergunta / Enunciado:** Busque o valor 15 e mostre seu índice, ou -1.

**Resposta (Código):**
```python
valores = [5, 10, 15, 20]
procurado = 15
indice = -1

for i, valor in enumerate(valores):
    if valor == procurado:
        indice = i
        break

print("Índice:", indice)
```
**Explicação:** A busca linear percorre a lista sequencialmente até encontrar o alvo e interrompe com `break`.

---

### 10. Inverter sem reverse
**Pergunta / Enunciado:** Construa uma nova lista com os elementos na ordem inversa.

**Resposta (Código):**
```python
original = [1, 2, 3, 4]
invertida = []

for i in range(len(original) - 1, -1, -1):
    invertida.append(original[i])

print(invertida)
```
**Explicação:** O `range` percorre os índices do último (`len(original) - 1`) até o primeiro (`0`) com passo `-1`.

---

### 11. Eliminar duplicatas
**Pergunta / Enunciado:** Crie uma lista sem valores repetidos, preservando a ordem.

**Resposta (Código):**
```python
valores = [2, 3, 2, 5, 3, 7]
unicos = []

for valor in valores:
    if valor not in unicos:
        unicos.append(valor)

print(unicos)
```
**Explicação:** Cada elemento só é adicionado à lista `unicos` se ainda não estiver presente nela.

---

### 12. Ordenação por seleção
**Pergunta / Enunciado:** Ordene uma lista crescente sem usar `sort()` ou `sorted()`.

**Resposta (Código):**
```python
valores = [9, 4, 7, 1, 3]

for i in range(len(valores)):
    menor = i
    for j in range(i + 1, len(valores)):
        if valores[j] < valores[menor]:
            menor = j
    valores[i], valores[menor] = valores[menor], valores[i]

print(valores)
```
**Explicação:** O *Selection Sort* encontra o menor elemento da parte não ordenada e o troca com a posição atual `i`.

---

## Pilhas (13 a 24)

### 13. Empilhar três elementos
**Pergunta / Enunciado:** Implemente uma pilha com lista e operações push.

**Resposta (Código):**
```python
pilha = []

for item in ["A", "B", "C"]:
    pilha.append(item)

print("Pilha:", pilha)
```
**Explicação:** `append()` realiza a operação *push* inserindo no topo da pilha (final da lista).

---

### 14. Desempilhar com segurança
**Pergunta / Enunciado:** Remova o topo somente quando a pilha não estiver vazia.

**Resposta (Código):**
```python
pilha = [10, 20, 30]

if pilha:
    removido = pilha.pop()
    print("Removido:", removido)
else:
    print("Pilha vazia")
```
**Explicação:** `pop()` remove e retorna o último elemento adicionado, seguindo a regra LIFO (*Last In, First Out*).

---

### 15. Consultar topo
**Pergunta / Enunciado:** Mostre o elemento do topo sem removê-lo.

**Resposta (Código):**
```python
pilha = ["base", "meio", "topo"]

if pilha:
    print("Topo:", pilha[-1])
else:
    print("Pilha vazia")
```
**Explicação:** O índice `-1` acessa o último elemento da lista sem alterar o conteúdo da pilha.

---

### 16. Verificar pilha vazia
**Pergunta / Enunciado:** Crie uma função que informe se a pilha está vazia.

**Resposta (Código):**
```python
def vazia(pilha):
    return len(pilha) == 0


print(vazia([]))
print(vazia([1, 2]))
```
**Explicação:** Uma pilha sem elementos possui tamanho `0`.

---

### 17. Inverter uma palavra
**Pergunta / Enunciado:** Utilize uma pilha para inverter uma palavra.

**Resposta (Código):**
```python
palavra = "PYTHON"
pilha = []

for letra in palavra:
    pilha.append(letra)

invertida = ""
while pilha:
    invertida += pilha.pop()

print(invertida)
```
**Explicação:** Ao empilhar letra por letra e desempilhar com `pop()`, a ordem LIFO inverte a palavra.

---

### 18. Validar parênteses
**Pergunta / Enunciado:** Verifique se uma expressão possui parênteses balanceados.

**Resposta (Código):**
```python
expressao = "(a + (b * c))"
pilha = []
valida = True

for char in expressao:
    if char == "(":
        pilha.append(char)
    elif char == ")":
        if not pilha:
            valida = False
            break
        pilha.pop()

print("Balanceada:", valida and not pilha)
```
**Explicação:** Cada `)` deve encontrar um `(` correspondente na pilha; ao final, a pilha deve estar vazia.

---

### 19. Converter decimal para binário
**Pergunta / Enunciado:** Converta 13 para binário usando uma pilha de restos.

**Resposta (Código):**
```python
numero = 13
pilha = []

if numero == 0:
    pilha.append("0")

while numero > 0:
    pilha.append(str(numero % 2))
    numero //= 2

binario = ""
while pilha:
    binario += pilha.pop()

print(binario)
```
**Explicação:** Os restos da divisão inteira por 2 são empilhados e depois desempilhados do bit mais significativo ao menos significativo.

---

### 20. Histórico de páginas
**Pergunta / Enunciado:** Simule o botão voltar de um navegador usando uma pilha.

**Resposta (Código):**
```python
historico = []
atual = "Início"

for pagina in ["Cursos", "Python", "Exercícios"]:
    historico.append(atual)
    atual = pagina

print("Atual:", atual)

if historico:
    atual = historico.pop()

print("Após voltar:", atual)
```
**Explicação:** A página atual é salva em `historico` antes de avançar; ao voltar, recupera-se o último estado visitado.

---

### 21. Desfazer uma edição
**Pergunta / Enunciado:** Implemente uma operação simples de desfazer texto.

**Resposta (Código):**
```python
historico = []
texto = "olá"

historico.append(texto)
texto += " mundo"
print("Editado:", texto)

if historico:
    texto = historico.pop()

print("Desfeito:", texto)
```
**Explicação:** O estado anterior do texto é empilhado antes da alteração e restaurado com `pop()`.

---

### 22. Avaliar expressão pós-fixa
**Pergunta / Enunciado:** Calcule a expressão pós-fixa `3 4 + 2 *`.

**Resposta (Código):**
```python
tokens = ["3", "4", "+", "2", "*"]
pilha = []

for token in tokens:
    if token.lstrip("-").isdigit():
        pilha.append(int(token))
    else:
        b = pilha.pop()
        a = pilha.pop()
        if token == "+":
            pilha.append(a + b)
        elif token == "-":
            pilha.append(a - b)
        elif token == "*":
            pilha.append(a * b)
        elif token == "/":
            pilha.append(a / b)

print("Resultado:", pilha.pop())
```
**Explicação:** Números são empilhados; ao encontrar um operador, os dois últimos operandos são desempilhados e combinados na ordem correta (`a` antes de `b`).

---

### 23. Ordenar pilha com pilha auxiliar
**Pergunta / Enunciado:** Ordene uma pilha utilizando outra pilha auxiliar.

**Resposta (Código):**
```python
pilha = [3, 1, 4, 2]
auxiliar = []

while pilha:
    valor = pilha.pop()
    while auxiliar and auxiliar[-1] > valor:
        pilha.append(auxiliar.pop())
    auxiliar.append(valor)

print("Pilha auxiliar:", auxiliar)
```
**Explicação:** Elementos maiores no topo de `auxiliar` retornam temporariamente para `pilha` até encontrar a posição correta de `valor`.

---

### 24. Classe Pilha
**Pergunta / Enunciado:** Crie uma classe com `push`, `pop`, `topo` e `vazia`.

**Resposta (Código):**
```python
class Pilha:
    def __init__(self):
        self.itens = []

    def push(self, item):
        self.itens.append(item)

    def pop(self):
        return self.itens.pop() if self.itens else None

    def topo(self):
        return self.itens[-1] if self.itens else None

    def vazia(self):
        return not self.itens


p = Pilha()
p.push(10)
p.push(20)
print(p.topo(), p.pop(), p.vazia())
```
**Explicação:** A classe encapsula os dados internos e protege contra acessos ou remoções em pilhas vazias.

---

## Filas (25 a 36)

### 25. Enfileirar clientes
**Pergunta / Enunciado:** Cadastre quatro clientes em uma fila.

**Resposta (Código):**
```python
from collections import deque

fila = deque()
for nome in ["Ana", "Beto", "Caio", "Duda"]:
    fila.append(nome)

print(list(fila))
```
**Explicação:** `collections.deque` permite inserções e remoções eficientes nas extremidades.

---

### 26. Atender primeiro cliente
**Pergunta / Enunciado:** Remova o primeiro cliente com `popleft()`.

**Resposta (Código):**
```python
from collections import deque

fila = deque(["Ana", "Beto", "Caio"])

if fila:
    print("Atendido:", fila.popleft())

print("Restantes:", list(fila))
```
**Explicação:** `popleft()` remove do início da fila, respeitando o princípio FIFO (*First In, First Out*).

---

### 27. Consultar frente
**Pergunta / Enunciado:** Mostre o primeiro da fila sem removê-lo.

**Resposta (Código):**
```python
from collections import deque

fila = deque(["Pedido 1", "Pedido 2"])
print("Próximo:", fila[0] if fila else "Vazia")
```
**Explicação:** O índice `0` consulta o próximo item a ser atendido sem retirá-lo da fila.

---

### 28. Verificar fila vazia
**Pergunta / Enunciado:** Crie uma função que identifique filas vazias.

**Resposta (Código):**
```python
from collections import deque


def esta_vazia(fila):
    return len(fila) == 0


print(esta_vazia(deque()))
print(esta_vazia(deque([5])))
```
**Explicação:** Retorna `True` quando o tamanho da fila é igual a zero.

---

### 29. Fila de impressão
**Pergunta / Enunciado:** Simule a impressão de três documentos na ordem de chegada.

**Resposta (Código):**
```python
from collections import deque

fila = deque(["relatorio.pdf", "aula.pdf", "prova.pdf"])

while fila:
    print("Imprimindo:", fila.popleft())
```
**Explicação:** Cada documento sai pela frente com `popleft()` exatamente na ordem em que entrou.

---

### 30. Atendimento com novos clientes
**Pergunta / Enunciado:** Atenda um cliente, inclua outro e atenda o restante.

**Resposta (Código):**
```python
from collections import deque

fila = deque(["Ana", "Beto"])
print("Atendido:", fila.popleft())

fila.append("Caio")

while fila:
    print("Atendido:", fila.popleft())
```
**Explicação:** Novos elementos entram no final (`append`) enquanto o atendimento ocorre sempre pela frente (`popleft`).

---

### 31. Limitar capacidade
**Pergunta / Enunciado:** Implemente uma fila com capacidade máxima de três itens.

**Resposta (Código):**
```python
from collections import deque

fila = deque()
capacidade = 3

for item in [1, 2, 3, 4]:
    if len(fila) < capacidade:
        fila.append(item)
    else:
        print("Fila cheia; recusado:", item)

print(list(fila))
```
**Explicação:** Antes de inserir, verifica-se se `len(fila)` está abaixo do limite máximo definido.

---

### 32. Simular senhas de atendimento
**Pergunta / Enunciado:** Gere cinco senhas e atenda-as em ordem.

**Resposta (Código):**
```python
from collections import deque

fila = deque()

for numero in range(1, 6):
    fila.append(f"A{numero:03d}")

while fila:
    print("Chamando:", fila.popleft())
```
**Explicação:** As senhas são formatadas (`A001` a `A005`), enfileiradas e chamadas na ordem FIFO.

---

### 33. Intercalar duas filas
**Pergunta / Enunciado:** Intercale elementos de duas filas em uma nova fila.

**Resposta (Código):**
```python
from collections import deque

a = deque([1, 3, 5])
b = deque([2, 4, 6])
saida = deque()

while a or b:
    if a:
        saida.append(a.popleft())
    if b:
        saida.append(b.popleft())

print(list(saida))
```
**Explicação:** A cada iteração, se houver elemento em `a` ou `b`, ele é retirado da frente e adicionado a `saida`.

---

### 34. Fila circular com deque
**Pergunta / Enunciado:** Simule rodízio de três processos usando `rotate()`.

**Resposta (Código):**
```python
from collections import deque

fila = deque(["P1", "P2", "P3"])

for _ in range(5):
    atual = fila[0]
    print("Executando:", atual)
    fila.rotate(-1)
```
**Explicação:** `fila.rotate(-1)` desloca o elemento da frente para o final, simulando uma fila circular.

---

### 35. Classe Fila
**Pergunta / Enunciado:** Crie uma classe com `enfileirar`, `desenfileirar` e `frente`.

**Resposta (Código):**
```python
from collections import deque


class Fila:
    def __init__(self):
        self.itens = deque()

    def enfileirar(self, item):
        self.itens.append(item)

    def desenfileirar(self):
        return self.itens.popleft() if self.itens else None

    def frente(self):
        return self.itens[0] if self.itens else None


f = Fila()
f.enfileirar("A")
f.enfileirar("B")
print(f.frente(), f.desenfileirar())
```
**Explicação:** A classe agrupa as operações fundamentais de uma fila FIFO utilizando `deque`.

---

### 36. Escalonamento Round Robin
**Pergunta / Enunciado:** Simule três processos com tempos de CPU e quantum de 2.

**Resposta (Código):**
```python
from collections import deque

fila = deque([("P1", 5), ("P2", 3), ("P3", 2)])
quantum = 2

while fila:
    nome, restante = fila.popleft()
    executado = min(quantum, restante)
    restante -= executado
    print(nome, "executou", executado)
    if restante > 0:
        fila.append((nome, restante))
```
**Explicação:** Cada processo executa por no máximo `quantum` unidades de tempo; se ainda restar tempo, volta ao fim da fila.

---

## Árvore de Processos (37 a 48)

### 37. Representar pai e filhos
**Pergunta / Enunciado:** Represente um processo pai e três processos filhos usando dicionário.

**Resposta (Código):**
```python
arvore = {
    "PID 100": ["PID 101", "PID 102", "PID 103"]
}

for pai, filhos in arvore.items():
    print("Pai:", pai)
    for filho in filhos:
        print("  Filho:", filho)
```
**Explicação:** Cada chave do dicionário representa um processo pai e sua lista associada contém os processos filhos.

---

### 38. Criar nó de árvore
**Pergunta / Enunciado:** Defina uma classe de nó com nome e lista de filhos.

**Resposta (Código):**
```python
class No:
    def __init__(self, nome):
        self.nome = nome
        self.filhos = []


raiz = No("P100")
raiz.filhos.append(No("P101"))
raiz.filhos.append(No("P102"))

print(raiz.nome, [f.nome for f in raiz.filhos])
```
**Explicação:** Cada instância de `No` guarda seu identificador (`nome`) e referências aos nós filhos em `self.filhos`.

---

### 39. Adicionar processos filhos
**Pergunta / Enunciado:** Crie uma função para adicionar um filho a um nó.

**Resposta (Código):**
```python
class No:
    def __init__(self, nome):
        self.nome = nome
        self.filhos = []


def adicionar(pai, nome):
    filho = No(nome)
    pai.filhos.append(filho)
    return filho


raiz = No("P100")
adicionar(raiz, "P101")
print([n.nome for n in raiz.filhos])
```
**Explicação:** A função instancia o novo `No`, anexa à lista de filhos do `pai` e retorna a referência criada.

---

### 40. Percurso em profundidade
**Pergunta / Enunciado:** Percorra uma árvore de processos em pré-ordem (DFS).

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def dfs(no):
    print(no)
    for filho in arvore.get(no, []):
        dfs(filho)


dfs("P1")
```
**Explicação:** Na busca em profundidade pré-ordem (*DFS*), o nó atual é visitado antes de percorrer recursivamente cada filho.

---

### 41. Percurso em largura
**Pergunta / Enunciado:** Percorra a árvore por níveis usando uma fila (BFS).

**Resposta (Código):**
```python
from collections import deque

arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}

fila = deque(["P1"])

while fila:
    no = fila.popleft()
    print(no)
    fila.extend(arvore.get(no, []))
```
**Explicação:** A busca em largura (*BFS*) usa uma fila para explorar todos os nós de um nível antes de avançar ao próximo.

---

### 42. Contar processos
**Pergunta / Enunciado:** Conte todos os processos existentes em uma árvore.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def contar(no):
    return 1 + sum(contar(f) for f in arvore.get(no, []))


print("Total:", contar("P1"))
```
**Explicação:** Soma `1` (o próprio nó) com a quantidade total de processos em cada subárvore filha.

---

### 43. Calcular altura
**Pergunta / Enunciado:** Determine a altura de uma árvore em número de arestas.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def altura(no):
    filhos = arvore.get(no, [])
    if not filhos:
        return 0
    return 1 + max(altura(f) for f in filhos)


print("Altura:", altura("P1"))
```
**Explicação:** Um nó folha tem altura `0`; cada nível superior adiciona `1` à maior altura entre seus filhos.

---

### 44. Encontrar processo
**Pergunta / Enunciado:** Verifique recursivamente se um PID está na árvore.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def existe(no, alvo):
    if no == alvo:
        return True
    return any(existe(f, alvo) for f in arvore.get(no, []))


print(existe("P1", "P4"))
```
**Explicação:** Compara o nó atual com `alvo` e, se não for igual, verifica recursivamente se algum filho contém o processo.

---

### 45. Listar processos folha
**Pergunta / Enunciado:** Mostre processos sem filhos.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def folhas(no):
    filhos = arvore.get(no, [])
    if not filhos:
        print(no)
    for filho in filhos:
        folhas(filho)


folhas("P1")
```
**Explicação:** Processos folha não possuem descendentes diretos (`not filhos`).

---

### 46. Caminho até um processo
**Pergunta / Enunciado:** Encontre o caminho da raiz até um PID.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def caminho(no, alvo):
    if no == alvo:
        return [no]
    for filho in arvore.get(no, []):
        resultado = caminho(filho, alvo)
        if resultado is not None:
            return [no] + resultado
    return None


print(caminho("P1", "P4"))
```
**Explicação:** Quando o alvo é encontrado, cada chamada recursiva prefixa seu próprio nó (`[no] + resultado`) até reconstruir o caminho da raiz.

---

### 47. Contar descendentes
**Pergunta / Enunciado:** Calcule quantos descendentes possui um processo.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def descendentes(no):
    return sum(1 + descendentes(f) for f in arvore.get(no, []))


print("Descendentes de P1:", descendentes("P1"))
```
**Explicação:** Conta todos os filhos, netos e demais descendentes de `no`, sem incluir o próprio `no`.

---

### 48. Encerrar uma subárvore simulada
**Pergunta / Enunciado:** Remova um processo e seus descendentes de uma representação em memória.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}


def remover_subarvore(no):
    for filho in arvore.get(no, [])[:]:
        remover_subarvore(filho)
    arvore.pop(no, None)


if "P2" in arvore.get("P1", []):
    arvore["P1"].remove("P2")

remover_subarvore("P2")
print(arvore)
```
**Explicação:** Remove a referência de `"P2"` da lista de filhos de `"P1"` e apaga recursivamente `"P2"` e seus descendentes do dicionário.

---

## Integração (49 a 50)

### 49. DFS iterativa com pilha
**Pergunta / Enunciado:** Percorra uma árvore de processos em profundidade sem recursão.

**Resposta (Código):**
```python
arvore = {
    "P1": ["P2", "P3"],
    "P2": ["P4"],
    "P3": [],
    "P4": [],
}

pilha = ["P1"]

while pilha:
    no = pilha.pop()
    print(no)
    pilha.extend(reversed(arvore.get(no, [])))
```
**Explicação:** Empilhar os filhos em ordem reversa (`reversed`) faz com que o primeiro filho fique no topo da pilha LIFO e seja visitado primeiro.

---

### 50. Gerenciador didático de tarefas
**Pergunta / Enunciado:** Implemente tarefas pendentes em fila, histórico em pilha e registros em lista.

**Resposta (Código):**
```python
from collections import deque

pendentes = deque(["Compilar", "Testar", "Publicar"])
historico = []
concluidas = []

while pendentes:
    tarefa = pendentes.popleft()
    print("Executando:", tarefa)
    historico.append(tarefa)
    concluidas.append(tarefa)

print("Concluídas:", concluidas)
if historico:
    print("Última execução:", historico[-1])
```
**Explicação:** Integra três estruturas: `pendentes` (fila FIFO) ordena a execução, `historico` (pilha LIFO) guarda a execução mais recente no topo e `concluidas` (lista) registra os itens concluídos.

---

## Referências Bibliográficas

- CORMEN, Thomas H. et al. *Introduction to Algorithms*. 4. ed. MIT Press, 2022.
- GOODRICH, Michael T.; TAMASSIA, Roberto; GOLDWASSER, Michael H. *Data Structures and Algorithms in Python*. Wiley, 2013.
- DOWNEY, Allen B. *Think Python: How to Think Like a Computer Scientist*. 3. ed. O'Reilly Media, 2024.
- PYTHON SOFTWARE FOUNDATION. *Python 3 Documentation*. Disponível em: <https://docs.python.org/3/>.
- PYTHON SOFTWARE FOUNDATION. *collections — Container datatypes*. Disponível em: <https://docs.python.org/3/library/collections.html>.
- TANENBAUM, Andrew S.; BOS, Herbert. *Modern Operating Systems*. 4. ed. Pearson, 2014.