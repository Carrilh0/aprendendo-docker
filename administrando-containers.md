# Administrando Containers Docker

## Comandos:

```docker run -ti --name <nome-do-container> <imagem> /bin/bash```

### Executar/instanciar um contêiner (básico):

* ```-ti```: Permite assumir o bash do contêiner logo após instanciá-lo
    * ```-t``` : é para que você tenha uma terminal
    * ```-i``` : é para que você tenha uma interação com o container
* ```-d```: Usado no lugar do ‘-ti’. Instancia e inicia o contêiner em background
* ```--name <nome_container>```: Permite dar um nome ao contêiner. Recomendável para que possa tratá-lo por um nome ao invés de seu ID sha1.
* ```<nome_imagem>```: Imagem de base para o contêiner.

---

```docker images ```

* Listas todas as imagens baixadas no docker
---

```docker stop  <container-id/name>```

* Para um container

---

```docker start  <container-id/name>```

* Inicia um container

---

```docker pause  <container-id/name>```

* Pausa um container

---

```docker unpause  <container-id/name>```

* Despausa um container

---

```docker ps -a ```
* Listar containers
> -a Lista containers que não estão em execução

---

```docker attach <container-id/name> ```
* Entrar em um container em execução

---

```Ctrl + p + q ```
* Sair de um container sem matar ele

---

```docker stats  <container-id/name>```

* Visualiza o quanto o container está ultilizando de recurso

---

```docker top  <container-id/name>```

* Visualiza os processos executados no container

---

```docker logs  <container-id/name>```

* Retorna os logs do container

---

```docker rm -f  <container-id/name>```

* Remove um container do docker
    * ```-f```: Força a exculsão do container caso ele esteja em execução

---
