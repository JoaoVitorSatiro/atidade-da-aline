# **Atidade-da-aline**
## **Atividade sobre pesquisa javascript**
<hr>

>## *Tipo de Dados:*
### **tipo boolean:** representa uma entidade com dois valores(true, false);
```
let a= Boolean('Hi');
console.log(a); // true
console.log (typeof(a)); // boolean
```
### **tipo null:** tem valor nulo;<br>
```
// foo não existe, não foi definido e jamais foi inicializado:
> foo
"ReferenceError: foo is not defined"

// foo é conhecido e existe, mas não aponta para nenhum tipo ou valor:
> var foo = null; foo
"null"
```
### **tipo undefined:** ele aparece quando uma entidade fica sem valor;<br>
```
var myvar = "um valor";

(function() {
  var myvar;
  console.log(myvar); // undefined
  myvar = "valor local";
```
### **tipo numericos:** apresenta valores do tipo number e bigint;<br>
```
var meuLazer = new Function("5 + 2");
var forma = "redondo";
var tamanho = 1;
var hoje = new Date();
```
### **tipo number:** é capaz de armazena tipo de numeros de ponto flutuante;<br>
```
new Number(value);
var maxInt = 9007199254740992;
var minInt = -9007199254740992;
```
### **tipo bingint:** representa numeros do tipo inteiro além do limite;<br>
```
BigInt(value);
typeof 1n === 'bigint'; // true
typeof BigInt('1') === 'bigint'; // true
```
### **NaN:** é encontrado quando um numero não pode ser expresso;<br>
```
// Toma um BigInt como argumento e retorna um BigInt
function nthPrime(nth) {
  let maybePrime = 2n;
  let prime = 0n;

  while (nth >= 0n) {
    if (isPrime(maybePrime)) {
      nth -= 1n;
      prime = maybePrime;
    }
    maybePrime += 1n;
  }

  return prime;
}

nthPrime(20n)
// ↪ 73n
```
### **tipo string:** é usado para representar dados textuais;<br>
```
var str = "esta string \
está quebrada \
em várias\
linhas."
console.log(str);   // esta string está quebrada em várias linhas.
```
### **tipo symbol:** poe ser usado como chave de uma propriedade;<br>
```
let strname = "string name"; // Uma string para usar como um nome de propriedade
let symname = Symbol("propname"); // Um Symbol para usar como um nome de propriedade

typeof strname // => "string": strname é uma string
typeof symname = Symbol("propname"); // Um Symbol para usar como um nome de propriedade
let o = {}; // cria um novo objetivo
```
___
>## *Propriedade de Dados:*
### **value:** Valor do Java recuperado por um acesso da propriedade;<br>

