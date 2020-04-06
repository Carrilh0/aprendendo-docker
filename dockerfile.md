# Dockerfile

### O dockerfile nada mais é do que as instruções que se deve mandar para o docker para fazer o build da sua aplicação
---
#### Alguns parametro do Dockerfile:

```FROM ubuntu```

* Define a image base para montar a imagem

---
```RUN apt-get update && apt-get install apache2 && apt-get clean```

* Serve para instalar pacotes. O quanto menos RUN tiver é melhor, pois é menos camada, a cada RUN executado é uma nova camada.
---

```ADD opa.txt /diretorio/```

* Adiciona um arquivo da maquina host para um diretorio do container
---

```CMD ["sh", "-c", "echo", "$HOME"```

* CMD é um parametro para o entrypoint
---

```LABEL Description="bla bla bla"```

* Serve para conseguir colocar metadata que você precisar do container
---

```COPY opa.txt /diretorio/```

* Copia um arquivo da sua maquina host para o seu container
---

```ENTRYPOINT ["/usr/bin/apache2ctl", "-D", "FOREGROUND"]```

* Define qual é o processo principal para o container, caso ele morra, o container morre junto
---

```EBV meunome="Vitor Carrilho"```

* Serve para configurar variáveis de ambiente para o container
---

```EXPOSE 3333```

* Define qual a porta do container deve ser exposta
---

```USER carrilho```

* Define o usário default da imagem
---

```WORKDIR /diretorio/```

* Define o diretorio de trabalho do container, ou seja, aonde será direcionado ao abrir o container.
---

```VOLUME  /opt/host /opt/container```

* Define a image base para montar a imagem
---

```MAINTAINER Vitor Carrilho```

* Define o criado da imagem

## Build

### Para realizar o build de um dockerfiler é necessario rodar o seguinte comando:

```docker build -t nome:1.0 .```

* ```-t <nome da imagem:versão>``` Define o nome e versão da respectiva imagem gerada pelo dockerfile

* ```.``` É o diretorio em que o dockerfile está
