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
                font-family: "Salesforce Sans", sans-serif;
            }
            .embeddedServiceHelpButton .helpButton .uiButton:focus {
                outline: 1px solid #1874AE;
            }
            @font-face {
                font-family: 'Salesforce Sans';
                src: url('https://c1.sfdcstatic.com/etc/clientlibs/sfdc-aem-master/clientlibs_base/fonts/SalesforceSans-Regular.woff') format('woff'),
                url('https://c1.sfdcstatic.com/etc/clientlibs/sfdc-aem-master/clientlibs_base/fonts/SalesforceSans-Regular.ttf') format('truetype');
            }
        </style>
	
        <script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
        <script type='text/javascript'>
            var initESW = function(gslbBaseURL) {
                embedded_svc.settings.displayHelpButton = false; //Or false
                embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'
        
                //embedded_svc.settings.defaultMinimizedText = '...'; //(Defaults to Chat with an Expert)
                //embedded_svc.settings.disabledMinimizedText = '...'; //(Defaults to Agent Offline)
        
                //embedded_svc.settings.loadingText = ''; //(Defaults to Loading)
                //embedded_svc.settings.storageDomain = 'yourdomain.com'; //(Sets the domain for your deployment so that visitors can navigate subdomains during a chat session)
        
                // Settings for Chat
                //embedded_svc.settings.directToButtonRouting = function(prechatFormData) {
                    // Dynamically changes the button ID based on what the visitor enters in the pre-chat form.
                    // Returns a valid button ID.
                //};
                //embedded_svc.settings.prepopulatedPrechatFields = {}; //Sets the auto-population of pre-chat form fields
                //embedded_svc.settings.fallbackRouting = []; //An array of button IDs, user IDs, or userId_buttonId
                //embedded_svc.settings.offlineSupportMinimizedText = '...'; //(Defaults to Contact Us)
		
                embedded_svc.settings.enabledFeatures = ['LiveAgent'];
                embedded_svc.settings.entryFeature = 'LiveAgent';
        
                embedded_svc.init(
                    'https://spglobal--devserv1.sandbox.my.salesforce.com',
                    'https://spglobal--devserv1.sandbox.my.site.com/VAHelpCenter',
                    gslbBaseURL,
                    '00D3J0000001MaO',
                    'Visible_Alpha_Support_Insights',
                    {
                        baseLiveAgentContentURL: 'https://c.la12s-core1.sfdc-lywfpd.salesforceliveagent.com/content',
                        deploymentId: '572O5000004bVc1',
                        buttonId: '573O50000016oZR',
                        baseLiveAgentURL: 'https://d.la12s-core1.sfdc-lywfpd.salesforceliveagent.com/chat',
                        eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04IO5000000EkPZMA0_195dd56bdfe',
                        isOfflineSupportEnabled: false
                    }
                );
            };
        
            if (!window.embedded_svc) {
                var s = document.createElement('script');
                s.setAttribute('src', 'https://spglobal--devserv1.sandbox.my.salesforce.com/embeddedservice/5.0/esw.min.js');
                s.onload = function() {
                    initESW(null);
                };
                document.body.appendChild(s);
            } else {
                initESW('https://service.force.com');
            }
        </script>
	<script>
 		function showChat() {
	       		console.log('show chat');
			  embedded_svc.liveAgentAPI.startChat({
			        directToAgentRouting: {
			          buttonId: "573O50000016oZR",
			          fallback: true
			        },
			        extraPrechatInfo: [],
			        extraPrechatFormDetails: []
	      		});
	       	}
	 </script>
    </body>
</html>
