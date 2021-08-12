<h1 align="center">Tech4Hack</h1>

## Introdução
Sejam Bem vindos ao Hackaton da tech4humans. Nesta Hackaton vai ser proposto um desafio nos seguintes segmentos.
## Desafio
O desafio deverá ser hospedado em um repositório do github, e deverá conter um arquivo Readme explicando o que
foi feito, como rodar a aplicação, qual a funcionalidade do NLU GOTIT na aplicação. O link do projeto do github
deverá ser enviado para o seguinte email: tech4hackaton@gmail.com 

<ol>
    <li>Seguir os passos do tutorial para estabelecer um ambiente inicial de desenvolvimento</li>
    <li>Criação de uma página para simulação de um chat.( React )</li>
    <li>Banco Postgres para salvar (user(opcional), mensagens, requests de Api do GotIT, a critério do participante)</li>
    <li>Api de análise de <b>sentimento</b> GoTIT de NLU(<a href="https://www.gotit.ai/">GOT</a>). O que é -> Fazer com que as máquinas compreendam o sentimento envolvido na linguagem natural foi um dos problemas mais difíceis da inteligência artificial até hoje. Usando a nossa API você tem acesso imediato a anos de desenvolvimento de ponta para fazer a máquina compreender cada nuance do contexto e assim estar apta a extrair com precisão as emoções e sentimentos envolvidos em uma sentença.</li>
    <h3>Desafios Opcionais</h3>
    <li>Fazer a conexão por usuario</li>
    <li>Utilizar A API GOTIT de maneira inventiva</li>
</ol>
    
## Início Rápido:
Usar o JavaScript para criar uma sala de chat com o Azure Functions e o Serviço do SignalR
O Serviço do Azure SignalR permite que você adicione funcionalidades em tempo real ao seu aplicativo com 
facilidade, e o Azure Functions é uma plataforma sem servidor que permite que você execute o código sem 
gerenciar nenhuma infraestrutura. Neste início rápido, você usará o JavaScript para criar um aplicativo 
de chat sem servidor e em tempo real usando o Serviço do SignalR e o Functions.
<hr></hr>
<h2>Pré-requisitos</h2>
    • Um editor de códigos, como o Visual Studio Code <br>
    • Node.js, versão 10.x
<hr></hr>      
      <h2>Clonar o aplicativo de exemplo</h2>
      Durante a implantação do serviço, vamos trabalhar com o código. <br>
    1-Clone o aplicativo de exemplo do GitHub. <br>
    2-Abra uma janela de terminal git. Mude para uma pasta em que deseja clonar o projeto de exemplo.<br>
    3-Execute o comando a seguir para clonar o repositório de exemplo. Este comando cria uma cópia do aplicativo de exemplo no seu computador.<br>
    
    git clone https://github.com/Tech4Hackaton/Hackaton.git
    
   4-No terminal entre na pasta src/chat/javascript do repositório clonado, e execute um npm install.<br>
    OBS: Lembre-se que o node precisa estar instalado e a versão precisa ser a versão 10 do node.<br>      

<br><h2>Configurar e executar o aplicativo do Azure Functions</h2>
    1-No editor de códigos, abra a pasta src/chat/javascript no repositório clonado.<br>
    2-Renomeie local.settings.sample.json como local.settings.json.<br>
    3-Em local.settings.json, cole a cadeia de conexão no valor da configuração AzureSignalRConnectionString. Salve o arquivo. 
    A string endpoint está logo abaixo.<br>
    
    "Endpoint=https://hackaton-tech.service.signalr.net; AccessKey=oUtL6nMCUwhBPhfmyfjUBO2ls9Qy4W99cuZY7VGL0S8=;Version=1.0;"
   <br>4- As funções JavaScript são organizadas em pastas. Há dois arquivos em cada pasta: function.json define as associações que são usadas na função, e index.js é o corpo da função. Há duas funções de gatilho HTTP nesse aplicativo de funções:
  <br>◦ negociar – usa a associação de entrada SignalRConnectionInfo para gerar e retornar informações de conexão válidas.
  <br>◦ mensagens – recebe uma mensagem de chat no corpo da solicitação e usa a associação de saída SignalR para difundir a mensagem a todos os aplicativos cliente conectados.
  <br>5-No terminal, verifique se você está na pasta src/chat/javascript. Execute o aplicativo de funções.
func start

<h2>Executar o aplicativo Web</h2>
Para simplificar o teste do cliente, abra o navegador para o nosso aplicativo Web de página única de amostra https://azure-samples.github.io/signalr-service-quickstart-serverless-chat/demo/chat-v2/ .<br>
<h3>Observação</h3>
A origem do arquivo HTML está localizada em /docs/chat-v2/index.html. 
<br>Verifique se a origem foi adicionada para a configuração CORS em local.settings.json semelhante à amostra.<br>

    "Host": {
     "LocalHttpPort": 7071,
     "CORS": "http://localhost:8080,https://azure-samples.github.io",
     "CORSCredentials": true
    }
<br>
1. Quando for solicitada a URL base do aplicativo de funções, digite http://localhost:7071.<br>
2. Insira um nome de usuário quando solicitado.<br>
3. O aplicativo Web chama a função GetSignalRInfo o aplicativo de funções para recuperar as informações de conexão para se conectar ao Serviço Azure SignalR. Quando a conexão for concluída, a caixa de entrada de mensagem de chat será exibida.<br>
4. Digite uma mensagem e pressione Enter. O aplicativo envia a mensagem para a função SendMessage no aplicativo Função do Azure, que usa a associação da saída do SignalR para difundir a mensagem para todos os clientes conectados. Se tudo estiver funcionando corretamente, a mensagem deverá aparecer no aplicativo.<br>
5. Digite uma mensagem e pressione Enter. O aplicativo envia a mensagem para a função SendMessage no aplicativo Função do Azure, que usa a associação da saída do SignalR para difundir a mensagem para todos os clientes conectados. Se tudo estiver funcionando corretamente, a mensagem deverá aparecer no aplicativo.<br>
6. Abra outra instância do aplicativo Web em outra janela do navegador. Você verá que todas as mensagens enviadas serão exibidas em todas as instâncias do aplicativo.<br>
