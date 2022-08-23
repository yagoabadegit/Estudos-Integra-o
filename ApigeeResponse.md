
# Montando um response de um metodo POST 

´´´

try {
	// Declarando valor na variavel contentResponse
	var contentResponse = JSON.parse(context.getVariable('response.content'));


	// Payload Composition
	var msg = {
		apiVersion: context.getVariable('apiVersion') || "1",
		transactionId: context.getVariable('transactionId'),
		data: {
			hpId: contentResponse.data.hpId,
			message: contentResponse.data.message

		}
	};

	// set response in context
	response.content = JSON.stringify(msg);

} catch (e) {
	context.setVariable('customfault.name', 'ResponseTransform');
	throw new Error(e);
}
 ´´´´
