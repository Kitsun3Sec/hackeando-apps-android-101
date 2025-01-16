# Configurando Ambiente de Testes

Durante o livro utilizaremos emuladores de Android para os testes. Utilizaremos tanto a aplicação Genymotion como o emulador do próprio Android Studio. Fique a vontade para escolher o que melhor se adaptar. Eu costumo utilizar mais o Genymotion.

### Genymotion - Emulador Android

Para instalar o Genymotion seja no windows, linux ou no MacOS é necessário criar uma conta e  realizar o download no seguinte site: https://www.genymotion.com/product-desktop/.

A instalação é simples como qualquer outra aplicação.

### Android Studio

A instalação do Android Studio também é fácil, uma vez que segue a lógica de aplicações windows. Mas ainda assim vamos tratar dessa instalação para assim descrever a criação de AVD (Android Virtual Device).

Os passos para a instalação são basicamente Next, Next e Finish como podem ser vistas na imagens abaixo. É importante aceitar as licenças do Android SDK e Android SDK ARM para finalizar a instalação.

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

Instaladores da versão Community e Professional podem ser encontrados na seguinte URL: https://portswigger.net/burp/releases/professional-community-2024-1-1-6


### Jadx - Dex to Java Decompiler

A instalação da ferramenta Jadx é bem simples, uma vez que já existe um tutorial de instalação no repositório GitHub da própria ferramenta. Basta seguir os passos, de acordo com a sua arquitetura e Sistema Operacional que podem ser vistos na seguinte URL: https://github.com/skylot/jadx?tab=readme-ov-file#install

### Frida-Tools - Dispositivo com root

O pacote de ferramenta frida é composto de alguns utilitários para a análise e instrumentação dinâmica. A instrumentação dinâmica é a ação de explorar o aplicativo enquanto ele está em execução (esse tema será abordado em outra seção desse e-book). As ferramentas que compõe o pacote são: frida (instrumentador dinâmico), frida-trace (permite que o pentester inpecione chamadas a funções), frida-ps (lista todos os processos (aplicativos) no dispositivo), frida-ls-devices (lista os dispositivos em que o frida (instrumentador dinâmico) pode se conectar.

Mas, e ai? Como instalar esse pacote de ferramentas?

O client é instalado bem facilmente, apenas por executar o comando: 

```bash
pip(2-3...) install frida-tools
```
e para remover, executa o comando:

```bash
pip(2-3...) uninstall frida-tools
```

Já o server, pois o tipo de comunicação do frida é client <-> server, pode ser instalado facilmente seguindo as etapas abaixo encontradas na documentação oficial do frida.

![image](https://github.com/user-attachments/assets/2977483e-2868-44d2-80b5-a0d74bb782af)

**Explicando o passo a passo da figura:**

1. Baixa o binário do frida-server no repositório oficial com base na sua arquitetura e sistema (https://github.com/frida/frida/releases);
2. `unxz frida-server.xz` Extrai o binário;
3. `adb root` Garante que o seu adb está com privilégio administrativo no sistema Android;
4. `adb push frida-server /data/local/tmp/` Faz o upload do binário do frida-server para o sistema Android no diretório /data/local/tmp;
5. `adb shell "chmod 755 /data/local/tmp/frida-server"` Concede as permissões para o binário ser executado corretamente;
6. `adb shell "/data/local/tmp/frida-server &"` Inicia o servidor do frida.

Obs: em alguns casos podem ocorrer o seguinte erro:

```bash
$ adb root
adbd cannot run as root in production builds
```

Em situações como essas, você poderá executar os comandos utilizando `adb shell "su -c comando"` como podemos ver a seguir:

```bash
$ adb shell "ls /data"
ls: /data: Permission Denied

$ adb shell "su -c ls /data"
adb
anr 
```

### Frida - Dispositivo sem root

### Objection

[Objection](https://github.com/sensepost/objection)

objection é um kit de ferramentas de exploração móvel em tempo de execução, desenvolvido pela Frida, tem como objectivo ajudá-lo a avaliar a postura de segurança de seus aplicativos móveis, sem a necessidade de jailbreak.

```bash
pip(2-3...) install objection
```

### LSPosed (Old XPosed) Framework

### AntiSplit

### ApkTools

### APK-mitm

#### MobSF

Mobile Security Framework (MobSF) é um scanner de vulnerabilidades para aplicações móveis. Utilizadas tanto para Android e iOS como para Windows Mobile. MobSF pode ser utilizado para diferentes propósitos como por exemplo Penetration Testing, Análise de Malware e Análise de Privacidade.

São suportados pelo scanner os seguintes tipos de arquivos para análise estática:
- APK;
- IPA;
- APPX;
- Código Fonte;

Para análise dinâmica são suportadas apenas as aplicações Android e iOS. Também é possível integrar o MobSF a esteira de desenvolvimento seguro.

Para utilizar com o docker basta realizar os seguintes comandos:

Baixar a imagem docker: 
```bash
docker pull opensecurity/mobile-security-framework-mobsf:latest
```
Executar um container docker com a aplicação no IP e porta https://0.0.0.0:8000. O login e senha para a plataforma é mobsf:mobsf.

```bash
docker run -it --rm -p 8000:8000 opensecurity/mobile-security-framework-mobsf:latest
```


