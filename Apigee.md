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





# Montando validações em Post 

```

validateRequest();

function validateRequest() {
    
    var body = JSON.parse(context.getVariable('message.content'));
    
    var errorDescription = null;
  
    if (!body.data.troubleTicket.associatedDocument || !body.data.troubleTicket.customer.name || !body.data.troubleTicket.customer.subscriberId) {
        errorDescription = 'OSB Validate action failed validation';
    } 
    
    for (var i in body.data.troubleTicket.addresses) {
        if (!body.data.troubleTicket.addresses[i].id) {
            errorDescription = 'OSB Validate action failed validation';
        }
    }
    
    if (errorDescription) {
        context.setVariable('validatePayloadValues.error', errorDescription);
        context.setVariable('validatePayloadValues.fail', true);
        context.setVariable('errorDescription.error', errorDescription);
    }
}


```
