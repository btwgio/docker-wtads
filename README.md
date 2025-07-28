# Minicurso de Docker

Aplicação Django para Minicurso de Docker

Este projeto foi criado para ser utilizado no minicurso de Docker ministrado por Giovanna Moura durante o WTADS/WINFO, evento dos cursos de Tecnologia em Análise e Desenvolvimento de Sistemas e Informática para Internet (DIATINF) no IFRN.

## Objetivo

Os participantes irão utilizar esta aplicação para aprender a criar um Dockerfile e rodar o projeto em containers Docker.

## Passo a Passo



### 1. Clonando o repositório e acessando os arquivos do projeto

```bash
git clone https://github.com/btwgio/docker-wtads.git
cd docker-wtads
cd project   # aqui estão os arquivos Django
```

### 2. Rodando sem Docker

#### Requisitos
- Python 3.11+
- pip

#### Instalando dependências
```bash
pip install django
```

#### Migrando e rodando
```bash
python manage.py migrate
python manage.py runserver
```
Acesse: http://127.0.0.1:8000/wtads2025

---

### 3. Rodando com Docker

#### Passo 1: A partir da pasta `project`, crie o arquivo `Dockerfile`:

```bash
touch Dockerfile
```

Você irá preenche-lo de acordo com o que aprendeu durante o minicurso.

#### Passo 2: Crie o arquivo `requirements.txt` dentro da pasta `project` (adicione pelo menos `django`)

#### Passo 3: Construa a imagem

```bash
docker build -t wtads2025 .
```

#### Passo 4: Rode o container

Sem volumes:
```bash
docker run -p 8000:8000 wtads2025
```

Com volumes (no Linux):
```bash
docker run -p 8000:8000 -v $(pwd):/app wtads2025
```
No Windows:
```powershell
docker run -p 8000:8000 -v ${PWD}:/app wtads2025
```

---

## Observações
- Os arquivos `Dockerfile` e `requirements.txt` devem ser criados por você durante o minicurso.
- O projeto já está pronto para ser usado como base para o seu container.
- Qualquer dúvida, procure a instrutora durante o evento.
