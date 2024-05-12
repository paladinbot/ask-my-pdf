# Multsent



Obrigado pelo seu interesse na minha aplicação. Esteja atento que essa é apenas uma prova de conceito para a disciplina de Projeto Final Integrador 2 da [Universidade de Fortaleza](https://www.unifor.br/) e pode conter alguns bugs e features incompletas. Se você gostar desse app você pode [me seguir](https://twitter.com/Yur1Herbert) no Twitter para novidades e atualizações.


### Multsent - Ferramente de Análise de Sentimento construída sobre o GPT3.5.



🎲 The primary use case for this app is to assist users in answering  questions about board game rules based on the instruction manual. While  the app can be used for other tasks, helping users with board game rules is particularly meaningful to me since I'm an avid fan of board games  myself. Additionally, this use case is relatively harmless, even in  cases where the model may experience hallucinations.



🌐 The app can be accessed on the Streamlit Community Cloud at https://ask-my-pdf.streamlit.app/. 🔑 However, to use the app, you will need your own [OpenAI's API key](https://platform.openai.com/account/api-keys).



📄 The app implements the following academic papers:

- [In-Context Retrieval-Augmented Language Models](https://arxiv.org/abs/2302.00083) aka **RALM**

- [Precise Zero-Shot Dense Retrieval without Relevance Labels](https://arxiv.org/abs/2212.10496) aka **HyDE** (Hypothetical Document Embeddings)



### Instalação



1. Clone o repositório:

   `git clone https://github.com/mobarski/ask-my-pdf`

2. Instale as dependencias:

   `pip install -r ask-my-pdf/requirements.txt`

3. Rode o app:

   `cd ask-my-pdf/src`
   
   `run.sh` ou `run.bat`



### High-level documentation



#### RALM + HyDE

![RALM + HyDE](docs/ralm_hyde.jpg)



#### RALM + HyDE + context

![RALM + HyDE + context](docs/ralm_hyde_wc.jpg)



### Environment variables used for configuration



##### General configuration:

- **STORAGE_SALT** - cryptograpic salt used when deriving user/folder name and encryption key from API key, hexadecimal notation, 2-16 characters

- **STORAGE_MODE** - index storage mode:  S3, LOCAL, DICT (default)

- **STATS_MODE** - usage stats storage mode: REDIS, DICT (default)

- **FEEDBACK_MODE** - user feedback storage mode: REDIS, NONE (default)

- **CACHE_MODE** - embeddings cache mode: S3, DISK, NONE (default)

  

##### Local filesystem configuration (storage / cache):

- **STORAGE_PATH** - directory path for index storage

- **CACHE_PATH** - directory path for embeddings cache

  

##### S3 configuration (storage / cache):

- **S3_REGION** - region code

- **S3_BUCKET** - bucket name (storage)

- **S3_SECRET** - secret key

- **S3_KEY** - access key

- **S3_URL** - URL

- **S3_PREFIX** - object name prefix

- **S3_CACHE_BUCKET** - bucket name (cache)

- **S3_CACHE_PREFIX** - object name prefix (cache)

  

##### Redis configuration (for persistent usage statistics / user feedback):

- **REDIS_URL** - Redis DB URL (redis[s]://:password@host:port/[db])

  

##### Community version related options:

- **OPENAI_KEY** - API key used for the default user
- **COMMUNITY_DAILY_USD** - default user's daily budget
- **COMMUNITY_USER** - default user's code

