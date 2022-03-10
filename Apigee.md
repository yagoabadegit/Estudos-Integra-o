# Exemplos



# Montando trasformações basicas em um metodo POst

```
var body = JSON.parse(context.getVariable('message.content'));
var msg = {};
if (!body.data.correlationOrderId || !body.data.associatedDocumentId) {
	context.setVariable('customfault.name', 'ParameterValidation');
	throw new Error('ParameterValidation');
}



msg = {
	order: {
		correlationOrder: body.data.correlationOrderId,
		associatedDocument: body.data.associatedDocumentId,
		appointment: {
			hasSlot: body.data.appointment.hasSlot,
			date: body.data.appointment.date,
			mandatoryType: body.data.appointment.mandatoryType,
			workOrderId: body.data.appointment.workOrderId
		},
		issue: {
			code: body.data.issue.code,
			observation: body.data.issue.note,
			userId: body.data.issue.userId,
			updateDate: body.data.issue.changeDate,
			action: body.data.issue.action
		}
	}
}

var orderId = context.getVariable('orderId');

var request = JSON.stringify(msg);
context.setVariable('request.content', request);
```
# Explicando o codigo 

Esse trecho você esta usando o JSON.parse para que ele faça uma tranformação na estrutura do body da requisição que é um JSON e vem na arvore do message.content, e construindo o valor ou um objeto JavaScript em um tipo que podemos trabalhar e manipular.

```
var body = JSON.parse(context.getVariable('message.content'));

```
