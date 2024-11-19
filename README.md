# OpenGL 3D Model Viewer

Este projeto é um visualizador de modelo 3D utilizando OpenGL, GLEW, GLFW, GLM e Assimp. Ele carrega um modelo no formato OBJ e renderiza em uma janela interativa com movimentação de câmera.

## Estrutura do Projeto
- *GLFW*: Gerencia a janela, entrada e eventos do usuário.
- *GLEW*: Permite o uso de funções modernas do OpenGL.
- *GLM*: Gerencia as transformações de matriz e manipulação de vetores.
- *Assimp*: Lê e processa o modelo OBJ.
- *Shader Program*: Define os shaders de vértice e fragmento.

## Controles
- *W, A, S, D*: Movimentação da câmera.
- *Mouse*: Rotacionar a câmera.
- *Scroll*: Zoom in/out.

## Problemas Comuns
- Erro ao inicializar o GLFW ou GLEW: Verifique se as bibliotecas foram instaladas e configuradas corretamente.
- Modelo não encontrado: Certifique-se de que o caminho do modelo .obj está correto.
- Shader não compila: Verifique os logs do shader para identificar erros de sintaxe.

### Observações
Este projeto é uma base para um visualizador de modelos 3D. Pode ser estendido para incluir texturas, iluminação, ou manipulação de modelos mais complexos.
