# Minha participação

Projeto desenvolvido em equipe como Trabalho de Conclusão de Curso. Leia o trabalho completo em:
👉 docs/TCC.pdf

Principais contribuições:
- fluxograma analítica do escopo
- diagrama de processo do treinamento do modelo e interpolação
- testes e validação do modelo

# SCAN
Spatial Channel Attention Network 

SCAN é um modelo de interpolação de frames que utiliza canais de atenção em conjunto com atenção espacial para interpolar frames.


# DEMOS

24 -> 48 fps

https://github.com/user-attachments/assets/81806a65-13b4-4443-a70c-754579dc7771

30 -> 60 fps



https://github.com/user-attachments/assets/e0808c1c-f5f2-45a8-ac8e-44366538f6ae

# INSTRUÇÕES

### DEPENDÊNCIAS

Este projeto utiliza o FFmpeg para processamento de vídeo e áudio.
Baixe o FFmpeg em:
👉 https://www.gyan.dev/ffmpeg/builds/
Para certificá-lo que o mesmo está funcionando, pode-se usar o comando
```ffmpeg -version```

Para rodar o programa será necessário intalar as bibliotecas de requirements.txt utilizando

```pip install -r requirements.txt```

Como também instalar a biblioteca do torchvision com suporte ao CUDA encontrada no site do pytorch https://pytorch.org/get-started/locally/ ou rodar o seguinte código para instalar a bilbioteca

```pip3 install torch torchvision --index-url https://download.pytorch.org/whl/cu128```

AVISO

CUDA é uma plataforma de computação paralela da NVIDIA, se a sua máquina não houver uma placa gráfica correspondente, o código anterior não irá rodar.
Ainda é possível instalar a biblioteca do torchvision e utilizar a CPU como motor gráfico com os seguinte comandos

```
pip install torch
pip install torchvission
```

Porém isto levará a uma severa perda de poder computacional, resultando numa demora mais prolongada do programa rodar.

Por fim, resta apenas instalar o modelo de interpolação encontrado no seguinte link: [Google Drive](https://drive.google.com/file/d/172T2bWhCSaQkn2BsEYUF7GPtOOn1MYNb/view?usp=sharing) 

### RODANDO O CÓDIGO

No mesmo diretório do projeto rode o código para inicializar a interface

```python interface.py```

A seguinte interface deve aparecer na tela

<img width="798" height="627" alt="Janela de configuração de alta fidelidade" src="https://github.com/user-attachments/assets/070d0add-c640-4e95-822e-e02a1a8c1fab" />

No campo "Modelo", clique e selecione o caminho do .pth instalado préviamente pelo Google Drive, ou arraste o .pth direto de seu computador.

No campo "Vídeo de Entrada", clique e selecione o caminho do vídeo que deseja fazer a interpolação de frames. Assim que selecionar o vídeo, as informações de resolução e FPS do vídeo serão sinalizadas logo abaixo

Selecione então a Taxa de Interpolação que deseja, por exemplo, uma taxa de interpolação 2 duplicará o número de quadros entre os quadros originais.

No campo "Diretório de Saída", clique e selecione aonde deseja salvar o novo vídeo que sera interpolado com base no fornecido préviamente. Se desejar, a resolução de saída do vídeo pode ser alterada informando no campo logo abaixo deste mesmo.

Por fim, clique em "Interpolar", e assim a barra de progresso da interpolação irá aparecer informando seu progresso. Assim que o progresso terminar, a interface abrirá uma nova aba com o resultado da interpolação da seguinte maneira.

<img width="798" height="627" alt="Tela_apuracao" src="https://github.com/user-attachments/assets/7ac0129d-63c4-4fc1-b875-f54772a98210" />

O qual nesta nova aba de apuração, é possível fazer a comparação direta do vídeo original (À esquerda) com o vídeo interpolado (À direita) controlando ambos ao mesmo tempo de forma sincronizada.
