<p align="center">
<img src="https://cwmkt.com.br/wp-content/uploads/2024/04/logo_github.png" width="240" />
<p align="center">Seja bem-vindo ao Guia de Instalação EasyPanel Easyappointments 🚀</p>
</p>
  
<p align="center"> 
<a href="https://hubconnect.top" target="_blank">👉 Participe da Comunidade HubConnect 👈</a>
</p>

<hr />
<hr />

## Comando para Instalar EasyPanel

```bash
curl -sSL https://get.easypanel.io | sh
```

Adicione nome de Project

![48098522-0c485df00f5cadb0d329061c35fee46c](https://github.com/cwmkt/easypanelevotypebot/assets/91642837/b72c1359-91ca-4bf6-9fb1-32525ba5747b)

Clique na aba Templates

![48098535-90f9b4f370bb8b06cfd7e4acf0ee0f97](https://github.com/cwmkt/easypanelevotypebot/assets/91642837/03c1830c-621c-40b3-94ee-93eb568c8d2e)

Va ate final da pagina

![image](https://github.com/comunidadehubconnect/easypanelwoofedcrm/assets/91642837/828a9e88-45f2-4b6b-98f1-ab4f164d2889)

Adicione codigo abaixo dentro do Schema

![image](https://github.com/comunidadehubconnect/easypanelwoofedcrm/assets/91642837/74b97f33-e5d2-495d-aaba-25bb8b433adf)

```bash
{
  "services": [
    {
      "type": "mysql",
      "data": {
        "projectName": "easyappointments-db",
        "serviceName": "easyappointments-db",
        "image": "mysql:latest"
      }
    }
  ]
}
```

Adicione codigo abaixo dentro do Schema com credenciais Mysql

![image](https://github.com/comunidadehubconnect/easypanelwoofedcrm/assets/91642837/74b97f33-e5d2-495d-aaba-25bb8b433adf)

```bash
{
  "services": [
    {
      "type": "app",
      "data": {
        "projectName": "easyappointments",
        "serviceName": "easyappointments",
        "source": {
          "type": "image",
          "image": "alextselegidis/easyappointments:latest"
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "port": 3001
          }
        ],
        "env":"BASE_URL=https://$(PRIMARY_DOMAIN) \nDEBUG_MODE=true \nMYSQL_HOST=mysql \nMYSQL_NAME=BANCODEDADOS \nMYSQL_USERNAME=USER \nMYSQL_PASSWORD=SENHA \nMYSQL_ROOT=SENHAROOT",
        "mounts": [
          {
            "type": "volume",
            "name": "easyapointments_data",
            "mountPath": "/var/www/html"
          }
        ]
      }
    }
  ]
}
```


Pronto tudo Funcionando ✅😎
