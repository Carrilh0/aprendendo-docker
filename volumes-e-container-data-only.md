# Volumes e container data-only

### Volumes é uma forma de referenciar um file system ou um diretorio da máquina host drentro do container

### Container data-only é um container que nem precisa estar em execução, ele vai possuir volumes, e esses volumes serão compartilhados com outros containers


```docker run -ti -v /root/pasta:/volume --name <nome-do-container> <imagem> /bin/bash```
### Executar/instanciar um contêiner referenciando o volume:

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