# Automação Web com Selenium

- Python + Selenium
> 2 requisitos 

- Instalar o Selenium 
  
- Webdriver Manager
  - é o que permite o Selenium controlar seu navegador, de certa forma ele vai automatizar uma coisa que precisaria fazer manualmente que é as instalações de drives
  - Como assim? O selenium ele pode sim controlar o navegador sem o WM mas ele precisaria que você baixasse os drives mais atuais do navegador que ele vai usar
  - E isso é um problema pois quando o navegador atualizar para uma nova versão o código iria quebrar
  - Com o WM ele faz isso automáticamente

```py
# como eu disse antes o selenium ja possui uma parte de webdriver
from selenium import webdriver

# Aqui você está importando o driver mais atual do chrome
from webdriver_manager.chrome import ChromeDriverManager

# E aqui você importa o Service que vai simplesmente executar o ChromeDriverManager
from selenium.webdriver.chrome.service import Service

# E aqui ChromeDriverManager() vai procurar qual a versão atual do teu chrome e vai instalar a versao do driver correspondente

servico = Service(ChromeDriverManager().install())

# Aqui você indica qual navegador vai usar, e dentro dos parenteses como param
# você meio que vai passar a versão que o selenium vai usar
# Para ele saber o que esta fazendo 
navegador = webdriver.Chrome(service=servico)


# Aqui é um comando que te permite navegar para qualquer página da internet
navegador .get("https://pages.hashtagtreinamentos.com/inscricao-minicurso-python-automacao-org?origemurl=hashtag_yt_org_minipython_8AMNaVt0z_M")

# Para pegar um elemento
# Aqui você pode usar qualquer tipo de busca
# Mas pelo xpath é mais certeira 
# entrando no navegador no site, e apertando inspecionar no elemento você pode copiar o xpath dele
# E o .send_keys indica o valor que você quer que o selenium mande 
navegador.find_element("xpath",'//*[@id="section-10356508"]/section/div[2]/div/div[2]/form/div[1]/div/div[1]/div/input').send_keys("Erick")
```
