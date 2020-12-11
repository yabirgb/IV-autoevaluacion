# Ejercicios

## Instalar etcd

Para instalar etcd me he descargado un comprimido desde el repositorio oficial.
Este comprimido contiene dos ejecutables, uno de ellos inicial el servicio de
etcd  y otro actua como cliente. 

Para usar etcd en primer lugar tenemos que iniciar el servidor. Despues desde el
client podemos alamacera un par clave valor con 

    etcdctl put ETHPORT2 32

Si queremos consultar su valor usamos 

    etcdctl get ETHPORT2

Para borrar una clave podemos usar 

    etcdctl del ETHPORT2

En el caso de rust [etcd-client](https://github.com/etcdv3/etcd-client) que
además funciona de manera asíncrona. Para conectarnos a un servidor de etcd
tenemos que hacer

    let mut client = Client::connect(["localhost:2379"], None).await?;

y podemos consultar una clave con

    client.get("foo", None).await?

## Resto de ejercicios

Como respuesta al resto de ejercicios presento el miniproyecto que hay en esta
carpeta y lo realizado durante el curso de tdd en [TDD-AY](https://github.com/TDD-AY/TDD-Project)