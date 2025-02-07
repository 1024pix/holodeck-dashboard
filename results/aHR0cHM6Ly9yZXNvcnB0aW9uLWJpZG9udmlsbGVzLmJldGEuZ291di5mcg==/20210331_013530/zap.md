
# ZAP Scanning Report

Generated on Wed, 31 Mar 2021 01:33:59


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 2 |
| Low | 5 |
| Informational | 5 |

## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- | 
| Content Security Policy (CSP) Header Not Set | Medium | 4 | 
| X-Frame-Options Header Not Set | Medium | 4 | 
| Dangerous JS Functions | Low | 2 | 
| Feature Policy Header Not Set | Low | 6 | 
| Incomplete or No Cache-control and Pragma HTTP Header Set | Low | 6 | 
| Server Leaks Version Information via "Server" HTTP Response Header Field | Low | 9 | 
| X-Content-Type-Options Header Missing | Low | 9 | 
| Base64 Disclosure | Informational | 2 | 
| Information Disclosure - Suspicious Comments | Informational | 8 | 
| Modern Web Application | Informational | 6 | 
| Storable and Cacheable Content | Informational | 9 | 
| Timestamp Disclosure - Unix | Informational | 13 | 

## Alert Detail


  
  
  
  
### Content Security Policy (CSP) Header Not Set
##### Medium (High)
  
  
  
  
#### Description
<p>Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
Instances: 4
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to set the Content-Security-Policy header, to achieve optimal browser support: "Content-Security-Policy" for Chrome 25+, Firefox 23+ and Safari 7+, "X-Content-Security-Policy" for Firefox 4.0+ and Internet Explorer 10+, and "X-WebKit-CSP" for Chrome 14+ and Safari 6+.</p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy
* https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html
* http://www.w3.org/TR/CSP/
* http://w3c.github.io/webappsec/specs/content-security-policy/csp-specification.dev.html
* http://www.html5rocks.com/en/tutorials/security/content-security-policy/
* http://caniuse.com/#feat=contentsecuritypolicy
* http://content-security-policy.com/

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### X-Frame-Options Header Not Set
##### Medium (Medium)
  
  
  
  
#### Description
<p>X-Frame-Options header is not included in the HTTP response to protect against 'ClickJacking' attacks.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Frame-Options`
  
  
  
  
Instances: 4
  
### Solution
<p>Most modern Web browsers support the X-Frame-Options HTTP header. Ensure it's set on all web pages returned by your site (if you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. Alternatively consider implementing Content Security Policy's "frame-ancestors" directive. </p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Dangerous JS Functions
##### Low (Low)
  
  
  
  
#### Description
<p>A dangerous JS function seems to be in use that would leave the site vulnerable.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eval`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eval`
  
  
  
  
Instances: 2
  
### Solution
<p>See the references for security advice on the use of these functions.</p>
  
### Reference
* https://angular.io/guide/security

  
#### CWE Id : 749
  
#### Source ID : 3

  
  
  
  
### Feature Policy Header Not Set
##### Low (Medium)
  
  
  
  
#### Description
<p>Feature Policy Header is an added layer of security that helps to restrict from unauthorized access or usage of browser/client features by web resources. This policy ensures the user privacy by limiting or specifying the features of the browsers can be used by the web resources. Feature Policy provides a set of standard HTTP headers that allow website owners to limit which features of browsers can be used by the page such as camera, microphone, location, full screen etc.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
Instances: 6
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to set the Feature-Policy header.</p>
  
### Reference
* https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy
* https://developers.google.com/web/updates/2018/06/feature-policy
* https://scotthelme.co.uk/a-new-security-header-feature-policy/
* https://w3c.github.io/webappsec-feature-policy/
* https://www.smashingmagazine.com/2018/12/feature-policy/

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Incomplete or No Cache-control and Pragma HTTP Header Set
##### Low (Medium)
  
  
  
  
#### Description
<p>The cache-control and pragma HTTP header have not been set properly or are missing allowing the browser and proxies to cache content.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css](https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css](https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
Instances: 6
  
### Solution
<p>Whenever possible ensure the cache-control HTTP header is set with no-cache, no-store, must-revalidate; and that the pragma HTTP header is set with no-cache.</p>
  
### Reference
* https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching

  
#### CWE Id : 525
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Server Leaks Version Information via "Server" HTTP Response Header Field
##### Low (High)
  
  
  
  
#### Description
<p>The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico](https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css](https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css](https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.17.10`
  
  
  
  
Instances: 9
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to suppress the "Server" header or provide generic details.</p>
  