```
var obj = { foo: "bar", baz: 42 };
console.log(Object.values(obj)); // ['bar', 42]

// array como objeto
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.values(obj)); // ['a', 'b', 'c']
```
### **gravável:** Valor do tipo Booleano que pode indicar se a propriedade pode ser alterada com uma atribuição;<br>
```
var pessoa = {
  nome: ['Bob', 'Smith'],
  idade: 32,
  sexo: 'masculino',
  interesses: ['música', 'esquiar'],
  bio: function() {
    alert(this.nome[0] + ' ' + this.nome[1] + ' tem ' + this.idade + ' anos de idade. Ele gosta de ' + this.interesses[0] + ' e ' + this.interesses[1] + '.');
  },
  saudacao: function() {
    alert('Oi! Eu sou ' + this.nome[0] + '.');
  }
};
```
### **enumerável:** Valor do tipo Booleano que indica se a propriedade pode ser enumerada por um loop;<br>
```
var o = {};

Object.defineProperty(o, 'a', {
  value: 1,
  enumerable: true
});

Object.defineProperty(o, 'b', {
  value: 2,
  enumerable: false
});
```
### **configurável:** Valor do tipo Booleano que indica se a propriedade pode ser excluída ou alterada para uma propriedade acessora e pode ter seus atributos alterados;<br>
```
 var o = {};

Object.defineProperty(o, 'a', {
  get: function() { return 1; },
  configurable: false
});

Object.defineProperty(o, 'a', {
  configurable: true
}); // lança um TypeError
```
___
>## *Estrutura de Repetição:*
### **do...While(enquanto):** a condição vai se repetir até que se torne falsa;<br>
```
var resultado = '';
var i = 0;
do {
   i += 1;
   resultado += i + ' ';
} while (i < 5);
document.getElementById('exemplo').innerHTML = resultado;
```
### **for:** se repete até que a condição específica seja falsa;<br>
```
for (var i = 0; i < 5; i++) {
    // Will execute 5 times
}
```
### **while:** executa seuas funções desde que sua condição seja verdadeira;<br>
```
var n = 0;
var x = 0;

while (n < 3) {
  n++;
  x += n;
}
```
### **label:** serve para identificar um laço, e então usar break ou continue, para saber se deve interromper ou continuar;<br>
```
label :
   declaração

   var i, j;

loop1:
for (i = 0; i < 3; i++) {      //O primeiro 'for' é etiquetado(label) com "loop1"
   loop2:
   for (j = 0; j < 3; j++) {   //O segundo é etiquetado(label) com "loop2"
      if (i == 1 && j == 1) {
         continue loop1;
      } else {
         console.log("i = " + i + ", j = " + j);
      }
   }
}
```
### **break:** serve para interromper laços ou conjuntos;<br>
```
var allPass = true;
var i, j;

top:
for (i = 0; items.length; i++)
  for (j = 0; j < tests.length; i++)
    if (!tests[j].pass(items[i])){
      allPass = false;
      break top;
    }
```
### **continue:** serve para reiniciar uma instrução;<br>
```
var itemsPassed = 0;
var i, j;

top:
for (i = 0; i < items.length; i++){
  for (j = 0; j < tests.length; j++)
    if (!tests[j].pass(items[i]))
      continue top;
  itemsPassed++;
}
```
### **for...in:** executa iterações de uma variável específica;<br>
```
for (let variavel in objeto) {
    faça...
}
```
### **for...of:** serve para criar laços com objetos iterativos;<br>
```
for (let variavel of objeto) {
    faça
}
```
___
>## *Estruturas Condicionais:*
### **if(se):** serve para executar comandos que estão no bloco caso seu condição seja verdadeira;<br>
```
if (idade > 15 && idade < 18 || idade > 70){
	console.log("O voto é opcional");
}
```
### **else(senão):** serve para executar uma condição de outro bloco caso seja falsa;<br>
```
// Valor atribuído à variável mensagem: “Pare”
semaforo = "vermelho";

if (semaforo == "verde") {
    mensagem = "Pode passar";
} else {
    mensagem = "Pare";
}
```
### **else if:** permite executar alterações de um codigo entre duas opções;<br>
```
if (x > 5) {

} else if (x > 50) {

} else {

}
```
### **if ternário:** várias formas de se utilizar uma condição para a verificação;<br>
```
resultado = (a > b) ? "a é maior que b" : "b é maior que a";

if (a > b) {
    resultado = "a é maior que b";
} else {
    resultado = "b é maior que a";
}
```
### **&&:** sua forma de trabalho possibilita executar um código de forma parecida do if;<br>
```
var a1 =  true && true;     // t && t retorna true
var a2 =  true && false;    // t && f retorna false
var a3 = false && true;     // f && t retorna false
var a4 = false && (3 == 4); // f && f retorna false
var a5 = "Gato" && "Cão";   // t && t retorna Cão
var a6 = false && "Gato";   // f && t retorna false
var a7 = "Gato" && false;   // t && f retorna false
```
___
>## *Switch case:*
### **switch:** serve para selecionar blocos de códigos;<br>
```
switch(action) {
    case 'draw':
        drawit();
        break;
    case 'eat':
        eatit();
        break;
    default:
        donothing();
}
```
Quando o JavaScript atinge uma break, isso fara ele sair do bloco switch, assim, interrompendo a execução do bloco;<br>
A default serve para especificar o código a ser executado se não houver correspondencia de maiusculas e minúsculas;<br>
Detalhes de troca - se varios casos corresponderem a um valor de caso, o primeiro caso será selecionado, se nenhum caso correspondente for encontrado, o programa continua funcionando normalmente;<br>
Comparação estrita - os casos de troca usam comparação estrita, os valores devem serdo mesmo tipo para corresponder, essa comparação sera considerada verdadeira caso os operandos sejam do mesmo tipo;<br>
___
>## *Elementos Gráficos do Androis Studio:*
### **View:** serve para que o usuário utilize para visualizar ou interagir com algo;<br>
```
   <View ...
           android:tag="@string/mytag_value" />
     <View ...>
         <tag android:id="@+id/mytag"
              android:value="@string/mytag_value" />
     </View>
```
### **viewgroup:** é uma caixa invisível que estrutura o layout para o view;<br>
```
<ViewGroup
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@[+][package:]id/resource_name"
    android:layout_height=["dimension" | "match_parent" | "wrap_content"]
    android:layout_width=["dimension" | "match_parent" | "wrap_content"]
    [ViewGroup-specific attributes] >
    <View
        android:id="@[+][package:]id/resource_name"
        android:layout_height=["dimension" | "match_parent" | "wrap_content"]
        android:layout_width=["dimension" | "match_parent" | "wrap_content"]
        [View-specific attributes] >
        <requestFocus/>
    </View>
    <ViewGroup >
        <View />
    </ViewGroup>
    <include layout="@layout/layout_resource"/>
</ViewGroup>
```
### **textview:** serve para definir um texto de um arquivo;<br>
```
android:text="Olá Androideiro!"
android background="@android:color/darker_gray"
android:layout_width="150dp"
android:layout_height="75dp"
```
### **requestfocus:** serve para manipular o foco de uma exibição específica;<br>
```
public final boolean requestFocus ()

public boolean requestFocus (int direction, 
                Rect previouslyFocusedRect)
```
### **setvisibility:** mostra ou esconde a visualização;<br>
```
public void setVisibility (int visibility)
```
### **button:** serve para que o usuário possa clicar num botão çara executar algo;<br>
```
android:text="Button"
android:layout_width="match_parent"
android:layout_height:"wrap_content"
android:id="@+id/button"
android:layout_weight="1"
android:onclick="onbuttonclicked"/>
```
### **linearlayout:** serve para organizar informações ou comandos na horizontal em  uma coluna só ou uma linha;<br>
```
xmlns:android="http://achemas.android.com/apk/res/android"
android:orientation="vertical"
android:layout_width:"wrap_content"
android:layout_heigth="wrap_content"
```
### **editText:** serve para editar o texto exibido pelo usuário;<br>
```
<SomeLayout>
    .
    .
    <Edittext
        android:SomeAttribute1 = "Value of attribute1"
        android:SomeAttribute2 = "Value of attribute2"
        .
        .
        android:SomeAttributeN = "Value of attributeN"/>
    .
    .
</SomeLayout>
```
___