# Arquitetura Android

## O que é o Android

Android é um Sistema Operacional de Código aberto para dispositivos móveis e tem como base o Kernel Linux.

Em 22 de Outubro de 2008, foi lançado o primeiro smartphone utilizando esse Sistema Operacional no mercado. O fabricante  HTC Dream lançou o modelo T-Mobile com objetivo de competir diretamente com os celulares Sybiam, BlackBerry, Windows e a segunda geração de Iphones.

Os aplicativos Android geralmente são desenvolvidos em linguagens como Java, Kotlin. Não é necessário programar nessas linguagens para entender o conteúdo desse livro ou de artigos que falem sobre pentest em aplicações android, mas é extremamente necessário entender Lógica de Programação e conhecimento em alguma outra linguagem que facilite a leitura dos códigos que veremos durante nossos laboratórios.

## Visão geral AOSP

O Android Open Source Project (AOSP) está disponível publicamente e é um código-fonte modificável do Android. Qualquer pessoa pode fazer o download e modificar o AOSP para o dispositivo. O AOSP fornece uma implementação completa e totalmente funcional da plataforma móvel Android.

A pilha de software do AOSP contém as seguintes camadas:

![alt text](https://source.android.com/static/images/android-stack.svg?hl=pt-br)


#### App Android
Um app criado exclusivamente usando a API Android. A Google Play Store é amplamente usada para encontrar e fazer o download de apps Android, embora existam muitas outras alternativas. Em alguns casos, o fabricante de um dispositivo pode querer pré-instalar um app Android para oferecer suporte à funcionalidade principal do dispositivo. Se você tiver interesse em desenvolver apps Android, consulte developers.android.com.

#### App privilegiado
Um app criado usando uma combinação das APIs do Android e do sistema. Esses apps precisam ser pré-instalados como apps privilegiados em um dispositivo.

#### App do fabricante do dispositivo
Um app criado usando uma combinação da API do Android, da API do sistema e acesso direto à implementação do framework do Android. Como um fabricante de dispositivos pode acessar diretamente APIs instáveis no framework do Android, esses apps precisam ser pré-instalados no dispositivo e só podem ser atualizados quando o software do sistema do dispositivo é atualizado.

#### API System
A API System representa APIs do Android disponíveis apenas para parceiros e OEMs para inclusão em aplicativos agrupados. Essas APIs são marcadas como @SystemApi no código-fonte.

#### API do Android
A API Android é a API disponível publicamente para desenvolvedores de apps Android de terceiros. Para informações sobre a API do Android, consulte a Referência da API do Android.

#### Framework do Android
Um grupo de classes, interfaces e outros códigos pré-compilados do Java em que os apps são criados. Partes do framework são acessíveis publicamente pelo uso da API do Android. Outras partes do framework estão disponíveis apenas para OEMs usando as APIs do sistema. O código do framework do Android é executado dentro do processo de um app.

#### Serviços do sistema
Os serviços do sistema são componentes modulares e focados, como system_server, SurfaceFlinger e MediaService. A funcionalidade exposta pela API do framework do Android se comunica com os serviços do sistema para acessar o hardware.

#### Ambiente de execução do Android (ART)
Um ambiente de execução Java fornecido pelo AOSP. O ART realiza a tradução do bytecode do app em instruções específicas do processador que são executadas pelo ambiente de execução do dispositivo.

#### Camada de abstração de hardware (HAL)
Uma HAL é uma camada de abstração com uma interface padrão para fornecedores de hardware implementarem. As HALs permitem que o Android seja independente em relação a implementações de drivers de nível inferior. O uso de um HAL permite implementar funcionalidades sem afetar ou modificar o sistema de nível superior. Para mais informações, consulte a visão geral do HAL.

#### Daemons e bibliotecas nativos
Os demônios nativos nessa camada incluem init, healthd, logd e storaged. Esses demônios interagem diretamente com o kernel ou outras interfaces e não dependem de uma implementação de HAL baseada no espaço do usuário.

As bibliotecas nativas nessa camada incluem libc, liblog, libutils, libbinder e libselinux. Essas bibliotecas nativas interagem diretamente com o kernel ou outras interfaces e não dependem de uma implementação HAL baseada no espaço do usuário.

#### Kernel
O kernel é a parte central de qualquer sistema operacional e se comunica com o hardware subjacente de um dispositivo. Sempre que possível, o kernel do AOSP é dividido em módulos independentes de hardware e específicos do fornecedor. Para conferir uma descrição, incluindo definições, de componentes do kernel do AOSP, consulte a Visão geral do kernel.

## Versionamento Android



## Estrutura de Aplicação Android

