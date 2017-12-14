HTML

<form>
  <fieldset>
  <legend>Choose your interests</legend>
    <div>
      <input type="checkbox" id="coding" name="interest" value="coding">
      <label for="coding">Coding</label>
    </div>
    <div>
      <input type="checkbox" id="music" name="interest" value="music">
      <label for="music">Music</label>
    </div>
    <div>
      <input type="checkbox" id="art" name="interest" value="art">
      <label for="art">Art</label>
    </div>
    <div>
      <input type="checkbox" id="sports" name="interest" value="sports">
      <label for="sports">Sports</label>
    </div>
    <div>
      <input type="checkbox" id="cooking" name="interest" value="cooking">
      <label for="cooking">Cooking</label>
    </div>
    <div>
      <input type="checkbox" id="other" name="interest" value="other">
      <label for="other">Other</label>
      <input type="text" id="otherValue" name="other">
    </div>
    <div>
      <button type="submit">Submit form</button>
    </div>
  </fieldset>
</form>


CSS

html {
  font-family: sans-serif;
}

form {
  width: 600px;
  margin: 0 auto;
}

div {
  margin-bottom: 10px;
}

fieldset {
  background: cyan;
  border: 5px solid blue;
}

legend {
  padding: 10px;
  background: blue;
  color: cyan;
}

#otherValue
{
  display: none;
}

#other:checked ~ #otherValue
{
  display: inline-block;
}

estudar essas 2 ultimas


Quando o formulário é submetido, name=value -> titleIncricao=free
Se o value attribute for omitido, o default value for the checkbox is on,
então quando os dados forem submitidos -> name=on -> titleIncricao=on
Se a checkbox está sem o check quando o form é submetido (value=unchecked),
o valor não é enviado ao servidor

Se os checkbox estão com o mesmo name, eles estão todos relacionados
Se ambos estão checked e então o form is submitted,
uma string será enviada name=value&name=value
titleIncricao=free&titleIncricao=payment
Esses dados são recebidos do lado do servidor como um Array que relaciona valor com descrição

Se colocar o atributo "checked" em algum dos inputs, ele já vem selecionado no navegador



De qualquer forma, o navegador entenderá que a checkbox deve ser assinalada. Uma coisa importante de se dizer é que a propriedade value é inútil. Explico, se o controle for clicado, o valor que é enviado para o servidor é value=on e se NÂO clicado, o valor é value=off, certo??? Errado, e isso é muito triste! Quando o controle não é clicado ele não envia nada, nada mesmo. Quando é clicado, ele envia o valor que você especificar na propriedade value.




Por causa do FOR ligado ao ID
Nos exemplos acima, você pode ter notado que você pode alternar uma caixa de seleção clicando em seu elemento <label> associado, bem como na própria caixa de seleção. Esta é uma característica realmente útil dos rótulos de formulários HTML que facilita o clique na opção desejada, especialmente em dispositivos de tela pequena como smartphones.

  Além da acessibilidade, esta é outra boa razão para configurar corretamente os elementos <label> em seus formulários.


<input> types - https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/Input
  <input type="button">
  <input type="checkbox">
  <input type="color">
  <input type="date">
  <input type="datetime">
  <input type="datetime-local">
  <input type="email">
  <input type="file">
  <input type="hidden">
  <input type="image">
  <input type="month">
  <input type="number">
  <input type="password">
  <input type="radio">
  <input type="range">
  <input type="reset">
  <input type="search">
  <input type="submit">
  <input type="tel">
  <input type="tel">
  <input type="text">
  <input type="time">
  <input type="url">
  <input type="week">


Como estilizar o placeholder do input.... Mega interessante, entender melhor...
https://www.todoespacoonline.com/w/2014/07/estilizar-placeholder-dos-inputs/


Ler melhor... Como fazer formulários...
https://developer.mozilla.org/pt-BR/docs/Web/Guide/HTML/Forms/Meu_primeiro_formulario_HTML


30 seletores de CSS que precisamos saber de cor
https://code.tutsplus.com/tutorials/the-30-css-selectors-you-must-memorize--net-16048

Outros desenhos possíveis de fazer nos inputs Checkbox
http://cssdeck.com/labs/css-checkbox-styles


CSS form
https://www.w3schools.com/css/css_form.asp


/*Fazer post sobre como trabalhar com variáveis no CSS*/



cartao.on ("focusin" , function () {
  cartao.addClass ("cartao--focado")
})

cartao.on ("focusout" , function () {
  cartao.removeClass("cartao--focado")
})

cartao.on ("change" , ".opcoesDoCartao-radioTipo" , function mudaCor (event) {
  cartao.css("background-color" , event.target.value)
})

cartao.on ("keydown" , function deixaClicarComEnter (event) {
  if (event.target.classList.contains ("opcoesDoCartao-opcao") && (event.key == "Enter" || event.key == " ")) {
    event.target.click ()
  }
})

cartao.on ("click" , function (event) {
  const elementoSelecionado = event.target
  if (elementoSelecionado.classList.contains ("opcoesDoCartao-remove")) {
    cartao.addClass ("cartao--some")
    cartao.on ("transitionend" , function () {
      cartao.remove()
    })
  }
})