### Reference
* http://httpd.apache.org/docs/current/mod/core.html#servertokens
* http://msdn.microsoft.com/en-us/library/ff648552.aspx#ht_urlscan_007
* http://blogs.msdn.com/b/varunm/archive/2013/04/23/remove-unwanted-http-response-headers.aspx
* http://www.troyhunt.com/2012/02/shhh-dont-let-your-response-headers.html

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### X-Content-Type-Options Header Missing
##### Low (Medium)
  
  
  
  
#### Description
<p>The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css](https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css](https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico](https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
Instances: 9
  
### Solution
<p>Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.</p><p>If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.</p>
  
### Other information
<p>This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.</p><p>At "High" threshold this scan rule will not alert on client or server error responses.</p>
  
### Reference
* http://msdn.microsoft.com/en-us/library/ie/gg622941%28v=vs.85%29.aspx
* https://owasp.org/www-community/Security_Headers

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Base64 Disclosure
##### Informational (Medium)
  
  
  
  
#### Description
<p>Base64 encoded data was disclosed by the application/web server. Note: in the interests of performance not all base64 strings in the response were analyzed individually, the entire response should be looked at by the analyst/security team/developer(s).</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `416H64v-96h160v96zm0-160H64v-96h160v96zm224`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `indexOfHighlightedSuggestion-1`
  
  
  
  
Instances: 2
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>�^�����u�K��9��^�\x001f�/�ޡ׭/����n</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Low)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `from`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `db`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `select`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `user`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `username`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `XXX`
  
  
  
  
Instances: 8
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bFROM\b and was detected 4 times, the first in the element starting with: "var r={en:/^[A-Z]*$/i,cs:/^[A-ZÁČĎÉĚÍŇÓŘŠŤÚŮÝŽ]*$/i,da:/^[A-ZÆØÅ]*$/i,de:/^[A-ZÄÖÜß]*$/i,es:/^[A-ZÁÉÍÑÓÚÜ]*$/i,fa:/^[ءآأؤإئابةتث", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Modern Web Application
##### Informational (Medium)
  
  
  
  
#### Description
<p>The application appears to be a modern web application. If you need to explore it automatically then the Ajax Spider may well be more effective than the standard one.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="/js/chunk-vendors.30da3263.js"></script>`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a>")})),l=function(){return"$0"==="a".replace(/./,"$0")}(),h=o("replace"),f=function(){return!!/./[h]&&""===/./[h]("a","$0")}(),d=!i((function(){var t=/(?:)/,e=t.exec;t.exec=function(){return e.apply(this,arguments)};var n="ab".split(t);return 2!==n.length||"a"!==n[0]||"b"!==n[1]}));t.exports=function(t,e,n,h){var p=o(t),m=!i((function(){var e={};return e[p]=function(){return 7},7!=""[t](e)})),v=m&&!i((function(){var e=!1,n=/a/;return"split"===t&&(n={},n.constructor={},n.constructor[c]=function(){return n},n.flags="",n[p]=/./[p]),n.exec=function(){return e=!0,null},n[p](""),!e}));if(!m||!v||"replace"===t&&(!u||!l||f)||"split"===t&&!d){var g=/./[p],y=n(p,""[t],(function(t,e,n,r,i){return e.exec===a?m&&!i?{done:!0,value:g.call(e,n,r)}:{done:!0,value:t.call(n,e,r)}:{done:!1}}),{REPLACE_KEEPS_$0:l,REGEXP_REPLACE_SUBSTITUTES_UNDEFINED_CAPTURE:f}),_=y[0],b=y[1];r(String.prototype,t,_),r(RegExp.prototype,p,2==e?function(t,e){return b.call(t,this,e)}:function(t){return b.call(t,this)})}h&&s(RegExp.prototype[p],"sham",!0)}},d80f:function(t,e,n){var r=n("23e7"),i=n("fc6a"),o=n("50c4");r({target:"String",stat:!0},{raw:function(t){var e=i(t.raw),n=o(e.length),r=arguments.length,a=[],s=0;while(n>s)a.push(String(e[s++])),s<r&&a.push(String(arguments[s]));return a.join("")}})},d81d:function(t,e,n){"use strict";var r=n("23e7"),i=n("b727").map,o=n("1dde"),a=n("ae40"),s=o("map"),c=a("map");r({target:"Array",proto:!0,forced:!s||!c},{map:function(t){return i(this,t,arguments.length>1?arguments[1]:void 0)}})},da84:function(t,e,n){(function(e){var n=function(t){return t&&t.Math==Math&&t};t.exports=n("object"==typeof globalThis&&globalThis)||n("object"==typeof window&&window)||n("object"==typeof self&&self)||n("object"==typeof e&&e)||Function("return this")()}).call(this,n("c8ba"))},dac4:function(t,e,n){},db96:function(t,e,n){var r=n("23e7"),i=n("825a"),o=Object.isExtensible;r({target:"Reflect",stat:!0},{isExtensible:function(t){return i(t),!o||o(t)}})},dbb4:function(t,e,n){var r=n("23e7"),i=n("83ab"),o=n("56ef"),a=n("fc6a"),s=n("06cf"),c=n("8418");r({target:"Object",stat:!0,sham:!i},{getOwnPropertyDescriptors:function(t){var e,n,r=a(t),i=s.f,u=o(r),l={},h=0;while(u.length>h)n=i(r,e=u[h++]),void 0!==n&&c(l,e,n);return l}})},dc8d:function(t,e,n){var r=n("746f");r("hasInstance")},dca8:function(t,e,n){var r=n("23e7"),i=n("bb2f"),o=n("d039"),a=n("861d"),s=n("f183").onFreeze,c=Object.freeze,u=o((function(){c(1)}));r({target:"Object",stat:!0,forced:u,sham:!i},{freeze:function(t){return c&&a(t)?c(s(t)):t}})},ddb0:function(t,e,n){var r=n("da84"),i=n("fdbc"),o=n("e260"),a=n("9112"),s=n("b622"),c=s("iterator"),u=s("toStringTag"),l=o.values;for(var h in i){var f=r[h],d=f&&f.prototype;if(d){if(d[c]!==l)try{a(d,c,l)}catch(m){d[c]=l}if(d[u]||a(d,u,h),i[h])for(var p in o)if(d[p]!==o[p])try{a(d,p,o[p])}catch(m){d[p]=o[p]}}}},df75:function(t,e,n){var r=n("ca84"),i=n("7839");t.exports=Object.keys||function(t){return r(t,i)}},e01a:function(t,e,n){"use strict";var r=n("23e7"),i=n("83ab"),o=n("da84"),a=n("5135"),s=n("861d"),c=n("9bf2").f,u=n("e893"),l=o.Symbol;if(i&&"function"==typeof l&&(!("description"in l.prototype)||void 0!==l().description)){var h={},f=function(){var t=arguments.length<1||void 0===arguments[0]?void 0:String(arguments[0]),e=this instanceof f?new l(t):void 0===t?l():l(t);return""===t&&(h[e]=!0),e};u(f,l);var d=f.prototype=l.prototype;d.constructor=f;var p=d.toString,m="Symbol(test)"==String(l("test")),v=/^Symbol\((.*)\)[^)]+$/;c(d,"description",{configurable:!0,get:function(){var t=s(this)?this.valueOf():this,e=p.call(t);if(a(h,t))return"";var n=m?e.slice(7,-1):e.replace(v,"$1");return""===n?void 0:n}}),r({global:!0,forced:!0},{Symbol:f})}},e11e:function(t,e,n){
/* @preserve
 * Leaflet 1.7.1, a JS library for interactive maps. http://leafletjs.com
 * (c) 2010-2019 Vladimir Agafonkin, (c) 2010-2011 CloudMade
 */
(function(t,n){n(e)})(0,(function(t){"use strict";var e="1.7.1";function n(t){var e,n,r,i;for(n=1,r=arguments.length;n<r;n++)for(e in i=arguments[n],i)t[e]=i[e];return t}var r=Object.create||function(){function t(){}return function(e){return t.prototype=e,new t}}();function i(t,e){var n=Array.prototype.slice;if(t.bind)return t.bind.apply(t,n.call(arguments,1));var r=n.call(arguments,2);return function(){return t.apply(e,r.length?r.concat(n.call(arguments)):arguments)}}var o=0;function a(t){return t._leaflet_id=t._leaflet_id||++o,t._leaflet_id}function s(t,e,n){var r,i,o,a;return a=function(){r=!1,i&&(o.apply(n,i),i=!1)},o=function(){r?i=arguments:(t.apply(n,arguments),setTimeout(a,e),r=!0)},o}function c(t,e,n){var r=e[1],i=e[0],o=r-i;return t===r&&n?t:((t-i)%o+o)%o+i}function u(){return!1}function l(t,e){var n=Math.pow(10,void 0===e?6:e);return Math.round(t*n)/n}function h(t){return t.trim?t.trim():t.replace(/^\s+|\s+$/g,"")}function f(t){return h(t).split(/\s+/)}function d(t,e){for(var n in Object.prototype.hasOwnProperty.call(t,"options")||(t.options=t.options?r(t.options):{}),e)t.options[n]=e[n];return t.options}function p(t,e,n){var r=[];for(var i in t)r.push(encodeURIComponent(n?i.toUpperCase():i)+"="+encodeURIComponent(t[i]));return(e&&-1!==e.indexOf("?")?"&":"?")+r.join("&")}var m=/\{ *([\w_-]+) *\}/g;function v(t,e){return t.replace(m,(function(t,n){var r=e[n];if(void 0===r)throw new Error("No value provided for variable "+t);return"function"===typeof r&&(r=r(e)),r}))}var g=Array.isArray||function(t){return"[object Array]"===Object.prototype.toString.call(t)};function y(t,e){for(var n=0;n<t.length;n++)if(t[n]===e)return n;return-1}var _="data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=";function b(t){return window["webkit"+t]||window["moz"+t]||window["ms"+t]}var w=0;function x(t){var e=+new Date,n=Math.max(0,16-(e-w));return w=e+n,window.setTimeout(t,n)}var C=window.requestAnimationFrame||b("RequestAnimationFrame")||x,A=window.cancelAnimationFrame||b("CancelAnimationFrame")||b("CancelRequestAnimationFrame")||function(t){window.clearTimeout(t)};function S(t,e,n){if(!n||C!==x)return C.call(window,i(t,e));t.call(e)}function k(t){t&&A.call(window,t)}var T={extend:n,create:r,bind:i,lastId:o,stamp:a,throttle:s,wrapNum:c,falseFn:u,formatNum:l,trim:h,splitWords:f,setOptions:d,getParamString:p,template:v,isArray:g,indexOf:y,emptyImageUrl:_,requestFn:C,cancelFn:A,requestAnimFrame:S,cancelAnimFrame:k};function M(){}function O(t){if("undefined"!==typeof L&&L&&L.Mixin){t=g(t)?t:[t];for(var e=0;e<t.length;e++)t[e]===L.Mixin.Events&&console.warn("Deprecated include of L.Mixin.Events: this property will be removed in future releases, please inherit from L.Evented instead.",(new Error).stack)}}M.extend=function(t){var e=function(){this.initialize&&this.initialize.apply(this,arguments),this.callInitHooks()},i=e.__super__=this.prototype,o=r(i);for(var a in o.constructor=e,e.prototype=o,this)Object.prototype.hasOwnProperty.call(this,a)&&"prototype"!==a&&"__super__"!==a&&(e[a]=this[a]);return t.statics&&(n(e,t.statics),delete t.statics),t.includes&&(O(t.includes),n.apply(null,[o].concat(t.includes)),delete t.includes),o.options&&(t.options=n(r(o.options),t.options)),n(o,t),o._initHooks=[],o.callInitHooks=function(){if(!this._initHooksCalled){i.callInitHooks&&i.callInitHooks.call(this),this._initHooksCalled=!0;for(var t=0,e=o._initHooks.length;t<e;t++)o._initHooks[t].call(this)}},e},M.include=function(t){return n(this.prototype,t),this},M.mergeOptions=function(t){return n(this.prototype.options,t),this},M.addInitHook=function(t){var e=Array.prototype.slice.call(arguments,1),n="function"===typeof t?t:function(){this[t].apply(this,e)};return this.prototype._initHooks=this.prototype._initHooks||[],this.prototype._initHooks.push(n),this};var P={on:function(t,e,n){if("object"===typeof t)for(var r in t)this._on(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._on(t[i],e,n)}return this},off:function(t,e,n){if(t)if("object"===typeof t)for(var r in t)this._off(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._off(t[i],e,n)}else delete this._events;return this},_on:function(t,e,n){this._events=this._events||{};var r=this._events[t];r||(r=[],this._events[t]=r),n===this&&(n=void 0);for(var i={fn:e,ctx:n},o=r,a=0,s=o.length;a<s;a++)if(o[a].fn===e&&o[a].ctx===n)return;o.push(i)},_off:function(t,e,n){var r,i,o;if(this._events&&(r=this._events[t],r))if(e){if(n===this&&(n=void 0),r)for(i=0,o=r.length;i<o;i++){var a=r[i];if(a.ctx===n&&a.fn===e)return a.fn=u,this._firingCount&&(this._events[t]=r=r.slice()),void r.splice(i,1)}}else{for(i=0,o=r.length;i<o;i++)r[i].fn=u;delete this._events[t]}},fire:function(t,e,r){if(!this.listens(t,r))return this;var i=n({},e,{type:t,target:this,sourceTarget:e&&e.sourceTarget||this});if(this._events){var o=this._events[t];if(o){this._firingCount=this._firingCount+1||1;for(var a=0,s=o.length;a<s;a++){var c=o[a];c.fn.call(c.ctx||this,i)}this._firingCount--}}return r&&this._propagateEvent(i),this},listens:function(t,e){var n=this._events&&this._events[t];if(n&&n.length)return!0;if(e)for(var r in this._eventParents)if(this._eventParents[r].listens(t,e))return!0;return!1},once:function(t,e,n){if("object"===typeof t){for(var r in t)this.once(r,t[r],e);return this}var o=i((function(){this.off(t,e,n).off(t,o,n)}),this);return this.on(t,e,n).on(t,o,n)},addEventParent:function(t){return this._eventParents=this._eventParents||{},this._eventParents[a(t)]=t,this},removeEventParent:function(t){return this._eventParents&&delete this._eventParents[a(t)],this},_propagateEvent:function(t){for(var e in this._eventParents)this._eventParents[e].fire(t.type,n({layer:t.target,propagatedFrom:t.target},t),!0)}};P.addEventListener=P.on,P.removeEventListener=P.clearAllEventListeners=P.off,P.addOneTimeEventListener=P.once,P.fireEvent=P.fire,P.hasEventListeners=P.listens;var E=M.extend(P);function D(t,e,n){this.x=n?Math.round(t):t,this.y=n?Math.round(e):e}var z=Math.trunc||function(t){return t>0?Math.floor(t):Math.ceil(t)};function R(t,e,n){return t instanceof D?t:g(t)?new D(t[0],t[1]):void 0===t||null===t?t:"object"===typeof t&&"x"in t&&"y"in t?new D(t.x,t.y):new D(t,e,n)}function j(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function I(t,e){return!t||t instanceof j?t:new j(t,e)}function N(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function B(t,e){return t instanceof N?t:new N(t,e)}function F(t,e,n){if(isNaN(t)||isNaN(e))throw new Error("Invalid LatLng object: ("+t+", "+e+")");this.lat=+t,this.lng=+e,void 0!==n&&(this.alt=+n)}function $(t,e,n){return t instanceof F?t:g(t)&&"object"!==typeof t[0]?3===t.length?new F(t[0],t[1],t[2]):2===t.length?new F(t[0],t[1]):null:void 0===t||null===t?t:"object"===typeof t&&"lat"in t?new F(t.lat,"lng"in t?t.lng:t.lon,t.alt):void 0===e?null:new F(t,e,n)}D.prototype={clone:function(){return new D(this.x,this.y)},add:function(t){return this.clone()._add(R(t))},_add:function(t){return this.x+=t.x,this.y+=t.y,this},subtract:function(t){return this.clone()._subtract(R(t))},_subtract:function(t){return this.x-=t.x,this.y-=t.y,this},divideBy:function(t){return this.clone()._divideBy(t)},_divideBy:function(t){return this.x/=t,this.y/=t,this},multiplyBy:function(t){return this.clone()._multiplyBy(t)},_multiplyBy:function(t){return this.x*=t,this.y*=t,this},scaleBy:function(t){return new D(this.x*t.x,this.y*t.y)},unscaleBy:function(t){return new D(this.x/t.x,this.y/t.y)},round:function(){return this.clone()._round()},_round:function(){return this.x=Math.round(this.x),this.y=Math.round(this.y),this},floor:function(){return this.clone()._floor()},_floor:function(){return this.x=Math.floor(this.x),this.y=Math.floor(this.y),this},ceil:function(){return this.clone()._ceil()},_ceil:function(){return this.x=Math.ceil(this.x),this.y=Math.ceil(this.y),this},trunc:function(){return this.clone()._trunc()},_trunc:function(){return this.x=z(this.x),this.y=z(this.y),this},distanceTo:function(t){t=R(t);var e=t.x-this.x,n=t.y-this.y;return Math.sqrt(e*e+n*n)},equals:function(t){return t=R(t),t.x===this.x&&t.y===this.y},contains:function(t){return t=R(t),Math.abs(t.x)<=Math.abs(this.x)&&Math.abs(t.y)<=Math.abs(this.y)},toString:function(){return"Point("+l(this.x)+", "+l(this.y)+")"}},j.prototype={extend:function(t){return t=R(t),this.min||this.max?(this.min.x=Math.min(t.x,this.min.x),this.max.x=Math.max(t.x,this.max.x),this.min.y=Math.min(t.y,this.min.y),this.max.y=Math.max(t.y,this.max.y)):(this.min=t.clone(),this.max=t.clone()),this},getCenter:function(t){return new D((this.min.x+this.max.x)/2,(this.min.y+this.max.y)/2,t)},getBottomLeft:function(){return new D(this.min.x,this.max.y)},getTopRight:function(){return new D(this.max.x,this.min.y)},getTopLeft:function(){return this.min},getBottomRight:function(){return this.max},getSize:function(){return this.max.subtract(this.min)},contains:function(t){var e,n;return t="number"===typeof t[0]||t instanceof D?R(t):I(t),t instanceof j?(e=t.min,n=t.max):e=n=t,e.x>=this.min.x&&n.x<=this.max.x&&e.y>=this.min.y&&n.y<=this.max.y},intersects:function(t){t=I(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>=e.x&&r.x<=n.x,a=i.y>=e.y&&r.y<=n.y;return o&&a},overlaps:function(t){t=I(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>e.x&&r.x<n.x,a=i.y>e.y&&r.y<n.y;return o&&a},isValid:function(){return!(!this.min||!this.max)}},N.prototype={extend:function(t){var e,n,r=this._southWest,i=this._northEast;if(t instanceof F)e=t,n=t;else{if(!(t instanceof N))return t?this.extend($(t)||B(t)):this;if(e=t._southWest,n=t._northEast,!e||!n)return this}return r||i?(r.lat=Math.min(e.lat,r.lat),r.lng=Math.min(e.lng,r.lng),i.lat=Math.max(n.lat,i.lat),i.lng=Math.max(n.lng,i.lng)):(this._southWest=new F(e.lat,e.lng),this._northEast=new F(n.lat,n.lng)),this},pad:function(t){var e=this._southWest,n=this._northEast,r=Math.abs(e.lat-n.lat)*t,i=Math.abs(e.lng-n.lng)*t;return new N(new F(e.lat-r,e.lng-i),new F(n.lat+r,n.lng+i))},getCenter:function(){return new F((this._southWest.lat+this._northEast.lat)/2,(this._southWest.lng+this._northEast.lng)/2)},getSouthWest:function(){return this._southWest},getNorthEast:function(){return this._northEast},getNorthWest:function(){return new F(this.getNorth(),this.getWest())},getSouthEast:function(){return new F(this.getSouth(),this.getEast())},getWest:function(){return this._southWest.lng},getSouth:function(){return this._southWest.lat},getEast:function(){return this._northEast.lng},getNorth:function(){return this._northEast.lat},contains:function(t){t="number"===typeof t[0]||t instanceof F||"lat"in t?$(t):B(t);var e,n,r=this._southWest,i=this._northEast;return t instanceof N?(e=t.getSouthWest(),n=t.getNorthEast()):e=n=t,e.lat>=r.lat&&n.lat<=i.lat&&e.lng>=r.lng&&n.lng<=i.lng},intersects:function(t){t=B(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>=e.lat&&r.lat<=n.lat,a=i.lng>=e.lng&&r.lng<=n.lng;return o&&a},overlaps:function(t){t=B(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>e.lat&&r.lat<n.lat,a=i.lng>e.lng&&r.lng<n.lng;return o&&a},toBBoxString:function(){return[this.getWest(),this.getSouth(),this.getEast(),this.getNorth()].join(",")},equals:function(t,e){return!!t&&(t=B(t),this._southWest.equals(t.getSouthWest(),e)&&this._northEast.equals(t.getNorthEast(),e))},isValid:function(){return!(!this._southWest||!this._northEast)}},F.prototype={equals:function(t,e){if(!t)return!1;t=$(t);var n=Math.max(Math.abs(this.lat-t.lat),Math.abs(this.lng-t.lng));return n<=(void 0===e?1e-9:e)},toString:function(t){return"LatLng("+l(this.lat,t)+", "+l(this.lng,t)+")"},distanceTo:function(t){return U.distance(this,$(t))},wrap:function(){return U.wrapLatLng(this)},toBounds:function(t){var e=180*t/40075017,n=e/Math.cos(Math.PI/180*this.lat);return B([this.lat-e,this.lng-n],[this.lat+e,this.lng+n])},clone:function(){return new F(this.lat,this.lng,this.alt)}};var Z={latLngToPoint:function(t,e){var n=this.projection.project(t),r=this.scale(e);return this.transformation._transform(n,r)},pointToLatLng:function(t,e){var n=this.scale(e),r=this.transformation.untransform(t,n);return this.projection.unproject(r)},project:function(t){return this.projection.project(t)},unproject:function(t){return this.projection.unproject(t)},scale:function(t){return 256*Math.pow(2,t)},zoom:function(t){return Math.log(t/256)/Math.LN2},getProjectedBounds:function(t){if(this.infinite)return null;var e=this.projection.bounds,n=this.scale(t),r=this.transformation.transform(e.min,n),i=this.transformation.transform(e.max,n);return new j(r,i)},infinite:!1,wrapLatLng:function(t){var e=this.wrapLng?c(t.lng,this.wrapLng,!0):t.lng,n=this.wrapLat?c(t.lat,this.wrapLat,!0):t.lat,r=t.alt;return new F(n,e,r)},wrapLatLngBounds:function(t){var e=t.getCenter(),n=this.wrapLatLng(e),r=e.lat-n.lat,i=e.lng-n.lng;if(0===r&&0===i)return t;var o=t.getSouthWest(),a=t.getNorthEast(),s=new F(o.lat-r,o.lng-i),c=new F(a.lat-r,a.lng-i);return new N(s,c)}},U=n({},Z,{wrapLng:[-180,180],R:6371e3,distance:function(t,e){var n=Math.PI/180,r=t.lat*n,i=e.lat*n,o=Math.sin((e.lat-t.lat)*n/2),a=Math.sin((e.lng-t.lng)*n/2),s=o*o+Math.cos(r)*Math.cos(i)*a*a,c=2*Math.atan2(Math.sqrt(s),Math.sqrt(1-s));return this.R*c}}),H=6378137,V={R:H,MAX_LATITUDE:85.0511287798,project:function(t){var e=Math.PI/180,n=this.MAX_LATITUDE,r=Math.max(Math.min(n,t.lat),-n),i=Math.sin(r*e);return new D(this.R*t.lng*e,this.R*Math.log((1+i)/(1-i))/2)},unproject:function(t){var e=180/Math.PI;return new F((2*Math.atan(Math.exp(t.y/this.R))-Math.PI/2)*e,t.x*e/this.R)},bounds:function(){var t=H*Math.PI;return new j([-t,-t],[t,t])}()};function W(t,e,n,r){if(g(t))return this._a=t[0],this._b=t[1],this._c=t[2],void(this._d=t[3]);this._a=t,this._b=e,this._c=n,this._d=r}function q(t,e,n,r){return new W(t,e,n,r)}W.prototype={transform:function(t,e){return this._transform(t.clone(),e)},_transform:function(t,e){return e=e||1,t.x=e*(this._a*t.x+this._b),t.y=e*(this._c*t.y+this._d),t},untransform:function(t,e){return e=e||1,new D((t.x/e-this._b)/this._a,(t.y/e-this._d)/this._c)}};var G=n({},U,{code:"EPSG:3857",projection:V,transformation:function(){var t=.5/(Math.PI*V.R);return q(t,.5,-t,.5)}()}),Y=n({},G,{code:"EPSG:900913"});function J(t){return document.createElementNS("http://www.w3.org/2000/svg",t)}function X(t,e){var n,r,i,o,a,s,c="";for(n=0,i=t.length;n<i;n++){for(a=t[n],r=0,o=a.length;r<o;r++)s=a[r],c+=(r?"L":"M")+s.x+" "+s.y;c+=e?Mt?"z":"x":""}return c||"M0 0"}var K=document.documentElement.style,Q="ActiveXObject"in window,tt=Q&&!document.addEventListener,et="msLaunchUri"in navigator&&!("documentMode"in document),nt=Pt("webkit"),rt=Pt("android"),it=Pt("android 2")||Pt("android 3"),ot=parseInt(/WebKit\/([0-9]+)|$/.exec(navigator.userAgent)[1],10),at=rt&&Pt("Google")&&ot<537&&!("AudioNode"in window),st=!!window.opera,ct=!et&&Pt("chrome"),ut=Pt("gecko")&&!nt&&!st&&!Q,lt=!ct&&Pt("safari"),ht=Pt("phantom"),ft="OTransition"in K,dt=0===navigator.platform.indexOf("Win"),pt=Q&&"transition"in K,mt="WebKitCSSMatrix"in window&&"m11"in new window.WebKitCSSMatrix&&!it,vt="MozPerspective"in K,gt=!window.L_DISABLE_3D&&(pt||mt||vt)&&!ft&&!ht,yt="undefined"!==typeof orientation||Pt("mobile"),_t=yt&&nt,bt=yt&&mt,wt=!window.PointerEvent&&window.MSPointerEvent,xt=!(!window.PointerEvent&&!wt),Ct=!window.L_NO_TOUCH&&(xt||"ontouchstart"in window||window.DocumentTouch&&document instanceof window.DocumentTouch),At=yt&&st,St=yt&&ut,kt=(window.devicePixelRatio||window.screen.deviceXDPI/window.screen.logicalXDPI)>1,Lt=function(){var t=!1;try{var e=Object.defineProperty({},"passive",{get:function(){t=!0}});window.addEventListener("testPassiveEventSupport",u,e),window.removeEventListener("testPassiveEventSupport",u,e)}catch(n){}return t}(),Tt=function(){return!!document.createElement("canvas").getContext}(),Mt=!(!document.createElementNS||!J("svg").createSVGRect),Ot=!Mt&&function(){try{var t=document.createElement("div");t.innerHTML='<v:shape adj="1"/>';var e=t.firstChild;return e.style.behavior="url(#default#VML)",e&&"object"===typeof e.adj}catch(n){return!1}}();function Pt(t){return navigator.userAgent.toLowerCase().indexOf(t)>=0}var Et={ie:Q,ielt9:tt,edge:et,webkit:nt,android:rt,android23:it,androidStock:at,opera:st,chrome:ct,gecko:ut,safari:lt,phantom:ht,opera12:ft,win:dt,ie3d:pt,webkit3d:mt,gecko3d:vt,any3d:gt,mobile:yt,mobileWebkit:_t,mobileWebkit3d:bt,msPointer:wt,pointer:xt,touch:Ct,mobileOpera:At,mobileGecko:St,retina:kt,passiveEvents:Lt,canvas:Tt,svg:Mt,vml:Ot},Dt=wt?"MSPointerDown":"pointerdown",zt=wt?"MSPointerMove":"pointermove",Rt=wt?"MSPointerUp":"pointerup",jt=wt?"MSPointerCancel":"pointercancel",It={},Nt=!1;function Bt(t,e,n,r){return"touchstart"===e?$t(t,n,r):"touchmove"===e?Wt(t,n,r):"touchend"===e&&qt(t,n,r),this}function Ft(t,e,n){var r=t["_leaflet_"+e+n];return"touchstart"===e?t.removeEventListener(Dt,r,!1):"touchmove"===e?t.removeEventListener(zt,r,!1):"touchend"===e&&(t.removeEventListener(Rt,r,!1),t.removeEventListener(jt,r,!1)),this}function $t(t,e,n){var r=i((function(t){t.MSPOINTER_TYPE_TOUCH&&t.pointerType===t.MSPOINTER_TYPE_TOUCH&&Ue(t),Vt(t,e)}));t["_leaflet_touchstart"+n]=r,t.addEventListener(Dt,r,!1),Nt||(document.addEventListener(Dt,Zt,!0),document.addEventListener(zt,Ut,!0),document.addEventListener(Rt,Ht,!0),document.addEventListener(jt,Ht,!0),Nt=!0)}function Zt(t){It[t.pointerId]=t}function Ut(t){It[t.pointerId]&&(It[t.pointerId]=t)}function Ht(t){delete It[t.pointerId]}function Vt(t,e){for(var n in t.touches=[],It)t.touches.push(It[n]);t.changedTouches=[t],e(t)}function Wt(t,e,n){var r=function(t){t.pointerType===(t.MSPOINTER_TYPE_MOUSE||"mouse")&&0===t.buttons||Vt(t,e)};t["_leaflet_touchmove"+n]=r,t.addEventListener(zt,r,!1)}function qt(t,e,n){var r=function(t){Vt(t,e)};t["_leaflet_touchend"+n]=r,t.addEventListener(Rt,r,!1),t.addEventListener(jt,r,!1)}var Gt=wt?"MSPointerDown":xt?"pointerdown":"touchstart",Yt=wt?"MSPointerUp":xt?"pointerup":"touchend",Jt="_leaflet_";function Xt(t,e,n){var r,i,o=!1,a=250;function s(t){if(xt){if(!t.isPrimary)return;if("mouse"===t.pointerType)return}else if(t.touches.length>1)return;var e=Date.now(),n=e-(r||e);i=t.touches?t.touches[0]:t,o=n>0&&n<=a,r=e}function c(t){if(o&&!i.cancelBubble){if(xt){if("mouse"===t.pointerType)return;var n,a,s={};for(a in i)n=i[a],s[a]=n&&n.bind?n.bind(i):n;i=s}i.type="dblclick",i.button=0,e(i),r=null}}return t[Jt+Gt+n]=s,t[Jt+Yt+n]=c,t[Jt+"dblclick"+n]=e,t.addEventListener(Gt,s,!!Lt&&{passive:!1}),t.addEventListener(Yt,c,!!Lt&&{passive:!1}),t.addEventListener("dblclick",e,!1),this}function Kt(t,e){var n=t[Jt+Gt+e],r=t[Jt+Yt+e],i=t[Jt+"dblclick"+e];return t.removeEventListener(Gt,n,!!Lt&&{passive:!1}),t.removeEventListener(Yt,r,!!Lt&&{passive:!1}),t.removeEventListener("dblclick",i,!1),this}var Qt,te,ee,ne,re,ie=we(["transform","webkitTransform","OTransform","MozTransform","msTransform"]),oe=we(["webkitTransition","transition","OTransition","MozTransition","msTransition"]),ae="webkitTransition"===oe||"OTransition"===oe?oe+"End":"transitionend";function se(t){return"string"===typeof t?document.getElementById(t):t}function ce(t,e){var n=t.style[e]||t.currentStyle&&t.currentStyle[e];if((!n||"auto"===n)&&document.defaultView){var r=document.defaultView.getComputedStyle(t,null);n=r?r[e]:null}return"auto"===n?null:n}function ue(t,e,n){var r=document.createElement(t);return r.className=e||"",n&&n.appendChild(r),r}function le(t){var e=t.parentNode;e&&e.removeChild(t)}function he(t){while(t.firstChild)t.removeChild(t.firstChild)}function fe(t){var e=t.parentNode;e&&e.lastChild!==t&&e.appendChild(t)}function de(t){var e=t.parentNode;e&&e.firstChild!==t&&e.insertBefore(t,e.firstChild)}function pe(t,e){if(void 0!==t.classList)return t.classList.contains(e);var n=ye(t);return n.length>0&&new RegExp("(^|\\s)"+e+"(\\s|$)").test(n)}function me(t,e){if(void 0!==t.classList)for(var n=f(e),r=0,i=n.length;r<i;r++)t.classList.add(n[r]);else if(!pe(t,e)){var o=ye(t);ge(t,(o?o+" ":"")+e)}}function ve(t,e){void 0!==t.classList?t.classList.remove(e):ge(t,h((" "+ye(t)+" ").replace(" "+e+" "," ")))}function ge(t,e){void 0===t.className.baseVal?t.className=e:t.className.baseVal=e}function ye(t){return t.correspondingElement&&(t=t.correspondingElement),void 0===t.className.baseVal?t.className:t.className.baseVal}function _e(t,e){"opacity"in t.style?t.style.opacity=e:"filter"in t.style&&be(t,e)}function be(t,e){var n=!1,r="DXImageTransform.Microsoft.Alpha";try{n=t.filters.item(r)}catch(i){if(1===e)return}e=Math.round(100*e),n?(n.Enabled=100!==e,n.Opacity=e):t.style.filter+=" progid:"+r+"(opacity="+e+")"}function we(t){for(var e=document.documentElement.style,n=0;n<t.length;n++)if(t[n]in e)return t[n];return!1}function xe(t,e,n){var r=e||new D(0,0);t.style[ie]=(pt?"translate("+r.x+"px,"+r.y+"px)":"translate3d("+r.x+"px,"+r.y+"px,0)")+(n?" scale("+n+")":"")}function Ce(t,e){t._leaflet_pos=e,gt?xe(t,e):(t.style.left=e.x+"px",t.style.top=e.y+"px")}function Ae(t){return t._leaflet_pos||new D(0,0)}if("onselectstart"in document)Qt=function(){De(window,"selectstart",Ue)},te=function(){Re(window,"selectstart",Ue)};else{var Se=we(["userSelect","WebkitUserSelect","OUserSelect","MozUserSelect","msUserSelect"]);Qt=function(){if(Se){var t=document.documentElement.style;ee=t[Se],t[Se]="none"}},te=function(){Se&&(document.documentElement.style[Se]=ee,ee=void 0)}}function ke(){De(window,"dragstart",Ue)}function Le(){Re(window,"dragstart",Ue)}function Te(t){while(-1===t.tabIndex)t=t.parentNode;t.style&&(Me(),ne=t,re=t.style.outline,t.style.outline="none",De(window,"keydown",Me))}function Me(){ne&&(ne.style.outline=re,ne=void 0,re=void 0,Re(window,"keydown",Me))}function Oe(t){do{t=t.parentNode}while((!t.offsetWidth||!t.offsetHeight)&&t!==document.body);return t}function Pe(t){var e=t.getBoundingClientRect();return{x:e.width/t.offsetWidth||1,y:e.height/t.offsetHeight||1,boundingClientRect:e}}var Ee={TRANSFORM:ie,TRANSITION:oe,TRANSITION_END:ae,get:se,getStyle:ce,create:ue,remove:le,empty:he,toFront:fe,toBack:de,hasClass:pe,addClass:me,removeClass:ve,setClass:ge,getClass:ye,setOpacity:_e,testProp:we,setTransform:xe,setPosition:Ce,getPosition:Ae,disableTextSelection:Qt,enableTextSelection:te,disableImageDrag:ke,enableImageDrag:Le,preventOutline:Te,restoreOutline:Me,getSizedParentNode:Oe,getScale:Pe};function De(t,e,n,r){if("object"===typeof e)for(var i in e)Ne(t,i,e[i],n);else{e=f(e);for(var o=0,a=e.length;o<a;o++)Ne(t,e[o],n,r)}return this}var ze="_leaflet_events";function Re(t,e,n,r){if("object"===typeof e)for(var i in e)Be(t,i,e[i],n);else if(e){e=f(e);for(var o=0,a=e.length;o<a;o++)Be(t,e[o],n,r)}else{for(var s in t[ze])Be(t,s,t[ze][s]);delete t[ze]}return this}function je(){if(xt)return!(et||lt)}var Ie={mouseenter:"mouseover",mouseleave:"mouseout",wheel:!("onwheel"in window)&&"mousewheel"};function Ne(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):"");if(t[ze]&&t[ze][i])return this;var o=function(e){return n.call(r||t,e||window.event)},s=o;xt&&0===e.indexOf("touch")?Bt(t,e,o,i):Ct&&"dblclick"===e&&!je()?Xt(t,o,i):"addEventListener"in t?"touchstart"===e||"touchmove"===e||"wheel"===e||"mousewheel"===e?t.addEventListener(Ie[e]||e,o,!!Lt&&{passive:!1}):"mouseenter"===e||"mouseleave"===e?(o=function(e){e=e||window.event,Xe(t,e)&&s(e)},t.addEventListener(Ie[e],o,!1)):t.addEventListener(e,s,!1):"attachEvent"in t&&t.attachEvent("on"+e,o),t[ze]=t[ze]||{},t[ze][i]=o}function Be(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):""),o=t[ze]&&t[ze][i];if(!o)return this;xt&&0===e.indexOf("touch")?Ft(t,e,i):Ct&&"dblclick"===e&&!je()?Kt(t,i):"removeEventListener"in t?t.removeEventListener(Ie[e]||e,o,!1):"detachEvent"in t&&t.detachEvent("on"+e,o),t[ze][i]=null}function Fe(t){return t.stopPropagation?t.stopPropagation():t.originalEvent?t.originalEvent._stopped=!0:t.cancelBubble=!0,Je(t),this}function $e(t){return Ne(t,"wheel",Fe),this}function Ze(t){return De(t,"mousedown touchstart dblclick",Fe),Ne(t,"click",Ye),this}function Ue(t){return t.preventDefault?t.preventDefault():t.returnValue=!1,this}function He(t){return Ue(t),Fe(t),this}function Ve(t,e){if(!e)return new D(t.clientX,t.clientY);var n=Pe(e),r=n.boundingClientRect;return new D((t.clientX-r.left)/n.x-e.clientLeft,(t.clientY-r.top)/n.y-e.clientTop)}var We=dt&&ct?2*window.devicePixelRatio:ut?window.devicePixelRatio:1;function qe(t){return et?t.wheelDeltaY/2:t.deltaY&&0===t.deltaMode?-t.deltaY/We:t.deltaY&&1===t.deltaMode?20*-t.deltaY:t.deltaY&&2===t.deltaMode?60*-t.deltaY:t.deltaX||t.deltaZ?0:t.wheelDelta?(t.wheelDeltaY||t.wheelDelta)/2:t.detail&&Math.abs(t.detail)<32765?20*-t.detail:t.detail?t.detail/-32765*60:0}var Ge={};function Ye(t){Ge[t.type]=!0}function Je(t){var e=Ge[t.type];return Ge[t.type]=!1,e}function Xe(t,e){var n=e.relatedTarget;if(!n)return!0;try{while(n&&n!==t)n=n.parentNode}catch(r){return!1}return n!==t}var Ke={on:De,off:Re,stopPropagation:Fe,disableScrollPropagation:$e,disableClickPropagation:Ze,preventDefault:Ue,stop:He,getMousePosition:Ve,getWheelDelta:qe,fakeStop:Ye,skipped:Je,isExternalTarget:Xe,addListener:De,removeListener:Re},Qe=E.extend({run:function(t,e,n,r){this.stop(),this._el=t,this._inProgress=!0,this._duration=n||.25,this._easeOutPower=1/Math.max(r||.5,.2),this._startPos=Ae(t),this._offset=e.subtract(this._startPos),this._startTime=+new Date,this.fire("start"),this._animate()},stop:function(){this._inProgress&&(this._step(!0),this._complete())},_animate:function(){this._animId=S(this._animate,this),this._step()},_step:function(t){var e=+new Date-this._startTime,n=1e3*this._duration;e<n?this._runFrame(this._easeOut(e/n),t):(this._runFrame(1),this._complete())},_runFrame:function(t,e){var n=this._startPos.add(this._offset.multiplyBy(t));e&&n._round(),Ce(this._el,n),this.fire("step")},_complete:function(){k(this._animId),this._inProgress=!1,this.fire("end")},_easeOut:function(t){return 1-Math.pow(1-t,this._easeOutPower)}}),tn=E.extend({options:{crs:G,center:void 0,zoom:void 0,minZoom:void 0,maxZoom:void 0,layers:[],maxBounds:void 0,renderer:void 0,zoomAnimation:!0,zoomAnimationThreshold:4,fadeAnimation:!0,markerZoomAnimation:!0,transform3DLimit:8388608,zoomSnap:1,zoomDelta:1,trackResize:!0},initialize:function(t,e){e=d(this,e),this._handlers=[],this._layers={},this._zoomBoundLayers={},this._sizeChanged=!0,this._initContainer(t),this._initLayout(),this._onResize=i(this._onResize,this),this._initEvents(),e.maxBounds&&this.setMaxBounds(e.maxBounds),void 0!==e.zoom&&(this._zoom=this._limitZoom(e.zoom)),e.center&&void 0!==e.zoom&&this.setView($(e.center),e.zoom,{reset:!0}),this.callInitHooks(),this._zoomAnimated=oe&&gt&&!At&&this.options.zoomAnimation,this._zoomAnimated&&(this._createAnimProxy(),De(this._proxy,ae,this._catchTransitionEnd,this)),this._addLayers(this.options.layers)},setView:function(t,e,r){if(e=void 0===e?this._zoom:this._limitZoom(e),t=this._limitCenter($(t),e,this.options.maxBounds),r=r||{},this._stop(),this._loaded&&!r.reset&&!0!==r){void 0!==r.animate&&(r.zoom=n({animate:r.animate},r.zoom),r.pan=n({animate:r.animate,duration:r.duration},r.pan));var i=this._zoom!==e?this._tryAnimatedZoom&&this._tryAnimatedZoom(t,e,r.zoom):this._tryAnimatedPan(t,r.pan);if(i)return clearTimeout(this._sizeTimer),this}return this._resetView(t,e),this},setZoom:function(t,e){return this._loaded?this.setView(this.getCenter(),t,{zoom:e}):(this._zoom=t,this)},zoomIn:function(t,e){return t=t||(gt?this.options.zoomDelta:1),this.setZoom(this._zoom+t,e)},zoomOut:function(t,e){return t=t||(gt?this.options.zoomDelta:1),this.setZoom(this._zoom-t,e)},setZoomAround:function(t,e,n){var r=this.getZoomScale(e),i=this.getSize().divideBy(2),o=t instanceof D?t:this.latLngToContainerPoint(t),a=o.subtract(i).multiplyBy(1-1/r),s=this.containerPointToLatLng(i.add(a));return this.setView(s,e,{zoom:n})},_getBoundsCenterZoom:function(t,e){e=e||{},t=t.getBounds?t.getBounds():B(t);var n=R(e.paddingTopLeft||e.padding||[0,0]),r=R(e.paddingBottomRight||e.padding||[0,0]),i=this.getBoundsZoom(t,!1,n.add(r));if(i="number"===typeof e.maxZoom?Math.min(e.maxZoom,i):i,i===1/0)return{center:t.getCenter(),zoom:i};var o=r.subtract(n).divideBy(2),a=this.project(t.getSouthWest(),i),s=this.project(t.getNorthEast(),i),c=this.unproject(a.add(s).divideBy(2).add(o),i);return{center:c,zoom:i}},fitBounds:function(t,e){if(t=B(t),!t.isValid())throw new Error("Bounds are not valid.");var n=this._getBoundsCenterZoom(t,e);return this.setView(n.center,n.zoom,e)},fitWorld:function(t){return this.fitBounds([[-90,-180],[90,180]],t)},panTo:function(t,e){return this.setView(t,this._zoom,{pan:e})},panBy:function(t,e){if(t=R(t).round(),e=e||{},!t.x&&!t.y)return this.fire("moveend");if(!0!==e.animate&&!this.getSize().contains(t))return this._resetView(this.unproject(this.project(this.getCenter()).add(t)),this.getZoom()),this;if(this._panAnim||(this._panAnim=new Qe,this._panAnim.on({step:this._onPanTransitionStep,end:this._onPanTransitionEnd},this)),e.noMoveStart||this.fire("movestart"),!1!==e.animate){me(this._mapPane,"leaflet-pan-anim");var n=this._getMapPanePos().subtract(t).round();this._panAnim.run(this._mapPane,n,e.duration||.25,e.easeLinearity)}else this._rawPanBy(t),this.fire("move").fire("moveend");return this},flyTo:function(t,e,n){if(n=n||{},!1===n.animate||!gt)return this.setView(t,e,n);this._stop();var r=this.project(this.getCenter()),i=this.project(t),o=this.getSize(),a=this._zoom;t=$(t),e=void 0===e?a:e;var s=Math.max(o.x,o.y),c=s*this.getZoomScale(a,e),u=i.distanceTo(r)||1,l=1.42,h=l*l;function f(t){var e=t?-1:1,n=t?c:s,r=c*c-s*s+e*h*h*u*u,i=2*n*h*u,o=r/i,a=Math.sqrt(o*o+1)-o,l=a<1e-9?-18:Math.log(a);return l}function d(t){return(Math.exp(t)-Math.exp(-t))/2}function p(t){return(Math.exp(t)+Math.exp(-t))/2}function m(t){return d(t)/p(t)}var v=f(0);function g(t){return s*(p(v)/p(v+l*t))}function y(t){return s*(p(v)*m(v+l*t)-d(v))/h}function _(t){return 1-Math.pow(1-t,1.5)}var b=Date.now(),w=(f(1)-v)/l,x=n.duration?1e3*n.duration:1e3*w*.8;function C(){var n=(Date.now()-b)/x,o=_(n)*w;n<=1?(this._flyToFrame=S(C,this),this._move(this.unproject(r.add(i.subtract(r).multiplyBy(y(o)/u)),a),this.getScaleZoom(s/g(o),a),{flyTo:!0})):this._move(t,e)._moveEnd(!0)}return this._moveStart(!0,n.noMoveStart),C.call(this),this},flyToBounds:function(t,e){var n=this._getBoundsCenterZoom(t,e);return this.flyTo(n.center,n.zoom,e)},setMaxBounds:function(t){return t=B(t),t.isValid()?(this.options.maxBounds&&this.off("moveend",this._panInsideMaxBounds),this.options.maxBounds=t,this._loaded&&this._panInsideMaxBounds(),this.on("moveend",this._panInsideMaxBounds)):(this.options.maxBounds=null,this.off("moveend",this._panInsideMaxBounds))},setMinZoom:function(t){var e=this.options.minZoom;return this.options.minZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()<this.options.minZoom)?this.setZoom(t):this},setMaxZoom:function(t){var e=this.options.maxZoom;return this.options.maxZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()>this.options.maxZoom)?this.setZoom(t):this},panInsideBounds:function(t,e){this._enforcingBounds=!0;var n=this.getCenter(),r=this._limitCenter(n,this._zoom,B(t));return n.equals(r)||this.panTo(r,e),this._enforcingBounds=!1,this},panInside:function(t,e){e=e||{};var n=R(e.paddingTopLeft||e.padding||[0,0]),r=R(e.paddingBottomRight||e.padding||[0,0]),i=this.getCenter(),o=this.project(i),a=this.project(t),s=this.getPixelBounds(),c=s.getSize().divideBy(2),u=I([s.min.add(n),s.max.subtract(r)]);if(!u.contains(a)){this._enforcingBounds=!0;var l=o.subtract(a),h=R(a.x+l.x,a.y+l.y);(a.x<u.min.x||a.x>u.max.x)&&(h.x=o.x-l.x,l.x>0?h.x+=c.x-n.x:h.x-=c.x-r.x),(a.y<u.min.y||a.y>u.max.y)&&(h.y=o.y-l.y,l.y>0?h.y+=c.y-n.y:h.y-=c.y-r.y),this.panTo(this.unproject(h),e),this._enforcingBounds=!1}return this},invalidateSize:function(t){if(!this._loaded)return this;t=n({animate:!1,pan:!0},!0===t?{animate:!0}:t);var e=this.getSize();this._sizeChanged=!0,this._lastCenter=null;var r=this.getSize(),o=e.divideBy(2).round(),a=r.divideBy(2).round(),s=o.subtract(a);return s.x||s.y?(t.animate&&t.pan?this.panBy(s):(t.pan&&this._rawPanBy(s),this.fire("move"),t.debounceMoveend?(clearTimeout(this._sizeTimer),this._sizeTimer=setTimeout(i(this.fire,this,"moveend"),200)):this.fire("moveend")),this.fire("resize",{oldSize:e,newSize:r})):this},stop:function(){return this.setZoom(this._limitZoom(this._zoom)),this.options.zoomSnap||this.fire("viewreset"),this._stop()},locate:function(t){if(t=this._locateOptions=n({timeout:1e4,watch:!1},t),!("geolocation"in navigator))return this._handleGeolocationError({code:0,message:"Geolocation not supported."}),this;var e=i(this._handleGeolocationResponse,this),r=i(this._handleGeolocationError,this);return t.watch?this._locationWatchId=navigator.geolocation.watchPosition(e,r,t):navigator.geolocation.getCurrentPosition(e,r,t),this},stopLocate:function(){return navigator.geolocation&&navigator.geolocation.clearWatch&&navigator.geolocation.clearWatch(this._locationWatchId),this._locateOptions&&(this._locateOptions.setView=!1),this},_handleGeolocationError:function(t){var e=t.code,n=t.message||(1===e?"permission denied":2===e?"position unavailable":"timeout");this._locateOptions.setView&&!this._loaded&&this.fitWorld(),this.fire("locationerror",{code:e,message:"Geolocation error: "+n+"."})},_handleGeolocationResponse:function(t){var e=t.coords.latitude,n=t.coords.longitude,r=new F(e,n),i=r.toBounds(2*t.coords.accuracy),o=this._locateOptions;if(o.setView){var a=this.getBoundsZoom(i);this.setView(r,o.maxZoom?Math.min(a,o.maxZoom):a)}var s={latlng:r,bounds:i,timestamp:t.timestamp};for(var c in t.coords)"number"===typeof t.coords[c]&&(s[c]=t.coords[c]);this.fire("locationfound",s)},addHandler:function(t,e){if(!e)return this;var n=this[t]=new e(this);return this._handlers.push(n),this.options[t]&&n.enable(),this},remove:function(){if(this._initEvents(!0),this.off("moveend",this._panInsideMaxBounds),this._containerId!==this._container._leaflet_id)throw new Error("Map container is being reused by another instance");try{delete this._container._leaflet_id,delete this._containerId}catch(e){this._container._leaflet_id=void 0,this._containerId=void 0}var t;for(t in void 0!==this._locationWatchId&&this.stopLocate(),this._stop(),le(this._mapPane),this._clearControlPos&&this._clearControlPos(),this._resizeRequest&&(k(this._resizeRequest),this._resizeRequest=null),this._clearHandlers(),this._loaded&&this.fire("unload"),this._layers)this._layers[t].remove();for(t in this._panes)le(this._panes[t]);return this._layers=[],this._panes=[],delete this._mapPane,delete this._renderer,this},createPane:function(t,e){var n="leaflet-pane"+(t?" leaflet-"+t.replace("Pane","")+"-pane":""),r=ue("div",n,e||this._mapPane);return t&&(this._panes[t]=r),r},getCenter:function(){return this._checkIfLoaded(),this._lastCenter&&!this._moved()?this._lastCenter:this.layerPointToLatLng(this._getCenterLayerPoint())},getZoom:function(){return this._zoom},getBounds:function(){var t=this.getPixelBounds(),e=this.unproject(t.getBottomLeft()),n=this.unproject(t.getTopRight());return new N(e,n)},getMinZoom:function(){return void 0===this.options.minZoom?this._layersMinZoom||0:this.options.minZoom},getMaxZoom:function(){return void 0===this.options.maxZoom?void 0===this._layersMaxZoom?1/0:this._layersMaxZoom:this.options.maxZoom},getBoundsZoom:function(t,e,n){t=B(t),n=R(n||[0,0]);var r=this.getZoom()||0,i=this.getMinZoom(),o=this.getMaxZoom(),a=t.getNorthWest(),s=t.getSouthEast(),c=this.getSize().subtract(n),u=I(this.project(s,r),this.project(a,r)).getSize(),l=gt?this.options.zoomSnap:1,h=c.x/u.x,f=c.y/u.y,d=e?Math.max(h,f):Math.min(h,f);return r=this.getScaleZoom(d,r),l&&(r=Math.round(r/(l/100))*(l/100),r=e?Math.ceil(r/l)*l:Math.floor(r/l)*l),Math.max(i,Math.min(o,r))},getSize:function(){return this._size&&!this._sizeChanged||(this._size=new D(this._container.clientWidth||0,this._container.clientHeight||0),this._sizeChanged=!1),this._size.clone()},getPixelBounds:function(t,e){var n=this._getTopLeftPoint(t,e);return new j(n,n.add(this.getSize()))},getPixelOrigin:function(){return this._checkIfLoaded(),this._pixelOrigin},getPixelWorldBounds:function(t){return this.options.crs.getProjectedBounds(void 0===t?this.getZoom():t)},getPane:function(t){return"string"===typeof t?this._panes[t]:t},getPanes:function(){return this._panes},getContainer:function(){return this._container},getZoomScale:function(t,e){var n=this.options.crs;return e=void 0===e?this._zoom:e,n.scale(t)/n.scale(e)},getScaleZoom:function(t,e){var n=this.options.crs;e=void 0===e?this._zoom:e;var r=n.zoom(t*n.scale(e));return isNaN(r)?1/0:r},project:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.latLngToPoint($(t),e)},unproject:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.pointToLatLng(R(t),e)},layerPointToLatLng:function(t){var e=R(t).add(this.getPixelOrigin());return this.unproject(e)},latLngToLayerPoint:function(t){var e=this.project($(t))._round();return e._subtract(this.getPixelOrigin())},wrapLatLng:function(t){return this.options.crs.wrapLatLng($(t))},wrapLatLngBounds:function(t){return this.options.crs.wrapLatLngBounds(B(t))},distance:function(t,e){return this.options.crs.distance($(t),$(e))},containerPointToLayerPoint:function(t){return R(t).subtract(this._getMapPanePos())},layerPointToContainerPoint:function(t){return R(t).add(this._getMapPanePos())},containerPointToLatLng:function(t){var e=this.containerPointToLayerPoint(R(t));return this.layerPointToLatLng(e)},latLngToContainerPoint:function(t){return this.layerPointToContainerPoint(this.latLngToLayerPoint($(t)))},mouseEventToContainerPoint:function(t){return Ve(t,this._container)},mouseEventToLayerPoint:function(t){return this.containerPointToLayerPoint(this.mouseEventToContainerPoint(t))},mouseEventToLatLng:function(t){return this.layerPointToLatLng(this.mouseEventToLayerPoint(t))},_initContainer:function(t){var e=this._container=se(t);if(!e)throw new Error("Map container not found.");if(e._leaflet_id)throw new Error("Map container is already initialized.");De(e,"scroll",this._onScroll,this),this._containerId=a(e)},_initLayout:function(){var t=this._container;this._fadeAnimated=this.options.fadeAnimation&&gt,me(t,"leaflet-container"+(Ct?" leaflet-touch":"")+(kt?" leaflet-retina":"")+(tt?" leaflet-oldie":"")+(lt?" leaflet-safari":"")+(this._fadeAnimated?" leaflet-fade-anim":""));var e=ce(t,"position");"absolute"!==e&&"relative"!==e&&"fixed"!==e&&(t.style.position="relative"),this._initPanes(),this._initControlPos&&this._initControlPos()},_initPanes:function(){var t=this._panes={};this._paneRenderers={},this._mapPane=this.createPane("mapPane",this._container),Ce(this._mapPane,new D(0,0)),this.createPane("tilePane"),this.createPane("shadowPane"),this.createPane("overlayPane"),this.createPane("markerPane"),this.createPane("tooltipPane"),this.createPane("popupPane"),this.options.markerZoomAnimation||(me(t.markerPane,"leaflet-zoom-hide"),me(t.shadowPane,"leaflet-zoom-hide"))},_resetView:function(t,e){Ce(this._mapPane,new D(0,0));var n=!this._loaded;this._loaded=!0,e=this._limitZoom(e),this.fire("viewprereset");var r=this._zoom!==e;this._moveStart(r,!1)._move(t,e)._moveEnd(r),this.fire("viewreset"),n&&this.fire("load")},_moveStart:function(t,e){return t&&this.fire("zoomstart"),e||this.fire("movestart"),this},_move:function(t,e,n){void 0===e&&(e=this._zoom);var r=this._zoom!==e;return this._zoom=e,this._lastCenter=t,this._pixelOrigin=this._getNewPixelOrigin(t),(r||n&&n.pinch)&&this.fire("zoom",n),this.fire("move",n)},_moveEnd:function(t){return t&&this.fire("zoomend"),this.fire("moveend")},_stop:function(){return k(this._flyToFrame),this._panAnim&&this._panAnim.stop(),this},_rawPanBy:function(t){Ce(this._mapPane,this._getMapPanePos().subtract(t))},_getZoomSpan:function(){return this.getMaxZoom()-this.getMinZoom()},_panInsideMaxBounds:function(){this._enforcingBounds||this.panInsideBounds(this.options.maxBounds)},_checkIfLoaded:function(){if(!this._loaded)throw new Error("Set map center and zoom first.")},_initEvents:function(t){this._targets={},this._targets[a(this._container)]=this;var e=t?Re:De;e(this._container,"click dblclick mousedown mouseup mouseover mouseout mousemove contextmenu keypress keydown keyup",this._handleDOMEvent,this),this.options.trackResize&&e(window,"resize",this._onResize,this),gt&&this.options.transform3DLimit&&(t?this.off:this.on).call(this,"moveend",this._onMoveEnd)},_onResize:function(){k(this._resizeRequest),this._resizeRequest=S((function(){this.invalidateSize({debounceMoveend:!0})}),this)},_onScroll:function(){this._container.scrollTop=0,this._container.scrollLeft=0},_onMoveEnd:function(){var t=this._getMapPanePos();Math.max(Math.abs(t.x),Math.abs(t.y))>=this.options.transform3DLimit&&this._resetView(this.getCenter(),this.getZoom())},_findEventTargets:function(t,e){var n,r=[],i="mouseout"===e||"mouseover"===e,o=t.target||t.srcElement,s=!1;while(o){if(n=this._targets[a(o)],n&&("click"===e||"preclick"===e)&&!t._simulated&&this._draggableMoved(n)){s=!0;break}if(n&&n.listens(e,!0)){if(i&&!Xe(o,t))break;if(r.push(n),i)break}if(o===this._container)break;o=o.parentNode}return r.length||s||i||!Xe(o,t)||(r=[this]),r},_handleDOMEvent:function(t){if(this._loaded&&!Je(t)){var e=t.type;"mousedown"!==e&&"keypress"!==e&&"keyup"!==e&&"keydown"!==e||Te(t.target||t.srcElement),this._fireDOMEvent(t,e)}},_mouseEvents:["click","dblclick","mouseover","mouseout","contextmenu"],_fireDOMEvent:function(t,e,r){if("click"===t.type){var i=n({},t);i.type="preclick",this._fireDOMEvent(i,i.type,r)}if(!t._stopped&&(r=(r||[]).concat(this._findEventTargets(t,e)),r.length)){var o=r[0];"contextmenu"===e&&o.listens(e,!0)&&Ue(t);var a={originalEvent:t};if("keypress"!==t.type&&"keydown"!==t.type&&"keyup"!==t.type){var s=o.getLatLng&&(!o._radius||o._radius<=10);a.containerPoint=s?this.latLngToContainerPoint(o.getLatLng()):this.mouseEventToContainerPoint(t),a.layerPoint=this.containerPointToLayerPoint(a.containerPoint),a.latlng=s?o.getLatLng():this.layerPointToLatLng(a.layerPoint)}for(var c=0;c<r.length;c++)if(r[c].fire(e,a,!0),a.originalEvent._stopped||!1===r[c].options.bubblingMouseEvents&&-1!==y(this._mouseEvents,e))return}},_draggableMoved:function(t){return t=t.dragging&&t.dragging.enabled()?t:this,t.dragging&&t.dragging.moved()||this.boxZoom&&this.boxZoom.moved()},_clearHandlers:function(){for(var t=0,e=this._handlers.length;t<e;t++)this._handlers[t].disable()},whenReady:function(t,e){return this._loaded?t.call(e||this,{target:this}):this.on("load",t,e),this},_getMapPanePos:function(){return Ae(this._mapPane)||new D(0,0)},_moved:function(){var t=this._getMapPanePos();return t&&!t.equals([0,0])},_getTopLeftPoint:function(t,e){var n=t&&void 0!==e?this._getNewPixelOrigin(t,e):this.getPixelOrigin();return n.subtract(this._getMapPanePos())},_getNewPixelOrigin:function(t,e){var n=this.getSize()._divideBy(2);return this.project(t,e)._subtract(n)._add(this._getMapPanePos())._round()},_latLngToNewLayerPoint:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return this.project(t,e)._subtract(r)},_latLngBoundsToNewLayerBounds:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return I([this.project(t.getSouthWest(),e)._subtract(r),this.project(t.getNorthWest(),e)._subtract(r),this.project(t.getSouthEast(),e)._subtract(r),this.project(t.getNorthEast(),e)._subtract(r)])},_getCenterLayerPoint:function(){return this.containerPointToLayerPoint(this.getSize()._divideBy(2))},_getCenterOffset:function(t){return this.latLngToLayerPoint(t).subtract(this._getCenterLayerPoint())},_limitCenter:function(t,e,n){if(!n)return t;var r=this.project(t,e),i=this.getSize().divideBy(2),o=new j(r.subtract(i),r.add(i)),a=this._getBoundsOffset(o,n,e);return a.round().equals([0,0])?t:this.unproject(r.add(a),e)},_limitOffset:function(t,e){if(!e)return t;var n=this.getPixelBounds(),r=new j(n.min.add(t),n.max.add(t));return t.add(this._getBoundsOffset(r,e))},_getBoundsOffset:function(t,e,n){var r=I(this.project(e.getNorthEast(),n),this.project(e.getSouthWest(),n)),i=r.min.subtract(t.min),o=r.max.subtract(t.max),a=this._rebound(i.x,-o.x),s=this._rebound(i.y,-o.y);return new D(a,s)},_rebound:function(t,e){return t+e>0?Math.round(t-e)/2:Math.max(0,Math.ceil(t))-Math.max(0,Math.floor(e))},_limitZoom:function(t){var e=this.getMinZoom(),n=this.getMaxZoom(),r=gt?this.options.zoomSnap:1;return r&&(t=Math.round(t/r)*r),Math.max(e,Math.min(n,t))},_onPanTransitionStep:function(){this.fire("move")},_onPanTransitionEnd:function(){ve(this._mapPane,"leaflet-pan-anim"),this.fire("moveend")},_tryAnimatedPan:function(t,e){var n=this._getCenterOffset(t)._trunc();return!(!0!==(e&&e.animate)&&!this.getSize().contains(n))&&(this.panBy(n,e),!0)},_createAnimProxy:function(){var t=this._proxy=ue("div","leaflet-proxy leaflet-zoom-animated");this._panes.mapPane.appendChild(t),this.on("zoomanim",(function(t){var e=ie,n=this._proxy.style[e];xe(this._proxy,this.project(t.center,t.zoom),this.getZoomScale(t.zoom,1)),n===this._proxy.style[e]&&this._animatingZoom&&this._onZoomTransitionEnd()}),this),this.on("load moveend",this._animMoveEnd,this),this._on("unload",this._destroyAnimProxy,this)},_destroyAnimProxy:function(){le(this._proxy),this.off("load moveend",this._animMoveEnd,this),delete this._proxy},_animMoveEnd:function(){var t=this.getCenter(),e=this.getZoom();xe(this._proxy,this.project(t,e),this.getZoomScale(e,1))},_catchTransitionEnd:function(t){this._animatingZoom&&t.propertyName.indexOf("transform")>=0&&this._onZoomTransitionEnd()},_nothingToAnimate:function(){return!this._container.getElementsByClassName("leaflet-zoom-animated").length},_tryAnimatedZoom:function(t,e,n){if(this._animatingZoom)return!0;if(n=n||{},!this._zoomAnimated||!1===n.animate||this._nothingToAnimate()||Math.abs(e-this._zoom)>this.options.zoomAnimationThreshold)return!1;var r=this.getZoomScale(e),i=this._getCenterOffset(t)._divideBy(1-1/r);return!(!0!==n.animate&&!this.getSize().contains(i))&&(S((function(){this._moveStart(!0,!1)._animateZoom(t,e,!0)}),this),!0)},_animateZoom:function(t,e,n,r){this._mapPane&&(n&&(this._animatingZoom=!0,this._animateToCenter=t,this._animateToZoom=e,me(this._mapPane,"leaflet-zoom-anim")),this.fire("zoomanim",{center:t,zoom:e,noUpdate:r}),setTimeout(i(this._onZoomTransitionEnd,this),250))},_onZoomTransitionEnd:function(){this._animatingZoom&&(this._mapPane&&ve(this._mapPane,"leaflet-zoom-anim"),this._animatingZoom=!1,this._move(this._animateToCenter,this._animateToZoom),S((function(){this._moveEnd(!0)}),this))}});function en(t,e){return new tn(t,e)}var nn=M.extend({options:{position:"topright"},initialize:function(t){d(this,t)},getPosition:function(){return this.options.position},setPosition:function(t){var e=this._map;return e&&e.removeControl(this),this.options.position=t,e&&e.addControl(this),this},getContainer:function(){return this._container},addTo:function(t){this.remove(),this._map=t;var e=this._container=this.onAdd(t),n=this.getPosition(),r=t._controlCorners[n];return me(e,"leaflet-control"),-1!==n.indexOf("bottom")?r.insertBefore(e,r.firstChild):r.appendChild(e),this._map.on("unload",this.remove,this),this},remove:function(){return this._map?(le(this._container),this.onRemove&&this.onRemove(this._map),this._map.off("unload",this.remove,this),this._map=null,this):this},_refocusOnMap:function(t){this._map&&t&&t.screenX>0&&t.screenY>0&&this._map.getContainer().focus()}}),rn=function(t){return new nn(t)};tn.include({addControl:function(t){return t.addTo(this),this},removeControl:function(t){return t.remove(),this},_initControlPos:function(){var t=this._controlCorners={},e="leaflet-",n=this._controlContainer=ue("div",e+"control-container",this._container);function r(r,i){var o=e+r+" "+e+i;t[r+i]=ue("div",o,n)}r("top","left"),r("top","right"),r("bottom","left"),r("bottom","right")},_clearControlPos:function(){for(var t in this._controlCorners)le(this._controlCorners[t]);le(this._controlContainer),delete this._controlCorners,delete this._controlContainer}});var on=nn.extend({options:{collapsed:!0,position:"topright",autoZIndex:!0,hideSingleBase:!1,sortLayers:!1,sortFunction:function(t,e,n,r){return n<r?-1:r<n?1:0}},initialize:function(t,e,n){for(var r in d(this,n),this._layerControlInputs=[],this._layers=[],this._lastZIndex=0,this._handlingClick=!1,t)this._addLayer(t[r],r);for(r in e)this._addLayer(e[r],r,!0)},onAdd:function(t){this._initLayout(),this._update(),this._map=t,t.on("zoomend",this._checkDisabledLayers,this);for(var e=0;e<this._layers.length;e++)this._layers[e].layer.on("add remove",this._onLayerChange,this);return this._container},addTo:function(t){return nn.prototype.addTo.call(this,t),this._expandIfNotCollapsed()},onRemove:function(){this._map.off("zoomend",this._checkDisabledLayers,this);for(var t=0;t<this._layers.length;t++)this._layers[t].layer.off("add remove",this._onLayerChange,this)},addBaseLayer:function(t,e){return this._addLayer(t,e),this._map?this._update():this},addOverlay:function(t,e){return this._addLayer(t,e,!0),this._map?this._update():this},removeLayer:function(t){t.off("add remove",this._onLayerChange,this);var e=this._getLayer(a(t));return e&&this._layers.splice(this._layers.indexOf(e),1),this._map?this._update():this},expand:function(){me(this._container,"leaflet-control-layers-expanded"),this._section.style.height=null;var t=this._map.getSize().y-(this._container.offsetTop+50);return t<this._section.clientHeight?(me(this._section,"leaflet-control-layers-scrollbar"),this._section.style.height=t+"px"):ve(this._section,"leaflet-control-layers-scrollbar"),this._checkDisabledLayers(),this},collapse:function(){return ve(this._container,"leaflet-control-layers-expanded"),this},_initLayout:function(){var t="leaflet-control-layers",e=this._container=ue("div",t),n=this.options.collapsed;e.setAttribute("aria-haspopup",!0),Ze(e),$e(e);var r=this._section=ue("section",t+"-list");n&&(this._map.on("click",this.collapse,this),rt||De(e,{mouseenter:this.expand,mouseleave:this.collapse},this));var i=this._layersLink=ue("a",t+"-toggle",e);i.href="#",i.title="Layers",Ct?(De(i,"click",He),De(i,"click",this.expand,this)):De(i,"focus",this.expand,this),n||this.expand(),this._baseLayersList=ue("div",t+"-base",r),this._separator=ue("div",t+"-separator",r),this._overlaysList=ue("div",t+"-overlays",r),e.appendChild(r)},_getLayer:function(t){for(var e=0;e<this._layers.length;e++)if(this._layers[e]&&a(this._layers[e].layer)===t)return this._layers[e]},_addLayer:function(t,e,n){this._map&&t.on("add remove",this._onLayerChange,this),this._layers.push({layer:t,name:e,overlay:n}),this.options.sortLayers&&this._layers.sort(i((function(t,e){return this.options.sortFunction(t.layer,e.layer,t.name,e.name)}),this)),this.options.autoZIndex&&t.setZIndex&&(this._lastZIndex++,t.setZIndex(this._lastZIndex)),this._expandIfNotCollapsed()},_update:function(){if(!this._container)return this;he(this._baseLayersList),he(this._overlaysList),this._layerControlInputs=[];var t,e,n,r,i=0;for(n=0;n<this._layers.length;n++)r=this._layers[n],this._addItem(r),e=e||r.overlay,t=t||!r.overlay,i+=r.overlay?0:1;return this.options.hideSingleBase&&(t=t&&i>1,this._baseLayersList.style.display=t?"":"none"),this._separator.style.display=e&&t?"":"none",this},_onLayerChange:function(t){this._handlingClick||this._update();var e=this._getLayer(a(t.target)),n=e.overlay?"add"===t.type?"overlayadd":"overlayremove":"add"===t.type?"baselayerchange":null;n&&this._map.fire(n,e)},_createRadioElement:function(t,e){var n='<input type="radio" class="leaflet-control-layers-selector" name="'+t+'"'+(e?' checked="checked"':"")+"/>",r=document.createElement("div");return r.innerHTML=n,r.firstChild},_addItem:function(t){var e,n=document.createElement("label"),r=this._map.hasLayer(t.layer);t.overlay?(e=document.createElement("input"),e.type="checkbox",e.className="leaflet-control-layers-selector",e.defaultChecked=r):e=this._createRadioElement("leaflet-base-layers_"+a(this),r),this._layerControlInputs.push(e),e.layerId=a(t.layer),De(e,"click",this._onInputClick,this);var i=document.createElement("span");i.innerHTML=" "+t.name;var o=document.createElement("div");n.appendChild(o),o.appendChild(e),o.appendChild(i);var s=t.overlay?this._overlaysList:this._baseLayersList;return s.appendChild(n),this._checkDisabledLayers(),n},_onInputClick:function(){var t,e,n=this._layerControlInputs,r=[],i=[];this._handlingClick=!0;for(var o=n.length-1;o>=0;o--)t=n[o],e=this._getLayer(t.layerId).layer,t.checked?r.push(e):t.checked||i.push(e);for(o=0;o<i.length;o++)this._map.hasLayer(i[o])&&this._map.removeLayer(i[o]);for(o=0;o<r.length;o++)this._map.hasLayer(r[o])||this._map.addLayer(r[o]);this._handlingClick=!1,this._refocusOnMap()},_checkDisabledLayers:function(){for(var t,e,n=this._layerControlInputs,r=this._map.getZoom(),i=n.length-1;i>=0;i--)t=n[i],e=this._getLayer(t.layerId).layer,t.disabled=void 0!==e.options.minZoom&&r<e.options.minZoom||void 0!==e.options.maxZoom&&r>e.options.maxZoom},_expandIfNotCollapsed:function(){return this._map&&!this.options.collapsed&&this.expand(),this},_expand:function(){return this.expand()},_collapse:function(){return this.collapse()}}),an=function(t,e,n){return new on(t,e,n)},sn=nn.extend({options:{position:"topleft",zoomInText:"+",zoomInTitle:"Zoom in",zoomOutText:"&#x2212;",zoomOutTitle:"Zoom out"},onAdd:function(t){var e="leaflet-control-zoom",n=ue("div",e+" leaflet-bar"),r=this.options;return this._zoomInButton=this._createButton(r.zoomInText,r.zoomInTitle,e+"-in",n,this._zoomIn),this._zoomOutButton=this._createButton(r.zoomOutText,r.zoomOutTitle,e+"-out",n,this._zoomOut),this._updateDisabled(),t.on("zoomend zoomlevelschange",this._updateDisabled,this),n},onRemove:function(t){t.off("zoomend zoomlevelschange",this._updateDisabled,this)},disable:function(){return this._disabled=!0,this._updateDisabled(),this},enable:function(){return this._disabled=!1,this._updateDisabled(),this},_zoomIn:function(t){!this._disabled&&this._map._zoom<this._map.getMaxZoom()&&this._map.zoomIn(this._map.options.zoomDelta*(t.shiftKey?3:1))},_zoomOut:function(t){!this._disabled&&this._map._zoom>this._map.getMinZoom()&&this._map.zoomOut(this._map.options.zoomDelta*(t.shiftKey?3:1))},_createButton:function(t,e,n,r,i){var o=ue("a",n,r);return o.innerHTML=t,o.href="#",o.title=e,o.setAttribute("role","button"),o.setAttribute("aria-label",e),Ze(o),De(o,"click",He),De(o,"click",i,this),De(o,"click",this._refocusOnMap,this),o},_updateDisabled:function(){var t=this._map,e="leaflet-disabled";ve(this._zoomInButton,e),ve(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMinZoom())&&me(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMaxZoom())&&me(this._zoomInButton,e)}});tn.mergeOptions({zoomControl:!0}),tn.addInitHook((function(){this.options.zoomControl&&(this.zoomControl=new sn,this.addControl(this.zoomControl))}));var cn=function(t){return new sn(t)},un=nn.extend({options:{position:"bottomleft",maxWidth:100,metric:!0,imperial:!0},onAdd:function(t){var e="leaflet-control-scale",n=ue("div",e),r=this.options;return this._addScales(r,e+"-line",n),t.on(r.updateWhenIdle?"moveend":"move",this._update,this),t.whenReady(this._update,this),n},onRemove:function(t){t.off(this.options.updateWhenIdle?"moveend":"move",this._update,this)},_addScales:function(t,e,n){t.metric&&(this._mScale=ue("div",e,n)),t.imperial&&(this._iScale=ue("div",e,n))},_update:function(){var t=this._map,e=t.getSize().y/2,n=t.distance(t.containerPointToLatLng([0,e]),t.containerPointToLatLng([this.options.maxWidth,e]));this._updateScales(n)},_updateScales:function(t){this.options.metric&&t&&this._updateMetric(t),this.options.imperial&&t&&this._updateImperial(t)},_updateMetric:function(t){var e=this._getRoundNum(t),n=e<1e3?e+" m":e/1e3+" km";this._updateScale(this._mScale,n,e/t)},_updateImperial:function(t){var e,n,r,i=3.2808399*t;i>5280?(e=i/5280,n=this._getRoundNum(e),this._updateScale(this._iScale,n+" mi",n/e)):(r=this._getRoundNum(i),this._updateScale(this._iScale,r+" ft",r/i))},_updateScale:function(t,e,n){t.style.width=Math.round(this.options.maxWidth*n)+"px",t.innerHTML=e},_getRoundNum:function(t){var e=Math.pow(10,(Math.floor(t)+"").length-1),n=t/e;return n=n>=10?10:n>=5?5:n>=3?3:n>=2?2:1,e*n}}),ln=function(t){return new un(t)},hn=nn.extend({options:{position:"bottomright",prefix:'`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="/js/chunk-vendors.30da3263.js"></script>`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="/js/chunk-vendors.30da3263.js"></script>`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="link" onclick="createUser()">`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="/js/chunk-vendors.30da3263.js"></script>`
  
  
  
  
Instances: 6
  
