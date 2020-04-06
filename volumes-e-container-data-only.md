# Volumes <s> e container data-only </s>

### Volumes é uma forma de referenciar um file system ou um diretorio da máquina host drentro do container

<s> Container data-only é um container que nem precisa estar em execução, ele vai possuir volumes, e esses volumes serão compartilhados com outros containers </s>
###  Os contêineres data-only são obsoletos e agora são considerados um antipadrão! Deve-se usar o docker volume. 
```docker volume create dados-do-banco```
* Cria um novo volume

---
```docker volume ls```
* Lista todos os volumes

---


### Executar/instanciar um contêiner referenciando o volume:


```docker run -ti -v /root/pasta:/volume --name <nome-do-container> <imagem> /bin/bash```

* ```-ti```: Permite assumir o bash do contêiner logo após instanciá-lo
    * ```-t``` : é para que você tenha uma terminal
    * ```-i``` : é para que você tenha uma interação com o container
* ```-d```: Usado no lugar do ‘-ti’. Instancia e inicia o contêiner em background
* ```--name <nome_container>```: Permite dar um nome ao contêiner. Recomendável para que possa tratá-lo por um nome ao invés de seu ID sha1.
* ```<nome_imagem>```: Imagem de base para o contêiner.
* ```-v <pasta no host>:<pasta no container>```: Define o local do volume (Pasta compartilhada do host para o container).

---

```df -h```
* Lista todos as montagens do container (Ou do host);

---

```docker inspect -f {{.Mounts}} <id/nome do container>```
* Retorna o local em quem o mount do volume está na maquina host


---

## <s>Container data-only

```docker run -d -p 5432:5432 --name pgsql --volumes-from dbdados -e POSTGRESQL_USER=docker -e POSTGRESQL_PASS=docker -e POSTGRESQL_DB=docker kamui/postgresql```

* ```-p <porta-host:porta-container``` : expõe uma porta do container com a no host
* ```-d```: Usado no lugar do ‘-ti’. Instancia e inicia o contêiner em background
* ```--volumes-from```:  Permite usar o volume de outro container
* ```--name <nome_container>```: Permite dar um nome ao contêiner. Recomendável para que possa tratá-lo por um nome ao invés de seu ID sha1.
* ```kamui/postgresql = <nome_imagem>```: Imagem de base para o contêiner.
* ```-e <NOME_VARIAVEL=valor>```: Define variaveis de ambiente no container
---

</s>