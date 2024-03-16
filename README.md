---

# Instalação do Easypanel na VPS da Oracle Cloud (ARM64/V8) 🚀

Esta documentação descreve os passos para instalar o Easypanel em uma VPS da Oracle Cloud usando a arquitetura ARM64/V8.

## Pré-requisitos 🛠️

- Uma VPS da Oracle Cloud configurada e acessível via SSH.
- Acesso de superusuário (sudo) ou root à VPS.
- Conhecimento básico de linha de comando do Linux.

## Passo 1: Adicionar Swap Space 🔄

Antes de começar a instalação do Easypanel, garanta que sua VPS tenha espaço de swap suficiente seguindo [este tutorial](#). Aumentar o swap ajuda a evitar problemas de memória durante a instalação e operação do Easypanel.

## Passo 2: Instalação do Docker 🔧

Certifique-se de que o Docker esteja instalado e em execução em sua VPS. Caso contrário, instale-o executando os seguintes comandos:

```bash
curl -sSL https://get.docker.com | sh
```

## Passo 3: Instalação do Easypanel Canário 🐤

Execute o seguinte comando para instalar o Easypanel Canário em sua VPS:

```bash
docker run --rm -it \
  -v /etc/easypanel:/etc/easypanel \
  -v /var/run/docker.sock:/var/run/docker.sock:ro \
  -e RELEASE_TAG=canary \
  easypanel/easypanel:canary setup
```

Siga as instruções fornecidas para concluir a instalação do Easypanel.

## Passo 4: Acesso ao Easypanel 🖥️

Após a instalação, acesse o Easypanel pelo navegador web. Use o endereço IP da sua VPS seguido pela porta 80 para acessar o painel de controle.

## Passo 5: Instalação do Appwrite (Opcional) ⚙️

Se desejar, você pode instalar o Appwrite no Easypanel para adicionar mais funcionalidades ao seu servidor. Certifique-se de que o Docker esteja em execução e siga as instruções de instalação do Appwrite no GitHub.

---

Esta documentação fornece os passos essenciais para instalar o Easypanel na sua VPS da Oracle Cloud, permitindo que você gerencie facilmente seu servidor com uma interface amigável.

Se surgirem dúvidas ou problemas durante a instalação, consulte a documentação oficial do Easypanel ou entre em contato com o suporte técnico.

---
