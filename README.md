# Android-Environment

## This is a step-by-step of how to configure an android environment

### I made this because every time i try to configure my environment to work along with expo, react-native and an emulator, everything goes wrong, so steps is:

* Baixe somente as ferramentas de linha de comando(cmdline-tools):

[CMDLINE-TOOLS está geralmente no final da página](https://developer.android.com/studio?hl=pt-br)

* Descompacte o arquivo e pegue o conteúdo dele(cmdline-tools) e jogue para dentro de uma nova pasta(de preferencia na sua home) chamada androidtools.
* Dentro desta pasta crie outra chamada skd e jogue novamente a pasta cmdline-tools para dentro de sdk e após isso dentro da pasta sdk crie outra chamada tools e jogue os 4 items dentro dela, no final ficará:

```<sua_home>/android-tools/sdk/cmdline-tools/tools```

* Instale o JAVA:

jre:
```sudo apt install default-jre```

jdk:
```sudo apt install default-jdk```

* Para as variáveis de ambiente:

* Para JAVA_HOME, procure o diretório do java(geralmente a pasta jvm em /usr/lib/jvm), copie o caminho até esta pasta colocando um / no final e escrevendo o nome da pasta do java que está no formato:

```/usr/lib/jvm/java-<versao instalada>/openjdk-amd-64```

* Continuando, pegue esse caminho, salve em um txt para usarmos mais para frente.

* Para ANDROID_HOME, peque o caminho usado antes que era "<sua_home>/android-tools/sdk/cmdline-tools/tools" e tire uma parte dele mantendo apenas:

```<sua_home>/android-tools/sdk```

* Continuando, pegue esse caminho e salve no mesmo txt criado acima.

* Após tudo isso, entre no terminal e escreva nano ~/.bashrc e aperte enter, dentro dele cole o seguinte:

```

export JAVA_HOME=<aqui voce o seu caminho do java que tá no txt>

export PATH=$JAVA_HOME/bin:$PATH

export ANDROID_HOME=<aqui voce cola o caminho do android que tmb tá no txt>

export PATH=$ANDROID_HOME/cmdline-tools/tools/bin:$PATH

```

* Depois disso salve o arquivo correntamente seguindo os padroes do nano(ctrl + o, enter, ctrl + x). Após fechar o arquivo rode:

```source ~/.bashrc```

* Agora é possivel usar comandos de cmd do android no terminal, ent execute os seguintes comandos:

update:
```sdkmanager --update```

install packages:
```sdkmanager "build-tools;30.0.3" "platform-tools" "platforms;android-30" "tools"```

licenses:
```sdkmanager --licenses```

* No ultimo comando é necessário aceitar todos os termos.

## Feito, após isso voce já pode redirecionar seu app expo apertando a letra a dentro do servidor expo criado com "npx expo start" para dentro de um emulador instalado, pode ser genymotion ou qualquer um outro.
