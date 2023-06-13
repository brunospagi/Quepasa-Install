#INSTALAÇÃO API QUEPASA#

```
git clone https://github.com/nocodeleaks/quepasa /opt/quepasa-source
bash /opt/quepasa-source/helpers/install.sh
```


</p>

</p>
sudo nano /etc/nginx/sites-available/quepasa
</p>


```
server {

  server_name quepasa.dominio.com.br;

  location / {

    proxy_pass http://127.0.0.1:31000;

    proxy_http_version 1.1;

    proxy_set_header Upgrade $http_upgrade;

    proxy_set_header Connection 'upgrade';

    proxy_set_header Host $host;

    proxy_set_header X-Real-IP $remote_addr;

    proxy_set_header X-Forwarded-Proto $scheme;

    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    
    proxy_cache_bypass $http_upgrade;

  }

  }
```

sudo ln -s /etc/nginx/sites-available/quepasa /etc/nginx/sites-enabled
</p>
</p>
sudo certbot --nginx
</p>
sudo service nginx restart
</p>
</p>

<hr />

**Ativando SSL da API Quepasa**

nano /opt/quepasa-source/src/.env
</p>
Alterar linha 1
</p>
WEBSOCKETSSL=false
</p>
para
</p>
WEBSOCKETSSL=true
</p>
systemctl restart quepasa
</p>

<hr />

***Execute esse processo abaixo parra deixar mais rapida sua API**

nano /etc/hosts

Adicione isso na primeira linha 
127.0.0.1       localhost app.dominio.com.br conector.dominio.com.br api.dominio.com.br

<hr />

**Instalação Finalizadas**

</p>
quepa.dominio.com.br/setup
</p>
Faça os cadastros em todos eles
</p>

</p>

<hr />
