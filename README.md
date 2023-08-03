# LoadingViewingSavingImages
**Documentação do Projeto OpenCV - Carregando e Manipulando Imagens**

Este projeto tem como objetivo demonstrar como carregar e manipular imagens utilizando o OpenCV em Python. O OpenCV (Open Source Computer Vision Library) é uma biblioteca de código aberto desenvolvida para visão computacional e processamento de imagens.

## Importando os pacotes necessários

Antes de começar, vamos importar os pacotes necessários:

```python
import cv2
import matplotlib.pyplot as plt
```

Certifique-se de ter o OpenCV e o Matplotlib instalados em seu ambiente. Você pode instalar o OpenCV com o comando `pip install opencv-python`.

## Carregando Imagens com OpenCV

A função utilizada para carregar imagens do disco é `cv2.imread(filename[, flags])`. Vamos carregar uma imagem em tons de cinza chamada "c_cinza.png":

```python
letra_c = cv2.imread("c_cinza.png", cv2.IMREAD_GRAYSCALE)
```

A função `cv2.imread()` carrega a imagem especificada do disco para a memória. No nosso caso, a imagem é armazenada como um objeto NumPy multidimensional.

## Propriedades da Imagem

Vamos explorar algumas propriedades da imagem carregada:

```python
print("Tipo (pixels): {}\n".format(letra_c.dtype))
print("Tipo (objeto): {}\n".format(type(letra_c.dtype)))
print("Dimensões: {}\n".format(letra_c.shape))
```

Essas informações nos darão o tipo de dados dos pixels (uint8 no caso da imagem em tons de cinza), o tipo de objeto (numpy.ndarray) e as dimensões da imagem (15x15 pixels).

## Visualizando Imagens

Para visualizar imagens em um notebook Jupyter, usaremos o Matplotlib, pois a função `cv2.imshow()` do OpenCV pode causar problemas no ambiente do Jupyter.

```python
# Exibir a imagem com matplotlib
plt.imshow(letra_c, cmap='gray');
```

O parâmetro `cmap='gray'` é usado para garantir que a imagem seja exibida em tons de cinza.

## Manipulando Pixels

Vamos agora manipular os pixels da imagem. Podemos acessar e modificar pixels simplesmente indexando a matriz da imagem:

```python
# Acessando o pixel na primeira linha e terceira coluna
print(letra_c[0, 2])

# Modificando o pixel na primeira linha e terceira coluna
letra_c[0, 2] = 0
print(letra_c[0, 2])
```

## Região de Interesse (ROI)

Vamos também explorar o conceito de Região de Interesse (ROI). Podemos definir uma ROI usando a indexação de matrizes:

```python
# Definindo uma ROI
roi = letra_c[0:10, 0:5]
```

## Salvando Imagens com OpenCV

Por fim, vamos salvar a imagem manipulada em um novo arquivo:

```python
cv2.imwrite('c_cinza_roi.png', roi)
```

O método `cv2.imwrite()` é utilizado para salvar a imagem da memória para o disco.

Esse projeto demonstra as etapas básicas para carregar, visualizar, manipular e salvar imagens usando o OpenCV em Python. Existem muitas outras funcionalidades poderosas no OpenCV para processamento de imagens e visão computacional, e você pode explorá-las consultando a documentação oficial do OpenCV.
