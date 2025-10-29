# 🎬 Conversor 3D - Spatial Video para SBS

Script em Shell para macOS que converte vídeos espaciais (Spatial Video) gravados em iPhone 15 Pro/Pro Max ou superiores para o formato 3D Side-by-Side (SBS), compatível com TV 3D, headsets de VR como Meta Quest, Google Cardboard e outros visualizadores 3D.

## 📋 Requisitos

- macOS (testado em Ventura e Sonoma)
- FFmpeg 7.1 ou superior
- Homebrew (para instalação do FFmpeg)
- iPhone com suporte a Spatial Video (iPhone 15 Pro, iPhone 15 Pro Max ou superior)

## 🚀 Instalação

### Passo 1: Instalar o Homebrew

Se você ainda não tem o Homebrew instalado, execute no Terminal:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Passo 2: Instalar o FFmpeg

```
brew install ffmpeg
```

Verifique se a instalação foi bem-sucedida:

```
ffmpeg -version
```

> **Importante:** Certifique-se de que a versão do FFmpeg seja 7.1 ou superior para suporte ao formato MV-HEVC.

### Passo 3: Baixar e instalar o script

#### Opção A: Download direto

```
curl -o ~/conversor3d https://raw.githubusercontent.com/jfcardososantos/spatial2sbs/main/conversor3d
chmod +x ~/conversor3d
sudo mv ~/conversor3d /usr/local/bin/
```

#### Opção B: Clonar o repositório

```
git clone https://github.com/jfcardososantos/spatial2sbs.git
cd spatial2sbs
chmod +x conversor3d
sudo mv conversor3d /usr/local/bin/
```

## 💻 Como usar

### Uso básico

1. Abra o Terminal (você pode encontrá-lo em Aplicativos > Utilitários > Terminal)

2. Digite o comando:
```
conversor3d
```

3. Quando solicitado, **arraste o arquivo de vídeo espacial** da pasta do Finder diretamente para a janela do Terminal

4. Pressione **ENTER** e aguarde o processo de conversão

5. O vídeo convertido será salvo na mesma pasta do arquivo original com o sufixo `_SBS.mp4`

### Exemplo visual

```
====================================
  CONVERSOR 3D - SPATIAL VIDEO → SBS
====================================

Arraste o arquivo de vídeo espacial para esta janela e pressione ENTER:
/Users/seu-usuario/Videos/meu-video-espacial.mov

📁 Arquivo de entrada: meu-video-espacial.mov
📂 Pasta de saída: /Users/seu-usuario/Videos

⏳ Iniciando conversão...

🎬 [1/3] Extraindo view esquerda...
🎬 [2/3] Extraindo view direita...
🎬 [3/3] Combinando em formato SBS e adicionando áudio...

====================================
✅ CONVERSÃO CONCLUÍDA COM SUCESSO!
====================================

📹 Arquivo de saída: meu-video-espacial_SBS.mp4
📂 Local: /Users/seu-usuario/Videos
```

## 🎥 Como gravar vídeos espaciais no iPhone

1. Abra o app **Câmera** no seu iPhone 15 Pro/Pro Max
2. Deslize para o modo **Espacial**
3. Segure o iPhone na **horizontal**
4. Toque no ícone de **Spatial Video** (No canto superior direito)
5. Pressione o botão de gravação

## 👓 Como assistir os vídeos convertidos

Após a conversão, você pode assistir seus vídeos 3D SBS em:

- **Projetor**: Usando projetores (datashow) com suporte a 3D SBS.
- **Meta Quest / Quest 2 / Quest 3**: Usando apps como Bigscreen, DeoVR ou Oculus TV
- **Google Cardboard / Visualizadores VR para smartphone**: Usando apps como VR Player ou Cardboard
- **Computador**: Usando players com suporte a 3D SBS como VLC ou PotPlayer

## ⚙️ Especificações técnicas

O script executa três etapas principais:

1. **Extração da view esquerda**: Extrai o canal do olho esquerdo do vídeo MV-HEVC
2. **Extração da view direita**: Extrai o canal do olho direito do vídeo MV-HEVC
3. **Combinação SBS**: Une ambos os canais lado a lado e reinsere o áudio original

### Configurações de codificação

- **Codec de vídeo**: H.264 (libx264)
- **Preset**: Medium (balanceado entre qualidade e velocidade)
- **CRF**: 18 (qualidade muito alta)
- **Codec de áudio**: AAC
- **Bitrate de áudio**: 192 kbps

## 🐛 Solução de problemas

### Erro: "comando não encontrado"

Certifique-se de que o script está no PATH. Execute:

```
echo $PATH
```

Se `/usr/local/bin` não estiver listado, adicione ao seu `~/.zshrc`:

```
export PATH="/usr/local/bin:$PATH"
```

### Erro: "ffmpeg: comando não encontrado"

O FFmpeg não está instalado. Instale usando:

```
brew install ffmpeg
```

### Conversão muito lenta

A velocidade depende da duração do vídeo e da capacidade do seu Mac. Vídeos longos podem levar vários minutos. Você pode ajustar o preset para `fast` ou `veryfast` editando a linha no script que contém `-preset medium`.

### Vídeo sem áudio

Verifique se o vídeo original possui áudio. Alguns vídeos espaciais podem ser gravados sem som.

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

Desenvolvido por **ALF Studio Tech**

## 🤝 Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para:

1. Fazer um fork do projeto
2. Criar uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abrir um Pull Request

## ⭐ Apoie o projeto

Se este script foi útil para você, considere dar uma ⭐ no repositório!

## 📧 Contato

Para dúvidas, sugestões ou reportar bugs, abra uma [issue](https://github.com/jfcardososantos/spatial2sbs/issues).

---

**Feito com ❤️ em Bom Jesus da Lapa, BA, Brasil**
