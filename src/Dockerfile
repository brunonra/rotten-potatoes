#De onde a imagem esta saindo (buscando no DOCKERHUB tem as informaçoes)
FROM python:3.8-slim-buster 

#"Area de trabalho" da imagem, onde as coisas serao executadas durante o processo.
WORKDIR /app
COPY requirements.txt /app/

#Executa o comando do python para instalar os pacotes necessarios que estao na lista requirements
RUN python -m pip install -r requirements.txt

#Copia o resto dos arquivos para o local de execução
COPY . /app

#Porta exposta no servidor que servira de acesso a aplicacao.
EXPOSE 5000

#Os comandos abaixo sao os parametros a serem executados dentro da imagem.
CMD ["gunicorn", "--workers=3", "--bind", "0.0.0.0:5000", "app:app"]
