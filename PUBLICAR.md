# Publicar Android System Pro no GitHub Pages

## 1. Enviar os arquivos do site
Copie o `index.html` deste pacote para a raiz do repositório `androi` e faça commit/push.
O GitHub Pages deve estar configurado para publicar a partir da branch principal e da pasta `/ (root)`.

## 2. Preparar a compilação automática
Copie `.github/workflows/build-apk.yml` para o mesmo caminho no repositório.
O workflow compila o APK quando uma tag `v*` é enviada e publica o arquivo como ativo de um GitHub Release.

## 3. Colocar o projeto Android na raiz
A raiz do repositório precisa conter `settings.gradle.kts`, `build.gradle.kts`, `gradle.properties` e a pasta `app/` do projeto AndroidSystemPro.
Não coloque o conteúdo do README no lugar do `index.html`.

## 4. Criar a primeira versão
No terminal, dentro do repositório:
    git add .
    git commit -m "Publica Android System Pro"
    git push
    git tag v1.0.0
    git push origin v1.0.0

Acesse a aba Actions e espere o workflow terminar. Depois, abra Releases e confira se o APK foi anexado.

## 5. Link de download
O botão do site aponta para:
https://github.com/hackermesteriozo-blip/androi/releases/latest/download/AndroidSystemPro.apk

ATENÇÃO: a compilação de exemplo gera `app-debug.apk`. Para o link acima funcionar com esse nome, renomeie o arquivo no workflow ou ajuste o nome do ativo e do link. O workflow abaixo publica o arquivo como `app-debug.apk`; portanto, use o link:
https://github.com/hackermesteriozo-blip/androi/releases/latest/download/app-debug.apk

Este pacote é um site de download e automação de compilação. Ele não contém um APK já compilado.
