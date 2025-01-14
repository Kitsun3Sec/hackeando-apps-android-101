# Configurando Ambiente de Testes

Durante o livro utilizaremos emuladores de Android para os testes. Utilizaremos tanto a aplicação Genymotion como o emulador do próprio Android Studio. Fique a vontade para escolher o que melhor se adaptar. Eu costumo utilizar mais o Genymotion.

### Genymotion - Emulador Android

Para instalar o Genymotion seja no windows, linux ou no MacOS é necessário criar uma conta e  realizar o download no seguinte site: https://www.genymotion.com/product-desktop/.

A instalação é simples como qualquer outra aplicação.

### Android Studio

A instalação do Android Studio também é fácil, uma vez que segue a lógica de aplicações windows. Mas ainda assim vamos tratar dessa instalação para assim descrever a criação de AVD (Android Virtual Device).

Os passos para a instalação são basicamente Next, Next e Finish como podem ser vistas na imagens abaix. É importante aceitar as licenças do Android SDK e Android SDK ARM para finalizar a instalação.

![alt text](image.png)

![alt text](image-1.png)

![alt text](image-2.png)

![alt text](image-3.png)

Agora só ir buscar um café enquanto espera a instalação.

![alt text](image-4.png)

As pastas das ferramentas que são instaladas juntos com o Android Studio podem ser localizadas nos seguintes caminhos:

##### MacOS

Android Emulator

```bash
/Users/USER/Library/Android/sdk/emulator
```

ADB

```bash
/Users/USER/Library/Android/sdk/platform-tools
```

##### Windows


##### Linux 


### BurpSuite 

Burpsuite é um proxy muito útil durante os testes de segurança em web e aplicações móveis. O burpusuite fica entre o cliente que em nosso contexto do livro são os aplicativos Android e o Servidor a qual a aplicação se comunica. 

A in
https://portswigger.net/burp/releases/professional-community-2024-1-1-6


### Jadx - Dex to Java Decompiler

A instalação da ferramenta Jadx é bem simples, uma vez que já existe um tutorial de instalação no repositório GitHub da própria ferramenta. Basta seguir os passos, de acordo com a sua arquitetura e Sistema Operacional que podem ser vistos na seguinte URL: https://github.com/skylot/jadx?tab=readme-ov-file#install

### Frida-Tools


### Objection


### ApkTools


### APK-mitm

#### MobSF



