# SCAN
(Spatial Channel Attention Network) é um modelo de interpolação de frames baseado em redes neurais convolucionais, capaz de aumentar a taxa de quadros de vídeos preservando a qualidade visual.

O projeto foi desenvolvido como Trabalho de Conclusão de Curso (TCC) e integra técnicas modernas de visão computacional, deep learning e processamento de vídeo.

📄 **TCC completo:** `docs/TCC.pdf`

---

##  Demonstração

### 24 → 48 FPS
Vídeo original comparado com o interpolado lado a lado:

https://github.com/user-attachments/assets/81806a65-13b4-4443-a70c-754579dc7771


### 30 → 60 FPS
Outro exemplo de interpolação:

https://github.com/user-attachments/assets/e0808c1c-f5f2-45a8-ac8e-44366538f6ae


## O que o projeto faz

- Interpolação de frames (ex: 24 → 48 FPS, 30 → 60 FPS)
- Interface gráfica para facilitar o uso
- Comparação sincronizada entre vídeo original e interpolado


## Arquitetura e técnicas utilizadas

O modelo SCAN utiliza:

- Spatial Attention + Channel Attention
- Perceptual Loss
- SSIM (Structural Similarity Index)
- Charbonnier Loss 
- PyTorch (framework de Deep Learning)
- Skip connection
- Pixel Shuffle
- Pipeline completo de treino e validação

---

## ⚙️ Instalação


### 1. Clonar o repositório

```bash
git clone <seu-repositorio>
cd SCAN-dev
```
Ou se não tiver familiaridade com o git, pode apenas baixar o .zip do projeto



### 2. Criar ambiente virtual

```bash
python -m venv venv
```

#### Ativar no Windows (PowerShell):

```powershell
.\venv\Scripts\Activate
```


### 3. Instalar dependências

```bash
pip install -r requirements.txt
```


### 4. Instalar PyTorch

#### 🟢 GPU (CUDA - recomendado)

Instale conforme seu sistema operacional:  
https://pytorch.org/get-started/locally/

Exemplo para Windows:

```bash
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu128
```

CUDA é uma plataforma de computação paralela exclusiva da NVIDIA, se sua máquina não possuir uma placa de vídeo correspondente, opte por


#### 🟡 CPU (sem GPU)

```bash
pip install torch torchvision
```

⚠️ O uso de CPU reduz significativamente o desempenho.

---

## Dependência externa: FFmpeg

Este projeto utiliza o FFmpeg para processamento de vídeo e áudio.

### Instalação

Baixe o ffmpeg-git-full.7z:  
👉 https://www.gyan.dev/ffmpeg/builds/

Após baixar:

1. Crie um nova pasta chamada "ffmpeg" no cd local
2. Extraia o arquivo `.zip`
3. armazene o conteudo da pasta \bin encontrada no arquivo extraído, na nova pasta criada
4. acesse a partir do barra de pesquisa de seu computador o ambiente "Editar as variáveis de ambiente para sua conta"
5. nas variáveis de usuário, acesse a variável "Path"
6. clique no botão "Novo", e cole o caminho da pasta "ffmpeg", então aperte "OK"

### Verificação
Caso tenha sido devidamente instalado e reconhecido pele sistema, o seguinte comando mostrará a versão instalada do ffmpeg

```bash
ffmpeg -version
```

### Download do modelo

Baixe o modelo treinado (.pth):

👉 [Google Drive](https://drive.google.com/file/d/1LymsoEl4TCanVm3ke_Wvo1ZWM7RkF_NX/view?usp=drive_link)

---

## Como rodar o projeto

Execute o seguinte comando no diretório do projeto:

```bash
python interface.py
```


### Interface

### Tela principal (Configurações)

<img src="https://github.com/user-attachments/assets/070d0add-c640-4e95-822e-e02a1a8c1fab" width="600"/>


### Tela de comparação (Apuração)

<img src="https://github.com/user-attachments/assets/7ac0129d-63c4-4fc1-b875-f54772a98210" width="600"/>


##  Como usar

1. Selecione o modelo `.pth`
2. Escolha o vídeo de entrada
3. Defina a taxa de interpolação (ex: 2)
4. Escolha o diretório de saída
5. Clique em **Interpolar**

Após o processamento:

- O vídeo interpolado será gerado
- A interface exibirá comparação lado a lado
- Reprodução sincronizada entre original e resultado

---

## ⚠️ Problemas comuns

### ❌ FFmpeg não encontrado

Isso resulta no vídeo final ficar sem áudio, como na interface de apuração de comparação lado a lado fechar instantaneamente

- Certifique-se de que o FFmpeg está instalado corretamente


### ❌ Execução lenta

- Verifique ao rodar o programa, se no "[INFO]:" informa "CUDA" ou "CPU"
- se estiver CPU, o programa não está utilizando a bilbioteca do torchvision com suporte ao CUDA
- CPU pode ser significativamente mais lenta

---

## 👨‍💻 Minha contribuição

Projeto desenvolvido em equipe como Trabalho de Conclusão de Curso.

Principais contribuições:

- Desenvolvimento de fluxograma analítico do escopo
- Modelagem do pipeline de treinamento e interpolação
- Testes e validação do modelo

---

## 📌 Tecnologias utilizadas

- Python
- PyTorch
- OpenCV
- FFmpeg
- Tkinter (interface gráfica)

---

## 📄 Licença

Este projeto foi desenvolvido para fins acadêmicos.
