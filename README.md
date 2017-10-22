# Scrollbar-js

Script para personalizar a Scrollbar padrão do navegador ou qualquer parte da aplicação como menu vertical e etc.

# Requisitos

jQuery = Versão usada (3.2.1)

```
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
```
Observação: O plugin foi testado na versão 3.2.1 que até o momento é a ultima e mais atual versão do jQuery, porem você pode testar com a versão me mais lhe agradar. Creio que funcione com outras versões mais antigas.

# Modo de uso

Adicione ao head do seu projeto o arquivo CSS contido dentro da pasta "dist" do repositorio.<br>
Como falado acima este plugin usa a dependencia do jQuery então vamos importar-lo junto com o arquivo Scrollbar.js<br>
Assim como no exemplo abaixo:


```
<link href="css/Scrollbar.css" rel="stylesheet" />
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
```

Depois de adicionar o arquivo de estilo, vamos adicionar o arquivo JS antes do fechamento da body que vai iniciar a função e criar as div com as class.<br>
Assim como o exemplo abaixo:


```
<script src="js/Scrollbar.js"></script>
```

Já estamos carregando os arquivos vamos iniciar a função.<br>
Assim como no exemplo abaix:

```
<script>
  (function($){
      $(window).on("load",function(){
          $.mCustomScrollbar.defaults.scrollButtons.enable=true; //Ativar botoes (Setas)
          $(".conteudo").mCustomScrollbar({
            scrollInertia: 150 //Velocidade do Scroll
          });
      });
  })(jQuery);
</script>
```

No exemplo acima iniciei um codigo JS rapido antes do fechamento da BODY e antes do arquivo Scrollbar.js<br>
Neste trecho de codigo ele inicia a scroll bar personalizada da DIV com a class "conteudo".<br>
Crie a div com a class "conteudo", assim como o codigo abaixo:


```
<div class="conteudo" data-mcs-theme="dark">
   <!-- Aqui vai ficar seu conteudo -->
</div>
```

A função junto a div (data-mcs-theme="dark") chama a função com o tema "dark", voce pode trocar para qualquer tema, o como o "light" para deixar a barra na cor clara.<br>

Agora adicione o estilo abaixo para definir as medidas da div e desabilitar o overflow da BODY, como abaixo:

```
<style media="screen">
  .conteudo {
    height: 100%; /* Define altura vertical da DIV como 100% */
    position: absolute;
    width: 99%;
  }
  body {
    overflow-y: hidden; /* Desabilita o scroll da pagina */
  }
</style>
```

# Projeto final
Pronto! Dando tudo certo seu arquivo basico HTML vai estar da seguinte forma:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title></title>
    <link href="css/Scrollbar.css" rel="stylesheet">
    <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
  </head>
  <body>

    <div class="conteudo" data-mcs-theme="dark">
      <!-- Aqui vai ficar seu conteudo -->
    </div>


    <script>
      (function($){
          $(window).on("load",function(){
              $.mCustomScrollbar.defaults.scrollButtons.enable=true; //Ativar botoes (Setas)
              $(".conteudo").mCustomScrollbar({
                scrollInertia: 150 //Velocidade do Scroll
              });
          });
      })(jQuery);
    </script>

    <style media="screen">
      .conteudo {
        height: 100%; /* Define altura vertical da DIV como 100% */
        position: absolute;
        width: 99%;
      }
      body {
        overflow-y: hidden; /* Desabilita o scroll da pagina */
      }
    </style>

    <script src="js/Scrollbar.js"></script>
  </body>
</html>

```

Onde esta escrito "```<!-- Aqui vai ficar seu conteudo -->```" apague e coloque seu conteudo, pois de imediato não vai aparecer a barra pois não tem nada para rolar para baixo, mais conforme colocar conteudo ele vai aparecer.

# Creditos e Informações

Você pode ver mais sobre o modulo no site: http://manos.malihu.gr/jquery-custom-content-scroller/ <br>
Temas para sua scrollbar personalizadas: http://manos.malihu.gr/repository/custom-scrollbar/demo/examples/scrollbar_themes_demo.html
