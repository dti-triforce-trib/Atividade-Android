# Bem vindo ao processo seletivo para desenvolvedor mobile da dti digital, obrigado por participar!

Segue a descrição da nossa atividade, alguns pontos importantes:

- Você terá 4 dias para enviar o retorno da atividade, a partir da data que você recebeu o convite para participar
- O código final deve ser postado no github e o link de acesso ao repositório deve ser enviado para o e-mail jordann.alessandro@dtidigital.com.br
- Devem ser passadas as instruções de como rodar o seu app (se tem que baixar alguma dependência, ou qualquer configuração necessária para compilar)
- Sua apk deve conseguir executar sem problemas pelo menos da api 21 a 29 do android.
- Sua apk deve apresentar o mesmo comportamento de layout para telas de 4,7" a 6,8" 

## Descrição

Seu app terá 2 telas: 
  - uma de login que deve conter 1 logo de sua escolha, 2 caixas de texto, uma para usuário e outra para senha e um botão de login. 
  - outra após o login que será uma lista de eventos, contendo uma imagem que representa o evento, o título, uma descrição e a data.

Seu app consumira 2 rotas:

Serviço 1: Realiza o login, nele teremos como resposta um token que deve ser salvo no shared preferences e o tempo de expiração do token (em minutos). Quando o tempo de expiração for concluído o usuário deve ser direcionado a tela de login novamente.

	  rota -> https://testapi.io/api/dti-triforce-trib/login
	  tipo -> POST
	  headers -> não possui
	  requestBody: 
	  {
		  "username": "Joao.lucas",
		  "pass": "123456"
	  }
	  response:
	  {
	    "token": "45848cssaev-scascsac-csacsav",
	    "tempoExpirar": "2"
	  }
	  http status do response: 200
  
  
  Obs: independente do usuário e senha informados a resposta será essa, todavia algum usuário e senha deve ser enviado (e feitas as devidas validações).
Validações: Senha no mínimo 6 digitos, caixa de texto usuario deve aceitar digitos com exceção de caracteres especiais.

Serviço 2: Retorna a lista de eventos para a segunda tela.

    rota ->  https://testapi.io/api/dti-triforce-trib/eventos-mensais
    tipo -> GET
    headers -> não possui
    response:
    {
      "eventos": [
          {
              "id": 1,
              "nome": "Churrasco social em prol da Apae",
              "descricao": "Será um churrasco muito bacana, venha e participe",
              "data": 1568948400000,
              "rotaImagem": "https://static.fecam.net.br/thumbs/681/2577965_resize_1500_840.jpg"
          },
          {
              "id": 2,
              "nome": "Bingo beneficente vila vicentina",
              "descricao": "Bingo em prol da vila vicentina e comunidade do idoso",
              "data": 1568516400000,
              "rotaImagem": "https://s3.portalt5.com.br/imagens/2017-10-05-PHOTO-00000034.jpg?mtime=20171009204746" 
          },
          {
              "id": 3,
              "nome": "Feijoada do Graac",
              "descricao": "Traga sua família para comer uma feijoada muito boa",
              "data": 1569380400000,
              "rotaImagem": "https://www.spdm.org.br/media/k2/items/cache/867519228d1d5325856fc61d710ded0e_L.jpg" 
          },
          {
              "id":4,
              "nome": "Churrasco social em prol da Apae",
              "descricao": "Será um churrasco muito bacana, venha e participe",
              "data": 1567306800000,
              "rotaImagem": "" 
          }
        ]
    }

A data do evento está escrita como um long, deve ser exibida no formato "dd/MM/yyyy". Os eventos devem aparecer na tela ordenados pela data, sendo o do topo da lista com a data menor. As imagens dos eventos são links que devem serem consumidos. As imagens virão de tamanhos diversos e devem se adequar ao seu layout da forma que preferir. Se a imagem não possuir um link deve ser utilizado uma imagem de sua escolha. A segunda tela é apenas de exibição dos dados e o layout fica ao seu agrado. Contudo todos os dados do evento devem ser exibidos de alguma forma.

## O que iremos avaliar:
  
  - Boas práticas de progamação
  - arquitetura utilizada
  - bibliotecas utilizadas
  - uso do git
  - Se o comportamento do app funciona conforme o que foi descrito 


Te desejamos boa sorte e esperamos que você venha pro nosso time! #vemSerDti
