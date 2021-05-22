<!DOCTYPE html>
<html lang="en">

    <head>
        <title>Code Editor</title>
        <meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  text-align: center;
}
header {
  margin: 10px;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}
span {
  flex-grow: 5;
  font-size: 30px;
  font-weight: bolder;
  color: #1c305e;
  text-align: left;
  margin-left: 50px;
}
#bu {
  width: 15%;
  align-items: flex-end;
}
.grid-html { grid-area: html; }
.grid-css { grid-area: css; }
.grid-js { grid-area: js; }
.grid-code { grid-area: code; }

.grid-container {
  display: grid;
  grid-template-areas:
    'html code'
    'css code'
    'js code';
  grid-gap: 10px;
  padding: 10px;
  height: 100%;
}
textarea { 
  width: 100%;
  min-height: 250px;
  overflow: scroll;
  margin: auto;
  display: inline-block;
  background: #e1e1e4;
  font-size: 13px;
}
textarea:focus {
  outline: none !important;
  border:2px solid #1c305e;
  box-shadow: 0 0 10px #719ECE;
}
.js {
}
iframe {
  bottom: 0;
  position: relative;
  width: 100%;
  height: 99%;
} 

</style>
    </head>
      
      <body>
        <div id="wrapper">
          <header>
            <span>Code Editor</span>
            <img id="bu" src="BU-logo.jpg" alt="Bryan University">
          </header>
          <div class="grid-container">
            <div class="input grid-html">
              <textarea id="html" placeholder="HTML"></textarea>
            </div>
            <div class="input grid-css">
              <textarea id="css" placeholder="CSS"></textarea>
            </div>
            <div class="input grid-js">
              <textarea id="js" placeholder="JavaScript"></textarea>
            </div>
            <div class="grid-code">
              <iframe id="code"></iframe>
            </div>
          </div>
          <footer>&copy; Bryan University </footer>
        </div>
    <script>
        function compile() {
            var html = document.getElementById("html");
            var css = document.getElementById("css");
            var js = document.getElementById("js");
            var code = document.getElementById("code").contentWindow.document;
            document.body.onkeyup = function () {
                code.open();
                code.writeln(html.value + "<style>" + css.value + "</style>" + "<script>" + js.value + "<\/script>");
            code.close();
            };
            };
            compile();
    </script>
</body>

</html>