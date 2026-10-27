# CompreRápido — apresentação interativa

Projeto acadêmico do **Grupo 1 — E-commerce e Varejo**, baseado nos materiais fornecidos sobre migração de arquitetura monolítica para escalabilidade horizontal, sharding e tolerância a falhas.

## Executar localmente

Abra o arquivo `index.html` no navegador (Chrome, Edge ou Firefox). O projeto não usa bibliotecas externas e funciona offline.

## Interatividades

- Compare **Scale-Up x Scale-Out** com alternância de modelos e controle didático de tráfego.
- Adicione ou remova instâncias no diagrama de arquitetura.
- Insira nomes de clientes para simular **Sharding por faixa (A–M/N–Z)** ou **hash (4 shards)**.
- Clique em **Simular falha de servidor** para acompanhar Health Check, redirecionamento, failover e auto-healing.

As demonstrações são simuladas no navegador; não criam servidores reais nem executam um banco de dados distribuído. Números de capacidade são meramente ilustrativos.

## Docker

É necessário ter Docker instalado e funcionando.

```bash
docker build -t comprerapido .
docker run --rm -p 10000:10000 comprerapido
```

Abra `http://localhost:10000`.

## Publicar no Render (entrega do professor)

1. Crie um repositório **público no GitHub**, por exemplo `comprerapido-apresentacao`.
2. Envie **todos os arquivos da pasta** (`index.html`, `Dockerfile`, `nginx.conf`, `.dockerignore` e `README.md`) para a raiz do repositório.
3. Acesse https://dashboard.render.com/ e escolha **New > Web Service**.
4. Conecte seu repositório GitHub e selecione **Language/Runtime: Docker** (ou Environment: Docker, dependendo da tela).
5. Use o `Dockerfile` da raiz e uma instância/plano disponível. O Nginx escuta na porta `10000`, padrão indicado para serviços Render.
6. Crie o serviço, aguarde o status de deploy e abra a URL pública que o Render fornecer.
7. Teste os botões, o sharding e a simulação de falhas. **Entregue somente a URL pública**, como solicitado.

O Render pode exigir conta e disponibilidade de plano. Não é necessário domínio personalizado.

## Conteúdo-base

- Relatório técnico: *CompreRápido — Plano de Modernização Arquitetural*.
- Relatório de arquitetura em PDF.
- Imagens com as instruções da atividade e os quatro pilares.

## Importante

A demonstração é um site estático e **não é uma implantação real do sistema distribuído da loja**. As simulações servem para a apresentação dos conceitos. O objetivo de continuidade do negócio requer testes reais e não significa garantia universal de zero indisponibilidade.
