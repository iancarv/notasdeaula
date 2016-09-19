# Capítulo 1

## Errors
**absolute**  
\\(|u-v|\\)  

**relative**  
\\(\frac{|u-v|}{|v|}\\)  
  
Relativo é mais relevante quando \\(u > 1\\)

  
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