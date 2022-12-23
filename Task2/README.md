# Hyperparameter Tuning - Weights & Biases's Sweep

Para a tarefa 2, foi requisitado que, partindo-se do modelo LeNet-5[1], fosse utilizada o **MNIST**[2] - mesma base originalmente usada no LeNet-5 - para realizar o ajuste de hiperparâmetros. Essa tarefa deveria ser realizada com a plataforma **Weights and Biases**[3], wandb, utilizando o *sweep*. O *sweep* é uma ferramenta interna que permite varrer valores pré-setados (pelo usuário), a fim de achar a melhor combinação possível de parâmetros para uma rede. Assim, economizando tempo e aumentando-se as chances de uma boa configuração. A partir dessas varreduras são, então, gerados *dashboards* com resultados para cada configuração, permitindo uma série de iterações e aprofundamentos sobre os dados e o que fora realizado.

Em assim sendo, partiu-se da arquitetura:
![LeNet5 - Imagem retirada de https://github.com/ivanovitchm/embedded.ai](https://drive.google.com/uc?export=view&id=1nqbLzHfqorX80I8upHMWINwPNfrmLW-V)

## Sweep
O sweep levou em consideração as seguintes configurações:

```
1. método para sweep: 'bayes' 
# "método", aqui, leva em consideração o tipo de varredura a ser feito. O "bayes" usa um processo gaussiano para modelar as relações entre parâmetros e a métrica escolhida.
2. métricas:
 - nome: 'val_loss',
 # métrica tomada como objetivo: nesse caso, o objetivo é a minimização da perda da validação.
 - objetivo: 'minimize'
3. parâmetros:
 - camada de batch: [True, False]
 - camada de dropout: [True, False]
 - valores para o dropout (caso exista): [0.3, 0.4, 0.5]
 - tamanho do batch: [16, 32, 64]
 - funções de ativação: ['tanh', 'relu']
 - otimizadores: ['adam', 'sgd']
 - quantidade de épocas: [5, 10, 15]
 - taxa de aprendizado {'max': 0.1, 'min': 0.0001}
```

## Resultados

Diversos *sweeps* foram realizados durante o período de teste da ferramenta, porém selecionou-se os últimos 20 para ilustrar o comportamento, conforme gráficos que se seguem.
![image](https://user-images.githubusercontent.com/37004361/209260354-ef96fcd6-e4b8-4417-a8fc-9ab80894b8a6.png)

![Acurácia por época](https://user-images.githubusercontent.com/37004361/209259633-d9b65dbf-9fd1-49bf-8cbb-f383aaf4e7e5.png)

O mais interessante do experimento foi a percepção de que há formas diversas, quando o assunto é parâmetro, para se atingir bons resultados e que o resultado pode não vir de onde se espera, mas do conjunto de fatores ou de fatores inexplorados, mas que estão mantendo uma média inicial alta.
![Correlação parâmetros e acurácia](https://user-images.githubusercontent.com/37004361/209259196-2417e0b0-c02b-4b1e-9f57-16a617ad28c8.png)



## Referências

[1] LECUN, Yann et al. **Gradient-based learning applied to document recognition**. Proceedings of the IEEE, v. 86, n. 11, p. 2278-2324, 1998.

[2] https://www.tensorflow.org/datasets/catalog/mnist

[3] https://docs.wandb.ai/guides/sweeps

[4] https://github.com/ivanovitchm/embedded.ai - Os códigos e comentários iniciais do notebook baseiam-se no material do professor da disciplina.
