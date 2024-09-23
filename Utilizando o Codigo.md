
### Passo a Passo para Usar o Código no Google Colab

1. **Acesse o Google Colab**
   - Vá para [Google Colab](https://colab.research.google.com/).

2. **Criar um Novo Notebook**
   - Clique em "File" (Arquivo) > "New Notebook" (Novo Notebook).

3. **Instalar Dependências**
   - Execute o seguinte comando em uma célula para instalar o Pillow (caso ainda não esteja instalado):

   ```python
   !pip install pillow
   ```

4. **Carregar o Modelo e os Arquivos Necessários**
   - Faça o upload do seu modelo Keras (`keras_Model.h5`) e do arquivo de rótulos (`labels.txt`). Use o seguinte código:

   ```python
   from google.colab import files

   uploaded = files.upload()
   ```

   - Após executar isso, uma janela será aberta para você escolher os arquivos do seu computador.

5. **Código para Prever a Classe da Imagem**
   - Agora, você pode copiar e colar o seguinte código, ajustando o caminho da imagem para o que você deseja testar:

   ```python
   from keras.models import load_model
   from PIL import Image, ImageOps
   import numpy as np

   # Desativar notação científica para clareza
   np.set_printoptions(suppress=True)

   # Carregar o modelo
   model = load_model("keras_Model.h5", compile=False)

   # Carregar os rótulos
   class_names = open("labels.txt", "r").readlines()

   # Criar o array da forma correta para alimentar o modelo Keras
   data = np.ndarray(shape=(1, 224, 224, 3), dtype=np.float32)

   # Caminho para a imagem que você deseja classificar
   image_path = "<IMAGE_PATH>"  # Substitua pelo caminho da sua imagem
   image = Image.open(image_path).convert("RGB")

   # Redimensionar a imagem para 224x224
   size = (224, 224)
   image = ImageOps.fit(image, size, Image.Resampling.LANCZOS)

   # Transformar a imagem em um array numpy
   image_array = np.asarray(image)

   # Normalizar a imagem
   normalized_image_array = (image_array.astype(np.float32) / 127.5) - 1

   # Carregar a imagem no array
   data[0] = normalized_image_array

   # Prever a classe
   prediction = model.predict(data)
   index = np.argmax(prediction)
   class_name = class_names[index].strip()
   confidence_score = prediction[0][index]

   # Imprimir a previsão e o escore de confiança
   print("Class:", class_name, "| Confidence Score:", confidence_score)
   ```

6. **Executar o Código**
   - Certifique-se de que a imagem está no mesmo diretório ou forneça o caminho correto. Em seguida, execute a célula.

7. **Analisar os Resultados**
   - O resultado da previsão e o escore de confiança serão exibidos na saída da célula.

### Observações
- Você pode usar `files.upload()` para carregar múltiplos arquivos de uma vez, incluindo suas imagens.
- Para garantir que o código funcione corretamente, verifique se a imagem que você está usando é compatível com o modelo (tamanho e tipo).
