# Capítulo 1

## Errors
**absolute**  
\\(|u-v|\\)  

**relative**  
\\(\frac{|u-v|}{|v|}\\)  
  
Relativo
é mais relevante quando \\(|u| > 1\\)

  
## Tipos de erro

1. Erro no modelo
2. Erro de aproximação
	- Erro de discretização

		Decorrente de discretização, como interpolação, diferenciação ou integração.

	- Erro de convergência

		Em métidos iterativos, o resultado convengiria depois de um número finitos de iteração, porém como paramos o processo após um número finito de iterações. Algum erro decorre disso.

3. Erro de arredondamento
	
	Decorrente da representação finita.


## Critério de avaliação de um algorítmo

- **Acurácia**
- **Eficiência**
- **Robustez**
	
	Capacidade de devolver um resultado dentro de uma margem tolerável de erro. Ou falhar graciosamente.


## Condicionamento e estabilidade

Um problema é mal condicionado se pequenas pertubações nos dados causam uma grande diferença no resultado.

Um algoritmo estável devolve uma solução numérica que é a solução exata para um problema levemente perturbado em relação ao original.


# Capítulo 3

## Equações não lineares de uma variável

**Objetivo**: encontrar a solução para equações escalares, não lineares \\(f(x)=0\\)

## Resolvendo equações não lineares

Para \\(f(x)=0\\), assumiremos que f é *contínua* em um determinado intervalos. Denominamos \\(f \in C[a,b]\\). A solução (ou raiz) dessa equação será denominada \\(x^*\\)

## Métodos iterativos para encontrar as raizes

É raro encontrar fórmulas fechadas para o cálculo de raízes de uma equação, por isso os chamados *métodos iterativos* são utilizados. À partir de um valor inicial \\(x_0\\), o método gera uma sequência de iterados \\(x_1\\), \\(x_2\\),...,\\(x_k\\),... que (se tudo funcionar bem) converge para a raiz da função dada.

## Parando um precedimento iterativo

Não se pode esperar que o procedimento iterativo produza a exatamente solução \\(x^\*\\). Podemos concluir que a serie de iterados converge se os valores de \\(|f(x_k)|\\) e/ou de \\(|x_k-x_{k-1}|\\) decrescem suficientemente em direção a 0, conforme o contador *k* aumenta.

## Propriedades desejadas de algorítmos buscadores de raiz.

- **Eficiente**: Exige um pequeno número de avaliações da função.
- **Robusto**: Falha raramente. Avisa quando falha.
- Exige uma quantidade mínima de dados adicionais (ex. derivada da função).
- Facilmente generalizável para várias equações em várias incógnitas.

## Método da bisseção

Simples e seguro. Exige poucas suposições em relação a \\(f(x)\\). É lento e difícil de generalizar para maiores dimensões.

1. Suponha que para dada \\(f(x)\\), seja conhecido um intervalo \\([a,b]\\) na qual f muda de sinal (\\(f(a) * f(b) < 0\\)).
2. Calcule \\(f(p)\\), onde \\(p=\frac{a+b}{2}\\)
3. Verifique o sinal de \\(f(a) \* f(p)\\).
4. Se negativo, a raiz está em \\([a,p]\\). Faça \\(\mathbf{b \leftarrow p}\\)
5. Se positivo, a raiz está em \\([p, b]\\). Faça \\(\mathbf{a \leftarrow p}\\)
6. Repita \\(n = [\log_2{\frac{b-a}{2\*atol}}]\\) vezes, para que o erro absoluto seja menor que *atol*.