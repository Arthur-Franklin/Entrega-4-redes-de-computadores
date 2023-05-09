# Entrega-4-redes-de-computadores
# Arthur Franklin Souza de Oliveira
# Empresa: Grow Small Towns 

# Passo a passo para construir e executar o container do Grow Small Towns
Este documento descreve como construir e executar um container para o Grow Small Towns.

## Requisitos
Antes de começar, certifique-se de ter o Docker, o Dockerfile e o index.html instalados em sua máquina.
````
FROM python:3
COPY index.html /usr/src/app/
WORKDIR /usr/src/app/
EXPOSE 8000
CMD ["python3", "-m", "http.server", "8000"]
````
````
<!DOCTYPE html>
	<html lang="pt-BR">
	<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, 		initial-scale=1.0">
	<title>GST - Grow Small Towns</title>
	</head>
	<body>
	<header>
	<h1>GST - Grow Small Towns</h1>
	<nav>
	<ul>
	<li><a href="#">Início</a></li>
	<li><a href="#">Sobre Nós</a></li>
	<li><a href="#">Serviços</a></li>
	<li><a href="#">Contato</a></li>
	</ul>
	</nav>
	</header>
	<main>
	<section>
	<h2>Bem-vindo ao GST</h2>
	<p>O GST - Grow Small Towns é dedicado a fornecer soluções sustentáveis para o crescimento de cidades pequenas. Nossa equipe de especialistas está comprometida em trazer soluções para os problemas enfrentados nas cidades pequenas em todo o país.</p>
	</section>
	<section>
	<h2>Sobre Nós</h2>
	<p>O GST foi fundado com o objetivo de apoiar o crescimento de cidades pequenas.Ajudamos inúmeras cidades pequenas a alcançar a prosperidade econômica e social por meio de soluções inovadoras e uma equipe dedicada.</p>
	</section>
	<section>
	<h2>Serviços</h2>
	<ul>
	<li>Desenvolvimento de software</li>
	<li>Planejamento e design de infraestrutura</li>
	</ul>
	</section>
	<section>
	<h2>Contato</h2>
	<form>
	<label for="name">Nome:</label>
	<input type="text" id="name" name="name"><br><br>
	<label for="email">E-mail:</label>
	<input type="email" id="email" name="email"><br><br>
	<label for="message">Mensagem:</label><br>
	<textarea id="message" name="message"></textarea><br><br>
	<input type="submit" value="Enviar">
	</form>
	</section>
	</main>
	<footer>
	<p>&copy; 2023 GST - Grow Small Towns</p>
	</footer>
	</body>
	</html>
````

## Construindo a imagem do container
1. Clone o repositório do Grow Small Towns.
2. Abra o terminal e navegue até o diretório raiz do repositório.
3. Execute o comando abaixo para construir a imagem do container:

````
docker build -f Dockerfile . -t arthurfranklin
````

## Executando o container
Execute o comando abaixo para iniciar o container:

````
docker run -d -p 9772:8000 --name arthurhttp arthurfranklin
````

## Testando o container
Para testar se a página está no ar, execute o comando:
````
wget http://127.0.0.1:9772
cat index.html
````

## Parando o container
Para parar o container, execute o comando abaixo:

````
docker stop arthurhttp
````

## Removendo o container
Para remover o container, execute o comando abaixo:
````
docker rm arthurhttp
````

## Removendo a imagem
Para remover a imagem do container, execute o comando abaixo:
````
docker rmi arthurfranklin
````
