<html>
    <head>
    </head>
    <body>
        <h1>
        Legacy Chat Test
        </h1>
        <button onclick="showChat()">Show Chat</button>   
	    
        <style type='text/css'>
		.embeddedServiceHelpButton .helpButton .uiButton {
			background-color: #1874AE;
			font-family: "Arial", sans-serif;
		}
		.embeddedServiceHelpButton .helpButton .uiButton:focus {
			outline: 1px solid #1874AE;
		}
	</style>

	<script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
	<script type='text/javascript'>
		var initESW = function(gslbBaseURL) {
			embedded_svc.settings.displayHelpButton = false; // Hide Chat Button
			embedded_svc.settings.language = 'en-US';
			   embedded_svc.settings.prepopulatedPrechatFields = {
				    FirstName: 'John',
				    LastName: 'Doe',
				    Email: 'john.doe@salesforce.com'
			    };
       embedded_svc.settings.extraPrechatFormDetails = [ {
	"label" : "First Name",
	"value" : 'John Doe',
	"transcriptFields" : [ "First_Name__c" ]
} ];
	
			embedded_svc.settings.enabledFeatures = ['LiveAgent'];
			embedded_svc.settings.entryFeature = 'LiveAgent';
	
			embedded_svc.init(
				'https://spglobal--miomega.sandbox.my.salesforce.com',
				'https://support-omega.visiblealpha.com/',
				gslbBaseURL,
				'00DD10000004XJx',
				'Visible_Alpha_Support_Insights',
				{
					baseLiveAgentContentURL: 'https://c.la12s-core1.sfdc-lywfpd.salesforceliveagent.com/content',
					deploymentId: '572Nq000004dOpl',
					buttonId: '573Nq000001KiU9',
					baseLiveAgentURL: 'https://d.la12s-core1.sfdc-lywfpd.salesforceliveagent.com/chat',
					eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04INq0000005SWjMAM_195eb6be12a',
					isOfflineSupportEnabled: false
				}
			);
		};
	
		if (!window.embedded_svc) {
			var s = document.createElement('script');
			s.setAttribute('src', 'https://spglobal--miomega.sandbox.my.salesforce.com/embeddedservice/5.0/esw.min.js');
			s.onload = function() {
				initESW(null);
			};
			document.body.appendChild(s);
		} else {
			initESW('https://service.force.com');
		}
	</script>


	<script>
		/** Script to show chat dialog on button click **/
 		function showChat() {
	       		console.log('show chat');
	  embedded_svc.bootstrapEmbeddedService();
	  /**
			  embedded_svc.liveAgentAPI.startChat({
			        directToAgentRouting: {
			          buttonId: "573Nq000001KiU9",
			          fallback: true
			        },
			        extraPrechatInfo: [],
			        extraPrechatFormDetails: []
	      		});**/
	       	}
	 </script>
    </body>
</html>
