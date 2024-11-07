<html>
<style type='text/css'>
	.embeddedServiceHelpButton .helpButton .uiButton {
		background-color: #005290;
		font-family: "Arial", sans-serif;
	}
	.embeddedServiceHelpButton .helpButton .uiButton:focus {
		outline: 1px solid #005290;
	}
</style>

<script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
<script type='text/javascript'>
	var initESW = function(gslbBaseURL) {
		embedded_svc.settings.displayHelpButton = true; //Or false
		embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

		embedded_svc.settings.enabledFeatures = ['LiveAgent'];
		embedded_svc.settings.entryFeature = 'LiveAgent';

		embedded_svc.settings.prepopulatedPrechatFields = {
		    FirstName: "Test",
		    LastName: "Test",
		    Email: "test@test.com",
		    Subject: "Testing"
		};

		embedded_svc.settings.extraPrechatFormDetails = [ {
			"label" : "Site",
			"value" : window.location.href,
			"transcriptFields" : [ "Chat_Site__c" ]
		} ];

		embedded_svc.init(
			'https://infallibletechie-a-dev-ed.my.salesforce.com',
			'https://infallibletechie-a-dev-ed.my.salesforce-sites.com/',
			gslbBaseURL,
			'00D5f000001yyfh',
			'Embedded_Service_Chat_with_BOT',
			{
				baseLiveAgentContentURL: 'https://c.la4-c1-ia4.salesforceliveagent.com/content',
				deploymentId: '5725f000000hFSd',
				buttonId: '5735f000000hG5H',
				baseLiveAgentURL: 'https://d.la4-c1-ia4.salesforceliveagent.com/chat',
				eswLiveAgentDevName: 'EmbeddedServiceLiveAgent_Parent04I5f000000c9hqEAA_1882751481a',
				isOfflineSupportEnabled: false
			}
		);
	};

	if (!window.embedded_svc) {
		var s = document.createElement('script');
		s.setAttribute('src', 'https://infallibletechie-a-dev-ed.my.salesforce.com/embeddedservice/5.0/esw.min.js');
		s.onload = function() {
			initESW(null);
		};
		document.body.appendChild(s);
	} else {
		initESW('https://service.force.com');
	}
</script>
</html>
