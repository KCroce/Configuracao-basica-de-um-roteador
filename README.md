# Primeiros passos
(Recomendo desconectar de outras redes nesses primeiros passos)
Vou supor que você está conectado ao dispositivo via cabo Ethernet.

O dispositivo utilizado é um **TPLINK**, para conseguir se conectar procure por especificações sobre seu dispositivo.
## Conecte em http://192.168.1.1
- **user:** admin
- **password:** admin
  
Confira se esse realmente é o modelo do dispositivo que você quer modificar:

<img width="414" height="93" alt="Pasted image 20260228142942" src="https://github.com/user-attachments/assets/3482c494-d197-4754-bde9-8e0d1d438db8" />

## Modificação IP para evitar conflito(Opcional)
Acredito que essa seja a modificação mais interessante até o fim da configuração ela permite que você fique conectado na sua rede doméstica enquanto modifica esse dispositivo sem problemas.
1. <img width="208" height="89" alt="Pasted image 20260228143254" src="https://github.com/user-attachments/assets/9e5d9067-7d0f-43f8-a017-d01fdc218df0" />
2. 
	<img width="180" height="145" alt="Pasted image 20260228143530" src="https://github.com/user-attachments/assets/819a0c59-69cf-4ac3-81e6-9d6c1467a6ff" />
3. Modifique para uma faixa de IP que sua conexão doméstica não utilize.
	1. Por exemplo, a minha rede usa 192.168.1.1(A mesma faixa IP padrão do dispositivo do qual quero configurar) então para evitar conflito eu coloquei 192.168.12.1
	2. Ficando assim:
	    <img width="354" height="192" alt="Pasted image 20260228143842" src="https://github.com/user-attachments/assets/3ef18ce0-32fc-4677-b6ae-a0bc26c9c50a" />
4. Agora seu dispositivo estará em: http://192.168.12.1
5. Acredito que agora você possa voltar a se conectar na internet sem problemas
## Ativar Wireless
1. 
	<img width="287" height="93" alt="Pasted image 20260228222016" src="https://github.com/user-attachments/assets/f2592269-0fc6-4f34-8671-427f1a7c2780" />
2. 
	<img width="333" height="172" alt="Pasted image 20260228222259" src="https://github.com/user-attachments/assets/6a2d40f6-de50-4f88-ad70-99cc90db4018" />
3. 
	<img width="432" height="282" alt="Pasted image 20260301153604" src="https://github.com/user-attachments/assets/17867385-c456-4a9c-9321-2de4e9b460f1" />
  
	- **SSID** -> Nome da rede;
	- **Region** -> Região onde você está conectando o dispositivo;
	- **Channel** -> Canal que será utilizado para comunicação(Deixar Automático);
	- **Mode** -> Protocolo utilizado;
		- Recomendo utilizar o protocolo mais atual possível, porém isso pode limitar que dispositivos muito velhos se conectem a rede, nesse caso é melhor a opção com o "misto" no nome ou adotar um protocolo antigo.
		- **Exemplo:** <img width="283" height="42" alt="Pasted image 20260301154900" src="https://github.com/user-attachments/assets/b1a73951-2df2-442c-904d-8783ba806e89" />
	- **Enable Wireless Router Radio** -> Isso permite com que dispositivos Wireless possam se conectar. (Isso não fará a rede aparecer na busca de redes WiFi);
	- **Enable SSID Broadcast** -> Isso faz com que o sinal apareça para outros dispositivos que estejam procurando uma rede WiFi. 
### Password 
Atualmente sua rede está ativa e visível para qualquer dispositivo conectar, com o passos seguintes vou mostrar como configurar a rede para que seja necessário uma palavra chave   ao tentar realizar uma conexão.

Em dispositivos mais antigos **TPLINK** a parte de segurança aparece dessa forma:
	 <img width="899" height="569" alt="Pasted image 20260301160840" src="https://github.com/user-attachments/assets/dfbefd39-30d9-41bb-9257-e2c316516639" />
   
Em outros mais atuais ficaria algo assim:
1. Vá em:

	<img width="226" height="168" alt="Pasted image 20260301160952" src="https://github.com/user-attachments/assets/d66845a7-f977-45a8-8104-8d4ce2890d31" />
2. 
	<img width="841" height="197" alt="Pasted image 20260301161312" src="https://github.com/user-attachments/assets/ed9f92b4-981b-455a-b256-db75eec2044b" />
### Recommend Configs
- **Security Type/Versão**: WPA-PSK/WPA2-PSK | WPA2-PSK;
- **Encryption/Criptografia**: AES;
- **PSK Password/Senha do wireless**: "SuaSenha";
- **Group Key Update Period/Periodo de atualização da chave de grupo**: "value( 0 - ... )"
	- Recomendo colocar 7200, isso faria com que o dispositivo troque sua configuração do **GTK - Group Temporal Key** a cada 2 horas, evitando alguns tipos de ataque a sua rede. Em casos de problema com lentidão após esse período de tempo, aumente o intervalo entre as trocas **(6 horas -> 21600 | 12 horas -> 43200)**.
# Rede visitante 
(Cuidado que essa opção provavelmente vai afetar o desempenho da rede como um todo)
1. Procure essa opção (Não é todo dispositivo que possui essa função)
   
	<img width="225" height="96" alt="Pasted image 20260302152033" src="https://github.com/user-attachments/assets/96d87ed0-5a7d-4b6a-83cf-8fc2afc80a64" />
2. 
<img width="772" height="210" alt="Pasted image 20260302153818" src="https://github.com/user-attachments/assets/6fd7d19c-8671-4034-89ab-8ed075271168" />

- "**Permite Acesso de convidados à minha rede local** "-> Dispositivos convidados poderão se comunicar com os dispositivos na rede doméstica geral;
- "**Largura de Banda de Entrada para Rede de Convidados**" -> Recicla as regras de largura de banda do menu "Controle de largura de banda";
- "**Largura de Banda de Saída para Rede de Convidados**" -> Velocidade de upload da rede convidado;
- "**Largura de Banda de Entrada para Rede de Convidados**" -> Velocidade de download da rede convidado; 
4. Aqui é interessante configurar de forma parecida com as apresentadas em [Ir para Recommend Configs](#recommend-configs)
	<img width="764" height="435" alt="Pasted image 20260302160336" src="https://github.com/user-attachments/assets/fda2940e-7e6a-4242-97f7-c391c89cfe32" />
5. Modificações interessantes em "**Tempo de acesso:**"
	1.  A opção "**Agenda**" permite definir quando a rede ficará disponível.

		<img width="521" height="220" alt="Pasted image 20260302160621" src="https://github.com/user-attachments/assets/791ee9cd-c754-41ae-87ed-07f60272ba6f" />
	3. A opção "**Tempo Limite**" permite que você estipule um tempo para que a rede convidado fique ativa, depois desse tempo ela é completamente desativada.

		<img width="497" height="165" alt="Pasted image 20260302160856" src="https://github.com/user-attachments/assets/ac823667-9488-4e21-9886-d5e2702a9cb7" />

