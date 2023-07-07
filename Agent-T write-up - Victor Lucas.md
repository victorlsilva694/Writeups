
## Headers 

Dentro da primeira etapa temos um cabeçalho. Enviamos esse cabeçalho temos a resposta do lado do servidor.


GET / HTTP/1.1

Host: 10.10.174.126

Upgrade-Insecure-Requests: 1

User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.5672.93 Safari/537.36

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7

Accept-Encoding: gzip, deflate

Accept-Language: en-US,en;q=0.9

Connection: close
<img src="images/Pasted image 20230701214042.png">



Analisando essa resposta achamos esse resultado:

HTTP/1.1 200 OK
Host: 10.10.174.126
Date: Sun, 02 Jul 2023 00:32:59 GMT
Connection: close
X-Powered-By: PHP/8.1.0-dev
Content-type: text/html; charset=UTF-8

Solicitação aceita 200 status code a data e uma coisa um pouco estranha 
```X-Powered-By: PHP/8.1.0-dev```

Buscamos então alguma resposta sobre PHP/8.1.0-dev e encontramos https://www.exploit-db.com/exploits/49933. Trata-se de um backdoor com execução arbitraria de código por user-agent header.

Fazemos o download do código, rodamos e colocamos a url vulnerável ao exploit e conseguimos o acesso. Buscamos então pela flag iniciando pelo diretório raiz e capturamos a flag