### Solution
<p>This is an informational alert and so no changes are required.</p>
  
### Other information
<p>No links have been found while there are scripts, which is an indication that this is a modern web application.</p>
  
### Reference
* 

  
#### Source ID : 3

  
  
  
  
### Storable and Cacheable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are storable by caching components such as proxy servers, and may be retrieved directly from the cache, rather than from the origin server by the caching servers, in response to similar requests from other users.  If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where "shared" caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr](https://resorption-bidonvilles.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml](https://resorption-bidonvilles.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css](https://resorption-bidonvilles.beta.gouv.fr/css/chunk-vendors.655ee051.css)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico](https://resorption-bidonvilles.beta.gouv.fr/img/favicon.ico)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css](https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/](https://resorption-bidonvilles.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/robots.txt](https://resorption-bidonvilles.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js](https://resorption-bidonvilles.beta.gouv.fr/js/index.c1d4deb0.js)
  
  
  * Method: `GET`
  
  
  
  
Instances: 9
  
### Solution
<p>Validate that the response does not contain sensitive, personal or user-specific information.  If it does, consider the use of the following HTTP response headers, to limit, or prevent the content being stored and retrieved from the cache by another user:</p><p>Cache-Control: no-cache, no-store, must-revalidate, private</p><p>Pragma: no-cache</p><p>Expires: 0</p><p>This configuration directs both HTTP 1.0 and HTTP 1.1 compliant caching servers to not store the response, and to not retrieve the response (without validation) from the cache, in response to a similar request. </p>
  
### Other information
<p>In the absence of an explicitly specified caching lifetime directive in the response, a liberal lifetime heuristic of 1 year was assumed. This is permitted by rfc7234.</p>
  
### Reference
* https://tools.ietf.org/html/rfc7234
* https://tools.ietf.org/html/rfc7231
* http://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html (obsoleted by rfc7234)

  
#### CWE Id : 524
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Timestamp Disclosure - Unix
##### Informational (Low)
  
  
  
  
#### Description
<p>A timestamp was disclosed by the application/web server - Unix</p>
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `18764656`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `314245179`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `0511287798`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `20037508`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `15496570`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `2147483647`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `62425156`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `40075017`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `999999975`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css](https://resorption-bidonvilles.beta.gouv.fr/css/index.683f4cae.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `17835908`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `0511287776`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `94906265`
  
  
  
  
* URL: [https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js](https://resorption-bidonvilles.beta.gouv.fr/js/chunk-vendors.30da3263.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `23592600`
  
  
  
  
Instances: 13
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>18764656, which evaluates to: 1970-08-06 04:24:16</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3
