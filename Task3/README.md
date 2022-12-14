"Is this Santa?"

O presente diretório é objeto de uma tarefa da matéria de Inteligência Artificial Embarcada, da Universidade Federal do Rio Grande do Norte (UFRN). Ele se divide, tal qual a tarefa, em 2 notebooks: um para a prática com o modelo base sendo o VGG-16 e, outro, para a prática com o modelo base sendo o Xception. O dataset utilizado está disponível no Kaggle, sob o título "Is this Santa?", https://www.kaggle.com/datasets/deepcontractor/is-that-santa-image-classification. Assinalo que parte do código foi utilizado conforme o código demonstrado em sala de aula, sendo de autoria do professor Ivanovitch Silva, https://github.com/ivanovitchm/embedded.ai/blob/main/lessons/week_10/TransferLearning.ipynb. O notebook de embasamento também vai estar referenciado.

Apesar de não serem novidades no meio acadêmico, a popularização de técnicas de fine-tuning ainda está curso. Essa técnica permite a reutilização de modelos (camadas e parâmetros) já treinados, ainda que o objetivo daquele modelo seja completamento mudado e outras bases sejam utilizadas. Esses modelos pré-treinados, como são chamados, precisam ter sido treinados em bases enormes - e, preferencialmente, precisam ter se saído bem em suas respectivas tarefas. Assim, tendo-os em mãos, é possível exportar esse desempenho para outras tarefas, ainda que similares às iniciais, com outras bases. Fica nítido, assim, que o lado positivo dessa técnica é que ela permite a economia de tempo e de custos, tanto por não ser imperativo o uso de datasets gigantes quanto por não serem necessárias máquinas tão potentes para esse fim.

O artigo completo para esta tarefa pode ser encontrado em:
https://medium.com/@lariskelmer/is-this-santa-c1a13980df40

Uma breve apresentação também foi feita em forma de vídeo e pode ser encontrada em:
https://www.loom.com/share/72d2832e79324b8cb9aec9295b4b66a8
