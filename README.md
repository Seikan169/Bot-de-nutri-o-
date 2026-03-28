# Bot-de-nutri-o-
Este projeto implementa um Agente de Nutrição Interativo utilizando inteligência artificial. O sistema permite que o usuário faça perguntas sobre nutrição por meio de áudio. A voz é gravada, transcrita para texto utilizando o modelo Whisper da OpenAI, e essa transcrição é enviada a um modelo Gemini (configurado como um agente de nutrição).


# Agente de Nutrição Interativo

Este projeto desenvolve um agente de nutrição baseado em IA que interage com os usuários por voz, oferecendo orientações e conselhos nutricionais.

## Funcionalidades

*   **Gravação de Áudio:** Captura a fala do usuário diretamente no navegador.
*   **Transcrições de Voz:** Converte o áudio gravado em texto usando o modelo OpenAI Whisper.
*   **Geração de Respostas:** Utiliza o modelo Gemini (Google Generative AI) para interpretar as perguntas do usuário e gerar respostas como um especialista em nutrição.
*   **Síntese de Fala:** Converte as respostas do modelo Gemini de volta para áudio para uma experiência interativa.

## Tecnologias Utilizadas

*   **Python:** Linguagem de programação principal.
*   **Google Colab:** Ambiente de desenvolvimento.
*   **OpenAI Whisper:** Para transcrição de fala para texto.
*   **Google Generative AI (Gemini API):** Para processamento de linguagem natural e geração de respostas.
*   **gTTS (Google Text-to-Speech):** Para síntese de fala a partir de texto.
*   **HTML/JavaScript:** Para a interface de gravação de áudio no navegador.

## Como Configurar e Rodar

### 1. Ambiente Google Colab

Este projeto é projetado para ser executado no Google Colab. Certifique-se de ter uma conta Google.

### 2. Instalação das Dependências

Execute as seguintes células no seu notebook Colab para instalar as bibliotecas necessárias:

```python
!pip install openai-whisper
!pip install -q google-generativeai
!pip install gTTS
```

### 3. Configuração da Chave API do Gemini

Você precisará de uma chave API do Google Generative AI (Gemini). Se você não possui uma, pode criá-la em [Google AI Studio](https://aistudio.google.com/).

**No Colab:**
1.  Clique no ícone de chave (🔑) no painel esquerdo.
2.  Adicione sua chave API com o nome `GOOGLE_API_KEY`.

Ou, insira sua chave diretamente no código (não recomendado para produção):

```python
genai.configure(api_key="SUA_CHAVE_GEMINI_AQUI")
```

### 4. Executando o Notebook

Execute as células do notebook sequencialmente. O fluxo será:
1.  Definição do idioma.
2.  Definição e execução da função de gravação de áudio. Você precisará **clicar no botão 'Clique para Falar' e conceder permissão ao microfone**.
3.  Instalação do Whisper (se ainda não estiver instalado).
4.  Transcrever o áudio gravado.
5.  Configuração da API Gemini e geração da resposta.
6.  Síntese de fala da resposta do Gemini.

## Como Usar

Após executar as células:
1.  Um botão "Clique para Falar" aparecerá. Clique nele e fale sua pergunta sobre nutrição.
2.  Aguarde enquanto sua fala é processada e a resposta é gerada.
3.  A resposta do agente de nutrição será reproduzida em áudio.

## Próximos Passos (Possíveis Melhorias)

*   **Interface mais robusta:** Melhorar a interface do usuário para feedback visual sobre o status da gravação/processamento.
*   **Histórico de Conversa:** Implementar um histórico para que o agente possa ter contexto de conversas anteriores.
*   **Personalização:** Permitir que o usuário forneça informações sobre si (idade, peso, objetivos) para respostas mais personalizadas.
*   **Integração com fontes de dados:** Conectar a dados nutricionais atualizados para informações mais precisas.
*   **Tratamento de erros:** Adicionar tratamento de erros para problemas de conexão ou API.

