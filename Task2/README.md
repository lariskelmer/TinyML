# Hyperparameter Tuning - Weights & Biases's Sweep

Para a tarefa 2, foi requisitado que, partindo-se do modelo LeNet-5[1], fosse utilizada o **MNIST**[2] - mesma base originalmente usada no LeNet-5 - para realizar o ajuste de hiperparâmetros. Essa tarefa deveria ser realizada com a plataforma **Weights and Biases**[3], wandb, utilizando o *sweep*. O *sweep* é uma ferramenta interna que permite varrer valores pré-setados (pelo usuário), a fim de achar a melhor combinação possível de parâmetros para uma rede. Assim, economizando tempo e aumentando-se as chances de uma boa configuração. A partir dessas varreduras são, então, gerados *dashboards* com resultados para cada configuração, permitindo uma série de iterações e aprofundamentos sobre os dados e o que fora realizado.

Em assim sendo, partiu-se da arquitetura:
![LeNet5 - Imagem retirada de https://github.com/ivanovitchm/embedded.ai](https://drive.google.com/uc?export=view&id=1nqbLzHfqorX80I8upHMWINwPNfrmLW-V)

## Sweep
O sweep levou em consideração as seguintes configurações:

```
1. método para sweep: 'bayes' 
# o método "bayes"
2. métricas:
 - nome: 'val_loss',
 # 
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

![image](https://user-images.githubusercontent.com/37004361/209260354-ef96fcd6-e4b8-4417-a8fc-9ab80894b8a6.png)


![Acurácia por época](https://user-images.githubusercontent.com/37004361/209259633-d9b65dbf-9fd1-49bf-8cbb-f383aaf4e7e5.png)

![Parâmetros e acurácia final](https://user-images.githubusercontent.com/37004361/209259845-7fa05657-b321-4ed6-94ac-ea818bebbb1c.png)


![Correlação parâmetros e acurácia](https://user-images.githubusercontent.com/37004361/209259196-2417e0b0-c02b-4b1e-9f57-16a617ad28c8.png)



## Referências

[1] LECUN, Yann et al. **Gradient-based learning applied to document recognition**. Proceedings of the IEEE, v. 86, n. 11, p. 2278-2324, 1998.

[2] https://www.tensorflow.org/datasets/catalog/mnist

[3] https://docs.wandb.ai/guides/sweeps
