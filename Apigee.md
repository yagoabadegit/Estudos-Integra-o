# Exemplos

# Montando requisição para um metodo GET com parametros enviados via queryparam comt
```
var campoRequestAntigo1 = context.getVariable('request.queryparam.campoRequestAntigo1');
var campoRequestAntigo2 = context.getVariable('request.queryparam.campoRequestAntigo2');
var campoSemAlteração = context.getVariable('request.queryparam.campoSemAlteração');



// Remove X-QueryString and QueryParameters
if(campoRequestAntigo1){
    context.setVariable('request.queryparam.novoCampo1', campoRequestAntigo1);
    context.removeVariable('request.queryparam.campoRequestAntigo1');
}
if(campoRequestAntigo2){
    context.setVariable('request.queryparam.novoCampo2', campoRequestAntigo2);
    context.removeVariable('request.queryparam.campoRequestAntigo2');
}
// Lembrando que caso o nome do novo request permaneça o mesmo para o backend não coloca o context.removeVariable!
if(campoSemAlteração){
    context.setVariable('request.queryparam.novoCampo3', campoSemAlteração);
}
```


# Montando requisições para um metodo GET

# Montando trasformações basicas em um metodo Post/sem arrays

```
var body = JSON.parse(context.getVariable('message.content'));
var msg = {};
if (!body.data.campoObrigatorio1 || !body.data.campoObrigatorio2) {
	context.setVariable('customfault.name', 'ParameterValidation');
	throw new Error('ParameterValidation');
}



msg = {
	order: {
		CampoobrigatorioBackend1: body.data.campoObrigatorio1,
		CampoobrigatorioBackend2: body.data.campoObrigatorio2,
		CampoObjectBackend2: {
			Campo1BackendComum1: body.data.appointment.Campo1APIComum1,
			Campo1BackendComum2: body.data.appointment.Campo1APIComum2,
			Campo1BackendComum3: body.data.appointment.Campo1APIComum3
		},
		CampoObjectBackend1: {
			Campo1BackendComum1: body.data.issue.Campo1APIComum1,
			Campo1BackendComum2: body.data.issue.Campo1APIComum2,
			Campo1BackendComum3: body.data.issue.Campo1APIComum3
		}
	}
}

var orderId = context.getVariable('orderId');

var request = JSON.stringify(msg);
context.setVariable('request.content', request);

```
# Explicando o codigo 

- Esse trecho você esta usando o JSON.parse para que ele faça uma tranformação na estrutura do body da requisição que é um JSON que vem na arvore do message.content, e construindo o valor em um objeto JavaScript.

```
var body = JSON.parse(context.getVariable('message.content'));

```

- Criando um variavel "msg" em que seu valor é um objeto vazio.

```

var msg = {};

```

- Condição criada para verificar se os campos obrigatorios 1 e 2 estão vindo. E caso não estejam vindo caem na exceção de Error e no fim nos retornam BadRequest. 

#### Campos que dever ser alterados: ####

**campoObrigatorio1** =  Dependendo da necessidade do seu Swagger não só o campo como o estrutura devem ser aletrados. Ex: Poderia ser ".data.outroObject.campoObrigatorio1" ".data.campoObrigatorio1"  

**campoObrigatorio2** = Dependendo da necessidade do seu Swagger não só o campo como o estrutura devem ser aletrados ".Ex: Poderia ser ".data.outroObject.campoObrigatorio2" ".data.campoObrigatorio2"

```

if (!body.data.campoObrigatorio1 || !body.data.campoObrigatorio2) {
	context.setVariable('customfault.name', 'ParameterValidation');
	throw new Error('ParameterValidation');
}

```
- Neste trecho estou construindo literalemente a estrutura que o meu backend espera receber. Por que estou pegando o valor dos campos que estão vindo no payload que estou enviando(body.data......) e atribuindo eles nos campos e estruturas que o meu backend espera receber 

```
msg = {
	order: {
		CampoobrigatorioBackend1: body.data.campoObrigatorio1,
		CampoobrigatorioBackend2: body.data.campoObrigatorio2,
		CampoObjectBackend2: {
			Campo1BackendComum1: body.data.appointment.Campo1APIComum1,
			Campo1BackendComum2: body.data.appointment.Campo1APIComum2,
			Campo1BackendComum3: body.data.appointment.Campo1APIComum3
		},
		CampoObjectBackend1: {
			Campo1BackendComum1: body.data.issue.Campo1APIComum1,
			Campo1BackendComum2: body.data.issue.Campo1APIComum2,
			Campo1BackendComum3: body.data.issue.Campo1APIComum3
		}
	}
}

````

# Montando trasformações basicas em um metodo Post/com arrays

```

var ArrayList = [];    
var Array1 = [];       

if(body.data.objectQueContemOArray){
    ArrayList = body.data.objectQueContemOArray;
    for (var i in ArrayList){
        c = {
            Campo1BackendComum1: ArrayList[i].Campo1APIComum1,
            Campo1BackendComum2: ArrayList[i].Campo1APIComum2,
            Campo1BackendComum3: ArrayList[i].Campo1APIComum1,
        }
        Array1.push(c);
    }
}


var body = JSON.parse(context.getVariable('message.content'));
var msg = {};
if (!body.data.campoObrigatorio1 || !body.data.campoObrigatorio2) {
	context.setVariable('customfault.name', 'ParameterValidation');
	throw new Error('ParameterValidation');
}

msg = {
	order: {
		CampoobrigatorioBackend1: body.data.campoObrigatorio1,
		CampoobrigatorioBackend2: body.data.campoObrigatorio2,
		CampoObjectBackend2: {
			Campo1BackendComum1: body.data.appointment.Campo1APIComum1,
			Campo1BackendComum2: body.data.appointment.Campo1APIComum2,
			Campo1BackendComum3: body.data.appointment.Campo1APIComum3
		},
		CampoObjectBackend1: {
			Campo1BackendComum1: body.data.issue.Campo1APIComum1,
			Campo1BackendComum2: body.data.issue.Campo1APIComum2,
			Campo1BackendComum3: body.data.issue.Campo1APIComum3
		}
		objectQueContemOArray: {
                ArrayList: Array1
            }
	}
}

var request = JSON.stringify(msg);
context.setVariable('request.content', request);





````





