# django-la-ganalytics
Django app to add google-analytics code to your template

- Copy `ganalytics` APP folder to your project;

- Add ganalytics into `INSTALLED_APPS`;

- Create `GOOGLE_ANALYTICS_CODE` attribute in settings and set the value

- Call the templatetags into your template: `{% load google_analytics %}`

- Finally, add the code of analytics `{% google_analytics %}` into script. Ex.:
    ``` javascript
    (function(i, s, o, g, r, a, m) {
    	i['GoogleAnalyticsObject'] = r;
    	i[r] = i[r] ||
    	function() {
    		(i[r].q = i[r].q || []).push(arguments)
    	}, i[r].l = 1 * new Date();
    	a = s.createElement(o), m = s.getElementsByTagName(o)[0];
    	a.async = 1;
    	a.src = g;
    	m.parentNode.insertBefore(a, m)
    })(window, document, 'script', '//www.google-analytics.com/analytics.js', 'ga');

    ga('create', '{% google_analytics %}', 'auto');
    ga('send', 'pageview');
    ```