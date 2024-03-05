<html>
  <body>
    <script type='text/javascript'>
	function initEmbeddedMessaging() {
    console.log('inside initEmbeddedMessaging');
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			embeddedservice_bootstrap.init(
				'00DEm0000010wVl',
				'VA_Web_Chat_Github',
				'https://visiblealpha--full.sandbox.my.site.com/ESWVAWebChatGithub1709634412936',
				{
					scrt2URL: 'https://visiblealpha--full.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://visiblealpha--full.sandbox.my.site.com/ESWVAWebChatGithub1709634412936/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>

  </body>
</html>
