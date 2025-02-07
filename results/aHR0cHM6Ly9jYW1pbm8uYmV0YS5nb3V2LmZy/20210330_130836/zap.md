
# ZAP Scanning Report

Generated on Tue, 30 Mar 2021 13:07:40


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 2 |
| Low | 5 |
| Informational | 6 |

## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- | 
| Cross-Domain Misconfiguration | Medium | 9 | 
| CSP: Wildcard Directive | Medium | 5 | 
| Dangerous JS Functions | Low | 5 | 
| Feature Policy Header Not Set | Low | 10 | 
| Incomplete or No Cache-control and Pragma HTTP Header Set | Low | 3 | 
| Server Leaks Information via "X-Powered-By" HTTP Response Header Field(s) | Low | 11 | 
| Server Leaks Version Information via "Server" HTTP Response Header Field | Low | 11 | 
| Base64 Disclosure | Informational | 3 | 
| Information Disclosure - Suspicious Comments | Informational | 12 | 
| Modern Web Application | Informational | 4 | 
| Storable and Cacheable Content | Informational | 3 | 
| Storable but Non-Cacheable Content | Informational | 8 | 
| Timestamp Disclosure - Unix | Informational | 11 | 

## Alert Detail


  
  
  
  
### Cross-Domain Misconfiguration
##### Medium (Medium)
  
  
  
  
#### Description
<p>Web browser data loading may be possible, due to a Cross Origin Resource Sharing (CORS) misconfiguration on the web server</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/favicon.ico](https://camino.beta.gouv.fr/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app-legacy.2205671c.js](https://camino.beta.gouv.fr/js/app-legacy.2205671c.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `Access-Control-Allow-Origin: *`
  
  
  
  
Instances: 9
  
### Solution
<p>Ensure that sensitive data is not available in an unauthenticated manner (using IP address white-listing, for instance).</p><p>Configure the "Access-Control-Allow-Origin" HTTP header to a more restrictive set of domains, or remove all CORS headers entirely, to allow the web browser to enforce the Same Origin Policy (SOP) in a more restrictive manner.</p>
  
### Other information
<p>The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.</p>
  
### Reference
* http://www.hpenterprisesecurity.com/vulncat/en/vulncat/vb/html5_overly_permissive_cors_policy.html

  
#### CWE Id : 264
  
#### WASC Id : 14
  
#### Source ID : 3

  
  
  
  
### CSP: Wildcard Directive
##### Medium (Medium)
  
  
  
  
#### Description
<p>The following directives either allow wildcard sources (or ancestors), are not defined, or are overly broadly defined: </p><p>frame-ancestors, form-action</p><p></p><p>The directive(s): frame-ancestors, form-action are among the directives that do not fallback to default-src, missing/excluding them is the same as allowing anything.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/robots.txt](https://camino.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'none'`
  
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self'; script-src 'self' https://stats.data.gouv.fr 'sha256-4RS22DYeB7U14dra4KcQYxmwt5HkOInieXK1NUMBmQI='; style-src 'self' 'sha256-yUOnKCENzSdKikR9gEEAu8IogIBNlifamnNNH1E31SE='; connect-src 'self' api.camino.beta.gouv.fr sentry.io; img-src data: 'self' https://stats.data.gouv.fr a.tile.openstreetmap.org b.tile.openstreetmap.org c.tile.openstreetmap.org  a.tile.openstreetmap.fr b.tile.openstreetmap.fr c.tile.openstreetmap.fr geoservices.brgm.fr wxs.ign.fr; frame-src app.mailjet.com;`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self'; script-src 'self' https://stats.data.gouv.fr 'sha256-4RS22DYeB7U14dra4KcQYxmwt5HkOInieXK1NUMBmQI='; style-src 'self' 'sha256-yUOnKCENzSdKikR9gEEAu8IogIBNlifamnNNH1E31SE='; connect-src 'self' api.camino.beta.gouv.fr sentry.io; img-src data: 'self' https://stats.data.gouv.fr a.tile.openstreetmap.org b.tile.openstreetmap.org c.tile.openstreetmap.org  a.tile.openstreetmap.fr b.tile.openstreetmap.fr c.tile.openstreetmap.fr geoservices.brgm.fr wxs.ign.fr; frame-src app.mailjet.com;`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/sitemap.xml](https://camino.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'none'`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/a-propos.](https://camino.beta.gouv.fr/a-propos.)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'none'`
  
  
  
  
Instances: 5
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is properly configured to set the Content-Security-Policy header.</p>
  
### Reference
* http://www.w3.org/TR/CSP2/
* http://www.w3.org/TR/CSP/
* http://caniuse.com/#search=content+security+policy
* http://content-security-policy.com/
* https://github.com/shapesecurity/salvation
* https://developers.google.com/web/fundamentals/security/csp#policy_applies_to_a_wide_variety_of_resources

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Dangerous JS Functions
##### Low (Low)
  
  
  
  
#### Description
<p>A dangerous JS function seems to be in use that would leave the site vulnerable.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eval`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eval`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eVal`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eVal`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app-legacy.2205671c.js](https://camino.beta.gouv.fr/js/app-legacy.2205671c.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eVal`
  
  
  
  
Instances: 5
  
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
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app-legacy.2205671c.js](https://camino.beta.gouv.fr/js/app-legacy.2205671c.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/sitemap.xml](https://camino.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/a-propos.](https://camino.beta.gouv.fr/a-propos.)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/robots.txt](https://camino.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
Instances: 10
  
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
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
Instances: 3
  
### Solution
<p>Whenever possible ensure the cache-control HTTP header is set with no-cache, no-store, must-revalidate; and that the pragma HTTP header is set with no-cache.</p>
  
### Reference
* https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching

  
#### CWE Id : 525
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Server Leaks Information via "X-Powered-By" HTTP Response Header Field(s)
##### Low (Medium)
  
  
  
  
#### Description
<p>The web/application server is leaking information via one or more "X-Powered-By" HTTP response headers. Access to such information may facilitate attackers identifying other frameworks/components your web application is reliant upon and the vulnerabilities such components may be subject to.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/sitemap.xml](https://camino.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/robots.txt](https://camino.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/a-propos.](https://camino.beta.gouv.fr/a-propos.)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/favicon.ico](https://camino.beta.gouv.fr/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that your web server, application server, load balancer, etc. is configured to suppress "X-Powered-By" headers.</p>
  
### Reference
* http://blogs.msdn.com/b/varunm/archive/2013/04/23/remove-unwanted-http-response-headers.aspx
* http://www.troyhunt.com/2012/02/shhh-dont-let-your-response-headers.html

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Server Leaks Version Information via "Server" HTTP Response Header Field
##### Low (High)
  
  
  
  
#### Description
<p>The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/favicon.ico](https://camino.beta.gouv.fr/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/sitemap.xml](https://camino.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/robots.txt](https://camino.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/a-propos.](https://camino.beta.gouv.fr/a-propos.)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `nginx/1.19.2`
  
  
  
  
Instances: 11
  
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

  
  
  
  
### Base64 Disclosure
##### Informational (Medium)
  
  
  
  
#### Description
<p>Base64 encoded data was disclosed by the application/web server. Note: in the interests of performance not all base64 strings in the response were analyzed individually, the entire response should be looked at by the analyst/security team/developer(s).</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `iVBORw0KGgoAAAANSUhEUgAAADIAAABSCAMAAAAhFXfZAAAC91BMVEVMaXEzeak2f7I4g7g3g7cua5gzeKg8hJo3grY4g7c3grU0gLI2frE0daAubJc2gbQwd6QzeKk2gLMtd5sxdKIua5g1frA2f7IydaM0e6w2fq41fK01eqo3grgubJgta5cxdKI1f7AydaQydaMxc6EubJgvbJkwcZ4ubZkwcJwubZgubJcydqUydKIxapgubJctbJcubZcubJcvbJYubJcvbZkubJctbJctbZcubJg2f7AubJcrbZcubJcubJcua5g3grY0fq8ubJcubJdEkdEwhsw6i88vhswuhcsuhMtBjMgthMsrg8srgss6is8qgcs8i9A9iMYtg8spgcoogMo7hcMngMonf8olfso4gr8kfck5iM8jfMk4iM8he8k1fro7itAgesk2hs8eecgzfLcofssdeMg0hc4cd8g2hcsxeLQbdsgZdcgxeLImfcszhM0vda4xgckzhM4xg84wf8Yxgs4udKsvfcQucqhUndROmdM1fK0wcZ8vb5w0eqpQm9MzeKhXoNVcpdYydKNWn9VZotVKltJFjsIwcJ1Rms9OlslLmtH///8+kc9epdYzd6dbo9VHkMM2f7FHmNBClM8ydqVcpNY9hro3gLM9hLczealQmcw3fa46f7A8gLMxc6I3eagyc6FIldJMl9JSnNRSntNNl9JPnNJFi75UnM9ZodVKksg8kM45jc09e6ZHltFBk883gbRBh7pDk9EwcaBzn784g7dKkcY2i81Om9M7j85Llc81is09g7Q4grY/j9A0eqxKmdFFltBEjcXf6fFImdBCiLxJl9FGlNFBi78yiMxVndEvbpo6js74+vx+psPP3+o/ks5HkcpGmNCjwdZCkNDM3ehYoNJEls+lxNkxh8xHks0+jdC1zd5Lg6r+/v/H2ufz9/o3jM3t8/edvdM/k89Th61OiLBSjbZklbaTt9BfptdjmL1AicBHj8hGk9FAgK1dkLNTjLRekrdClc/k7fM0icy0y9tgp9c4jc2NtM9Dlc8zicxeXZn3AAAAQ3RSTlMAHDdTb4yPA+LtnEQmC4L2EmHqB7XA0d0sr478x4/Yd5i1zOfyPkf1sLVq4Nh3FvjxopQ2/STNuFzUwFIwxKaejILpIBEV9wAABhVJREFUeF6s1NdyFEcYBeBeoQIhRAkLlRDGrhIgY3BJL8CVeKzuyXFzzjkn5ZxzzuScg3PO8cKzu70JkO0LfxdTU//pM9vTu7Xgf6KqOVTb9X7toRrVEfBf1HTVjZccrT/2by1VV928Yty9ZbVuucdz90frG8DBjl9pVApbOstvmMuvVgaNXSfAAd6pGxpy6yxf5ph43pS/4f3uoaGm2rdu72S9xzOvMymkZFq/ptDrk90mhW7e4zl7HLzhxGWPR20xmSxJ/VqldG5m9XhaVOA1DadsNh3Pu5L2N6QtPO/32JpqQBVVk20oy/Pi2s23WEvyfHbe1thadVQttvm7Llf65gGmXK67XtupyoM7HQhmXdLS8oGWJNeOJ3C5fG5XCEJnkez3/oFdsvgJ4l2ANZwhrJKk/7OSXa+3Vw2WJMlKnGkobouYk6T0TyX30klOUnTD9HJ5qpckL3EW/w4XF3Xd0FGywXUrstrclVsqz5Pd/sXFYyDnPdrLcQODmGOK47IZb4CmibmMn+MYRzFZ5jg33ZL/EJrWcszHmANy3ARBK/IXtciJy8VsitPSdE3uuHxzougojcUdr8/32atnz/ev3f/K5wtpxUTpcaI45zusVDpYtZi+jg0oU9b3x74h7+n9ABvYEZeKaVq0sh0AtLKsFtqNBdeT0MrSzwwlq9+x6xAO4tgOtSzbCjrNQQiNvQUbUEubvzBUeGw26yDCsRHCoLkTHDa7IdOLIThs/gHvChszh2CimE8peRs47cxANI0lYNB5y1DljpOF0IhzBDPOZnDOqYYbeGKECbPzWnXludPphw5c2YBq5zlwXphIbO4VDCZ0gnPfUO1TwZoYwAs2ExPCedAu9DAjfQUjzITQb3jNj0KG2Sgt6BHaQUdYzWz+XmBktOHwanXjaSTcwwziBcuMOtwBmqPrTOxFQR/DRKKPqyur0aiW6cULYsx6tBm0jXpR/AUWR6HRq9WVW6MRhIq5jLyjbaCTDCijyYJNpCajdyobP/eTw0iexBAKkJ3gA5KcQb2zBXsIBckn+xVv8jkZSaEFHE+jFEleAEfayRU0MouNoBmB/L50Ai/HSLIHxcrpCvnhSQAuakKp2C/YbCylJjXRVy/z3+Kv/RrNcCo+WUzlVEhzKffnTQnxeN9fWF88fiNCUdSTsaufaChKWInHeysygfpIqagoakW+vV20J8uyl6TyNKEZWV4oRSPyCkWpgOLSbkCObT8o2r6tlG58HQquf6O0v50tB7JM7F4EORd2dx/K0w/KHsVkLPaoYrwgP/y7krr3SSMA4zj+OBgmjYkxcdIJQyQRKgg2viX9Hddi9UBb29LrKR7CVVEEEXWojUkXNyfTNDE14W9gbHJNuhjDettN3ZvbOvdOqCD3Jp/9l+/wJE+9PkYGjx/fqkys3S2rMozM/o2106rfMUINo6hVqz+eu/hd1c4xTg0TAfy5kV+4UG6+IthHTU9woWmxuKNbTfuCSfovBCxq7EtHqvYL4Sm6F8GVxsSXHMQ07TOi1DKtZxjWaaIyi4CXWjxPccUw8WVbMYY5wxC1mzEyXMJWkllpRloi+Kkoq69sxBTlElF6aAxYUbjXNlhlDZilDnM4U5SlN5biRsRHnbx3mbeWjEh4mEyiuJDl5XcWVmX5GvNkFgLWZM5qwsop4/AWfLhU1cR7k1VVvcYCWRkOI6Xy5gmnphCYIkvzuNYzHzosq2oNk2RtSs8khfUOfHIDgR6ysYBaMpl4uEgk2U/oJTs9AaTSwma7dT69geAE2ZpEjUsn2ieJNHeKfrI3EcAGJ2ZaNgVuC8EBctCLc57P5u5led6IOBkIYkuQMrmmjChs4VkfOerHqSBkPzZlhe06RslZ3zMjk2sscqKwY0RcjKK+LWbzd7KiHhkncs/siFJ+V5eXxD34B8nVuJEpGJNmxN2gH3vSvp7J70tF+D1Ej8qUJD1TkErAND2GZwTFg/LubvmgiBG3SOvdlsqFQrkEzJCL1rstlnVFROixZoDDSuXQFHESwVGlcuQcMb/b42NgjLowh5MTDFE3vNB5qStRIErdCQEh6pLPR92anSUb/wAIhldAaDMpGgAAAABJRU5ErkJggg==`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `iVBORw0KGgoAAAANSUhEUgAAADIAAABSCAMAAAAhFXfZAAAC91BMVEVMaXEzeak2f7I4g7g3g7cua5gzeKg8hJo3grY4g7c3grU0gLI2frE0daAubJc2gbQwd6QzeKk2gLMtd5sxdKIua5g1frA2f7IydaM0e6w2fq41fK01eqo3grgubJgta5cxdKI1f7AydaQydaMxc6EubJgvbJkwcZ4ubZkwcJwubZgubJcydqUydKIxapgubJctbJcubZcubJcvbJYubJcvbZkubJctbJctbZcubJg2f7AubJcrbZcubJcubJcua5g3grY0fq8ubJcubJdEkdEwhsw6i88vhswuhcsuhMtBjMgthMsrg8srgss6is8qgcs8i9A9iMYtg8spgcoogMo7hcMngMonf8olfso4gr8kfck5iM8jfMk4iM8he8k1fro7itAgesk2hs8eecgzfLcofssdeMg0hc4cd8g2hcsxeLQbdsgZdcgxeLImfcszhM0vda4xgckzhM4xg84wf8Yxgs4udKsvfcQucqhUndROmdM1fK0wcZ8vb5w0eqpQm9MzeKhXoNVcpdYydKNWn9VZotVKltJFjsIwcJ1Rms9OlslLmtH///8+kc9epdYzd6dbo9VHkMM2f7FHmNBClM8ydqVcpNY9hro3gLM9hLczealQmcw3fa46f7A8gLMxc6I3eagyc6FIldJMl9JSnNRSntNNl9JPnNJFi75UnM9ZodVKksg8kM45jc09e6ZHltFBk883gbRBh7pDk9EwcaBzn784g7dKkcY2i81Om9M7j85Llc81is09g7Q4grY/j9A0eqxKmdFFltBEjcXf6fFImdBCiLxJl9FGlNFBi78yiMxVndEvbpo6js74+vx+psPP3+o/ks5HkcpGmNCjwdZCkNDM3ehYoNJEls+lxNkxh8xHks0+jdC1zd5Lg6r+/v/H2ufz9/o3jM3t8/edvdM/k89Th61OiLBSjbZklbaTt9BfptdjmL1AicBHj8hGk9FAgK1dkLNTjLRekrdClc/k7fM0icy0y9tgp9c4jc2NtM9Dlc8zicxeXZn3AAAAQ3RSTlMAHDdTb4yPA+LtnEQmC4L2EmHqB7XA0d0sr478x4/Yd5i1zOfyPkf1sLVq4Nh3FvjxopQ2/STNuFzUwFIwxKaejILpIBEV9wAABhVJREFUeF6s1NdyFEcYBeBeoQIhRAkLlRDGrhIgY3BJL8CVeKzuyXFzzjkn5ZxzzuScg3PO8cKzu70JkO0LfxdTU//pM9vTu7Xgf6KqOVTb9X7toRrVEfBf1HTVjZccrT/2by1VV928Yty9ZbVuucdz90frG8DBjl9pVApbOstvmMuvVgaNXSfAAd6pGxpy6yxf5ph43pS/4f3uoaGm2rdu72S9xzOvMymkZFq/ptDrk90mhW7e4zl7HLzhxGWPR20xmSxJ/VqldG5m9XhaVOA1DadsNh3Pu5L2N6QtPO/32JpqQBVVk20oy/Pi2s23WEvyfHbe1thadVQttvm7Llf65gGmXK67XtupyoM7HQhmXdLS8oGWJNeOJ3C5fG5XCEJnkez3/oFdsvgJ4l2ANZwhrJKk/7OSXa+3Vw2WJMlKnGkobouYk6T0TyX30klOUnTD9HJ5qpckL3EW/w4XF3Xd0FGywXUrstrclVsqz5Pd/sXFYyDnPdrLcQODmGOK47IZb4CmibmMn+MYRzFZ5jg33ZL/EJrWcszHmANy3ARBK/IXtciJy8VsitPSdE3uuHxzougojcUdr8/32atnz/ev3f/K5wtpxUTpcaI45zusVDpYtZi+jg0oU9b3x74h7+n9ABvYEZeKaVq0sh0AtLKsFtqNBdeT0MrSzwwlq9+x6xAO4tgOtSzbCjrNQQiNvQUbUEubvzBUeGw26yDCsRHCoLkTHDa7IdOLIThs/gHvChszh2CimE8peRs47cxANI0lYNB5y1DljpOF0IhzBDPOZnDOqYYbeGKECbPzWnXludPphw5c2YBq5zlwXphIbO4VDCZ0gnPfUO1TwZoYwAs2ExPCedAu9DAjfQUjzITQb3jNj0KG2Sgt6BHaQUdYzWz+XmBktOHwanXjaSTcwwziBcuMOtwBmqPrTOxFQR/DRKKPqyur0aiW6cULYsx6tBm0jXpR/AUWR6HRq9WVW6MRhIq5jLyjbaCTDCijyYJNpCajdyobP/eTw0iexBAKkJ3gA5KcQb2zBXsIBckn+xVv8jkZSaEFHE+jFEleAEfayRU0MouNoBmB/L50Ai/HSLIHxcrpCvnhSQAuakKp2C/YbCylJjXRVy/z3+Kv/RrNcCo+WUzlVEhzKffnTQnxeN9fWF88fiNCUdSTsaufaChKWInHeysygfpIqagoakW+vV20J8uyl6TyNKEZWV4oRSPyCkWpgOLSbkCObT8o2r6tlG58HQquf6O0v50tB7JM7F4EORd2dx/K0w/KHsVkLPaoYrwgP/y7krr3SSMA4zj+OBgmjYkxcdIJQyQRKgg2viX9Hddi9UBb29LrKR7CVVEEEXWojUkXNyfTNDE14W9gbHJNuhjDettN3ZvbOvdOqCD3Jp/9l+/wJE+9PkYGjx/fqkys3S2rMozM/o2106rfMUINo6hVqz+eu/hd1c4xTg0TAfy5kV+4UG6+IthHTU9woWmxuKNbTfuCSfovBCxq7EtHqvYL4Sm6F8GVxsSXHMQ07TOi1DKtZxjWaaIyi4CXWjxPccUw8WVbMYY5wxC1mzEyXMJWkllpRloi+Kkoq69sxBTlElF6aAxYUbjXNlhlDZilDnM4U5SlN5biRsRHnbx3mbeWjEh4mEyiuJDl5XcWVmX5GvNkFgLWZM5qwsop4/AWfLhU1cR7k1VVvcYCWRkOI6Xy5gmnphCYIkvzuNYzHzosq2oNk2RtSs8khfUOfHIDgR6ysYBaMpl4uEgk2U/oJTs9AaTSwma7dT69geAE2ZpEjUsn2ieJNHeKfrI3EcAGJ2ZaNgVuC8EBctCLc57P5u5led6IOBkIYkuQMrmmjChs4VkfOerHqSBkPzZlhe06RslZ3zMjk2sscqKwY0RcjKK+LWbzd7KiHhkncs/siFJ+V5eXxD34B8nVuJEpGJNmxN2gH3vSvp7J70tF+D1Ej8qUJD1TkErAND2GZwTFg/LubvmgiBG3SOvdlsqFQrkEzJCL1rstlnVFROixZoDDSuXQFHESwVGlcuQcMb/b42NgjLowh5MTDFE3vNB5qStRIErdCQEh6pLPR92anSUb/wAIhldAaDMpGgAAAABJRU5ErkJggg==`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `iVBORw0KGgoAAAANSUhEUgAAABoAAAAaCAQAAAADQ4RFAAACf0lEQVR4AY1UM3gkARTePdvdoTxXKc+qTl3aU5U6b2Kbkz3Gtq3Zw6ziLGNPzrYx7946Tr6/ee/XeCQ4D3ykPtL5tHno4n0d/h3+xfuWHGLX81cn7r0iTNzjr7LrlxCqPtkbTQEHeqOrTy4Yyt3VCi/IOB0v7rVC7q45Q3Gr5K6jt+3Gl5nCoDD4MtO+j96Wu8atmhGqcNGHObuf8OM/x3AMx38+4Z2sPqzCxRFK2aF2e5Jol56XTLyggAMTL56XOMoS1W4pOyjUcGGQdZxU6qRh7B9Zp+PfpOFlqt0zyDZckPi1ttmIp03jX8gyJ8a/PG2yutpS/Vol7peZIbZcKBAEEheEIAgFbDkz5H6Zrkm2hVWGiXKiF4Ycw0RWKdtC16Q7qe3X4iOMxruonzegJzWaXFrU9utOSsLUmrc0YjeWYjCW4PDMADElpJSSQ0vQvA1Tm6/JlKnqFs1EGyZiFCqnRZTEJJJiKRYzVYzJck2Rm6P4iH+cmSY0YzimYa8l0EtTODFWhcMIMVqdsI2uiTvKmTisIDHJ3od5GILVhBCarCfVRmo4uTjkhrhzkiBV7SsaqS+TzrzM1qpGGUFt28pIySQHR6h7F6KSwGWm97ay+Z+ZqMcEjEWebE7wxCSQwpkhJqoZA5ivCdZDjJepuJ9IQjGGUmuXJdBFUygxVqVsxFsLMbDe8ZbDYVCGKxs+W080max1hFCarCfV+C1KATwcnvE9gRRuMP2prdbWGowm1KB1y+zwMMENkM755cJ2yPDtqhTI6ED1M/82yIDtC/4j4BijjeObflpO9I9MwXTCsSX8jWAFeHr05WoLTJ5G8IQVS/7vwR6ohirYM7f6HzYpogfS3R2OAAAAAElFTkSuQmCC`
  
  
  
  
Instances: 3
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>�PNG</p><p>\x001a</p><p>\x0000\x0000\x0000
IHDR\x0000\x0000\x00002\x0000\x0000\x0000R\x0008\x0003\x0000\x0000\x0000!\x0015w�\x0000\x0000\x0002�PLTELiq3y�6�8��7��.k�3x�<��7��8��7��4��6~�4u�.l�6��0w�3x�6��-w�1t�.k�5~�6�2u�4{�6~�5|�5z�7��.l�-k�1t�5�2u�2u�1s�.l�/l�0q�.m�0p�.m�.l�2v�2t�1j�.l�-l�.m�.l�/l�.l�/m�.l�-l�-m�.l�6�.l�+m�.l�.l�.k�7��4~�.l�.l�D��0��:��/��.��.��A��-��+��+��:��*��<��=��-��)��(��;��'��'�%~�8��$}�9��#|�8��!{�5~�;�� z�6��\x001ey�3|�(~�\x001dx�4��\x001cw�6��1x�\x001bv�\x0019u�1x�&}�3��/u�1��3��1��0�1��.t�/}�.r�T��N��5|�0q�/o�4z�P��3x�W��\��2t�V��Y��J��E��0p�Q��N��K�����>��^��3w�[��G��6�G��B��2v�\��=��7��=��3y�P��7}�:�<��1s�7y�2s�H��L��R��R��M��O��E��T��Y��J��<��9��={�G��A��7��A��C��0q�s��8��J��6��N��;��K��5��=��8��?��4z�J��E��D�����H��B��I��F��A��2��U��/n�:�����~�����?��G��F�У��B�����X��D�ϥ��1��G��>�е��K�����������7��������?��S��N��R��d�����_��c��@��G��F��@��]��S��^��B�����4�̴��`��8�͍��C��3��^]��\x0000\x0000\x0000CtRNS\x0000\x001c7So��\x0003��D&\x000b��\x0012a�\x0007����,���Ǐ�w�����>G���j��w\x0016��6�$͸\��R0Ħ���� \x0011\x0015�\x0000\x0000\x0006\x0015IDATx^���r\x0014G\x0018\x0005�^�\x0002!D	\x000b�\x0010Ʈ\x0012 cpI/��x���qs�9'�s�䜃s��³��	��\x000b\x0017SS��3�ӻ����9T��~�\x001a�\x0011�_�tՍ�\x001c�?�o-UWݼbܽe�n��s�G�\x001b���_iT</p><p>[:�o�˯V\x0006�]'�\x0001ީ\x001b\x001ar�,_�xޔ����ڷn�d��3�3)�dZ�����&�n��9{\x001c���e�Gm1�,I�Z�tnf�xZT�5
�l6\x001dϻ��7�-<��ؚj@\x0015U�m(����ͷXK�|v���ZuT-���.W��\x0001�\��^۩ʃ;\x001d\x0008f]���$׎'p�|nW\x0008Bg�����]��	�]�5�!������]��W
�$�J�i(n�����O%��INRt��ry��$/q\x0016�\x000e\x0017\x0017u��Q��u+��ܕ[*ϓ����c �=��q\x0003��c��\x0019o�������\x0018G1Y�87ݒ�\x0010��r�ǘ\x0003r�\x0004A+�\x0017�ȉ��l���tM�|s��(��\x001d���٫g�������\x000bi�D�q�8�;�T:X����
(S��Ǿ!���\x0000\x001b�\x0011��iZ��\x001d\x0000���\x0016ڍ\x0005ד����\x000c%�߱�\x0010\x000e��\x000e�,�</p><p>:�A\x0008��\x0005\x001bPK��0Txl6� ±\x0011 �\x0013\x001c6�!Ӌ!8l�\x0001�</p><p>\x001b3�`��O)y\x001b8��@4�%`�y�P厓�Јs\x00043�fpΩ�\x001bxb�	��Zu���\x000e\ـj�9p^�Hl�\x0015\x000c&t�s�P�S��\x0018�\x000b6\x0013\x0013�y�.�0#}\x0005#̄�ox͏B��(-�\x0011�AGX�l�^`d���ju�i$��\x000c�\x0005ˌ:�\x0001���L�EA\x001f�D���+�Ѩ���\x000bb�z�\x0019��zQ�\x0005\x0016G�ѫՕ[�\x0011������m��\x000c(�ɂM�&�w*\x001b?���H��\x0010</p><p>���\x0003��A��\x0005{\x0008\x0005�'�\x0015o�9\x0019I�\x0005\x001cO�\x0014I^\x0000G��\x001542���\x0019���t\x0002/�H�\x0007���</p><p>��I\x0000.jB��/�l,�&5�W/����\x001a�p*>YL�THs)��M	�x�_X_<~#BQԓ���h(JX��{+2��H��(jE��]�'˲���4�\x0019Y^(E#�</p><p>E����n@�m?(ھ��n|\x001d</p><p>�����-\x0007�L�^\x00049\x0017vw\x001f��\x000f�\x001e�d,��b� ?�����I#\x0000�8�8\x0018&��1q�	C$\x0011*\x00086�%�\x001d�b�@[���)\x001e�UQ\x0004\x0011u��I\x00177'�415�o`lrM�\x0018�z�Mݛ�:�N� �&�����$O�>F\x0006�\x001fߪL��-�2�����Ӫ�1B
��U�?���]��1N
\x0013\x0001���_�Pn�"�GMOp�i���[M��I�/\x0004,j�KG��\x000b�)�\x0017���ė\x001c�4�3��2�g\x0018�i�2���Z<Oq�0�e[1�9�\x0010��12\�V�YiFZ"��(��l�\x0014�\x0012Qzh\x000cXQ��6Xe
��\x000es8S��7��F�G��w����Hx�L�����w\x0016Ve�\x001a�d\x0016\x0002�d�j��)��\x0016|�T��{�UU��\x0002Y\x0019\x000e#���	��\x0010�"K��3\x001f:,�j
�dmJ�$��\x000e|r\x0003�\x001e���Z2�x�H$�O�%;=\x0001���f�u>���\x0004ٚD�K'�'�4w�~�7\x0011�\x0006'fZ6\x0005n\x000b�\x0001rЋs����eyވ8\x0019\x0008bK�2���(l�Y\x001f9�ǩ d?6e��:F�Y�3#�k,r��cD\���-f�w��\x001e\x0019'r��R~W���=�\x0007�ո�)\x0018�f�ݠ\x001f{Ҿ���KE�=D�ʔ$=S�J�4=�g\x0004Ń��n���\x0011�H�ݖʅB�\x0004̐�ֻ-�uED�f��J��\x0014q\x0012�Q�r�\x001c1���c`��0��\x0013\x000cQ7��y�+Q J�	\x0001!��Gݚ�%\x001b�\x0000\x0008�W@h3)\x001a\x0000\x0000\x0000\x0000IEND�B`�</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Low)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `from`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `FROM`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `FROM`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `bug`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `username`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `where`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `username`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `bug`
  
  
  
  
Instances: 12
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bFROM\b and was detected in the element starting with: "(function(t,a){e.exports=a()})(0,(function(){"use strict";var n,r;function i(){return n.apply(null,arguments)}function s(e){n=e}", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Modern Web Application
##### Informational (Medium)
  
  
  
  
#### Description
<p>The application appears to be a modern web application. If you need to explore it automatically then the Ajax Spider may well be more effective than the standard one.</p>
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script type="module" src="/js/chunk-vendors.c4f869d9.js"></script>`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a>")})),l=function(){return"$0"==="a".replace(/./,"$0")}(),h=o("replace"),f=function(){return!!/./[h]&&""===/./[h]("a","$0")}(),p=!i((function(){var t=/(?:)/,e=t.exec;t.exec=function(){return e.apply(this,arguments)};var n="ab".split(t);return 2!==n.length||"a"!==n[0]||"b"!==n[1]}));t.exports=function(t,e,n,h){var d=o(t),m=!i((function(){var e={};return e[d]=function(){return 7},7!=""[t](e)})),v=m&&!i((function(){var e=!1,n=/a/;return"split"===t&&(n={},n.constructor={},n.constructor[u]=function(){return n},n.flags="",n[d]=/./[d]),n.exec=function(){return e=!0,null},n[d](""),!e}));if(!m||!v||"replace"===t&&(!c||!l||f)||"split"===t&&!p){var _=/./[d],g=n(d,""[t],(function(t,e,n,r,i){return e.exec===a?m&&!i?{done:!0,value:_.call(e,n,r)}:{done:!0,value:t.call(n,e,r)}:{done:!1}}),{REPLACE_KEEPS_$0:l,REGEXP_REPLACE_SUBSTITUTES_UNDEFINED_CAPTURE:f}),y=g[0],b=g[1];r(String.prototype,t,y),r(RegExp.prototype,d,2==e?function(t,e){return b.call(t,this,e)}:function(t){return b.call(t,this)})}h&&s(RegExp.prototype[d],"sham",!0)}},d90b:function(t,e,n){"use strict";var r=n("a905");t.exports=function(t){return"undefined"!==typeof File&&t instanceof File||"undefined"!==typeof Blob&&t instanceof Blob||t instanceof r}},d9a4:function(t,e,n){"use strict";var r=n("4b6b");t.exports=function(t){var e={url:"/graphql",method:"POST",headers:{Accept:"application/json"}},n=r(t),i=n.clone,o=n.files,a=JSON.stringify(i);if(o.size){var s=new FormData;s.append("operations",a);var u={},c=0;o.forEach((function(t){u[++c]=t})),s.append("map",JSON.stringify(u)),c=0,o.forEach((function(t,e){s.append(""+ ++c,e,e.name)})),e.body=s}else e.headers["Content-Type"]="application/json",e.body=a;return e}},da84:function(t,e,n){(function(e){var n=function(t){return t&&t.Math==Math&&t};t.exports=n("object"==typeof globalThis&&globalThis)||n("object"==typeof window&&window)||n("object"==typeof self&&self)||n("object"==typeof e&&e)||function(){return this}()||Function("return this")()}).call(this,n("c8ba"))},dc21:function(t,e,n){"use strict";n.d(e,"a",(function(){return Se}));var r,i={};n.r(i),n.d(i,"FunctionToString",(function(){return a})),n.d(i,"InboundFilters",(function(){return j}));var o,a=function(){function t(){this.name=t.id}return t.prototype.setupOnce=function(){r=Function.prototype.toString,Function.prototype.toString=function(){for(var t=[],e=0;e<arguments.length;e++)t[e]=arguments[e];var n=this.__sentry_original__||this;return r.apply(n,t)}},t.id="FunctionToString",t}(),s=n("9ab4"),u=n("f404"),c=n("91db");(function(t){t["PENDING"]="PENDING",t["RESOLVED"]="RESOLVED",t["REJECTED"]="REJECTED"})(o||(o={}));var l,h=function(){function t(t){var e=this;this._state=o.PENDING,this._handlers=[],this._resolve=function(t){e._setResult(o.RESOLVED,t)},this._reject=function(t){e._setResult(o.REJECTED,t)},this._setResult=function(t,n){e._state===o.PENDING&&(Object(u["m"])(n)?n.then(e._resolve,e._reject):(e._state=t,e._value=n,e._executeHandlers()))},this._attachHandler=function(t){e._handlers=e._handlers.concat(t),e._executeHandlers()},this._executeHandlers=function(){if(e._state!==o.PENDING){var t=e._handlers.slice();e._handlers=[],t.forEach((function(t){t.done||(e._state===o.RESOLVED&&t.onfulfilled&&t.onfulfilled(e._value),e._state===o.REJECTED&&t.onrejected&&t.onrejected(e._value),t.done=!0)}))}};try{t(this._resolve,this._reject)}catch(n){this._reject(n)}}return t.resolve=function(e){return new t((function(t){t(e)}))},t.reject=function(e){return new t((function(t,n){n(e)}))},t.all=function(e){return new t((function(n,r){if(Array.isArray(e))if(0!==e.length){var i=e.length,o=[];e.forEach((function(e,a){t.resolve(e).then((function(t){o[a]=t,i-=1,0===i&&n(o)})).then(null,r)}))}else n([]);else r(new TypeError("Promise.all requires an array as input."))}))},t.prototype.then=function(e,n){var r=this;return new t((function(t,i){r._attachHandler({done:!1,onfulfilled:function(n){if(e)try{return void t(e(n))}catch(r){return void i(r)}else t(n)},onrejected:function(e){if(n)try{return void t(n(e))}catch(r){return void i(r)}else i(e)}})}))},t.prototype.catch=function(t){return this.then((function(t){return t}),t)},t.prototype.finally=function(e){var n=this;return new t((function(t,r){var i,o;return n.then((function(t){o=!1,i=t,e&&e()}),(function(t){o=!0,i=t,e&&e()})).then((function(){o?r(i):t(i)}))}))},t.prototype.toString=function(){return"[object SyncPromise]"},t}(),f=n("f7f6"),p=function(){function t(){this._notifyingListeners=!1,this._scopeListeners=[],this._eventProcessors=[],this._breadcrumbs=[],this._user={},this._tags={},this._extra={},this._contexts={}}return t.clone=function(e){var n=new t;return e&&(n._breadcrumbs=Object(s["e"])(e._breadcrumbs),n._tags=Object(s["a"])({},e._tags),n._extra=Object(s["a"])({},e._extra),n._contexts=Object(s["a"])({},e._contexts),n._user=e._user,n._level=e._level,n._span=e._span,n._session=e._session,n._transactionName=e._transactionName,n._fingerprint=e._fingerprint,n._eventProcessors=Object(s["e"])(e._eventProcessors)),n},t.prototype.addScopeListener=function(t){this._scopeListeners.push(t)},t.prototype.addEventProcessor=function(t){return this._eventProcessors.push(t),this},t.prototype.setUser=function(t){return this._user=t||{},this._session&&this._session.update({user:t}),this._notifyScopeListeners(),this},t.prototype.getUser=function(){return this._user},t.prototype.setTags=function(t){return this._tags=Object(s["a"])(Object(s["a"])({},this._tags),t),this._notifyScopeListeners(),this},t.prototype.setTag=function(t,e){var n;return this._tags=Object(s["a"])(Object(s["a"])({},this._tags),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setExtras=function(t){return this._extra=Object(s["a"])(Object(s["a"])({},this._extra),t),this._notifyScopeListeners(),this},t.prototype.setExtra=function(t,e){var n;return this._extra=Object(s["a"])(Object(s["a"])({},this._extra),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setFingerprint=function(t){return this._fingerprint=t,this._notifyScopeListeners(),this},t.prototype.setLevel=function(t){return this._level=t,this._notifyScopeListeners(),this},t.prototype.setTransactionName=function(t){return this._transactionName=t,this._notifyScopeListeners(),this},t.prototype.setTransaction=function(t){return this.setTransactionName(t)},t.prototype.setContext=function(t,e){var n;return null===e?delete this._contexts[t]:this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setSpan=function(t){return this._span=t,this._notifyScopeListeners(),this},t.prototype.getSpan=function(){return this._span},t.prototype.getTransaction=function(){var t,e,n,r,i=this.getSpan();return(null===(t=i)||void 0===t?void 0:t.transaction)?null===(e=i)||void 0===e?void 0:e.transaction:(null===(r=null===(n=i)||void 0===n?void 0:n.spanRecorder)||void 0===r?void 0:r.spans[0])?i.spanRecorder.spans[0]:void 0},t.prototype.setSession=function(t){return t?this._session=t:delete this._session,this._notifyScopeListeners(),this},t.prototype.getSession=function(){return this._session},t.prototype.update=function(e){if(!e)return this;if("function"===typeof e){var n=e(this);return n instanceof t?n:this}return e instanceof t?(this._tags=Object(s["a"])(Object(s["a"])({},this._tags),e._tags),this._extra=Object(s["a"])(Object(s["a"])({},this._extra),e._extra),this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),e._contexts),e._user&&Object.keys(e._user).length&&(this._user=e._user),e._level&&(this._level=e._level),e._fingerprint&&(this._fingerprint=e._fingerprint)):Object(u["h"])(e)&&(e=e,this._tags=Object(s["a"])(Object(s["a"])({},this._tags),e.tags),this._extra=Object(s["a"])(Object(s["a"])({},this._extra),e.extra),this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),e.contexts),e.user&&(this._user=e.user),e.level&&(this._level=e.level),e.fingerprint&&(this._fingerprint=e.fingerprint)),this},t.prototype.clear=function(){return this._breadcrumbs=[],this._tags={},this._extra={},this._user={},this._contexts={},this._level=void 0,this._transactionName=void 0,this._fingerprint=void 0,this._span=void 0,this._session=void 0,this._notifyScopeListeners(),this},t.prototype.addBreadcrumb=function(t,e){var n=Object(s["a"])({timestamp:Object(c["a"])()},t);return this._breadcrumbs=void 0!==e&&e>=0?Object(s["e"])(this._breadcrumbs,[n]).slice(-e):Object(s["e"])(this._breadcrumbs,[n]),this._notifyScopeListeners(),this},t.prototype.clearBreadcrumbs=function(){return this._breadcrumbs=[],this._notifyScopeListeners(),this},t.prototype.applyToEvent=function(t,e){var n;if(this._extra&&Object.keys(this._extra).length&&(t.extra=Object(s["a"])(Object(s["a"])({},this._extra),t.extra)),this._tags&&Object.keys(this._tags).length&&(t.tags=Object(s["a"])(Object(s["a"])({},this._tags),t.tags)),this._user&&Object.keys(this._user).length&&(t.user=Object(s["a"])(Object(s["a"])({},this._user),t.user)),this._contexts&&Object.keys(this._contexts).length&&(t.contexts=Object(s["a"])(Object(s["a"])({},this._contexts),t.contexts)),this._level&&(t.level=this._level),this._transactionName&&(t.transaction=this._transactionName),this._span){t.contexts=Object(s["a"])({trace:this._span.getTraceContext()},t.contexts);var r=null===(n=this._span.transaction)||void 0===n?void 0:n.name;r&&(t.tags=Object(s["a"])({transaction:r},t.tags))}return this._applyFingerprint(t),t.breadcrumbs=Object(s["e"])(t.breadcrumbs||[],this._breadcrumbs),t.breadcrumbs=t.breadcrumbs.length>0?t.breadcrumbs:void 0,this._notifyEventProcessors(Object(s["e"])(d(),this._eventProcessors),t,e)},t.prototype._notifyEventProcessors=function(t,e,n,r){var i=this;return void 0===r&&(r=0),new h((function(o,a){var c=t[r];if(null===e||"function"!==typeof c)o(e);else{var l=c(Object(s["a"])({},e),n);Object(u["m"])(l)?l.then((function(e){return i._notifyEventProcessors(t,e,n,r+1).then(o)})).then(null,a):i._notifyEventProcessors(t,l,n,r+1).then(o).then(null,a)}}))},t.prototype._notifyScopeListeners=function(){var t=this;this._notifyingListeners||(this._notifyingListeners=!0,this._scopeListeners.forEach((function(e){e(t)})),this._notifyingListeners=!1)},t.prototype._applyFingerprint=function(t){t.fingerprint=t.fingerprint?Array.isArray(t.fingerprint)?t.fingerprint:[t.fingerprint]:[],this._fingerprint&&(t.fingerprint=t.fingerprint.concat(this._fingerprint)),t.fingerprint&&!t.fingerprint.length&&delete t.fingerprint},t}();function d(){var t=Object(f["e"])();return t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.globalEventProcessors=t.__SENTRY__.globalEventProcessors||[],t.__SENTRY__.globalEventProcessors}function m(t){d().push(t)}(function(t){t["Ok"]="ok",t["Exited"]="exited",t["Crashed"]="crashed",t["Abnormal"]="abnormal"})(l||(l={}));var v=n("f0b6"),_=n("f80d"),g=n("e8f5"),y=function(){function t(t){this.errors=0,this.sid=Object(f["i"])(),this.timestamp=Date.now(),this.started=Date.now(),this.duration=0,this.status=l.Ok,this.init=!0,t&&this.update(t)}return t.prototype.update=function(t){void 0===t&&(t={}),t.user&&(t.user.ip_address&&(this.ipAddress=t.user.ip_address),t.did||(this.did=t.user.id||t.user.email||t.user.username)),this.timestamp=t.timestamp||Date.now(),t.sid&&(this.sid=32===t.sid.length?t.sid:Object(f["i"])()),void 0!==t.init&&(this.init=t.init),t.did&&(this.did=""+t.did),"number"===typeof t.started&&(this.started=t.started),"number"===typeof t.duration?this.duration=t.duration:this.duration=this.timestamp-this.started,t.release&&(this.release=t.release),t.environment&&(this.environment=t.environment),t.ipAddress&&(this.ipAddress=t.ipAddress),t.userAgent&&(this.userAgent=t.userAgent),"number"===typeof t.errors&&(this.errors=t.errors),t.status&&(this.status=t.status)},t.prototype.close=function(t){t?this.update({status:t}):this.status===l.Ok?this.update({status:l.Exited}):this.update()},t.prototype.toJSON=function(){return Object(g["a"])({sid:""+this.sid,init:this.init,started:new Date(this.started).toISOString(),timestamp:new Date(this.timestamp).toISOString(),status:this.status,errors:this.errors,did:"number"===typeof this.did||"string"===typeof this.did?""+this.did:void 0,duration:this.duration,attrs:Object(g["a"])({release:this.release,environment:this.environment,ip_address:this.ipAddress,user_agent:this.userAgent})})},t}(),b=3,w=100,x=100,k=function(){function t(t,e,n){void 0===e&&(e=new p),void 0===n&&(n=b),this._version=n,this._stack=[{}],this.getStackTop().scope=e,this.bindClient(t)}return t.prototype.isOlderThan=function(t){return this._version<t},t.prototype.bindClient=function(t){var e=this.getStackTop();e.client=t,t&&t.setupIntegrations&&t.setupIntegrations()},t.prototype.pushScope=function(){var t=p.clone(this.getScope());return this.getStack().push({client:this.getClient(),scope:t}),t},t.prototype.popScope=function(){return!(this.getStack().length<=1)&&!!this.getStack().pop()},t.prototype.withScope=function(t){var e=this.pushScope();try{t(e)}finally{this.popScope()}},t.prototype.getClient=function(){return this.getStackTop().client},t.prototype.getScope=function(){return this.getStackTop().scope},t.prototype.getStack=function(){return this._stack},t.prototype.getStackTop=function(){return this._stack[this._stack.length-1]},t.prototype.captureException=function(t,e){var n=this._lastEventId=Object(f["i"])(),r=e;if(!e){var i=void 0;try{throw new Error("Sentry syntheticException")}catch(t){i=t}r={originalException:t,syntheticException:i}}return this._invokeClient("captureException",t,Object(s["a"])(Object(s["a"])({},r),{event_id:n})),n},t.prototype.captureMessage=function(t,e,n){var r=this._lastEventId=Object(f["i"])(),i=n;if(!n){var o=void 0;try{throw new Error(t)}catch(a){o=a}i={originalException:t,syntheticException:o}}return this._invokeClient("captureMessage",t,e,Object(s["a"])(Object(s["a"])({},i),{event_id:r})),r},t.prototype.captureEvent=function(t,e){var n=this._lastEventId=Object(f["i"])();return this._invokeClient("captureEvent",t,Object(s["a"])(Object(s["a"])({},e),{event_id:n})),n},t.prototype.lastEventId=function(){return this._lastEventId},t.prototype.addBreadcrumb=function(t,e){var n=this.getStackTop(),r=n.scope,i=n.client;if(r&&i){var o=i.getOptions&&i.getOptions()||{},a=o.beforeBreadcrumb,u=void 0===a?null:a,l=o.maxBreadcrumbs,h=void 0===l?w:l;if(!(h<=0)){var p=Object(c["a"])(),d=Object(s["a"])({timestamp:p},t),m=u?Object(f["c"])((function(){return u(d,e)})):d;null!==m&&r.addBreadcrumb(m,Math.min(h,x))}}},t.prototype.setUser=function(t){var e=this.getScope();e&&e.setUser(t)},t.prototype.setTags=function(t){var e=this.getScope();e&&e.setTags(t)},t.prototype.setExtras=function(t){var e=this.getScope();e&&e.setExtras(t)},t.prototype.setTag=function(t,e){var n=this.getScope();n&&n.setTag(t,e)},t.prototype.setExtra=function(t,e){var n=this.getScope();n&&n.setExtra(t,e)},t.prototype.setContext=function(t,e){var n=this.getScope();n&&n.setContext(t,e)},t.prototype.configureScope=function(t){var e=this.getStackTop(),n=e.scope,r=e.client;n&&r&&t(n)},t.prototype.run=function(t){var e=C(this);try{t(this)}finally{C(e)}},t.prototype.getIntegration=function(t){var e=this.getClient();if(!e)return null;try{return e.getIntegration(t)}catch(n){return v["a"].warn("Cannot retrieve integration "+t.id+" from the current Hub"),null}},t.prototype.startSpan=function(t){return this._callExtensionMethod("startSpan",t)},t.prototype.startTransaction=function(t,e){return this._callExtensionMethod("startTransaction",t,e)},t.prototype.traceHeaders=function(){return this._callExtensionMethod("traceHeaders")},t.prototype.captureSession=function(t){if(void 0===t&&(t=!1),t)return this.endSession();this._sendSessionUpdate()},t.prototype.endSession=function(){var t,e,n,r,i;null===(n=null===(e=null===(t=this.getStackTop())||void 0===t?void 0:t.scope)||void 0===e?void 0:e.getSession())||void 0===n||n.close(),this._sendSessionUpdate(),null===(i=null===(r=this.getStackTop())||void 0===r?void 0:r.scope)||void 0===i||i.setSession()},t.prototype.startSession=function(t){var e=this.getStackTop(),n=e.scope,r=e.client,i=r&&r.getOptions()||{},o=i.release,a=i.environment,u=new y(Object(s["a"])(Object(s["a"])({release:o,environment:a},n&&{user:n.getUser()}),t));if(n){var c=n.getSession&&n.getSession();c&&c.status===l.Ok&&c.update({status:l.Exited}),this.endSession(),n.setSession(u)}return u},t.prototype._sendSessionUpdate=function(){var t=this.getStackTop(),e=t.scope,n=t.client;if(e){var r=e.getSession&&e.getSession();r&&n&&n.captureSession&&n.captureSession(r)}},t.prototype._invokeClient=function(t){for(var e,n=[],r=1;r<arguments.length;r++)n[r-1]=arguments[r];var i=this.getStackTop(),o=i.scope,a=i.client;a&&a[t]&&(e=a)[t].apply(e,Object(s["e"])(n,[o]))},t.prototype._callExtensionMethod=function(t){for(var e=[],n=1;n<arguments.length;n++)e[n-1]=arguments[n];var r=E(),i=r.__SENTRY__;if(i&&i.extensions&&"function"===typeof i.extensions[t])return i.extensions[t].apply(this,e);v["a"].warn("Extension method "+t+" couldn't be found, doing nothing.")},t}();function E(){var t=Object(f["e"])();return t.__SENTRY__=t.__SENTRY__||{extensions:{},hub:void 0},t}function C(t){var e=E(),n=L(e);return O(e,t),n}function A(){var t=E();return D(t)&&!L(t).isOlderThan(b)||O(t,new k),Object(_["b"])()?S(t):L(t)}function S(t){var e,n,r;try{var i=null===(r=null===(n=null===(e=E().__SENTRY__)||void 0===e?void 0:e.extensions)||void 0===n?void 0:n.domain)||void 0===r?void 0:r.active;if(!i)return L(t);if(!D(i)||L(i).isOlderThan(b)){var o=L(t).getStackTop();O(i,new k(o.client,p.clone(o.scope)))}return L(i)}catch(a){return L(t)}}function D(t){return!!(t&&t.__SENTRY__&&t.__SENTRY__.hub)}function L(t){return t&&t.__SENTRY__&&t.__SENTRY__.hub||(t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.hub=new k),t.__SENTRY__.hub}function O(t,e){return!!t&&(t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.hub=e,!0)}var T=n("fbdd"),P=[/^Script error\.?$/,/^Javascript error: Script error\.? on line 0$/],j=function(){function t(e){void 0===e&&(e={}),this._options=e,this.name=t.id}return t.prototype.setupOnce=function(){m((function(e){var n=A();if(!n)return e;var r=n.getIntegration(t);if(r){var i=n.getClient(),o=i?i.getOptions():{},a=r._mergeOptions(o);if(r._shouldDropEvent(e,a))return null}return e}))},t.prototype._shouldDropEvent=function(t,e){return this._isSentryError(t,e)?(v["a"].warn("Event dropped due to being internal Sentry Error.\nEvent: "+Object(f["d"])(t)),!0):this._isIgnoredError(t,e)?(v["a"].warn("Event dropped due to being matched by `ignoreErrors` option.\nEvent: "+Object(f["d"])(t)),!0):this._isDeniedUrl(t,e)?(v["a"].warn("Event dropped due to being matched by `denyUrls` option.\nEvent: "+Object(f["d"])(t)+".\nUrl: "+this._getEventFilterUrl(t)),!0):!this._isAllowedUrl(t,e)&&(v["a"].warn("Event dropped due to not being matched by `allowUrls` option.\nEvent: "+Object(f["d"])(t)+".\nUrl: "+this._getEventFilterUrl(t)),!0)},t.prototype._isSentryError=function(t,e){if(!e.ignoreInternal)return!1;try{return t&&t.exception&&t.exception.values&&t.exception.values[0]&&"SentryError"===t.exception.values[0].type||!1}catch(n){return!1}},t.prototype._isIgnoredError=function(t,e){return!(!e.ignoreErrors||!e.ignoreErrors.length)&&this._getPossibleEventMessages(t).some((function(t){return e.ignoreErrors.some((function(e){return Object(T["a"])(t,e)}))}))},t.prototype._isDeniedUrl=function(t,e){if(!e.denyUrls||!e.denyUrls.length)return!1;var n=this._getEventFilterUrl(t);return!!n&&e.denyUrls.some((function(t){return Object(T["a"])(n,t)}))},t.prototype._isAllowedUrl=function(t,e){if(!e.allowUrls||!e.allowUrls.length)return!0;var n=this._getEventFilterUrl(t);return!n||e.allowUrls.some((function(t){return Object(T["a"])(n,t)}))},t.prototype._mergeOptions=function(t){return void 0===t&&(t={}),{allowUrls:Object(s["e"])(this._options.whitelistUrls||[],this._options.allowUrls||[],t.whitelistUrls||[],t.allowUrls||[]),denyUrls:Object(s["e"])(this._options.blacklistUrls||[],this._options.denyUrls||[],t.blacklistUrls||[],t.denyUrls||[]),ignoreErrors:Object(s["e"])(this._options.ignoreErrors||[],t.ignoreErrors||[],P),ignoreInternal:"undefined"===typeof this._options.ignoreInternal||this._options.ignoreInternal}},t.prototype._getPossibleEventMessages=function(t){if(t.message)return[t.message];if(t.exception)try{var e=t.exception.values&&t.exception.values[0]||{},n=e.type,r=void 0===n?"":n,i=e.value,o=void 0===i?"":i;return[""+o,r+": "+o]}catch(a){return v["a"].error("Cannot extract message for event "+Object(f["d"])(t)),[]}return[]},t.prototype._getEventFilterUrl=function(t){try{if(t.stacktrace){var e=t.stacktrace.frames;return e&&e[e.length-1].filename||null}if(t.exception){var n=t.exception.values&&t.exception.values[0].stacktrace&&t.exception.values[0].stacktrace.frames;return n&&n[n.length-1].filename||null}return null}catch(r){return v["a"].error("Cannot extract url for event "+Object(f["d"])(t)),null}},t.id="InboundFilters",t}();function M(t,e){!0===e.debug&&v["a"].enable();var n=A(),r=new t(e);n.bindClient(r)}var B=n("a518");function R(){if(!("fetch"in Object(f["e"])()))return!1;try{return new Headers,new Request(""),new Response,!0}catch(t){return!1}}function F(t){return t&&/^function fetch\(\)\s+\{\s+\[native code\]\s+\}$/.test(t.toString())}function I(){if(!R())return!1;var t=Object(f["e"])();if(F(t.fetch))return!0;var e=!1,n=t.document;if(n&&"function"===typeof n.createElement)try{var r=n.createElement("iframe");r.hidden=!0,n.head.appendChild(r),r.contentWindow&&r.contentWindow.fetch&&(e=F(r.contentWindow.fetch)),n.head.removeChild(r)}catch(i){v["a"].warn("Could not create sandbox iframe for pure fetch check, bailing to window.fetch: ",i)}return e}function z(){if(!R())return!1;try{return new Request("_",{referrerPolicy:"origin"}),!0}catch(t){return!1}}function N(){var t=Object(f["e"])(),e=t.chrome,n=e&&e.app&&e.app.runtime,r="history"in t&&!!t.history.pushState&&!!t.history.replaceState;return!n&&r}var U,Z=Object(f["e"])(),$={},H={};function q(t){if(!H[t])switch(H[t]=!0,t){case"console":G();break;case"dom":at();break;case"xhr":J();break;case"fetch":Y();break;case"history":Q();break;case"error":ut();break;case"unhandledrejection":lt();break;default:v["a"].warn("unknown instrumentation type:",t)}}function V(t){t&&"string"===typeof t.type&&"function"===typeof t.callback&&($[t.type]=$[t.type]||[],$[t.type].push(t.callback),q(t.type))}function W(t,e){var n,r;if(t&&$[t])try{for(var i=Object(s["f"])($[t]||[]),o=i.next();!o.done;o=i.next()){var a=o.value;try{a(e)}catch(u){v["a"].error("Error while triggering instrumentation handler.\nType: "+t+"\nName: "+Object(B["a"])(a)+"\nError: "+u)}}}catch(c){n={error:c}}finally{try{o&&!o.done&&(r=i.return)&&r.call(i)}finally{if(n)throw n.error}}}function G(){"console"in Z&&["debug","info","warn","error","log","assert"].forEach((function(t){t in Z.console&&Object(g["c"])(Z.console,t,(function(e){return function(){for(var n=[],r=0;r<arguments.length;r++)n[r]=arguments[r];W("console",{args:n,level:t}),e&&Function.prototype.apply.call(e,Z.console,n)}}))}))}function Y(){I()&&Object(g["c"])(Z,"fetch",(function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r={args:e,fetchData:{method:K(e),url:X(e)},startTimestamp:Date.now()};return W("fetch",Object(s["a"])({},r)),t.apply(Z,e).then((function(t){return W("fetch",Object(s["a"])(Object(s["a"])({},r),{endTimestamp:Date.now(),response:t})),t}),(function(t){throw W("fetch",Object(s["a"])(Object(s["a"])({},r),{endTimestamp:Date.now(),error:t})),t}))}}))}function K(t){return void 0===t&&(t=[]),"Request"in Z&&Object(u["g"])(t[0],Request)&&t[0].method?String(t[0].method).toUpperCase():t[1]&&t[1].method?String(t[1].method).toUpperCase():"GET"}function X(t){return void 0===t&&(t=[]),"string"===typeof t[0]?t[0]:"Request"in Z&&Object(u["g"])(t[0],Request)?t[0].url:String(t[0])}function J(){if("XMLHttpRequest"in Z){var t=[],e=[],n=XMLHttpRequest.prototype;Object(g["c"])(n,"open",(function(n){return function(){for(var r=[],i=0;i<arguments.length;i++)r[i]=arguments[i];var o=this,a=r[1];o.__sentry_xhr__={method:Object(u["k"])(r[0])?r[0].toUpperCase():r[0],url:r[1]},Object(u["k"])(a)&&"POST"===o.__sentry_xhr__.method&&a.match(/sentry_key/)&&(o.__sentry_own_request__=!0);var s=function(){if(4===o.readyState){try{o.__sentry_xhr__&&(o.__sentry_xhr__.status_code=o.status)}catch(a){}try{var n=t.indexOf(o);if(-1!==n){t.splice(n);var i=e.splice(n)[0];o.__sentry_xhr__&&void 0!==i[0]&&(o.__sentry_xhr__.body=i[0])}}catch(a){}W("xhr",{args:r,endTimestamp:Date.now(),startTimestamp:Date.now(),xhr:o})}};return"onreadystatechange"in o&&"function"===typeof o.onreadystatechange?Object(g["c"])(o,"onreadystatechange",(function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];return s(),t.apply(o,e)}})):o.addEventListener("readystatechange",s),n.apply(o,r)}})),Object(g["c"])(n,"send",(function(n){return function(){for(var r=[],i=0;i<arguments.length;i++)r[i]=arguments[i];return t.push(this),e.push(r),W("xhr",{args:r,startTimestamp:Date.now(),xhr:this}),n.apply(this,r)}}))}}function Q(){if(N()){var t=Z.onpopstate;Z.onpopstate=function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=Z.location.href,i=U;if(U=r,W("history",{from:i,to:r}),t)return t.apply(this,e)},Object(g["c"])(Z.history,"pushState",e),Object(g["c"])(Z.history,"replaceState",e)}function e(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=e.length>2?e[2]:void 0;if(r){var i=U,o=String(r);U=o,W("history",{from:i,to:o})}return t.apply(this,e)}}}var tt,et,nt=1e3;function rt(t,e){if(!t)return!0;if(t.type!==e.type)return!0;try{if(t.target!==e.target)return!0}catch(n){}return!1}function it(t){if("keypress"!==t.type)return!1;try{var e=t.target;if(!e||!e.tagName)return!0;if("INPUT"===e.tagName||"TEXTAREA"===e.tagName||e.isContentEditable)return!1}catch(n){}return!0}function ot(t,e){return void 0===e&&(e=!1),function(n){if(n&&et!==n&&!it(n)){var r="keypress"===n.type?"input":n.type;(void 0===tt||rt(et,n))&&(t({event:n,name:r,global:e}),et=n),clearTimeout(tt),tt=Z.setTimeout((function(){tt=void 0}),nt)}}}function at(){if("document"in Z){var t=W.bind(null,"dom"),e=ot(t,!0);Z.document.addEventListener("click",e,!1),Z.document.addEventListener("keypress",e,!1),["EventTarget","Node"].forEach((function(e){var n=Z[e]&&Z[e].prototype;n&&n.hasOwnProperty&&n.hasOwnProperty("addEventListener")&&(Object(g["c"])(n,"addEventListener",(function(e){return function(n,r,i){if("click"===n||"keypress"==n)try{var o=this,a=o.__sentry_instrumentation_handlers__=o.__sentry_instrumentation_handlers__||{},s=a[n]=a[n]||{refCount:0};if(!s.handler){var u=ot(t);s.handler=u,e.call(this,n,u,i)}s.refCount+=1}catch(c){}return e.call(this,n,r,i)}})),Object(g["c"])(n,"removeEventListener",(function(t){return function(e,n,r){if("click"===e||"keypress"==e)try{var i=this,o=i.__sentry_instrumentation_handlers__||{},a=o[e];a&&(a.refCount-=1,a.refCount<=0&&(t.call(this,e,a.handler,r),a.handler=void 0,delete o[e]),0===Object.keys(o).length&&delete i.__sentry_instrumentation_handlers__)}catch(s){}return t.call(this,e,n,r)}})))}))}}var st=null;function ut(){st=Z.onerror,Z.onerror=function(t,e,n,r,i){return W("error",{column:r,error:i,line:n,msg:t,url:e}),!!st&&st.apply(this,arguments)}}var ct=null;function lt(){ct=Z.onunhandledrejection,Z.onunhandledrejection=function(t){return W("unhandledrejection",t),!ct||ct.apply(this,arguments)}}var ht="6.2.3",ft=Object.setPrototypeOf||({__proto__:[]}instanceof Array?pt:dt);function pt(t,e){return t.__proto__=e,t}function dt(t,e){for(var n in e)t.hasOwnProperty(n)||(t[n]=e[n]);return t}var mt=function(t){function e(e){var n=this.constructor,r=t.call(this,e)||this;return r.message=e,r.name=n.prototype.constructor.name,ft(r,n.prototype),r}return Object(s["b"])(e,t),e}(Error),vt=/^(?:(\w+):)\/\/(?:(\w+)(?::(\w+))?@)([\w.-]+)(?::(\d+))?\/(.+)/,_t="Invalid Dsn",gt=function(){function t(t){"string"===typeof t?this._fromString(t):this._fromComponents(t),this._validate()}return t.prototype.toString=function(t){void 0===t&&(t=!1);var e=this,n=e.host,r=e.path,i=e.pass,o=e.port,a=e.projectId,s=e.protocol,u=e.publicKey;return s+"://"+u+(t&&i?":"+i:"")+"@"+n+(o?":"+o:"")+"/"+(r?r+"/":r)+a},t.prototype._fromString=function(t){var e=vt.exec(t);if(!e)throw new mt(_t);var n=Object(s["c"])(e.slice(1),6),r=n[0],i=n[1],o=n[2],a=void 0===o?"":o,u=n[3],c=n[4],l=void 0===c?"":c,h=n[5],f="",p=h,d=p.split("/");if(d.length>1&&(f=d.slice(0,-1).join("/"),p=d.pop()),p){var m=p.match(/^\d+/);m&&(p=m[0])}this._fromComponents({host:u,pass:a,path:f,projectId:p,port:l,protocol:r,publicKey:i})},t.prototype._fromComponents=function(t){"user"in t&&!("publicKey"in t)&&(t.publicKey=t.user),this.user=t.publicKey||"",this.protocol=t.protocol,this.publicKey=t.publicKey||"",this.pass=t.pass||"",this.host=t.host,this.port=t.port||"",this.path=t.path||"",this.projectId=t.projectId},t.prototype._validate=function(){var t=this;if(["protocol","publicKey","host","projectId"].forEach((function(e){if(!t[e])throw new mt(_t+": "+e+" missing")})),!this.projectId.match(/^\d+$/))throw new mt(_t+": Invalid projectId "+this.projectId);if("http"!==this.protocol&&"https"!==this.protocol)throw new mt(_t+": Invalid protocol "+this.protocol);if(this.port&&isNaN(parseInt(this.port,10)))throw new mt(_t+": Invalid port "+this.port)},t}(),yt=[];function bt(t){var e=t.defaultIntegrations&&Object(s["e"])(t.defaultIntegrations)||[],n=t.integrations,r=[];if(Array.isArray(n)){var i=n.map((function(t){return t.name})),o=[];e.forEach((function(t){-1===i.indexOf(t.name)&&-1===o.indexOf(t.name)&&(r.push(t),o.push(t.name))})),n.forEach((function(t){-1===o.indexOf(t.name)&&(r.push(t),o.push(t.name))}))}else"function"===typeof n?(r=n(e),r=Array.isArray(r)?r:[r]):r=Object(s["e"])(e);var a=r.map((function(t){return t.name})),u="Debug";return-1!==a.indexOf(u)&&r.push.apply(r,Object(s["e"])(r.splice(a.indexOf(u),1))),r}function wt(t){-1===yt.indexOf(t.name)&&(t.setupOnce(m,A),yt.push(t.name),v["a"].log("Integration installed: "+t.name))}function xt(t){var e={};return bt(t).forEach((function(t){e[t.name]=t,wt(t)})),e}var kt,Et=function(){function t(t,e){this._integrations={},this._processing=0,this._backend=new t(e),this._options=e,e.dsn&&(this._dsn=new gt(e.dsn))}return t.prototype.captureException=function(t,e,n){var r=this,i=e&&e.event_id;return this._process(this._getBackend().eventFromException(t,e).then((function(t){return r._captureEvent(t,e,n)})).then((function(t){i=t}))),i},t.prototype.captureMessage=function(t,e,n,r){var i=this,o=n&&n.event_id,a=Object(u["i"])(t)?this._getBackend().eventFromMessage(String(t),e,n):this._getBackend().eventFromException(t,n);return this._process(a.then((function(t){return i._captureEvent(t,n,r)})).then((function(t){o=t}))),o},t.prototype.captureEvent=function(t,e,n){var r=e&&e.event_id;return this._process(this._captureEvent(t,e,n).then((function(t){r=t}))),r},t.prototype.captureSession=function(t){t.release?(this._sendSession(t),t.update({init:!1})):v["a"].warn("Discarded session because of missing release")},t.prototype.getDsn=function(){return this._dsn},t.prototype.getOptions=function(){return this._options},t.prototype.flush=function(t){var e=this;return this._isClientProcessing(t).then((function(n){return e._getBackend().getTransport().close(t).then((function(t){return n&&t}))}))},t.prototype.close=function(t){var e=this;return this.flush(t).then((function(t){return e.getOptions().enabled=!1,t}))},t.prototype.setupIntegrations=function(){this._isEnabled()&&(this._integrations=xt(this._options))},t.prototype.getIntegration=function(t){try{return this._integrations[t.id]||null}catch(e){return v["a"].warn("Cannot retrieve integration "+t.id+" from the current Client"),null}},t.prototype._updateSessionFromEvent=function(t,e){var n,r,i,o=!1,a=!1,u=e.exception&&e.exception.values;if(u){a=!0;try{for(var c=Object(s["f"])(u),h=c.next();!h.done;h=c.next()){var f=h.value,p=f.mechanism;if(p&&!1===p.handled){o=!0;break}}}catch(_){n={error:_}}finally{try{h&&!h.done&&(r=c.return)&&r.call(c)}finally{if(n)throw n.error}}}var d=e.user;if(!t.userAgent){var m=e.request?e.request.headers:{};for(var v in m)if("user-agent"===v.toLowerCase()){i=m[v];break}}t.update(Object(s["a"])(Object(s["a"])({},o&&{status:l.Crashed}),{user:d,userAgent:i,errors:t.errors+Number(a||o)})),this.captureSession(t)},t.prototype._sendSession=function(t){this._getBackend().sendSession(t)},t.prototype._isClientProcessing=function(t){var e=this;return new h((function(n){var r=0,i=1,o=setInterval((function(){0==e._processing?(clearInterval(o),n(!0)):(r+=i,t&&r>=t&&(clearInterval(o),n(!1)))}),i)}))},t.prototype._getBackend=function(){return this._backend},t.prototype._isEnabled=function(){return!1!==this.getOptions().enabled&&void 0!==this._dsn},t.prototype._prepareEvent=function(t,e,n){var r=this,i=this.getOptions().normalizeDepth,o=void 0===i?3:i,a=Object(s["a"])(Object(s["a"])({},t),{event_id:t.event_id||(n&&n.event_id?n.event_id:Object(f["i"])()),timestamp:t.timestamp||Object(c["a"])()});this._applyClientOptions(a),this._applyIntegrationsMetadata(a);var u=e;n&&n.captureContext&&(u=p.clone(u).update(n.captureContext));var l=h.resolve(a);return u&&(l=u.applyToEvent(a,n)),l.then((function(t){return"number"===typeof o&&o>0?r._normalizeEvent(t,o):t}))},t.prototype._normalizeEvent=function(t,e){if(!t)return null;var n=Object(s["a"])(Object(s["a"])(Object(s["a"])(Object(s["a"])(Object(s["a"])({},t),t.breadcrumbs&&{breadcrumbs:t.breadcrumbs.map((function(t){return Object(s["a"])(Object(s["a"])({},t),t.data&&{data:Object(g["d"])(t.data,e)})}))}),t.user&&{user:Object(g["d"])(t.user,e)}),t.contexts&&{contexts:Object(g["d"])(t.contexts,e)}),t.extra&&{extra:Object(g["d"])(t.extra,e)});return t.contexts&&t.contexts.trace&&(n.contexts.trace=t.contexts.trace),n},t.prototype._applyClientOptions=function(t){var e=this.getOptions(),n=e.environment,r=e.release,i=e.dist,o=e.maxValueLength,a=void 0===o?250:o;"environment"in t||(t.environment="environment"in e?n:"production"),void 0===t.release&&void 0!==r&&(t.release=r),void 0===t.dist&&void 0!==i&&(t.dist=i),t.message&&(t.message=Object(T["d"])(t.message,a));var s=t.exception&&t.exception.values&&t.exception.values[0];s&&s.value&&(s.value=Object(T["d"])(s.value,a));var u=t.request;u&&u.url&&(u.url=Object(T["d"])(u.url,a))},t.prototype._applyIntegrationsMetadata=function(t){var e=t.sdk,n=Object.keys(this._integrations);e&&n.length>0&&(e.integrations=n)},t.prototype._sendEvent=function(t){this._getBackend().sendEvent(t)},t.prototype._captureEvent=function(t,e,n){return this._processEvent(t,e,n).then((function(t){return t.event_id}),(function(t){v["a"].error(t)}))},t.prototype._processEvent=function(t,e,n){var r=this,i=this.getOptions(),o=i.beforeSend,a=i.sampleRate;if(!this._isEnabled())return h.reject(new mt("SDK not enabled, will not send event."));var s="transaction"===t.type;return!s&&"number"===typeof a&&Math.random()>a?h.reject(new mt("Discarding event because it's not included in the random sample (sampling rate = "+a+")")):this._prepareEvent(t,n,e).then((function(t){if(null===t)throw new mt("An event processor returned null, will not send event.");var n=e&&e.data&&!0===e.data.__sentry__;if(n||s||!o)return t;var r=o(t,e);if("undefined"===typeof r)throw new mt("`beforeSend` method has to return `null` or a valid event.");return Object(u["m"])(r)?r.then((function(t){return t}),(function(t){throw new mt("beforeSend rejected with "+t)})):r})).then((function(t){if(null===t)throw new mt("`beforeSend` returned `null`, will not send event.");var e=n&&n.getSession&&n.getSession();return!s&&e&&r._updateSessionFromEvent(e,t),r._sendEvent(t),t})).then(null,(function(t){if(t instanceof mt)throw t;throw r.captureException(t,{data:{__sentry__:!0},originalException:t}),new mt("Event processing pipeline threw an error, original event will not be sent. Details have been sent as a new event.\nReason: "+t)}))},t.prototype._process=function(t){var e=this;this._processing+=1,t.then((function(t){return e._processing-=1,t}),(function(t){return e._processing-=1,t}))},t}();(function(t){t["Unknown"]="unknown",t["Skipped"]="skipped",t["Success"]="success",t["RateLimit"]="rate_limit",t["Invalid"]="invalid",t["Failed"]="failed"})(kt||(kt={})),function(t){function e(e){return e>=200&&e<300?t.Success:429===e?t.RateLimit:e>=400&&e<500?t.Invalid:e>=500?t.Failed:t.Unknown}t.fromHttpCode=e}(kt||(kt={}));var Ct,At=function(){function t(){}return t.prototype.sendEvent=function(t){return h.resolve({reason:"NoopTransport: Event has been skipped because no Dsn is configured.",status:kt.Skipped})},t.prototype.close=function(t){return h.resolve(!0)},t}(),St=function(){function t(t){this._options=t,this._options.dsn||v["a"].warn("No DSN provided, backend will not do anything."),this._transport=this._setupTransport()}return t.prototype.eventFromException=function(t,e){throw new mt("Backend has to implement `eventFromException` method")},t.prototype.eventFromMessage=function(t,e,n){throw new mt("Backend has to implement `eventFromMessage` method")},t.prototype.sendEvent=function(t){this._transport.sendEvent(t).then(null,(function(t){v["a"].error("Error while sending event: "+t)}))},t.prototype.sendSession=function(t){this._transport.sendSession?this._transport.sendSession(t).then(null,(function(t){v["a"].error("Error while sending session: "+t)})):v["a"].warn("Dropping session because custom transport doesn't implement sendSession")},t.prototype.getTransport=function(){return this._transport},t.prototype._setupTransport=function(){return new At},t}();(function(t){t["Fatal"]="fatal",t["Error"]="error",t["Warning"]="warning",t["Log"]="log",t["Info"]="info",t["Debug"]="debug",t["Critical"]="critical"})(Ct||(Ct={})),function(t){function e(e){switch(e){case"debug":return t.Debug;case"info":return t.Info;case"warn":case"warning":return t.Warning;case"error":return t.Error;case"fatal":return t.Fatal;case"critical":return t.Critical;case"log":default:return t.Log}}t.fromString=e}(Ct||(Ct={}));var Dt="?",Lt=/^\s*at (?:(.*?) ?\()?((?:file|https?|blob|chrome-extension|address|native|eval|webpack|<anonymous>|[-a-z]+:|.*bundle|\/).*?)(?::(\d+))?(?::(\d+))?\)?\s*$/i,Ot=/^\s*(.*?)(?:\((.*?)\))?(?:^|@)?((?:file|https?|blob|chrome|webpack|resource|moz-extension|capacitor).*?:\/.*?|\[native code\]|[^@]*(?:bundle|\d+\.js)|\/[\w\-. /=]+)(?::(\d+))?(?::(\d+))?\s*$/i,Tt=/^\s*at (?:((?:\[object object\])?.+) )?\(?((?:file|ms-appx|https?|webpack|blob):.*?):(\d+)(?::(\d+))?\)?\s*$/i,Pt=/(\S+) line (\d+)(?: > eval line \d+)* > eval/i,jt=/\((\S*)(?::(\d+))(?::(\d+))\)/,Mt=/Minified React error #\d+;/i;function Bt(t){var e=null,n=0;t&&("number"===typeof t.framesToPop?n=t.framesToPop:Mt.test(t.message)&&(n=1));try{if(e=Ft(t),e)return It(e,n)}catch(r){}try{if(e=Rt(t),e)return It(e,n)}catch(r){}return{message:zt(t),name:t&&t.name,stack:[],failed:!0}}function Rt(t){if(!t||!t.stack)return null;for(var e,n,r,i,o=[],a=t.stack.split("\n"),s=0;s<a.length;++s){if(r=Lt.exec(a[s])){var u=r[2]&&0===r[2].indexOf("native");e=r[2]&&0===r[2].indexOf("eval"),e&&(n=jt.exec(r[2]))&&(r[2]=n[1],r[3]=n[2],r[4]=n[3]),i={url:r[2]&&0===r[2].indexOf("address at ")?r[2].substr("address at ".length):r[2],func:r[1]||Dt,args:u?[r[2]]:[],line:r[3]?+r[3]:null,column:r[4]?+r[4]:null}}else if(r=Tt.exec(a[s]))i={url:r[2],func:r[1]||Dt,args:[],line:+r[3],column:r[4]?+r[4]:null};else{if(!(r=Ot.exec(a[s])))continue;e=r[3]&&r[3].indexOf(" > eval")>-1,e&&(n=Pt.exec(r[3]))?(r[1]=r[1]||"eval",r[3]=n[1],r[4]=n[2],r[5]=""):0!==s||r[5]||void 0===t.columnNumber||(o[0].column=t.columnNumber+1),i={url:r[3],func:r[1]||Dt,args:r[2]?r[2].split(","):[],line:r[4]?+r[4]:null,column:r[5]?+r[5]:null}}!i.func&&i.line&&(i.func=Dt),o.push(i)}return o.length?{message:zt(t),name:t.name,stack:o}:null}function Ft(t){if(!t||!t.stacktrace)return null;for(var e,n=t.stacktrace,r=/ line (\d+).*script (?:in )?(\S+)(?:: in function (\S+))?$/i,i=/ line (\d+), column (\d+)\s*(?:in (?:<anonymous function: ([^>]+)>|([^)]+))\((.*)\))? in (.*):\s*$/i,o=n.split("\n"),a=[],s=0;s<o.length;s+=2){var u=null;(e=r.exec(o[s]))?u={url:e[2],func:e[3],args:[],line:+e[1],column:null}:(e=i.exec(o[s]))&&(u={url:e[6],func:e[3]||e[4],args:e[5]?e[5].split(","):[],line:+e[1],column:+e[2]}),u&&(!u.func&&u.line&&(u.func=Dt),a.push(u))}return a.length?{message:zt(t),name:t.name,stack:a}:null}function It(t,e){try{return Object(s["a"])(Object(s["a"])({},t),{stack:t.stack.slice(e)})}catch(n){return t}}function zt(t){var e=t&&t.message;return e?e.error&&"string"===typeof e.error.message?e.error.message:e:"No error message"}var Nt=50;function Ut(t){var e=Ht(t.stack),n={type:t.name,value:t.message};return e&&e.length&&(n.stacktrace={frames:e}),void 0===n.type&&""===n.value&&(n.value="Unrecoverable error caught"),n}function Zt(t,e,n){var r={exception:{values:[{type:Object(u["f"])(t)?t.constructor.name:n?"UnhandledRejection":"Error",value:"Non-Error "+(n?"promise rejection":"exception")+" captured with keys: "+Object(g["b"])(t)}]},extra:{__serialized__:Object(g["e"])(t)}};if(e){var i=Bt(e),o=Ht(i.stack);r.stacktrace={frames:o}}return r}function $t(t){var e=Ut(t);return{exception:{values:[e]}}}function Ht(t){if(!t||!t.length)return[];var e=t,n=e[0].func||"",r=e[e.length-1].func||"";return-1===n.indexOf("captureMessage")&&-1===n.indexOf("captureException")||(e=e.slice(1)),-1!==r.indexOf("sentryWrapped")&&(e=e.slice(0,-1)),e.slice(0,Nt).map((function(t){return{colno:null===t.column?void 0:t.column,filename:t.url||e[0].url,function:t.func||"?",in_app:!0,lineno:null===t.line?void 0:t.line}})).reverse()}function qt(t,e,n){var r=n&&n.syntheticException||void 0,i=Wt(e,r,{attachStacktrace:t.attachStacktrace});return Object(f["a"])(i,{handled:!0,type:"generic"}),i.level=Ct.Error,n&&n.event_id&&(i.event_id=n.event_id),h.resolve(i)}function Vt(t,e,n,r){void 0===n&&(n=Ct.Info);var i=r&&r.syntheticException||void 0,o=Gt(e,i,{attachStacktrace:t.attachStacktrace});return o.level=n,r&&r.event_id&&(o.event_id=r.event_id),h.resolve(o)}function Wt(t,e,n){var r;if(void 0===n&&(n={}),Object(u["e"])(t)&&t.error){var i=t;return t=i.error,r=$t(Bt(t)),r}if(Object(u["a"])(t)||Object(u["b"])(t)){var o=t,a=o.name||(Object(u["a"])(o)?"DOMError":"DOMException"),c=o.message?a+": "+o.message:a;return r=Gt(c,e,n),Object(f["b"])(r,c),"code"in o&&(r.tags=Object(s["a"])(Object(s["a"])({},r.tags),{"DOMException.code":""+o.code})),r}if(Object(u["d"])(t))return r=$t(Bt(t)),r;if(Object(u["h"])(t)||Object(u["f"])(t)){var l=t;return r=Zt(l,e,n.rejection),Object(f["a"])(r,{synthetic:!0}),r}return r=Gt(t,e,n),Object(f["b"])(r,""+t,void 0),Object(f["a"])(r,{synthetic:!0}),r}function Gt(t,e,n){void 0===n&&(n={});var r={message:t};if(n.attachStacktrace&&e){var i=Bt(e),o=Ht(i.stack);r.stacktrace={frames:o}}return r}function Yt(t){if(t.metadata&&t.metadata.sdk){var e=t.metadata.sdk,n=e.name,r=e.version;return{name:n,version:r}}}function Kt(t,e){return e?(t.sdk=t.sdk||{name:e.name,version:e.version},t.sdk.name=t.sdk.name||e.name,t.sdk.version=t.sdk.version||e.version,t.sdk.integrations=Object(s["e"])(t.sdk.integrations||[],e.integrations||[]),t.sdk.packages=Object(s["e"])(t.sdk.packages||[],e.packages||[]),t):t}function Xt(t,e){var n=Yt(e),r=JSON.stringify(Object(s["a"])({sent_at:(new Date).toISOString()},n&&{sdk:n})),i=JSON.stringify({type:"session"});return{body:r+"\n"+i+"\n"+JSON.stringify(t),type:"session",url:e.getEnvelopeEndpointWithUrlEncodedAuth()}}function Jt(t,e){var n=Yt(e),r=t.type||"event",i="transaction"===r,o=t.debug_meta||{},a=o.transactionSampling,u=Object(s["d"])(o,["transactionSampling"]),c=a||{},l=c.method,h=c.rate;0===Object.keys(u).length?delete t.debug_meta:t.debug_meta=u;var f={body:JSON.stringify(n?Kt(t,e.metadata.sdk):t),type:r,url:i?e.getEnvelopeEndpointWithUrlEncodedAuth():e.getStoreEndpointWithUrlEncodedAuth()};if(i){var p=JSON.stringify(Object(s["a"])({event_id:t.event_id,sent_at:(new Date).toISOString()},n&&{sdk:n})),d=JSON.stringify({type:t.type,sample_rates:[{id:l,rate:h}]}),m=p+"\n"+d+"\n"+f.body;f.body=m}return f}var Qt="7",te=function(){function t(t,e){void 0===e&&(e={}),this.dsn=t,this._dsnObject=new gt(t),this.metadata=e}return t.prototype.getDsn=function(){return this._dsnObject},t.prototype.getBaseApiEndpoint=function(){var t=this._dsnObject,e=t.protocol?t.protocol+":":"",n=t.port?":"+t.port:"";return e+"//"+t.host+n+(t.path?"/"+t.path:"")+"/api/"},t.prototype.getStoreEndpoint=function(){return this._getIngestEndpoint("store")},t.prototype.getStoreEndpointWithUrlEncodedAuth=function(){return this.getStoreEndpoint()+"?"+this._encodedAuth()},t.prototype.getEnvelopeEndpointWithUrlEncodedAuth=function(){return this._getEnvelopeEndpoint()+"?"+this._encodedAuth()},t.prototype.getStoreEndpointPath=function(){var t=this._dsnObject;return(t.path?"/"+t.path:"")+"/api/"+t.projectId+"/store/"},t.prototype.getRequestHeaders=function(t,e){var n=this._dsnObject,r=["Sentry sentry_version="+Qt];return r.push("sentry_client="+t+"/"+e),r.push("sentry_key="+n.publicKey),n.pass&&r.push("sentry_secret="+n.pass),{"Content-Type":"application/json","X-Sentry-Auth":r.join(", ")}},t.prototype.getReportDialogEndpoint=function(t){void 0===t&&(t={});var e=this._dsnObject,n=this.getBaseApiEndpoint()+"embed/error-page/",r=[];for(var i in r.push("dsn="+e.toString()),t)if("dsn"!==i)if("user"===i){if(!t.user)continue;t.user.name&&r.push("name="+encodeURIComponent(t.user.name)),t.user.email&&r.push("email="+encodeURIComponent(t.user.email))}else r.push(encodeURIComponent(i)+"="+encodeURIComponent(t[i]));return r.length?n+"?"+r.join("&"):n},t.prototype._getEnvelopeEndpoint=function(){return this._getIngestEndpoint("envelope")},t.prototype._getIngestEndpoint=function(t){var e=this.getBaseApiEndpoint(),n=this._dsnObject;return""+e+n.projectId+"/"+t+"/"},t.prototype._encodedAuth=function(){var t=this._dsnObject,e={sentry_key:t.publicKey,sentry_version:Qt};return Object(g["f"])(e)},t}(),ee=function(){function t(t){this._limit=t,this._buffer=[]}return t.prototype.isReady=function(){return void 0===this._limit||this.length()<this._limit},t.prototype.add=function(t){var e=this;return this.isReady()?(-1===this._buffer.indexOf(t)&&this._buffer.push(t),t.then((function(){return e.remove(t)})).then(null,(function(){return e.remove(t).then(null,(function(){}))})),t):h.reject(new mt("Not adding Promise due to buffer limit reached."))},t.prototype.remove=function(t){var e=this._buffer.splice(this._buffer.indexOf(t),1)[0];return e},t.prototype.length=function(){return this._buffer.length},t.prototype.drain=function(t){var e=this;return new h((function(n){var r=setTimeout((function(){t&&t>0&&n(!1)}),t);h.all(e._buffer).then((function(){clearTimeout(r),n(!0)})).then(null,(function(){n(!0)}))}))},t}(),ne=function(){function t(t){this.options=t,this._buffer=new ee(30),this._rateLimits={},this._api=new te(t.dsn,t._metadata),this.url=this._api.getStoreEndpointWithUrlEncodedAuth()}return t.prototype.sendEvent=function(t){throw new mt("Transport Class has to implement `sendEvent` method")},t.prototype.close=function(t){return this._buffer.drain(t)},t.prototype._handleResponse=function(t){var e=t.requestType,n=t.response,r=t.headers,i=t.resolve,o=t.reject,a=kt.fromHttpCode(n.status),s=this._handleRateLimit(r);s&&v["a"].warn("Too many requests, backing off until: "+this._disabledUntil(e)),a!==kt.Success?o(n):i({status:a})},t.prototype._disabledUntil=function(t){return this._rateLimits[t]||this._rateLimits.all},t.prototype._isRateLimited=function(t){return this._disabledUntil(t)>new Date(Date.now())},t.prototype._handleRateLimit=function(t){var e,n,r,i,o=Date.now(),a=t["x-sentry-rate-limits"],u=t["retry-after"];if(a){try{for(var c=Object(s["f"])(a.trim().split(",")),l=c.next();!l.done;l=c.next()){var h=l.value,p=h.split(":",2),d=parseInt(p[0],10),m=1e3*(isNaN(d)?60:d);try{for(var v=(r=void 0,Object(s["f"])(p[1].split(";"))),_=v.next();!_.done;_=v.next()){var g=_.value;this._rateLimits[g||"all"]=new Date(o+m)}}catch(y){r={error:y}}finally{try{_&&!_.done&&(i=v.return)&&i.call(v)}finally{if(r)throw r.error}}}}catch(b){e={error:b}}finally{try{l&&!l.done&&(n=c.return)&&n.call(c)}finally{if(e)throw e.error}}return!0}return!!u&&(this._rateLimits.all=new Date(o+Object(f["g"])(o,u)),!0)},t}();function re(){var t,e,n=Object(f["e"])(),r=n.document;if("function"===typeof(null===(t=r)||void 0===t?void 0:t.createElement))try{var i=r.createElement("iframe");if(i.hidden=!0,r.head.appendChild(i),null===(e=i.contentWindow)||void 0===e?void 0:e.fetch)return i.contentWindow.fetch.bind(n);r.head.removeChild(i)}catch(o){v["a"].warn("Could not create sandbox iframe for pure fetch check, bailing to window.fetch: ",o)}return n.fetch.bind(n)}var ie=function(t){function e(e,n){void 0===n&&(n=re());var r=t.call(this,e)||this;return r._fetch=n,r}return Object(s["b"])(e,t),e.prototype.sendEvent=function(t){return this._sendRequest(Jt(t,this._api),t)},e.prototype.sendSession=function(t){return this._sendRequest(Xt(t,this._api),t)},e.prototype._sendRequest=function(t,e){var n=this;if(this._isRateLimited(t.type))return Promise.reject({event:e,type:t.type,reason:"Transport locked till "+this._disabledUntil(t.type)+" due to too many requests.",status:429});var r={body:t.body,method:"POST",referrerPolicy:z()?"origin":""};return void 0!==this.options.fetchParameters&&Object.assign(r,this.options.fetchParameters),void 0!==this.options.headers&&(r.headers=this.options.headers),this._buffer.add(new h((function(e,i){n._fetch(t.url,r).then((function(r){var o={"x-sentry-rate-limits":r.headers.get("X-Sentry-Rate-Limits"),"retry-after":r.headers.get("Retry-After")};n._handleResponse({requestType:t.type,response:r,headers:o,resolve:e,reject:i})})).catch(i)})))},e}(ne),oe=function(t){function e(){return null!==t&&t.apply(this,arguments)||this}return Object(s["b"])(e,t),e.prototype.sendEvent=function(t){return this._sendRequest(Jt(t,this._api),t)},e.prototype.sendSession=function(t){return this._sendRequest(Xt(t,this._api),t)},e.prototype._sendRequest=function(t,e){var n=this;return this._isRateLimited(t.type)?Promise.reject({event:e,type:t.type,reason:"Transport locked till "+this._disabledUntil(t.type)+" due to too many requests.",status:429}):this._buffer.add(new h((function(e,r){var i=new XMLHttpRequest;for(var o in i.onreadystatechange=function(){if(4===i.readyState){var o={"x-sentry-rate-limits":i.getResponseHeader("X-Sentry-Rate-Limits"),"retry-after":i.getResponseHeader("Retry-After")};n._handleResponse({requestType:t.type,response:i,headers:o,resolve:e,reject:r})}},i.open("POST",t.url),n.options.headers)n.options.headers.hasOwnProperty(o)&&i.setRequestHeader(o,n.options.headers[o]);i.send(t.body)})))},e}(ne),ae=function(t){function e(){return null!==t&&t.apply(this,arguments)||this}return Object(s["b"])(e,t),e.prototype.eventFromException=function(t,e){return qt(this._options,t,e)},e.prototype.eventFromMessage=function(t,e,n){return void 0===e&&(e=Ct.Info),Vt(this._options,t,e,n)},e.prototype._setupTransport=function(){if(!this._options.dsn)return t.prototype._setupTransport.call(this);var e=Object(s["a"])(Object(s["a"])({},this._options.transportOptions),{dsn:this._options.dsn,_metadata:this._options._metadata});return this._options.transport?new this._options.transport(e):R()?new ie(e):new oe(e)},e}(St);function se(t){for(var e=[],n=1;n<arguments.length;n++)e[n-1]=arguments[n];var r=A();if(r&&r[t])return r[t].apply(r,Object(s["e"])(e));throw new Error("No hub defined or "+t+" was not found on the hub, please open a bug report.")}function ue(t,e){var n;try{throw new Error("Sentry syntheticException")}catch(t){n=t}return se("captureException",t,{captureContext:e,originalException:t,syntheticException:n})}function ce(t){se("withScope",t)}var le=0;function he(){return le>0}function fe(){le+=1,setTimeout((function(){le-=1}))}function pe(t,e,n){if(void 0===e&&(e={}),"function"!==typeof t)return t;try{if(t.__sentry__)return t;if(t.__sentry_wrapped__)return t.__sentry_wrapped__}catch(a){return t}var r=function(){var r=Array.prototype.slice.call(arguments);try{n&&"function"===typeof n&&n.apply(this,arguments);var i=r.map((function(t){return pe(t,e)}));return t.handleEvent?t.handleEvent.apply(this,i):t.apply(this,i)}catch(o){throw fe(),ce((function(t){t.addEventProcessor((function(t){var n=Object(s["a"])({},t);return e.mechanism&&(Object(f["b"])(n,void 0,void 0),Object(f["a"])(n,e.mechanism)),n.extra=Object(s["a"])(Object(s["a"])({},n.extra),{arguments:r}),n})),ue(o)})),o}};try{for(var i in t)Object.prototype.hasOwnProperty.call(t,i)&&(r[i]=t[i])}catch(u){}t.prototype=t.prototype||{},r.prototype=t.prototype,Object.defineProperty(t,"__sentry_wrapped__",{enumerable:!1,value:r}),Object.defineProperties(r,{__sentry__:{enumerable:!1,value:!0},__sentry_original__:{enumerable:!1,value:t}});try{var o=Object.getOwnPropertyDescriptor(r,"name");o.configurable&&Object.defineProperty(r,"name",{get:function(){return t.name}})}catch(u){}return r}function de(t){if(void 0===t&&(t={}),t.eventId)if(t.dsn){var e=document.createElement("script");e.async=!0,e.src=new te(t.dsn).getReportDialogEndpoint(t),t.onLoad&&(e.onload=t.onLoad),(document.head||document.body).appendChild(e)}else v["a"].error("Missing dsn option in showReportDialog call");else v["a"].error("Missing eventId option in showReportDialog call")}var me=n("bc5b"),ve=function(){function t(e){this.name=t.id,this._options=Object(s["a"])({console:!0,dom:!0,fetch:!0,history:!0,sentry:!0,xhr:!0},e)}return t.prototype.addSentryBreadcrumb=function(t){this._options.sentry&&A().addBreadcrumb({category:"sentry."+("transaction"===t.type?"transaction":"event"),event_id:t.event_id,level:t.level,message:Object(f["d"])(t)},{event:t})},t.prototype.setupOnce=function(){var t=this;this._options.console&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._consoleBreadcrumb.apply(t,Object(s["e"])(e))},type:"console"}),this._options.dom&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._domBreadcrumb.apply(t,Object(s["e"])(e))},type:"dom"}),this._options.xhr&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._xhrBreadcrumb.apply(t,Object(s["e"])(e))},type:"xhr"}),this._options.fetch&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._fetchBreadcrumb.apply(t,Object(s["e"])(e))},type:"fetch"}),this._options.history&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._historyBreadcrumb.apply(t,Object(s["e"])(e))},type:"history"})},t.prototype._consoleBreadcrumb=function(t){var e={category:"console",data:{arguments:t.args,logger:"console"},level:Ct.fromString(t.level),message:Object(T["b"])(t.args," ")};if("assert"===t.level){if(!1!==t.args[0])return;e.message="Assertion failed: "+(Object(T["b"])(t.args.slice(1)," ")||"console.assert"),e.data.arguments=t.args.slice(1)}A().addBreadcrumb(e,{input:t.args,level:t.level})},t.prototype._domBreadcrumb=function(t){var e;try{e=t.event.target?Object(me["a"])(t.event.target):Object(me["a"])(t.event)}catch(n){e="<unknown>"}0!==e.length&&A().addBreadcrumb({category:"ui."+t.name,message:e},{event:t.event,name:t.name,global:t.global})},t.prototype._xhrBreadcrumb=function(t){if(t.endTimestamp){if(t.xhr.__sentry_own_request__)return;var e=t.xhr.__sentry_xhr__||{},n=e.method,r=e.url,i=e.status_code,o=e.body;A().addBreadcrumb({category:"xhr",data:{method:n,url:r,status_code:i},type:"http"},{xhr:t.xhr,input:o})}else;},t.prototype._fetchBreadcrumb=function(t){t.endTimestamp&&(t.fetchData.url.match(/sentry_key/)&&"POST"===t.fetchData.method||(t.error?A().addBreadcrumb({category:"fetch",data:t.fetchData,level:Ct.Error,type:"http"},{data:t.error,input:t.args}):A().addBreadcrumb({category:"fetch",data:Object(s["a"])(Object(s["a"])({},t.fetchData),{status_code:t.response.status}),type:"http"},{input:t.args,response:t.response})))},t.prototype._historyBreadcrumb=function(t){var e=Object(f["e"])(),n=t.from,r=t.to,i=Object(f["h"])(e.location.href),o=Object(f["h"])(n),a=Object(f["h"])(r);o.path||(o=i),i.protocol===a.protocol&&i.host===a.host&&(r=a.relative),i.protocol===o.protocol&&i.host===o.host&&(n=o.relative),A().addBreadcrumb({category:"navigation",data:{from:n,to:r}})},t.id="Breadcrumbs",t}(),_e=function(t){function e(e){void 0===e&&(e={});var n=this;return e._metadata=e._metadata||{},e._metadata.sdk=e._metadata.sdk||{name:"sentry.javascript.browser",packages:[{name:"npm:@sentry/browser",version:ht}],version:ht},n=t.call(this,ae,e)||this,n}return Object(s["b"])(e,t),e.prototype.showReportDialog=function(t){void 0===t&&(t={});var e=Object(f["e"])().document;e&&(this._isEnabled()?de(Object(s["a"])(Object(s["a"])({},t),{dsn:t.dsn||this.getDsn()})):v["a"].error("Trying to call showReportDialog with Sentry Client disabled"))},e.prototype._prepareEvent=function(e,n,r){return e.platform=e.platform||"javascript",t.prototype._prepareEvent.call(this,e,n,r)},e.prototype._sendEvent=function(e){var n=this.getIntegration(ve);n&&n.addSentryBreadcrumb(e),t.prototype._sendEvent.call(this,e)},e}(Et),ge=["EventTarget","Window","Node","ApplicationCache","AudioTrackList","ChannelMergerNode","CryptoOperation","EventSource","FileReader","HTMLUnknownElement","IDBDatabase","IDBRequest","IDBTransaction","KeyOperation","MediaController","MessagePort","ModalWindow","Notification","SVGElementInstance","Screen","TextTrack","TextTrackCue","TextTrackList","WebSocket","WebSocketWorker","Worker","XMLHttpRequest","XMLHttpRequestEventTarget","XMLHttpRequestUpload"],ye=function(){function t(e){this.name=t.id,this._options=Object(s["a"])({XMLHttpRequest:!0,eventTarget:!0,requestAnimationFrame:!0,setInterval:!0,setTimeout:!0},e)}return t.prototype.setupOnce=function(){var t=Object(f["e"])();if(this._options.setTimeout&&Object(g["c"])(t,"setTimeout",this._wrapTimeFunction.bind(this)),this._options.setInterval&&Object(g["c"])(t,"setInterval",this._wrapTimeFunction.bind(this)),this._options.requestAnimationFrame&&Object(g["c"])(t,"requestAnimationFrame",this._wrapRAF.bind(this)),this._options.XMLHttpRequest&&"XMLHttpRequest"in t&&Object(g["c"])(XMLHttpRequest.prototype,"send",this._wrapXHR.bind(this)),this._options.eventTarget){var e=Array.isArray(this._options.eventTarget)?this._options.eventTarget:ge;e.forEach(this._wrapEventTarget.bind(this))}},t.prototype._wrapTimeFunction=function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=e[0];return e[0]=pe(r,{mechanism:{data:{function:Object(B["a"])(t)},handled:!0,type:"instrument"}}),t.apply(this,e)}},t.prototype._wrapRAF=function(t){return function(e){return t.call(this,pe(e,{mechanism:{data:{function:"requestAnimationFrame",handler:Object(B["a"])(t)},handled:!0,type:"instrument"}}))}},t.prototype._wrapEventTarget=function(t){var e=Object(f["e"])(),n=e[t]&&e[t].prototype;n&&n.hasOwnProperty&&n.hasOwnProperty("addEventListener")&&(Object(g["c"])(n,"addEventListener",(function(e){return function(n,r,i){try{"function"===typeof r.handleEvent&&(r.handleEvent=pe(r.handleEvent.bind(r),{mechanism:{data:{function:"handleEvent",handler:Object(B["a"])(r),target:t},handled:!0,type:"instrument"}}))}catch(o){}return e.call(this,n,pe(r,{mechanism:{data:{function:"addEventListener",handler:Object(B["a"])(r),target:t},handled:!0,type:"instrument"}}),i)}})),Object(g["c"])(n,"removeEventListener",(function(t){return function(e,n,r){var i,o=n;try{var a=null===(i=o)||void 0===i?void 0:i.__sentry_wrapped__;a&&t.call(this,e,a,r)}catch(s){}return t.call(this,e,o,r)}})))},t.prototype._wrapXHR=function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=this,i=["onload","onerror","onprogress","onreadystatechange"];return i.forEach((function(t){t in r&&"function"===typeof r[t]&&Object(g["c"])(r,t,(function(e){var n={mechanism:{data:{function:t,handler:Object(B["a"])(e)},handled:!0,type:"instrument"}};return e.__sentry_original__&&(n.mechanism.data.handler=Object(B["a"])(e.__sentry_original__)),pe(e,n)}))})),t.apply(this,e)}},t.id="TryCatch",t}(),be=function(){function t(e){this.name=t.id,this._onErrorHandlerInstalled=!1,this._onUnhandledRejectionHandlerInstalled=!1,this._options=Object(s["a"])({onerror:!0,onunhandledrejection:!0},e)}return t.prototype.setupOnce=function(){Error.stackTraceLimit=50,this._options.onerror&&(v["a"].log("Global Handler attached: onerror"),this._installGlobalOnErrorHandler()),this._options.onunhandledrejection&&(v["a"].log("Global Handler attached: onunhandledrejection"),this._installGlobalOnUnhandledRejectionHandler())},t.prototype._installGlobalOnErrorHandler=function(){var e=this;this._onErrorHandlerInstalled||(V({callback:function(n){var r=n.error,i=A(),o=i.getIntegration(t),a=r&&!0===r.__sentry_own_request__;if(o&&!he()&&!a){var s=i.getClient(),c=Object(u["i"])(r)?e._eventFromIncompleteOnError(n.msg,n.url,n.line,n.column):e._enhanceEventWithInitialFrame(Wt(r,void 0,{attachStacktrace:s&&s.getOptions().attachStacktrace,rejection:!1}),n.url,n.line,n.column);Object(f["a"])(c,{handled:!1,type:"onerror"}),i.captureEvent(c,{originalException:r})}},type:"error"}),this._onErrorHandlerInstalled=!0)},t.prototype._installGlobalOnUnhandledRejectionHandler=function(){var e=this;this._onUnhandledRejectionHandlerInstalled||(V({callback:function(n){var r=n;try{"reason"in n?r=n.reason:"detail"in n&&"reason"in n.detail&&(r=n.detail.reason)}catch(l){}var i=A(),o=i.getIntegration(t),a=r&&!0===r.__sentry_own_request__;if(!o||he()||a)return!0;var s=i.getClient(),c=Object(u["i"])(r)?e._eventFromRejectionWithPrimitive(r):Wt(r,void 0,{attachStacktrace:s&&s.getOptions().attachStacktrace,rejection:!0});c.level=Ct.Error,Object(f["a"])(c,{handled:!1,type:"onunhandledrejection"}),i.captureEvent(c,{originalException:r})},type:"unhandledrejection"}),this._onUnhandledRejectionHandlerInstalled=!0)},t.prototype._eventFromIncompleteOnError=function(t,e,n,r){var i,o=/^(?:[Uu]ncaught (?:exception: )?)?(?:((?:Eval|Internal|Range|Reference|Syntax|Type|URI|)Error): )?(.*)$/i,a=Object(u["e"])(t)?t.message:t;if(Object(u["k"])(a)){var s=a.match(o);s&&(i=s[1],a=s[2])}var c={exception:{values:[{type:i||"Error",value:a}]}};return this._enhanceEventWithInitialFrame(c,e,n,r)},t.prototype._eventFromRejectionWithPrimitive=function(t){return{exception:{values:[{type:"UnhandledRejection",value:"Non-Error promise rejection captured with value: "+String(t)}]}}},t.prototype._enhanceEventWithInitialFrame=function(t,e,n,r){t.exception=t.exception||{},t.exception.values=t.exception.values||[],t.exception.values[0]=t.exception.values[0]||{},t.exception.values[0].stacktrace=t.exception.values[0].stacktrace||{},t.exception.values[0].stacktrace.frames=t.exception.values[0].stacktrace.frames||[];var i=isNaN(parseInt(r,10))?void 0:r,o=isNaN(parseInt(n,10))?void 0:n,a=Object(u["k"])(e)&&e.length>0?e:Object(f["f"])();return 0===t.exception.values[0].stacktrace.frames.length&&t.exception.values[0].stacktrace.frames.push({colno:i,filename:a,function:"?",in_app:!0,lineno:o}),t},t.id="GlobalHandlers",t}(),we="cause",xe=5,ke=function(){function t(e){void 0===e&&(e={}),this.name=t.id,this._key=e.key||we,this._limit=e.limit||xe}return t.prototype.setupOnce=function(){m((function(e,n){var r=A().getIntegration(t);return r?r._handler(e,n):e}))},t.prototype._handler=function(t,e){if(!t.exception||!t.exception.values||!e||!Object(u["g"])(e.originalException,Error))return t;var n=this._walkErrorTree(e.originalException,this._key);return t.exception.values=Object(s["e"])(n,t.exception.values),t},t.prototype._walkErrorTree=function(t,e,n){if(void 0===n&&(n=[]),!Object(u["g"])(t[e],Error)||n.length+1>=this._limit)return n;var r=Bt(t[e]),i=Ut(r);return this._walkErrorTree(t[e],e,Object(s["e"])([i],n))},t.id="LinkedErrors",t}(),Ee=Object(f["e"])(),Ce=function(){function t(){this.name=t.id}return t.prototype.setupOnce=function(){m((function(e){var n,r,i;if(A().getIntegration(t)){if(!Ee.navigator&&!Ee.location&&!Ee.document)return e;var o=(null===(n=e.request)||void 0===n?void 0:n.url)||(null===(r=Ee.location)||void 0===r?void 0:r.href),a=(Ee.document||{}).referrer,u=(Ee.navigator||{}).userAgent,c=Object(s["a"])(Object(s["a"])(Object(s["a"])({},null===(i=e.request)||void 0===i?void 0:i.headers),a&&{Referer:a}),u&&{"User-Agent":u}),l=Object(s["a"])(Object(s["a"])({},o&&{url:o}),{headers:c});return Object(s["a"])(Object(s["a"])({},e),{request:l})}return e}))},t.id="UserAgent",t}(),Ae=[new i.InboundFilters,new i.FunctionToString,new ye,new ve,new be,new ke,new Ce];function Se(t){if(void 0===t&&(t={}),void 0===t.defaultIntegrations&&(t.defaultIntegrations=Ae),void 0===t.release){var e=Object(f["e"])();e.SENTRY_RELEASE&&e.SENTRY_RELEASE.id&&(t.release=e.SENTRY_RELEASE.id)}void 0===t.autoSessionTracking&&(t.autoSessionTracking=!0),M(_e,t),t.autoSessionTracking&&De()}function De(){var t=Object(f["e"])(),e=t.document;if("undefined"!==typeof e){var n=A();"startSession"in n&&(n.startSession(),n.captureSession(),V({callback:function(){n.startSession(),n.captureSession()},type:"history"}))}else v["a"].warn("Session tracking in non-browser environment with @sentry/browser is not supported.")}},dd40:function(t,e){t.exports=function(t){if(!t.webpackPolyfill){var e=Object.create(t);e.children||(e.children=[]),Object.defineProperty(e,"loaded",{enumerable:!0,get:function(){return e.l}}),Object.defineProperty(e,"id",{enumerable:!0,get:function(){return e.i}}),Object.defineProperty(e,"exports",{enumerable:!0}),e.webpackPolyfill=1}return e}},ddb0:function(t,e,n){var r=n("da84"),i=n("fdbc"),o=n("e260"),a=n("9112"),s=n("b622"),u=s("iterator"),c=s("toStringTag"),l=o.values;for(var h in i){var f=r[h],p=f&&f.prototype;if(p){if(p[u]!==l)try{a(p,u,l)}catch(m){p[u]=l}if(p[c]||a(p,c,h),i[h])for(var d in o)if(p[d]!==o[d])try{a(p,d,o[d])}catch(m){p[d]=o[d]}}}},df75:function(t,e,n){var r=n("ca84"),i=n("7839");t.exports=Object.keys||function(t){return r(t,i)}},df7c:function(t,e,n){(function(t){function n(t,e){for(var n=0,r=t.length-1;r>=0;r--){var i=t[r];"."===i?t.splice(r,1):".."===i?(t.splice(r,1),n++):n&&(t.splice(r,1),n--)}if(e)for(;n--;n)t.unshift("..");return t}function r(t){"string"!==typeof t&&(t+="");var e,n=0,r=-1,i=!0;for(e=t.length-1;e>=0;--e)if(47===t.charCodeAt(e)){if(!i){n=e+1;break}}else-1===r&&(i=!1,r=e+1);return-1===r?"":t.slice(n,r)}function i(t,e){if(t.filter)return t.filter(e);for(var n=[],r=0;r<t.length;r++)e(t[r],r,t)&&n.push(t[r]);return n}e.resolve=function(){for(var e="",r=!1,o=arguments.length-1;o>=-1&&!r;o--){var a=o>=0?arguments[o]:t.cwd();if("string"!==typeof a)throw new TypeError("Arguments to path.resolve must be strings");a&&(e=a+"/"+e,r="/"===a.charAt(0))}return e=n(i(e.split("/"),(function(t){return!!t})),!r).join("/"),(r?"/":"")+e||"."},e.normalize=function(t){var r=e.isAbsolute(t),a="/"===o(t,-1);return t=n(i(t.split("/"),(function(t){return!!t})),!r).join("/"),t||r||(t="."),t&&a&&(t+="/"),(r?"/":"")+t},e.isAbsolute=function(t){return"/"===t.charAt(0)},e.join=function(){var t=Array.prototype.slice.call(arguments,0);return e.normalize(i(t,(function(t,e){if("string"!==typeof t)throw new TypeError("Arguments to path.join must be strings");return t})).join("/"))},e.relative=function(t,n){function r(t){for(var e=0;e<t.length;e++)if(""!==t[e])break;for(var n=t.length-1;n>=0;n--)if(""!==t[n])break;return e>n?[]:t.slice(e,n-e+1)}t=e.resolve(t).substr(1),n=e.resolve(n).substr(1);for(var i=r(t.split("/")),o=r(n.split("/")),a=Math.min(i.length,o.length),s=a,u=0;u<a;u++)if(i[u]!==o[u]){s=u;break}var c=[];for(u=s;u<i.length;u++)c.push("..");return c=c.concat(o.slice(s)),c.join("/")},e.sep="/",e.delimiter=":",e.dirname=function(t){if("string"!==typeof t&&(t+=""),0===t.length)return".";for(var e=t.charCodeAt(0),n=47===e,r=-1,i=!0,o=t.length-1;o>=1;--o)if(e=t.charCodeAt(o),47===e){if(!i){r=o;break}}else i=!1;return-1===r?n?"/":".":n&&1===r?"/":t.slice(0,r)},e.basename=function(t,e){var n=r(t);return e&&n.substr(-1*e.length)===e&&(n=n.substr(0,n.length-e.length)),n},e.extname=function(t){"string"!==typeof t&&(t+="");for(var e=-1,n=0,r=-1,i=!0,o=0,a=t.length-1;a>=0;--a){var s=t.charCodeAt(a);if(47!==s)-1===r&&(i=!1,r=a+1),46===s?-1===e?e=a:1!==o&&(o=1):-1!==e&&(o=-1);else if(!i){n=a+1;break}}return-1===e||-1===r||0===o||1===o&&e===r-1&&e===n+1?"":t.slice(e,r)};var o="b"==="ab".substr(-1)?function(t,e,n){return t.substr(e,n)}:function(t,e,n){return e<0&&(e=t.length+e),t.substr(e,n)}}).call(this,n("4362"))},e01a:function(t,e,n){"use strict";var r=n("23e7"),i=n("83ab"),o=n("da84"),a=n("5135"),s=n("861d"),u=n("9bf2").f,c=n("e893"),l=o.Symbol;if(i&&"function"==typeof l&&(!("description"in l.prototype)||void 0!==l().description)){var h={},f=function(){var t=arguments.length<1||void 0===arguments[0]?void 0:String(arguments[0]),e=this instanceof f?new l(t):void 0===t?l():l(t);return""===t&&(h[e]=!0),e};c(f,l);var p=f.prototype=l.prototype;p.constructor=f;var d=p.toString,m="Symbol(test)"==String(l("test")),v=/^Symbol\((.*)\)[^)]+$/;u(p,"description",{configurable:!0,get:function(){var t=s(this)?this.valueOf():this,e=d.call(t);if(a(h,t))return"";var n=m?e.slice(7,-1):e.replace(v,"$1");return""===n?void 0:n}}),r({global:!0,forced:!0},{Symbol:f})}},e11e:function(t,e,n){
/* @preserve
 * Leaflet 1.7.1, a JS library for interactive maps. http://leafletjs.com
 * (c) 2010-2019 Vladimir Agafonkin, (c) 2010-2011 CloudMade
 */
(function(t,n){n(e)})(0,(function(t){"use strict";var e="1.7.1";function n(t){var e,n,r,i;for(n=1,r=arguments.length;n<r;n++)for(e in i=arguments[n],i)t[e]=i[e];return t}var r=Object.create||function(){function t(){}return function(e){return t.prototype=e,new t}}();function i(t,e){var n=Array.prototype.slice;if(t.bind)return t.bind.apply(t,n.call(arguments,1));var r=n.call(arguments,2);return function(){return t.apply(e,r.length?r.concat(n.call(arguments)):arguments)}}var o=0;function a(t){return t._leaflet_id=t._leaflet_id||++o,t._leaflet_id}function s(t,e,n){var r,i,o,a;return a=function(){r=!1,i&&(o.apply(n,i),i=!1)},o=function(){r?i=arguments:(t.apply(n,arguments),setTimeout(a,e),r=!0)},o}function u(t,e,n){var r=e[1],i=e[0],o=r-i;return t===r&&n?t:((t-i)%o+o)%o+i}function c(){return!1}function l(t,e){var n=Math.pow(10,void 0===e?6:e);return Math.round(t*n)/n}function h(t){return t.trim?t.trim():t.replace(/^\s+|\s+$/g,"")}function f(t){return h(t).split(/\s+/)}function p(t,e){for(var n in Object.prototype.hasOwnProperty.call(t,"options")||(t.options=t.options?r(t.options):{}),e)t.options[n]=e[n];return t.options}function d(t,e,n){var r=[];for(var i in t)r.push(encodeURIComponent(n?i.toUpperCase():i)+"="+encodeURIComponent(t[i]));return(e&&-1!==e.indexOf("?")?"&":"?")+r.join("&")}var m=/\{ *([\w_-]+) *\}/g;function v(t,e){return t.replace(m,(function(t,n){var r=e[n];if(void 0===r)throw new Error("No value provided for variable "+t);return"function"===typeof r&&(r=r(e)),r}))}var _=Array.isArray||function(t){return"[object Array]"===Object.prototype.toString.call(t)};function g(t,e){for(var n=0;n<t.length;n++)if(t[n]===e)return n;return-1}var y="data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=";function b(t){return window["webkit"+t]||window["moz"+t]||window["ms"+t]}var w=0;function x(t){var e=+new Date,n=Math.max(0,16-(e-w));return w=e+n,window.setTimeout(t,n)}var k=window.requestAnimationFrame||b("RequestAnimationFrame")||x,E=window.cancelAnimationFrame||b("CancelAnimationFrame")||b("CancelRequestAnimationFrame")||function(t){window.clearTimeout(t)};function C(t,e,n){if(!n||k!==x)return k.call(window,i(t,e));t.call(e)}function A(t){t&&E.call(window,t)}var S={extend:n,create:r,bind:i,lastId:o,stamp:a,throttle:s,wrapNum:u,falseFn:c,formatNum:l,trim:h,splitWords:f,setOptions:p,getParamString:d,template:v,isArray:_,indexOf:g,emptyImageUrl:y,requestFn:k,cancelFn:E,requestAnimFrame:C,cancelAnimFrame:A};function D(){}function O(t){if("undefined"!==typeof L&&L&&L.Mixin){t=_(t)?t:[t];for(var e=0;e<t.length;e++)t[e]===L.Mixin.Events&&console.warn("Deprecated include of L.Mixin.Events: this property will be removed in future releases, please inherit from L.Evented instead.",(new Error).stack)}}D.extend=function(t){var e=function(){this.initialize&&this.initialize.apply(this,arguments),this.callInitHooks()},i=e.__super__=this.prototype,o=r(i);for(var a in o.constructor=e,e.prototype=o,this)Object.prototype.hasOwnProperty.call(this,a)&&"prototype"!==a&&"__super__"!==a&&(e[a]=this[a]);return t.statics&&(n(e,t.statics),delete t.statics),t.includes&&(O(t.includes),n.apply(null,[o].concat(t.includes)),delete t.includes),o.options&&(t.options=n(r(o.options),t.options)),n(o,t),o._initHooks=[],o.callInitHooks=function(){if(!this._initHooksCalled){i.callInitHooks&&i.callInitHooks.call(this),this._initHooksCalled=!0;for(var t=0,e=o._initHooks.length;t<e;t++)o._initHooks[t].call(this)}},e},D.include=function(t){return n(this.prototype,t),this},D.mergeOptions=function(t){return n(this.prototype.options,t),this},D.addInitHook=function(t){var e=Array.prototype.slice.call(arguments,1),n="function"===typeof t?t:function(){this[t].apply(this,e)};return this.prototype._initHooks=this.prototype._initHooks||[],this.prototype._initHooks.push(n),this};var T={on:function(t,e,n){if("object"===typeof t)for(var r in t)this._on(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._on(t[i],e,n)}return this},off:function(t,e,n){if(t)if("object"===typeof t)for(var r in t)this._off(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._off(t[i],e,n)}else delete this._events;return this},_on:function(t,e,n){this._events=this._events||{};var r=this._events[t];r||(r=[],this._events[t]=r),n===this&&(n=void 0);for(var i={fn:e,ctx:n},o=r,a=0,s=o.length;a<s;a++)if(o[a].fn===e&&o[a].ctx===n)return;o.push(i)},_off:function(t,e,n){var r,i,o;if(this._events&&(r=this._events[t],r))if(e){if(n===this&&(n=void 0),r)for(i=0,o=r.length;i<o;i++){var a=r[i];if(a.ctx===n&&a.fn===e)return a.fn=c,this._firingCount&&(this._events[t]=r=r.slice()),void r.splice(i,1)}}else{for(i=0,o=r.length;i<o;i++)r[i].fn=c;delete this._events[t]}},fire:function(t,e,r){if(!this.listens(t,r))return this;var i=n({},e,{type:t,target:this,sourceTarget:e&&e.sourceTarget||this});if(this._events){var o=this._events[t];if(o){this._firingCount=this._firingCount+1||1;for(var a=0,s=o.length;a<s;a++){var u=o[a];u.fn.call(u.ctx||this,i)}this._firingCount--}}return r&&this._propagateEvent(i),this},listens:function(t,e){var n=this._events&&this._events[t];if(n&&n.length)return!0;if(e)for(var r in this._eventParents)if(this._eventParents[r].listens(t,e))return!0;return!1},once:function(t,e,n){if("object"===typeof t){for(var r in t)this.once(r,t[r],e);return this}var o=i((function(){this.off(t,e,n).off(t,o,n)}),this);return this.on(t,e,n).on(t,o,n)},addEventParent:function(t){return this._eventParents=this._eventParents||{},this._eventParents[a(t)]=t,this},removeEventParent:function(t){return this._eventParents&&delete this._eventParents[a(t)],this},_propagateEvent:function(t){for(var e in this._eventParents)this._eventParents[e].fire(t.type,n({layer:t.target,propagatedFrom:t.target},t),!0)}};T.addEventListener=T.on,T.removeEventListener=T.clearAllEventListeners=T.off,T.addOneTimeEventListener=T.once,T.fireEvent=T.fire,T.hasEventListeners=T.listens;var P=D.extend(T);function j(t,e,n){this.x=n?Math.round(t):t,this.y=n?Math.round(e):e}var M=Math.trunc||function(t){return t>0?Math.floor(t):Math.ceil(t)};function B(t,e,n){return t instanceof j?t:_(t)?new j(t[0],t[1]):void 0===t||null===t?t:"object"===typeof t&&"x"in t&&"y"in t?new j(t.x,t.y):new j(t,e,n)}function R(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function F(t,e){return!t||t instanceof R?t:new R(t,e)}function I(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function z(t,e){return t instanceof I?t:new I(t,e)}function N(t,e,n){if(isNaN(t)||isNaN(e))throw new Error("Invalid LatLng object: ("+t+", "+e+")");this.lat=+t,this.lng=+e,void 0!==n&&(this.alt=+n)}function U(t,e,n){return t instanceof N?t:_(t)&&"object"!==typeof t[0]?3===t.length?new N(t[0],t[1],t[2]):2===t.length?new N(t[0],t[1]):null:void 0===t||null===t?t:"object"===typeof t&&"lat"in t?new N(t.lat,"lng"in t?t.lng:t.lon,t.alt):void 0===e?null:new N(t,e,n)}j.prototype={clone:function(){return new j(this.x,this.y)},add:function(t){return this.clone()._add(B(t))},_add:function(t){return this.x+=t.x,this.y+=t.y,this},subtract:function(t){return this.clone()._subtract(B(t))},_subtract:function(t){return this.x-=t.x,this.y-=t.y,this},divideBy:function(t){return this.clone()._divideBy(t)},_divideBy:function(t){return this.x/=t,this.y/=t,this},multiplyBy:function(t){return this.clone()._multiplyBy(t)},_multiplyBy:function(t){return this.x*=t,this.y*=t,this},scaleBy:function(t){return new j(this.x*t.x,this.y*t.y)},unscaleBy:function(t){return new j(this.x/t.x,this.y/t.y)},round:function(){return this.clone()._round()},_round:function(){return this.x=Math.round(this.x),this.y=Math.round(this.y),this},floor:function(){return this.clone()._floor()},_floor:function(){return this.x=Math.floor(this.x),this.y=Math.floor(this.y),this},ceil:function(){return this.clone()._ceil()},_ceil:function(){return this.x=Math.ceil(this.x),this.y=Math.ceil(this.y),this},trunc:function(){return this.clone()._trunc()},_trunc:function(){return this.x=M(this.x),this.y=M(this.y),this},distanceTo:function(t){t=B(t);var e=t.x-this.x,n=t.y-this.y;return Math.sqrt(e*e+n*n)},equals:function(t){return t=B(t),t.x===this.x&&t.y===this.y},contains:function(t){return t=B(t),Math.abs(t.x)<=Math.abs(this.x)&&Math.abs(t.y)<=Math.abs(this.y)},toString:function(){return"Point("+l(this.x)+", "+l(this.y)+")"}},R.prototype={extend:function(t){return t=B(t),this.min||this.max?(this.min.x=Math.min(t.x,this.min.x),this.max.x=Math.max(t.x,this.max.x),this.min.y=Math.min(t.y,this.min.y),this.max.y=Math.max(t.y,this.max.y)):(this.min=t.clone(),this.max=t.clone()),this},getCenter:function(t){return new j((this.min.x+this.max.x)/2,(this.min.y+this.max.y)/2,t)},getBottomLeft:function(){return new j(this.min.x,this.max.y)},getTopRight:function(){return new j(this.max.x,this.min.y)},getTopLeft:function(){return this.min},getBottomRight:function(){return this.max},getSize:function(){return this.max.subtract(this.min)},contains:function(t){var e,n;return t="number"===typeof t[0]||t instanceof j?B(t):F(t),t instanceof R?(e=t.min,n=t.max):e=n=t,e.x>=this.min.x&&n.x<=this.max.x&&e.y>=this.min.y&&n.y<=this.max.y},intersects:function(t){t=F(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>=e.x&&r.x<=n.x,a=i.y>=e.y&&r.y<=n.y;return o&&a},overlaps:function(t){t=F(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>e.x&&r.x<n.x,a=i.y>e.y&&r.y<n.y;return o&&a},isValid:function(){return!(!this.min||!this.max)}},I.prototype={extend:function(t){var e,n,r=this._southWest,i=this._northEast;if(t instanceof N)e=t,n=t;else{if(!(t instanceof I))return t?this.extend(U(t)||z(t)):this;if(e=t._southWest,n=t._northEast,!e||!n)return this}return r||i?(r.lat=Math.min(e.lat,r.lat),r.lng=Math.min(e.lng,r.lng),i.lat=Math.max(n.lat,i.lat),i.lng=Math.max(n.lng,i.lng)):(this._southWest=new N(e.lat,e.lng),this._northEast=new N(n.lat,n.lng)),this},pad:function(t){var e=this._southWest,n=this._northEast,r=Math.abs(e.lat-n.lat)*t,i=Math.abs(e.lng-n.lng)*t;return new I(new N(e.lat-r,e.lng-i),new N(n.lat+r,n.lng+i))},getCenter:function(){return new N((this._southWest.lat+this._northEast.lat)/2,(this._southWest.lng+this._northEast.lng)/2)},getSouthWest:function(){return this._southWest},getNorthEast:function(){return this._northEast},getNorthWest:function(){return new N(this.getNorth(),this.getWest())},getSouthEast:function(){return new N(this.getSouth(),this.getEast())},getWest:function(){return this._southWest.lng},getSouth:function(){return this._southWest.lat},getEast:function(){return this._northEast.lng},getNorth:function(){return this._northEast.lat},contains:function(t){t="number"===typeof t[0]||t instanceof N||"lat"in t?U(t):z(t);var e,n,r=this._southWest,i=this._northEast;return t instanceof I?(e=t.getSouthWest(),n=t.getNorthEast()):e=n=t,e.lat>=r.lat&&n.lat<=i.lat&&e.lng>=r.lng&&n.lng<=i.lng},intersects:function(t){t=z(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>=e.lat&&r.lat<=n.lat,a=i.lng>=e.lng&&r.lng<=n.lng;return o&&a},overlaps:function(t){t=z(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>e.lat&&r.lat<n.lat,a=i.lng>e.lng&&r.lng<n.lng;return o&&a},toBBoxString:function(){return[this.getWest(),this.getSouth(),this.getEast(),this.getNorth()].join(",")},equals:function(t,e){return!!t&&(t=z(t),this._southWest.equals(t.getSouthWest(),e)&&this._northEast.equals(t.getNorthEast(),e))},isValid:function(){return!(!this._southWest||!this._northEast)}},N.prototype={equals:function(t,e){if(!t)return!1;t=U(t);var n=Math.max(Math.abs(this.lat-t.lat),Math.abs(this.lng-t.lng));return n<=(void 0===e?1e-9:e)},toString:function(t){return"LatLng("+l(this.lat,t)+", "+l(this.lng,t)+")"},distanceTo:function(t){return $.distance(this,U(t))},wrap:function(){return $.wrapLatLng(this)},toBounds:function(t){var e=180*t/40075017,n=e/Math.cos(Math.PI/180*this.lat);return z([this.lat-e,this.lng-n],[this.lat+e,this.lng+n])},clone:function(){return new N(this.lat,this.lng,this.alt)}};var Z={latLngToPoint:function(t,e){var n=this.projection.project(t),r=this.scale(e);return this.transformation._transform(n,r)},pointToLatLng:function(t,e){var n=this.scale(e),r=this.transformation.untransform(t,n);return this.projection.unproject(r)},project:function(t){return this.projection.project(t)},unproject:function(t){return this.projection.unproject(t)},scale:function(t){return 256*Math.pow(2,t)},zoom:function(t){return Math.log(t/256)/Math.LN2},getProjectedBounds:function(t){if(this.infinite)return null;var e=this.projection.bounds,n=this.scale(t),r=this.transformation.transform(e.min,n),i=this.transformation.transform(e.max,n);return new R(r,i)},infinite:!1,wrapLatLng:function(t){var e=this.wrapLng?u(t.lng,this.wrapLng,!0):t.lng,n=this.wrapLat?u(t.lat,this.wrapLat,!0):t.lat,r=t.alt;return new N(n,e,r)},wrapLatLngBounds:function(t){var e=t.getCenter(),n=this.wrapLatLng(e),r=e.lat-n.lat,i=e.lng-n.lng;if(0===r&&0===i)return t;var o=t.getSouthWest(),a=t.getNorthEast(),s=new N(o.lat-r,o.lng-i),u=new N(a.lat-r,a.lng-i);return new I(s,u)}},$=n({},Z,{wrapLng:[-180,180],R:6371e3,distance:function(t,e){var n=Math.PI/180,r=t.lat*n,i=e.lat*n,o=Math.sin((e.lat-t.lat)*n/2),a=Math.sin((e.lng-t.lng)*n/2),s=o*o+Math.cos(r)*Math.cos(i)*a*a,u=2*Math.atan2(Math.sqrt(s),Math.sqrt(1-s));return this.R*u}}),H=6378137,q={R:H,MAX_LATITUDE:85.0511287798,project:function(t){var e=Math.PI/180,n=this.MAX_LATITUDE,r=Math.max(Math.min(n,t.lat),-n),i=Math.sin(r*e);return new j(this.R*t.lng*e,this.R*Math.log((1+i)/(1-i))/2)},unproject:function(t){var e=180/Math.PI;return new N((2*Math.atan(Math.exp(t.y/this.R))-Math.PI/2)*e,t.x*e/this.R)},bounds:function(){var t=H*Math.PI;return new R([-t,-t],[t,t])}()};function V(t,e,n,r){if(_(t))return this._a=t[0],this._b=t[1],this._c=t[2],void(this._d=t[3]);this._a=t,this._b=e,this._c=n,this._d=r}function W(t,e,n,r){return new V(t,e,n,r)}V.prototype={transform:function(t,e){return this._transform(t.clone(),e)},_transform:function(t,e){return e=e||1,t.x=e*(this._a*t.x+this._b),t.y=e*(this._c*t.y+this._d),t},untransform:function(t,e){return e=e||1,new j((t.x/e-this._b)/this._a,(t.y/e-this._d)/this._c)}};var G=n({},$,{code:"EPSG:3857",projection:q,transformation:function(){var t=.5/(Math.PI*q.R);return W(t,.5,-t,.5)}()}),Y=n({},G,{code:"EPSG:900913"});function K(t){return document.createElementNS("http://www.w3.org/2000/svg",t)}function X(t,e){var n,r,i,o,a,s,u="";for(n=0,i=t.length;n<i;n++){for(a=t[n],r=0,o=a.length;r<o;r++)s=a[r],u+=(r?"L":"M")+s.x+" "+s.y;u+=e?Lt?"z":"x":""}return u||"M0 0"}var J=document.documentElement.style,Q="ActiveXObject"in window,tt=Q&&!document.addEventListener,et="msLaunchUri"in navigator&&!("documentMode"in document),nt=Tt("webkit"),rt=Tt("android"),it=Tt("android 2")||Tt("android 3"),ot=parseInt(/WebKit\/([0-9]+)|$/.exec(navigator.userAgent)[1],10),at=rt&&Tt("Google")&&ot<537&&!("AudioNode"in window),st=!!window.opera,ut=!et&&Tt("chrome"),ct=Tt("gecko")&&!nt&&!st&&!Q,lt=!ut&&Tt("safari"),ht=Tt("phantom"),ft="OTransition"in J,pt=0===navigator.platform.indexOf("Win"),dt=Q&&"transition"in J,mt="WebKitCSSMatrix"in window&&"m11"in new window.WebKitCSSMatrix&&!it,vt="MozPerspective"in J,_t=!window.L_DISABLE_3D&&(dt||mt||vt)&&!ft&&!ht,gt="undefined"!==typeof orientation||Tt("mobile"),yt=gt&&nt,bt=gt&&mt,wt=!window.PointerEvent&&window.MSPointerEvent,xt=!(!window.PointerEvent&&!wt),kt=!window.L_NO_TOUCH&&(xt||"ontouchstart"in window||window.DocumentTouch&&document instanceof window.DocumentTouch),Et=gt&&st,Ct=gt&&ct,At=(window.devicePixelRatio||window.screen.deviceXDPI/window.screen.logicalXDPI)>1,St=function(){var t=!1;try{var e=Object.defineProperty({},"passive",{get:function(){t=!0}});window.addEventListener("testPassiveEventSupport",c,e),window.removeEventListener("testPassiveEventSupport",c,e)}catch(n){}return t}(),Dt=function(){return!!document.createElement("canvas").getContext}(),Lt=!(!document.createElementNS||!K("svg").createSVGRect),Ot=!Lt&&function(){try{var t=document.createElement("div");t.innerHTML='<v:shape adj="1"/>';var e=t.firstChild;return e.style.behavior="url(#default#VML)",e&&"object"===typeof e.adj}catch(n){return!1}}();function Tt(t){return navigator.userAgent.toLowerCase().indexOf(t)>=0}var Pt={ie:Q,ielt9:tt,edge:et,webkit:nt,android:rt,android23:it,androidStock:at,opera:st,chrome:ut,gecko:ct,safari:lt,phantom:ht,opera12:ft,win:pt,ie3d:dt,webkit3d:mt,gecko3d:vt,any3d:_t,mobile:gt,mobileWebkit:yt,mobileWebkit3d:bt,msPointer:wt,pointer:xt,touch:kt,mobileOpera:Et,mobileGecko:Ct,retina:At,passiveEvents:St,canvas:Dt,svg:Lt,vml:Ot},jt=wt?"MSPointerDown":"pointerdown",Mt=wt?"MSPointerMove":"pointermove",Bt=wt?"MSPointerUp":"pointerup",Rt=wt?"MSPointerCancel":"pointercancel",Ft={},It=!1;function zt(t,e,n,r){return"touchstart"===e?Ut(t,n,r):"touchmove"===e?Vt(t,n,r):"touchend"===e&&Wt(t,n,r),this}function Nt(t,e,n){var r=t["_leaflet_"+e+n];return"touchstart"===e?t.removeEventListener(jt,r,!1):"touchmove"===e?t.removeEventListener(Mt,r,!1):"touchend"===e&&(t.removeEventListener(Bt,r,!1),t.removeEventListener(Rt,r,!1)),this}function Ut(t,e,n){var r=i((function(t){t.MSPOINTER_TYPE_TOUCH&&t.pointerType===t.MSPOINTER_TYPE_TOUCH&&$e(t),qt(t,e)}));t["_leaflet_touchstart"+n]=r,t.addEventListener(jt,r,!1),It||(document.addEventListener(jt,Zt,!0),document.addEventListener(Mt,$t,!0),document.addEventListener(Bt,Ht,!0),document.addEventListener(Rt,Ht,!0),It=!0)}function Zt(t){Ft[t.pointerId]=t}function $t(t){Ft[t.pointerId]&&(Ft[t.pointerId]=t)}function Ht(t){delete Ft[t.pointerId]}function qt(t,e){for(var n in t.touches=[],Ft)t.touches.push(Ft[n]);t.changedTouches=[t],e(t)}function Vt(t,e,n){var r=function(t){t.pointerType===(t.MSPOINTER_TYPE_MOUSE||"mouse")&&0===t.buttons||qt(t,e)};t["_leaflet_touchmove"+n]=r,t.addEventListener(Mt,r,!1)}function Wt(t,e,n){var r=function(t){qt(t,e)};t["_leaflet_touchend"+n]=r,t.addEventListener(Bt,r,!1),t.addEventListener(Rt,r,!1)}var Gt=wt?"MSPointerDown":xt?"pointerdown":"touchstart",Yt=wt?"MSPointerUp":xt?"pointerup":"touchend",Kt="_leaflet_";function Xt(t,e,n){var r,i,o=!1,a=250;function s(t){if(xt){if(!t.isPrimary)return;if("mouse"===t.pointerType)return}else if(t.touches.length>1)return;var e=Date.now(),n=e-(r||e);i=t.touches?t.touches[0]:t,o=n>0&&n<=a,r=e}function u(t){if(o&&!i.cancelBubble){if(xt){if("mouse"===t.pointerType)return;var n,a,s={};for(a in i)n=i[a],s[a]=n&&n.bind?n.bind(i):n;i=s}i.type="dblclick",i.button=0,e(i),r=null}}return t[Kt+Gt+n]=s,t[Kt+Yt+n]=u,t[Kt+"dblclick"+n]=e,t.addEventListener(Gt,s,!!St&&{passive:!1}),t.addEventListener(Yt,u,!!St&&{passive:!1}),t.addEventListener("dblclick",e,!1),this}function Jt(t,e){var n=t[Kt+Gt+e],r=t[Kt+Yt+e],i=t[Kt+"dblclick"+e];return t.removeEventListener(Gt,n,!!St&&{passive:!1}),t.removeEventListener(Yt,r,!!St&&{passive:!1}),t.removeEventListener("dblclick",i,!1),this}var Qt,te,ee,ne,re,ie=we(["transform","webkitTransform","OTransform","MozTransform","msTransform"]),oe=we(["webkitTransition","transition","OTransition","MozTransition","msTransition"]),ae="webkitTransition"===oe||"OTransition"===oe?oe+"End":"transitionend";function se(t){return"string"===typeof t?document.getElementById(t):t}function ue(t,e){var n=t.style[e]||t.currentStyle&&t.currentStyle[e];if((!n||"auto"===n)&&document.defaultView){var r=document.defaultView.getComputedStyle(t,null);n=r?r[e]:null}return"auto"===n?null:n}function ce(t,e,n){var r=document.createElement(t);return r.className=e||"",n&&n.appendChild(r),r}function le(t){var e=t.parentNode;e&&e.removeChild(t)}function he(t){while(t.firstChild)t.removeChild(t.firstChild)}function fe(t){var e=t.parentNode;e&&e.lastChild!==t&&e.appendChild(t)}function pe(t){var e=t.parentNode;e&&e.firstChild!==t&&e.insertBefore(t,e.firstChild)}function de(t,e){if(void 0!==t.classList)return t.classList.contains(e);var n=ge(t);return n.length>0&&new RegExp("(^|\\s)"+e+"(\\s|$)").test(n)}function me(t,e){if(void 0!==t.classList)for(var n=f(e),r=0,i=n.length;r<i;r++)t.classList.add(n[r]);else if(!de(t,e)){var o=ge(t);_e(t,(o?o+" ":"")+e)}}function ve(t,e){void 0!==t.classList?t.classList.remove(e):_e(t,h((" "+ge(t)+" ").replace(" "+e+" "," ")))}function _e(t,e){void 0===t.className.baseVal?t.className=e:t.className.baseVal=e}function ge(t){return t.correspondingElement&&(t=t.correspondingElement),void 0===t.className.baseVal?t.className:t.className.baseVal}function ye(t,e){"opacity"in t.style?t.style.opacity=e:"filter"in t.style&&be(t,e)}function be(t,e){var n=!1,r="DXImageTransform.Microsoft.Alpha";try{n=t.filters.item(r)}catch(i){if(1===e)return}e=Math.round(100*e),n?(n.Enabled=100!==e,n.Opacity=e):t.style.filter+=" progid:"+r+"(opacity="+e+")"}function we(t){for(var e=document.documentElement.style,n=0;n<t.length;n++)if(t[n]in e)return t[n];return!1}function xe(t,e,n){var r=e||new j(0,0);t.style[ie]=(dt?"translate("+r.x+"px,"+r.y+"px)":"translate3d("+r.x+"px,"+r.y+"px,0)")+(n?" scale("+n+")":"")}function ke(t,e){t._leaflet_pos=e,_t?xe(t,e):(t.style.left=e.x+"px",t.style.top=e.y+"px")}function Ee(t){return t._leaflet_pos||new j(0,0)}if("onselectstart"in document)Qt=function(){je(window,"selectstart",$e)},te=function(){Be(window,"selectstart",$e)};else{var Ce=we(["userSelect","WebkitUserSelect","OUserSelect","MozUserSelect","msUserSelect"]);Qt=function(){if(Ce){var t=document.documentElement.style;ee=t[Ce],t[Ce]="none"}},te=function(){Ce&&(document.documentElement.style[Ce]=ee,ee=void 0)}}function Ae(){je(window,"dragstart",$e)}function Se(){Be(window,"dragstart",$e)}function De(t){while(-1===t.tabIndex)t=t.parentNode;t.style&&(Le(),ne=t,re=t.style.outline,t.style.outline="none",je(window,"keydown",Le))}function Le(){ne&&(ne.style.outline=re,ne=void 0,re=void 0,Be(window,"keydown",Le))}function Oe(t){do{t=t.parentNode}while((!t.offsetWidth||!t.offsetHeight)&&t!==document.body);return t}function Te(t){var e=t.getBoundingClientRect();return{x:e.width/t.offsetWidth||1,y:e.height/t.offsetHeight||1,boundingClientRect:e}}var Pe={TRANSFORM:ie,TRANSITION:oe,TRANSITION_END:ae,get:se,getStyle:ue,create:ce,remove:le,empty:he,toFront:fe,toBack:pe,hasClass:de,addClass:me,removeClass:ve,setClass:_e,getClass:ge,setOpacity:ye,testProp:we,setTransform:xe,setPosition:ke,getPosition:Ee,disableTextSelection:Qt,enableTextSelection:te,disableImageDrag:Ae,enableImageDrag:Se,preventOutline:De,restoreOutline:Le,getSizedParentNode:Oe,getScale:Te};function je(t,e,n,r){if("object"===typeof e)for(var i in e)Ie(t,i,e[i],n);else{e=f(e);for(var o=0,a=e.length;o<a;o++)Ie(t,e[o],n,r)}return this}var Me="_leaflet_events";function Be(t,e,n,r){if("object"===typeof e)for(var i in e)ze(t,i,e[i],n);else if(e){e=f(e);for(var o=0,a=e.length;o<a;o++)ze(t,e[o],n,r)}else{for(var s in t[Me])ze(t,s,t[Me][s]);delete t[Me]}return this}function Re(){if(xt)return!(et||lt)}var Fe={mouseenter:"mouseover",mouseleave:"mouseout",wheel:!("onwheel"in window)&&"mousewheel"};function Ie(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):"");if(t[Me]&&t[Me][i])return this;var o=function(e){return n.call(r||t,e||window.event)},s=o;xt&&0===e.indexOf("touch")?zt(t,e,o,i):kt&&"dblclick"===e&&!Re()?Xt(t,o,i):"addEventListener"in t?"touchstart"===e||"touchmove"===e||"wheel"===e||"mousewheel"===e?t.addEventListener(Fe[e]||e,o,!!St&&{passive:!1}):"mouseenter"===e||"mouseleave"===e?(o=function(e){e=e||window.event,Xe(t,e)&&s(e)},t.addEventListener(Fe[e],o,!1)):t.addEventListener(e,s,!1):"attachEvent"in t&&t.attachEvent("on"+e,o),t[Me]=t[Me]||{},t[Me][i]=o}function ze(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):""),o=t[Me]&&t[Me][i];if(!o)return this;xt&&0===e.indexOf("touch")?Nt(t,e,i):kt&&"dblclick"===e&&!Re()?Jt(t,i):"removeEventListener"in t?t.removeEventListener(Fe[e]||e,o,!1):"detachEvent"in t&&t.detachEvent("on"+e,o),t[Me][i]=null}function Ne(t){return t.stopPropagation?t.stopPropagation():t.originalEvent?t.originalEvent._stopped=!0:t.cancelBubble=!0,Ke(t),this}function Ue(t){return Ie(t,"wheel",Ne),this}function Ze(t){return je(t,"mousedown touchstart dblclick",Ne),Ie(t,"click",Ye),this}function $e(t){return t.preventDefault?t.preventDefault():t.returnValue=!1,this}function He(t){return $e(t),Ne(t),this}function qe(t,e){if(!e)return new j(t.clientX,t.clientY);var n=Te(e),r=n.boundingClientRect;return new j((t.clientX-r.left)/n.x-e.clientLeft,(t.clientY-r.top)/n.y-e.clientTop)}var Ve=pt&&ut?2*window.devicePixelRatio:ct?window.devicePixelRatio:1;function We(t){return et?t.wheelDeltaY/2:t.deltaY&&0===t.deltaMode?-t.deltaY/Ve:t.deltaY&&1===t.deltaMode?20*-t.deltaY:t.deltaY&&2===t.deltaMode?60*-t.deltaY:t.deltaX||t.deltaZ?0:t.wheelDelta?(t.wheelDeltaY||t.wheelDelta)/2:t.detail&&Math.abs(t.detail)<32765?20*-t.detail:t.detail?t.detail/-32765*60:0}var Ge={};function Ye(t){Ge[t.type]=!0}function Ke(t){var e=Ge[t.type];return Ge[t.type]=!1,e}function Xe(t,e){var n=e.relatedTarget;if(!n)return!0;try{while(n&&n!==t)n=n.parentNode}catch(r){return!1}return n!==t}var Je={on:je,off:Be,stopPropagation:Ne,disableScrollPropagation:Ue,disableClickPropagation:Ze,preventDefault:$e,stop:He,getMousePosition:qe,getWheelDelta:We,fakeStop:Ye,skipped:Ke,isExternalTarget:Xe,addListener:je,removeListener:Be},Qe=P.extend({run:function(t,e,n,r){this.stop(),this._el=t,this._inProgress=!0,this._duration=n||.25,this._easeOutPower=1/Math.max(r||.5,.2),this._startPos=Ee(t),this._offset=e.subtract(this._startPos),this._startTime=+new Date,this.fire("start"),this._animate()},stop:function(){this._inProgress&&(this._step(!0),this._complete())},_animate:function(){this._animId=C(this._animate,this),this._step()},_step:function(t){var e=+new Date-this._startTime,n=1e3*this._duration;e<n?this._runFrame(this._easeOut(e/n),t):(this._runFrame(1),this._complete())},_runFrame:function(t,e){var n=this._startPos.add(this._offset.multiplyBy(t));e&&n._round(),ke(this._el,n),this.fire("step")},_complete:function(){A(this._animId),this._inProgress=!1,this.fire("end")},_easeOut:function(t){return 1-Math.pow(1-t,this._easeOutPower)}}),tn=P.extend({options:{crs:G,center:void 0,zoom:void 0,minZoom:void 0,maxZoom:void 0,layers:[],maxBounds:void 0,renderer:void 0,zoomAnimation:!0,zoomAnimationThreshold:4,fadeAnimation:!0,markerZoomAnimation:!0,transform3DLimit:8388608,zoomSnap:1,zoomDelta:1,trackResize:!0},initialize:function(t,e){e=p(this,e),this._handlers=[],this._layers={},this._zoomBoundLayers={},this._sizeChanged=!0,this._initContainer(t),this._initLayout(),this._onResize=i(this._onResize,this),this._initEvents(),e.maxBounds&&this.setMaxBounds(e.maxBounds),void 0!==e.zoom&&(this._zoom=this._limitZoom(e.zoom)),e.center&&void 0!==e.zoom&&this.setView(U(e.center),e.zoom,{reset:!0}),this.callInitHooks(),this._zoomAnimated=oe&&_t&&!Et&&this.options.zoomAnimation,this._zoomAnimated&&(this._createAnimProxy(),je(this._proxy,ae,this._catchTransitionEnd,this)),this._addLayers(this.options.layers)},setView:function(t,e,r){if(e=void 0===e?this._zoom:this._limitZoom(e),t=this._limitCenter(U(t),e,this.options.maxBounds),r=r||{},this._stop(),this._loaded&&!r.reset&&!0!==r){void 0!==r.animate&&(r.zoom=n({animate:r.animate},r.zoom),r.pan=n({animate:r.animate,duration:r.duration},r.pan));var i=this._zoom!==e?this._tryAnimatedZoom&&this._tryAnimatedZoom(t,e,r.zoom):this._tryAnimatedPan(t,r.pan);if(i)return clearTimeout(this._sizeTimer),this}return this._resetView(t,e),this},setZoom:function(t,e){return this._loaded?this.setView(this.getCenter(),t,{zoom:e}):(this._zoom=t,this)},zoomIn:function(t,e){return t=t||(_t?this.options.zoomDelta:1),this.setZoom(this._zoom+t,e)},zoomOut:function(t,e){return t=t||(_t?this.options.zoomDelta:1),this.setZoom(this._zoom-t,e)},setZoomAround:function(t,e,n){var r=this.getZoomScale(e),i=this.getSize().divideBy(2),o=t instanceof j?t:this.latLngToContainerPoint(t),a=o.subtract(i).multiplyBy(1-1/r),s=this.containerPointToLatLng(i.add(a));return this.setView(s,e,{zoom:n})},_getBoundsCenterZoom:function(t,e){e=e||{},t=t.getBounds?t.getBounds():z(t);var n=B(e.paddingTopLeft||e.padding||[0,0]),r=B(e.paddingBottomRight||e.padding||[0,0]),i=this.getBoundsZoom(t,!1,n.add(r));if(i="number"===typeof e.maxZoom?Math.min(e.maxZoom,i):i,i===1/0)return{center:t.getCenter(),zoom:i};var o=r.subtract(n).divideBy(2),a=this.project(t.getSouthWest(),i),s=this.project(t.getNorthEast(),i),u=this.unproject(a.add(s).divideBy(2).add(o),i);return{center:u,zoom:i}},fitBounds:function(t,e){if(t=z(t),!t.isValid())throw new Error("Bounds are not valid.");var n=this._getBoundsCenterZoom(t,e);return this.setView(n.center,n.zoom,e)},fitWorld:function(t){return this.fitBounds([[-90,-180],[90,180]],t)},panTo:function(t,e){return this.setView(t,this._zoom,{pan:e})},panBy:function(t,e){if(t=B(t).round(),e=e||{},!t.x&&!t.y)return this.fire("moveend");if(!0!==e.animate&&!this.getSize().contains(t))return this._resetView(this.unproject(this.project(this.getCenter()).add(t)),this.getZoom()),this;if(this._panAnim||(this._panAnim=new Qe,this._panAnim.on({step:this._onPanTransitionStep,end:this._onPanTransitionEnd},this)),e.noMoveStart||this.fire("movestart"),!1!==e.animate){me(this._mapPane,"leaflet-pan-anim");var n=this._getMapPanePos().subtract(t).round();this._panAnim.run(this._mapPane,n,e.duration||.25,e.easeLinearity)}else this._rawPanBy(t),this.fire("move").fire("moveend");return this},flyTo:function(t,e,n){if(n=n||{},!1===n.animate||!_t)return this.setView(t,e,n);this._stop();var r=this.project(this.getCenter()),i=this.project(t),o=this.getSize(),a=this._zoom;t=U(t),e=void 0===e?a:e;var s=Math.max(o.x,o.y),u=s*this.getZoomScale(a,e),c=i.distanceTo(r)||1,l=1.42,h=l*l;function f(t){var e=t?-1:1,n=t?u:s,r=u*u-s*s+e*h*h*c*c,i=2*n*h*c,o=r/i,a=Math.sqrt(o*o+1)-o,l=a<1e-9?-18:Math.log(a);return l}function p(t){return(Math.exp(t)-Math.exp(-t))/2}function d(t){return(Math.exp(t)+Math.exp(-t))/2}function m(t){return p(t)/d(t)}var v=f(0);function _(t){return s*(d(v)/d(v+l*t))}function g(t){return s*(d(v)*m(v+l*t)-p(v))/h}function y(t){return 1-Math.pow(1-t,1.5)}var b=Date.now(),w=(f(1)-v)/l,x=n.duration?1e3*n.duration:1e3*w*.8;function k(){var n=(Date.now()-b)/x,o=y(n)*w;n<=1?(this._flyToFrame=C(k,this),this._move(this.unproject(r.add(i.subtract(r).multiplyBy(g(o)/c)),a),this.getScaleZoom(s/_(o),a),{flyTo:!0})):this._move(t,e)._moveEnd(!0)}return this._moveStart(!0,n.noMoveStart),k.call(this),this},flyToBounds:function(t,e){var n=this._getBoundsCenterZoom(t,e);return this.flyTo(n.center,n.zoom,e)},setMaxBounds:function(t){return t=z(t),t.isValid()?(this.options.maxBounds&&this.off("moveend",this._panInsideMaxBounds),this.options.maxBounds=t,this._loaded&&this._panInsideMaxBounds(),this.on("moveend",this._panInsideMaxBounds)):(this.options.maxBounds=null,this.off("moveend",this._panInsideMaxBounds))},setMinZoom:function(t){var e=this.options.minZoom;return this.options.minZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()<this.options.minZoom)?this.setZoom(t):this},setMaxZoom:function(t){var e=this.options.maxZoom;return this.options.maxZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()>this.options.maxZoom)?this.setZoom(t):this},panInsideBounds:function(t,e){this._enforcingBounds=!0;var n=this.getCenter(),r=this._limitCenter(n,this._zoom,z(t));return n.equals(r)||this.panTo(r,e),this._enforcingBounds=!1,this},panInside:function(t,e){e=e||{};var n=B(e.paddingTopLeft||e.padding||[0,0]),r=B(e.paddingBottomRight||e.padding||[0,0]),i=this.getCenter(),o=this.project(i),a=this.project(t),s=this.getPixelBounds(),u=s.getSize().divideBy(2),c=F([s.min.add(n),s.max.subtract(r)]);if(!c.contains(a)){this._enforcingBounds=!0;var l=o.subtract(a),h=B(a.x+l.x,a.y+l.y);(a.x<c.min.x||a.x>c.max.x)&&(h.x=o.x-l.x,l.x>0?h.x+=u.x-n.x:h.x-=u.x-r.x),(a.y<c.min.y||a.y>c.max.y)&&(h.y=o.y-l.y,l.y>0?h.y+=u.y-n.y:h.y-=u.y-r.y),this.panTo(this.unproject(h),e),this._enforcingBounds=!1}return this},invalidateSize:function(t){if(!this._loaded)return this;t=n({animate:!1,pan:!0},!0===t?{animate:!0}:t);var e=this.getSize();this._sizeChanged=!0,this._lastCenter=null;var r=this.getSize(),o=e.divideBy(2).round(),a=r.divideBy(2).round(),s=o.subtract(a);return s.x||s.y?(t.animate&&t.pan?this.panBy(s):(t.pan&&this._rawPanBy(s),this.fire("move"),t.debounceMoveend?(clearTimeout(this._sizeTimer),this._sizeTimer=setTimeout(i(this.fire,this,"moveend"),200)):this.fire("moveend")),this.fire("resize",{oldSize:e,newSize:r})):this},stop:function(){return this.setZoom(this._limitZoom(this._zoom)),this.options.zoomSnap||this.fire("viewreset"),this._stop()},locate:function(t){if(t=this._locateOptions=n({timeout:1e4,watch:!1},t),!("geolocation"in navigator))return this._handleGeolocationError({code:0,message:"Geolocation not supported."}),this;var e=i(this._handleGeolocationResponse,this),r=i(this._handleGeolocationError,this);return t.watch?this._locationWatchId=navigator.geolocation.watchPosition(e,r,t):navigator.geolocation.getCurrentPosition(e,r,t),this},stopLocate:function(){return navigator.geolocation&&navigator.geolocation.clearWatch&&navigator.geolocation.clearWatch(this._locationWatchId),this._locateOptions&&(this._locateOptions.setView=!1),this},_handleGeolocationError:function(t){var e=t.code,n=t.message||(1===e?"permission denied":2===e?"position unavailable":"timeout");this._locateOptions.setView&&!this._loaded&&this.fitWorld(),this.fire("locationerror",{code:e,message:"Geolocation error: "+n+"."})},_handleGeolocationResponse:function(t){var e=t.coords.latitude,n=t.coords.longitude,r=new N(e,n),i=r.toBounds(2*t.coords.accuracy),o=this._locateOptions;if(o.setView){var a=this.getBoundsZoom(i);this.setView(r,o.maxZoom?Math.min(a,o.maxZoom):a)}var s={latlng:r,bounds:i,timestamp:t.timestamp};for(var u in t.coords)"number"===typeof t.coords[u]&&(s[u]=t.coords[u]);this.fire("locationfound",s)},addHandler:function(t,e){if(!e)return this;var n=this[t]=new e(this);return this._handlers.push(n),this.options[t]&&n.enable(),this},remove:function(){if(this._initEvents(!0),this.off("moveend",this._panInsideMaxBounds),this._containerId!==this._container._leaflet_id)throw new Error("Map container is being reused by another instance");try{delete this._container._leaflet_id,delete this._containerId}catch(e){this._container._leaflet_id=void 0,this._containerId=void 0}var t;for(t in void 0!==this._locationWatchId&&this.stopLocate(),this._stop(),le(this._mapPane),this._clearControlPos&&this._clearControlPos(),this._resizeRequest&&(A(this._resizeRequest),this._resizeRequest=null),this._clearHandlers(),this._loaded&&this.fire("unload"),this._layers)this._layers[t].remove();for(t in this._panes)le(this._panes[t]);return this._layers=[],this._panes=[],delete this._mapPane,delete this._renderer,this},createPane:function(t,e){var n="leaflet-pane"+(t?" leaflet-"+t.replace("Pane","")+"-pane":""),r=ce("div",n,e||this._mapPane);return t&&(this._panes[t]=r),r},getCenter:function(){return this._checkIfLoaded(),this._lastCenter&&!this._moved()?this._lastCenter:this.layerPointToLatLng(this._getCenterLayerPoint())},getZoom:function(){return this._zoom},getBounds:function(){var t=this.getPixelBounds(),e=this.unproject(t.getBottomLeft()),n=this.unproject(t.getTopRight());return new I(e,n)},getMinZoom:function(){return void 0===this.options.minZoom?this._layersMinZoom||0:this.options.minZoom},getMaxZoom:function(){return void 0===this.options.maxZoom?void 0===this._layersMaxZoom?1/0:this._layersMaxZoom:this.options.maxZoom},getBoundsZoom:function(t,e,n){t=z(t),n=B(n||[0,0]);var r=this.getZoom()||0,i=this.getMinZoom(),o=this.getMaxZoom(),a=t.getNorthWest(),s=t.getSouthEast(),u=this.getSize().subtract(n),c=F(this.project(s,r),this.project(a,r)).getSize(),l=_t?this.options.zoomSnap:1,h=u.x/c.x,f=u.y/c.y,p=e?Math.max(h,f):Math.min(h,f);return r=this.getScaleZoom(p,r),l&&(r=Math.round(r/(l/100))*(l/100),r=e?Math.ceil(r/l)*l:Math.floor(r/l)*l),Math.max(i,Math.min(o,r))},getSize:function(){return this._size&&!this._sizeChanged||(this._size=new j(this._container.clientWidth||0,this._container.clientHeight||0),this._sizeChanged=!1),this._size.clone()},getPixelBounds:function(t,e){var n=this._getTopLeftPoint(t,e);return new R(n,n.add(this.getSize()))},getPixelOrigin:function(){return this._checkIfLoaded(),this._pixelOrigin},getPixelWorldBounds:function(t){return this.options.crs.getProjectedBounds(void 0===t?this.getZoom():t)},getPane:function(t){return"string"===typeof t?this._panes[t]:t},getPanes:function(){return this._panes},getContainer:function(){return this._container},getZoomScale:function(t,e){var n=this.options.crs;return e=void 0===e?this._zoom:e,n.scale(t)/n.scale(e)},getScaleZoom:function(t,e){var n=this.options.crs;e=void 0===e?this._zoom:e;var r=n.zoom(t*n.scale(e));return isNaN(r)?1/0:r},project:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.latLngToPoint(U(t),e)},unproject:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.pointToLatLng(B(t),e)},layerPointToLatLng:function(t){var e=B(t).add(this.getPixelOrigin());return this.unproject(e)},latLngToLayerPoint:function(t){var e=this.project(U(t))._round();return e._subtract(this.getPixelOrigin())},wrapLatLng:function(t){return this.options.crs.wrapLatLng(U(t))},wrapLatLngBounds:function(t){return this.options.crs.wrapLatLngBounds(z(t))},distance:function(t,e){return this.options.crs.distance(U(t),U(e))},containerPointToLayerPoint:function(t){return B(t).subtract(this._getMapPanePos())},layerPointToContainerPoint:function(t){return B(t).add(this._getMapPanePos())},containerPointToLatLng:function(t){var e=this.containerPointToLayerPoint(B(t));return this.layerPointToLatLng(e)},latLngToContainerPoint:function(t){return this.layerPointToContainerPoint(this.latLngToLayerPoint(U(t)))},mouseEventToContainerPoint:function(t){return qe(t,this._container)},mouseEventToLayerPoint:function(t){return this.containerPointToLayerPoint(this.mouseEventToContainerPoint(t))},mouseEventToLatLng:function(t){return this.layerPointToLatLng(this.mouseEventToLayerPoint(t))},_initContainer:function(t){var e=this._container=se(t);if(!e)throw new Error("Map container not found.");if(e._leaflet_id)throw new Error("Map container is already initialized.");je(e,"scroll",this._onScroll,this),this._containerId=a(e)},_initLayout:function(){var t=this._container;this._fadeAnimated=this.options.fadeAnimation&&_t,me(t,"leaflet-container"+(kt?" leaflet-touch":"")+(At?" leaflet-retina":"")+(tt?" leaflet-oldie":"")+(lt?" leaflet-safari":"")+(this._fadeAnimated?" leaflet-fade-anim":""));var e=ue(t,"position");"absolute"!==e&&"relative"!==e&&"fixed"!==e&&(t.style.position="relative"),this._initPanes(),this._initControlPos&&this._initControlPos()},_initPanes:function(){var t=this._panes={};this._paneRenderers={},this._mapPane=this.createPane("mapPane",this._container),ke(this._mapPane,new j(0,0)),this.createPane("tilePane"),this.createPane("shadowPane"),this.createPane("overlayPane"),this.createPane("markerPane"),this.createPane("tooltipPane"),this.createPane("popupPane"),this.options.markerZoomAnimation||(me(t.markerPane,"leaflet-zoom-hide"),me(t.shadowPane,"leaflet-zoom-hide"))},_resetView:function(t,e){ke(this._mapPane,new j(0,0));var n=!this._loaded;this._loaded=!0,e=this._limitZoom(e),this.fire("viewprereset");var r=this._zoom!==e;this._moveStart(r,!1)._move(t,e)._moveEnd(r),this.fire("viewreset"),n&&this.fire("load")},_moveStart:function(t,e){return t&&this.fire("zoomstart"),e||this.fire("movestart"),this},_move:function(t,e,n){void 0===e&&(e=this._zoom);var r=this._zoom!==e;return this._zoom=e,this._lastCenter=t,this._pixelOrigin=this._getNewPixelOrigin(t),(r||n&&n.pinch)&&this.fire("zoom",n),this.fire("move",n)},_moveEnd:function(t){return t&&this.fire("zoomend"),this.fire("moveend")},_stop:function(){return A(this._flyToFrame),this._panAnim&&this._panAnim.stop(),this},_rawPanBy:function(t){ke(this._mapPane,this._getMapPanePos().subtract(t))},_getZoomSpan:function(){return this.getMaxZoom()-this.getMinZoom()},_panInsideMaxBounds:function(){this._enforcingBounds||this.panInsideBounds(this.options.maxBounds)},_checkIfLoaded:function(){if(!this._loaded)throw new Error("Set map center and zoom first.")},_initEvents:function(t){this._targets={},this._targets[a(this._container)]=this;var e=t?Be:je;e(this._container,"click dblclick mousedown mouseup mouseover mouseout mousemove contextmenu keypress keydown keyup",this._handleDOMEvent,this),this.options.trackResize&&e(window,"resize",this._onResize,this),_t&&this.options.transform3DLimit&&(t?this.off:this.on).call(this,"moveend",this._onMoveEnd)},_onResize:function(){A(this._resizeRequest),this._resizeRequest=C((function(){this.invalidateSize({debounceMoveend:!0})}),this)},_onScroll:function(){this._container.scrollTop=0,this._container.scrollLeft=0},_onMoveEnd:function(){var t=this._getMapPanePos();Math.max(Math.abs(t.x),Math.abs(t.y))>=this.options.transform3DLimit&&this._resetView(this.getCenter(),this.getZoom())},_findEventTargets:function(t,e){var n,r=[],i="mouseout"===e||"mouseover"===e,o=t.target||t.srcElement,s=!1;while(o){if(n=this._targets[a(o)],n&&("click"===e||"preclick"===e)&&!t._simulated&&this._draggableMoved(n)){s=!0;break}if(n&&n.listens(e,!0)){if(i&&!Xe(o,t))break;if(r.push(n),i)break}if(o===this._container)break;o=o.parentNode}return r.length||s||i||!Xe(o,t)||(r=[this]),r},_handleDOMEvent:function(t){if(this._loaded&&!Ke(t)){var e=t.type;"mousedown"!==e&&"keypress"!==e&&"keyup"!==e&&"keydown"!==e||De(t.target||t.srcElement),this._fireDOMEvent(t,e)}},_mouseEvents:["click","dblclick","mouseover","mouseout","contextmenu"],_fireDOMEvent:function(t,e,r){if("click"===t.type){var i=n({},t);i.type="preclick",this._fireDOMEvent(i,i.type,r)}if(!t._stopped&&(r=(r||[]).concat(this._findEventTargets(t,e)),r.length)){var o=r[0];"contextmenu"===e&&o.listens(e,!0)&&$e(t);var a={originalEvent:t};if("keypress"!==t.type&&"keydown"!==t.type&&"keyup"!==t.type){var s=o.getLatLng&&(!o._radius||o._radius<=10);a.containerPoint=s?this.latLngToContainerPoint(o.getLatLng()):this.mouseEventToContainerPoint(t),a.layerPoint=this.containerPointToLayerPoint(a.containerPoint),a.latlng=s?o.getLatLng():this.layerPointToLatLng(a.layerPoint)}for(var u=0;u<r.length;u++)if(r[u].fire(e,a,!0),a.originalEvent._stopped||!1===r[u].options.bubblingMouseEvents&&-1!==g(this._mouseEvents,e))return}},_draggableMoved:function(t){return t=t.dragging&&t.dragging.enabled()?t:this,t.dragging&&t.dragging.moved()||this.boxZoom&&this.boxZoom.moved()},_clearHandlers:function(){for(var t=0,e=this._handlers.length;t<e;t++)this._handlers[t].disable()},whenReady:function(t,e){return this._loaded?t.call(e||this,{target:this}):this.on("load",t,e),this},_getMapPanePos:function(){return Ee(this._mapPane)||new j(0,0)},_moved:function(){var t=this._getMapPanePos();return t&&!t.equals([0,0])},_getTopLeftPoint:function(t,e){var n=t&&void 0!==e?this._getNewPixelOrigin(t,e):this.getPixelOrigin();return n.subtract(this._getMapPanePos())},_getNewPixelOrigin:function(t,e){var n=this.getSize()._divideBy(2);return this.project(t,e)._subtract(n)._add(this._getMapPanePos())._round()},_latLngToNewLayerPoint:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return this.project(t,e)._subtract(r)},_latLngBoundsToNewLayerBounds:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return F([this.project(t.getSouthWest(),e)._subtract(r),this.project(t.getNorthWest(),e)._subtract(r),this.project(t.getSouthEast(),e)._subtract(r),this.project(t.getNorthEast(),e)._subtract(r)])},_getCenterLayerPoint:function(){return this.containerPointToLayerPoint(this.getSize()._divideBy(2))},_getCenterOffset:function(t){return this.latLngToLayerPoint(t).subtract(this._getCenterLayerPoint())},_limitCenter:function(t,e,n){if(!n)return t;var r=this.project(t,e),i=this.getSize().divideBy(2),o=new R(r.subtract(i),r.add(i)),a=this._getBoundsOffset(o,n,e);return a.round().equals([0,0])?t:this.unproject(r.add(a),e)},_limitOffset:function(t,e){if(!e)return t;var n=this.getPixelBounds(),r=new R(n.min.add(t),n.max.add(t));return t.add(this._getBoundsOffset(r,e))},_getBoundsOffset:function(t,e,n){var r=F(this.project(e.getNorthEast(),n),this.project(e.getSouthWest(),n)),i=r.min.subtract(t.min),o=r.max.subtract(t.max),a=this._rebound(i.x,-o.x),s=this._rebound(i.y,-o.y);return new j(a,s)},_rebound:function(t,e){return t+e>0?Math.round(t-e)/2:Math.max(0,Math.ceil(t))-Math.max(0,Math.floor(e))},_limitZoom:function(t){var e=this.getMinZoom(),n=this.getMaxZoom(),r=_t?this.options.zoomSnap:1;return r&&(t=Math.round(t/r)*r),Math.max(e,Math.min(n,t))},_onPanTransitionStep:function(){this.fire("move")},_onPanTransitionEnd:function(){ve(this._mapPane,"leaflet-pan-anim"),this.fire("moveend")},_tryAnimatedPan:function(t,e){var n=this._getCenterOffset(t)._trunc();return!(!0!==(e&&e.animate)&&!this.getSize().contains(n))&&(this.panBy(n,e),!0)},_createAnimProxy:function(){var t=this._proxy=ce("div","leaflet-proxy leaflet-zoom-animated");this._panes.mapPane.appendChild(t),this.on("zoomanim",(function(t){var e=ie,n=this._proxy.style[e];xe(this._proxy,this.project(t.center,t.zoom),this.getZoomScale(t.zoom,1)),n===this._proxy.style[e]&&this._animatingZoom&&this._onZoomTransitionEnd()}),this),this.on("load moveend",this._animMoveEnd,this),this._on("unload",this._destroyAnimProxy,this)},_destroyAnimProxy:function(){le(this._proxy),this.off("load moveend",this._animMoveEnd,this),delete this._proxy},_animMoveEnd:function(){var t=this.getCenter(),e=this.getZoom();xe(this._proxy,this.project(t,e),this.getZoomScale(e,1))},_catchTransitionEnd:function(t){this._animatingZoom&&t.propertyName.indexOf("transform")>=0&&this._onZoomTransitionEnd()},_nothingToAnimate:function(){return!this._container.getElementsByClassName("leaflet-zoom-animated").length},_tryAnimatedZoom:function(t,e,n){if(this._animatingZoom)return!0;if(n=n||{},!this._zoomAnimated||!1===n.animate||this._nothingToAnimate()||Math.abs(e-this._zoom)>this.options.zoomAnimationThreshold)return!1;var r=this.getZoomScale(e),i=this._getCenterOffset(t)._divideBy(1-1/r);return!(!0!==n.animate&&!this.getSize().contains(i))&&(C((function(){this._moveStart(!0,!1)._animateZoom(t,e,!0)}),this),!0)},_animateZoom:function(t,e,n,r){this._mapPane&&(n&&(this._animatingZoom=!0,this._animateToCenter=t,this._animateToZoom=e,me(this._mapPane,"leaflet-zoom-anim")),this.fire("zoomanim",{center:t,zoom:e,noUpdate:r}),setTimeout(i(this._onZoomTransitionEnd,this),250))},_onZoomTransitionEnd:function(){this._animatingZoom&&(this._mapPane&&ve(this._mapPane,"leaflet-zoom-anim"),this._animatingZoom=!1,this._move(this._animateToCenter,this._animateToZoom),C((function(){this._moveEnd(!0)}),this))}});function en(t,e){return new tn(t,e)}var nn=D.extend({options:{position:"topright"},initialize:function(t){p(this,t)},getPosition:function(){return this.options.position},setPosition:function(t){var e=this._map;return e&&e.removeControl(this),this.options.position=t,e&&e.addControl(this),this},getContainer:function(){return this._container},addTo:function(t){this.remove(),this._map=t;var e=this._container=this.onAdd(t),n=this.getPosition(),r=t._controlCorners[n];return me(e,"leaflet-control"),-1!==n.indexOf("bottom")?r.insertBefore(e,r.firstChild):r.appendChild(e),this._map.on("unload",this.remove,this),this},remove:function(){return this._map?(le(this._container),this.onRemove&&this.onRemove(this._map),this._map.off("unload",this.remove,this),this._map=null,this):this},_refocusOnMap:function(t){this._map&&t&&t.screenX>0&&t.screenY>0&&this._map.getContainer().focus()}}),rn=function(t){return new nn(t)};tn.include({addControl:function(t){return t.addTo(this),this},removeControl:function(t){return t.remove(),this},_initControlPos:function(){var t=this._controlCorners={},e="leaflet-",n=this._controlContainer=ce("div",e+"control-container",this._container);function r(r,i){var o=e+r+" "+e+i;t[r+i]=ce("div",o,n)}r("top","left"),r("top","right"),r("bottom","left"),r("bottom","right")},_clearControlPos:function(){for(var t in this._controlCorners)le(this._controlCorners[t]);le(this._controlContainer),delete this._controlCorners,delete this._controlContainer}});var on=nn.extend({options:{collapsed:!0,position:"topright",autoZIndex:!0,hideSingleBase:!1,sortLayers:!1,sortFunction:function(t,e,n,r){return n<r?-1:r<n?1:0}},initialize:function(t,e,n){for(var r in p(this,n),this._layerControlInputs=[],this._layers=[],this._lastZIndex=0,this._handlingClick=!1,t)this._addLayer(t[r],r);for(r in e)this._addLayer(e[r],r,!0)},onAdd:function(t){this._initLayout(),this._update(),this._map=t,t.on("zoomend",this._checkDisabledLayers,this);for(var e=0;e<this._layers.length;e++)this._layers[e].layer.on("add remove",this._onLayerChange,this);return this._container},addTo:function(t){return nn.prototype.addTo.call(this,t),this._expandIfNotCollapsed()},onRemove:function(){this._map.off("zoomend",this._checkDisabledLayers,this);for(var t=0;t<this._layers.length;t++)this._layers[t].layer.off("add remove",this._onLayerChange,this)},addBaseLayer:function(t,e){return this._addLayer(t,e),this._map?this._update():this},addOverlay:function(t,e){return this._addLayer(t,e,!0),this._map?this._update():this},removeLayer:function(t){t.off("add remove",this._onLayerChange,this);var e=this._getLayer(a(t));return e&&this._layers.splice(this._layers.indexOf(e),1),this._map?this._update():this},expand:function(){me(this._container,"leaflet-control-layers-expanded"),this._section.style.height=null;var t=this._map.getSize().y-(this._container.offsetTop+50);return t<this._section.clientHeight?(me(this._section,"leaflet-control-layers-scrollbar"),this._section.style.height=t+"px"):ve(this._section,"leaflet-control-layers-scrollbar"),this._checkDisabledLayers(),this},collapse:function(){return ve(this._container,"leaflet-control-layers-expanded"),this},_initLayout:function(){var t="leaflet-control-layers",e=this._container=ce("div",t),n=this.options.collapsed;e.setAttribute("aria-haspopup",!0),Ze(e),Ue(e);var r=this._section=ce("section",t+"-list");n&&(this._map.on("click",this.collapse,this),rt||je(e,{mouseenter:this.expand,mouseleave:this.collapse},this));var i=this._layersLink=ce("a",t+"-toggle",e);i.href="#",i.title="Layers",kt?(je(i,"click",He),je(i,"click",this.expand,this)):je(i,"focus",this.expand,this),n||this.expand(),this._baseLayersList=ce("div",t+"-base",r),this._separator=ce("div",t+"-separator",r),this._overlaysList=ce("div",t+"-overlays",r),e.appendChild(r)},_getLayer:function(t){for(var e=0;e<this._layers.length;e++)if(this._layers[e]&&a(this._layers[e].layer)===t)return this._layers[e]},_addLayer:function(t,e,n){this._map&&t.on("add remove",this._onLayerChange,this),this._layers.push({layer:t,name:e,overlay:n}),this.options.sortLayers&&this._layers.sort(i((function(t,e){return this.options.sortFunction(t.layer,e.layer,t.name,e.name)}),this)),this.options.autoZIndex&&t.setZIndex&&(this._lastZIndex++,t.setZIndex(this._lastZIndex)),this._expandIfNotCollapsed()},_update:function(){if(!this._container)return this;he(this._baseLayersList),he(this._overlaysList),this._layerControlInputs=[];var t,e,n,r,i=0;for(n=0;n<this._layers.length;n++)r=this._layers[n],this._addItem(r),e=e||r.overlay,t=t||!r.overlay,i+=r.overlay?0:1;return this.options.hideSingleBase&&(t=t&&i>1,this._baseLayersList.style.display=t?"":"none"),this._separator.style.display=e&&t?"":"none",this},_onLayerChange:function(t){this._handlingClick||this._update();var e=this._getLayer(a(t.target)),n=e.overlay?"add"===t.type?"overlayadd":"overlayremove":"add"===t.type?"baselayerchange":null;n&&this._map.fire(n,e)},_createRadioElement:function(t,e){var n='<input type="radio" class="leaflet-control-layers-selector" name="'+t+'"'+(e?' checked="checked"':"")+"/>",r=document.createElement("div");return r.innerHTML=n,r.firstChild},_addItem:function(t){var e,n=document.createElement("label"),r=this._map.hasLayer(t.layer);t.overlay?(e=document.createElement("input"),e.type="checkbox",e.className="leaflet-control-layers-selector",e.defaultChecked=r):e=this._createRadioElement("leaflet-base-layers_"+a(this),r),this._layerControlInputs.push(e),e.layerId=a(t.layer),je(e,"click",this._onInputClick,this);var i=document.createElement("span");i.innerHTML=" "+t.name;var o=document.createElement("div");n.appendChild(o),o.appendChild(e),o.appendChild(i);var s=t.overlay?this._overlaysList:this._baseLayersList;return s.appendChild(n),this._checkDisabledLayers(),n},_onInputClick:function(){var t,e,n=this._layerControlInputs,r=[],i=[];this._handlingClick=!0;for(var o=n.length-1;o>=0;o--)t=n[o],e=this._getLayer(t.layerId).layer,t.checked?r.push(e):t.checked||i.push(e);for(o=0;o<i.length;o++)this._map.hasLayer(i[o])&&this._map.removeLayer(i[o]);for(o=0;o<r.length;o++)this._map.hasLayer(r[o])||this._map.addLayer(r[o]);this._handlingClick=!1,this._refocusOnMap()},_checkDisabledLayers:function(){for(var t,e,n=this._layerControlInputs,r=this._map.getZoom(),i=n.length-1;i>=0;i--)t=n[i],e=this._getLayer(t.layerId).layer,t.disabled=void 0!==e.options.minZoom&&r<e.options.minZoom||void 0!==e.options.maxZoom&&r>e.options.maxZoom},_expandIfNotCollapsed:function(){return this._map&&!this.options.collapsed&&this.expand(),this},_expand:function(){return this.expand()},_collapse:function(){return this.collapse()}}),an=function(t,e,n){return new on(t,e,n)},sn=nn.extend({options:{position:"topleft",zoomInText:"+",zoomInTitle:"Zoom in",zoomOutText:"&#x2212;",zoomOutTitle:"Zoom out"},onAdd:function(t){var e="leaflet-control-zoom",n=ce("div",e+" leaflet-bar"),r=this.options;return this._zoomInButton=this._createButton(r.zoomInText,r.zoomInTitle,e+"-in",n,this._zoomIn),this._zoomOutButton=this._createButton(r.zoomOutText,r.zoomOutTitle,e+"-out",n,this._zoomOut),this._updateDisabled(),t.on("zoomend zoomlevelschange",this._updateDisabled,this),n},onRemove:function(t){t.off("zoomend zoomlevelschange",this._updateDisabled,this)},disable:function(){return this._disabled=!0,this._updateDisabled(),this},enable:function(){return this._disabled=!1,this._updateDisabled(),this},_zoomIn:function(t){!this._disabled&&this._map._zoom<this._map.getMaxZoom()&&this._map.zoomIn(this._map.options.zoomDelta*(t.shiftKey?3:1))},_zoomOut:function(t){!this._disabled&&this._map._zoom>this._map.getMinZoom()&&this._map.zoomOut(this._map.options.zoomDelta*(t.shiftKey?3:1))},_createButton:function(t,e,n,r,i){var o=ce("a",n,r);return o.innerHTML=t,o.href="#",o.title=e,o.setAttribute("role","button"),o.setAttribute("aria-label",e),Ze(o),je(o,"click",He),je(o,"click",i,this),je(o,"click",this._refocusOnMap,this),o},_updateDisabled:function(){var t=this._map,e="leaflet-disabled";ve(this._zoomInButton,e),ve(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMinZoom())&&me(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMaxZoom())&&me(this._zoomInButton,e)}});tn.mergeOptions({zoomControl:!0}),tn.addInitHook((function(){this.options.zoomControl&&(this.zoomControl=new sn,this.addControl(this.zoomControl))}));var un=function(t){return new sn(t)},cn=nn.extend({options:{position:"bottomleft",maxWidth:100,metric:!0,imperial:!0},onAdd:function(t){var e="leaflet-control-scale",n=ce("div",e),r=this.options;return this._addScales(r,e+"-line",n),t.on(r.updateWhenIdle?"moveend":"move",this._update,this),t.whenReady(this._update,this),n},onRemove:function(t){t.off(this.options.updateWhenIdle?"moveend":"move",this._update,this)},_addScales:function(t,e,n){t.metric&&(this._mScale=ce("div",e,n)),t.imperial&&(this._iScale=ce("div",e,n))},_update:function(){var t=this._map,e=t.getSize().y/2,n=t.distance(t.containerPointToLatLng([0,e]),t.containerPointToLatLng([this.options.maxWidth,e]));this._updateScales(n)},_updateScales:function(t){this.options.metric&&t&&this._updateMetric(t),this.options.imperial&&t&&this._updateImperial(t)},_updateMetric:function(t){var e=this._getRoundNum(t),n=e<1e3?e+" m":e/1e3+" km";this._updateScale(this._mScale,n,e/t)},_updateImperial:function(t){var e,n,r,i=3.2808399*t;i>5280?(e=i/5280,n=this._getRoundNum(e),this._updateScale(this._iScale,n+" mi",n/e)):(r=this._getRoundNum(i),this._updateScale(this._iScale,r+" ft",r/i))},_updateScale:function(t,e,n){t.style.width=Math.round(this.options.maxWidth*n)+"px",t.innerHTML=e},_getRoundNum:function(t){var e=Math.pow(10,(Math.floor(t)+"").length-1),n=t/e;return n=n>=10?10:n>=5?5:n>=3?3:n>=2?2:1,e*n}}),ln=function(t){return new cn(t)},hn=nn.extend({options:{position:"bottomright",prefix:'`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a>")})),l=function(){return"$0"==="a".replace(/./,"$0")}(),h=o("replace"),f=function(){return!!/./[h]&&""===/./[h]("a","$0")}(),p=!i((function(){var t=/(?:)/,e=t.exec;t.exec=function(){return e.apply(this,arguments)};var n="ab".split(t);return 2!==n.length||"a"!==n[0]||"b"!==n[1]}));t.exports=function(t,e,n,h){var d=o(t),m=!i((function(){var e={};return e[d]=function(){return 7},7!=""[t](e)})),v=m&&!i((function(){var e=!1,n=/a/;return"split"===t&&(n={},n.constructor={},n.constructor[u]=function(){return n},n.flags="",n[d]=/./[d]),n.exec=function(){return e=!0,null},n[d](""),!e}));if(!m||!v||"replace"===t&&(!c||!l||f)||"split"===t&&!p){var g=/./[d],_=n(d,""[t],(function(t,e,n,r,i){return e.exec===a?m&&!i?{done:!0,value:g.call(e,n,r)}:{done:!0,value:t.call(n,e,r)}:{done:!1}}),{REPLACE_KEEPS_$0:l,REGEXP_REPLACE_SUBSTITUTES_UNDEFINED_CAPTURE:f}),y=_[0],b=_[1];r(String.prototype,t,y),r(RegExp.prototype,d,2==e?function(t,e){return b.call(t,this,e)}:function(t){return b.call(t,this)})}h&&s(RegExp.prototype[d],"sham",!0)}},d81d:function(t,e,n){"use strict";var r=n("23e7"),i=n("b727").map,o=n("1dde"),a=n("ae40"),s=o("map"),u=a("map");r({target:"Array",proto:!0,forced:!s||!u},{map:function(t){return i(this,t,arguments.length>1?arguments[1]:void 0)}})},d90b:function(t,e,n){"use strict";var r=n("a905");t.exports=function(t){return"undefined"!==typeof File&&t instanceof File||"undefined"!==typeof Blob&&t instanceof Blob||t instanceof r}},d9a4:function(t,e,n){"use strict";n("4160"),n("b0c0"),n("159b");var r=n("4b6b");t.exports=function(t){var e={url:"/graphql",method:"POST",headers:{Accept:"application/json"}},n=r(t),i=n.clone,o=n.files,a=JSON.stringify(i);if(o.size){var s=new FormData;s.append("operations",a);var u={},c=0;o.forEach((function(t){u[++c]=t})),s.append("map",JSON.stringify(u)),c=0,o.forEach((function(t,e){s.append(""+ ++c,e,e.name)})),e.body=s}else e.headers["Content-Type"]="application/json",e.body=a;return e}},da84:function(t,e,n){(function(e){var n=function(t){return t&&t.Math==Math&&t};t.exports=n("object"==typeof globalThis&&globalThis)||n("object"==typeof window&&window)||n("object"==typeof self&&self)||n("object"==typeof e&&e)||function(){return this}()||Function("return this")()}).call(this,n("c8ba"))},dbb4:function(t,e,n){var r=n("23e7"),i=n("83ab"),o=n("56ef"),a=n("fc6a"),s=n("06cf"),u=n("8418");r({target:"Object",stat:!0,sham:!i},{getOwnPropertyDescriptors:function(t){var e,n,r=a(t),i=s.f,c=o(r),l={},h=0;while(c.length>h)n=i(r,e=c[h++]),void 0!==n&&u(l,e,n);return l}})},dc21:function(t,e,n){"use strict";n.d(e,"a",(function(){return Ae}));var r,i={};n.r(i),n.d(i,"FunctionToString",(function(){return a})),n.d(i,"InboundFilters",(function(){return P}));var o,a=function(){function t(){this.name=t.id}return t.prototype.setupOnce=function(){r=Function.prototype.toString,Function.prototype.toString=function(){for(var t=[],e=0;e<arguments.length;e++)t[e]=arguments[e];var n=this.__sentry_original__||this;return r.apply(n,t)}},t.id="FunctionToString",t}(),s=n("9ab4"),u=n("f404"),c=n("91db");(function(t){t["PENDING"]="PENDING",t["RESOLVED"]="RESOLVED",t["REJECTED"]="REJECTED"})(o||(o={}));var l,h=function(){function t(t){var e=this;this._state=o.PENDING,this._handlers=[],this._resolve=function(t){e._setResult(o.RESOLVED,t)},this._reject=function(t){e._setResult(o.REJECTED,t)},this._setResult=function(t,n){e._state===o.PENDING&&(Object(u["m"])(n)?n.then(e._resolve,e._reject):(e._state=t,e._value=n,e._executeHandlers()))},this._attachHandler=function(t){e._handlers=e._handlers.concat(t),e._executeHandlers()},this._executeHandlers=function(){if(e._state!==o.PENDING){var t=e._handlers.slice();e._handlers=[],t.forEach((function(t){t.done||(e._state===o.RESOLVED&&t.onfulfilled&&t.onfulfilled(e._value),e._state===o.REJECTED&&t.onrejected&&t.onrejected(e._value),t.done=!0)}))}};try{t(this._resolve,this._reject)}catch(n){this._reject(n)}}return t.resolve=function(e){return new t((function(t){t(e)}))},t.reject=function(e){return new t((function(t,n){n(e)}))},t.all=function(e){return new t((function(n,r){if(Array.isArray(e))if(0!==e.length){var i=e.length,o=[];e.forEach((function(e,a){t.resolve(e).then((function(t){o[a]=t,i-=1,0===i&&n(o)})).then(null,r)}))}else n([]);else r(new TypeError("Promise.all requires an array as input."))}))},t.prototype.then=function(e,n){var r=this;return new t((function(t,i){r._attachHandler({done:!1,onfulfilled:function(n){if(e)try{return void t(e(n))}catch(r){return void i(r)}else t(n)},onrejected:function(e){if(n)try{return void t(n(e))}catch(r){return void i(r)}else i(e)}})}))},t.prototype.catch=function(t){return this.then((function(t){return t}),t)},t.prototype.finally=function(e){var n=this;return new t((function(t,r){var i,o;return n.then((function(t){o=!1,i=t,e&&e()}),(function(t){o=!0,i=t,e&&e()})).then((function(){o?r(i):t(i)}))}))},t.prototype.toString=function(){return"[object SyncPromise]"},t}(),f=n("f7f6"),p=function(){function t(){this._notifyingListeners=!1,this._scopeListeners=[],this._eventProcessors=[],this._breadcrumbs=[],this._user={},this._tags={},this._extra={},this._contexts={}}return t.clone=function(e){var n=new t;return e&&(n._breadcrumbs=Object(s["e"])(e._breadcrumbs),n._tags=Object(s["a"])({},e._tags),n._extra=Object(s["a"])({},e._extra),n._contexts=Object(s["a"])({},e._contexts),n._user=e._user,n._level=e._level,n._span=e._span,n._session=e._session,n._transactionName=e._transactionName,n._fingerprint=e._fingerprint,n._eventProcessors=Object(s["e"])(e._eventProcessors)),n},t.prototype.addScopeListener=function(t){this._scopeListeners.push(t)},t.prototype.addEventProcessor=function(t){return this._eventProcessors.push(t),this},t.prototype.setUser=function(t){return this._user=t||{},this._session&&this._session.update({user:t}),this._notifyScopeListeners(),this},t.prototype.getUser=function(){return this._user},t.prototype.setTags=function(t){return this._tags=Object(s["a"])(Object(s["a"])({},this._tags),t),this._notifyScopeListeners(),this},t.prototype.setTag=function(t,e){var n;return this._tags=Object(s["a"])(Object(s["a"])({},this._tags),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setExtras=function(t){return this._extra=Object(s["a"])(Object(s["a"])({},this._extra),t),this._notifyScopeListeners(),this},t.prototype.setExtra=function(t,e){var n;return this._extra=Object(s["a"])(Object(s["a"])({},this._extra),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setFingerprint=function(t){return this._fingerprint=t,this._notifyScopeListeners(),this},t.prototype.setLevel=function(t){return this._level=t,this._notifyScopeListeners(),this},t.prototype.setTransactionName=function(t){return this._transactionName=t,this._notifyScopeListeners(),this},t.prototype.setTransaction=function(t){return this.setTransactionName(t)},t.prototype.setContext=function(t,e){var n;return null===e?delete this._contexts[t]:this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),(n={},n[t]=e,n)),this._notifyScopeListeners(),this},t.prototype.setSpan=function(t){return this._span=t,this._notifyScopeListeners(),this},t.prototype.getSpan=function(){return this._span},t.prototype.getTransaction=function(){var t,e,n,r,i=this.getSpan();return(null===(t=i)||void 0===t?void 0:t.transaction)?null===(e=i)||void 0===e?void 0:e.transaction:(null===(r=null===(n=i)||void 0===n?void 0:n.spanRecorder)||void 0===r?void 0:r.spans[0])?i.spanRecorder.spans[0]:void 0},t.prototype.setSession=function(t){return t?this._session=t:delete this._session,this._notifyScopeListeners(),this},t.prototype.getSession=function(){return this._session},t.prototype.update=function(e){if(!e)return this;if("function"===typeof e){var n=e(this);return n instanceof t?n:this}return e instanceof t?(this._tags=Object(s["a"])(Object(s["a"])({},this._tags),e._tags),this._extra=Object(s["a"])(Object(s["a"])({},this._extra),e._extra),this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),e._contexts),e._user&&Object.keys(e._user).length&&(this._user=e._user),e._level&&(this._level=e._level),e._fingerprint&&(this._fingerprint=e._fingerprint)):Object(u["h"])(e)&&(e=e,this._tags=Object(s["a"])(Object(s["a"])({},this._tags),e.tags),this._extra=Object(s["a"])(Object(s["a"])({},this._extra),e.extra),this._contexts=Object(s["a"])(Object(s["a"])({},this._contexts),e.contexts),e.user&&(this._user=e.user),e.level&&(this._level=e.level),e.fingerprint&&(this._fingerprint=e.fingerprint)),this},t.prototype.clear=function(){return this._breadcrumbs=[],this._tags={},this._extra={},this._user={},this._contexts={},this._level=void 0,this._transactionName=void 0,this._fingerprint=void 0,this._span=void 0,this._session=void 0,this._notifyScopeListeners(),this},t.prototype.addBreadcrumb=function(t,e){var n=Object(s["a"])({timestamp:Object(c["a"])()},t);return this._breadcrumbs=void 0!==e&&e>=0?Object(s["e"])(this._breadcrumbs,[n]).slice(-e):Object(s["e"])(this._breadcrumbs,[n]),this._notifyScopeListeners(),this},t.prototype.clearBreadcrumbs=function(){return this._breadcrumbs=[],this._notifyScopeListeners(),this},t.prototype.applyToEvent=function(t,e){var n;if(this._extra&&Object.keys(this._extra).length&&(t.extra=Object(s["a"])(Object(s["a"])({},this._extra),t.extra)),this._tags&&Object.keys(this._tags).length&&(t.tags=Object(s["a"])(Object(s["a"])({},this._tags),t.tags)),this._user&&Object.keys(this._user).length&&(t.user=Object(s["a"])(Object(s["a"])({},this._user),t.user)),this._contexts&&Object.keys(this._contexts).length&&(t.contexts=Object(s["a"])(Object(s["a"])({},this._contexts),t.contexts)),this._level&&(t.level=this._level),this._transactionName&&(t.transaction=this._transactionName),this._span){t.contexts=Object(s["a"])({trace:this._span.getTraceContext()},t.contexts);var r=null===(n=this._span.transaction)||void 0===n?void 0:n.name;r&&(t.tags=Object(s["a"])({transaction:r},t.tags))}return this._applyFingerprint(t),t.breadcrumbs=Object(s["e"])(t.breadcrumbs||[],this._breadcrumbs),t.breadcrumbs=t.breadcrumbs.length>0?t.breadcrumbs:void 0,this._notifyEventProcessors(Object(s["e"])(d(),this._eventProcessors),t,e)},t.prototype._notifyEventProcessors=function(t,e,n,r){var i=this;return void 0===r&&(r=0),new h((function(o,a){var c=t[r];if(null===e||"function"!==typeof c)o(e);else{var l=c(Object(s["a"])({},e),n);Object(u["m"])(l)?l.then((function(e){return i._notifyEventProcessors(t,e,n,r+1).then(o)})).then(null,a):i._notifyEventProcessors(t,l,n,r+1).then(o).then(null,a)}}))},t.prototype._notifyScopeListeners=function(){var t=this;this._notifyingListeners||(this._notifyingListeners=!0,this._scopeListeners.forEach((function(e){e(t)})),this._notifyingListeners=!1)},t.prototype._applyFingerprint=function(t){t.fingerprint=t.fingerprint?Array.isArray(t.fingerprint)?t.fingerprint:[t.fingerprint]:[],this._fingerprint&&(t.fingerprint=t.fingerprint.concat(this._fingerprint)),t.fingerprint&&!t.fingerprint.length&&delete t.fingerprint},t}();function d(){var t=Object(f["e"])();return t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.globalEventProcessors=t.__SENTRY__.globalEventProcessors||[],t.__SENTRY__.globalEventProcessors}function m(t){d().push(t)}(function(t){t["Ok"]="ok",t["Exited"]="exited",t["Crashed"]="crashed",t["Abnormal"]="abnormal"})(l||(l={}));var v=n("f0b6"),g=n("f80d"),_=n("e8f5"),y=function(){function t(t){this.errors=0,this.sid=Object(f["i"])(),this.timestamp=Date.now(),this.started=Date.now(),this.duration=0,this.status=l.Ok,this.init=!0,t&&this.update(t)}return t.prototype.update=function(t){void 0===t&&(t={}),t.user&&(t.user.ip_address&&(this.ipAddress=t.user.ip_address),t.did||(this.did=t.user.id||t.user.email||t.user.username)),this.timestamp=t.timestamp||Date.now(),t.sid&&(this.sid=32===t.sid.length?t.sid:Object(f["i"])()),void 0!==t.init&&(this.init=t.init),t.did&&(this.did=""+t.did),"number"===typeof t.started&&(this.started=t.started),"number"===typeof t.duration?this.duration=t.duration:this.duration=this.timestamp-this.started,t.release&&(this.release=t.release),t.environment&&(this.environment=t.environment),t.ipAddress&&(this.ipAddress=t.ipAddress),t.userAgent&&(this.userAgent=t.userAgent),"number"===typeof t.errors&&(this.errors=t.errors),t.status&&(this.status=t.status)},t.prototype.close=function(t){t?this.update({status:t}):this.status===l.Ok?this.update({status:l.Exited}):this.update()},t.prototype.toJSON=function(){return Object(_["a"])({sid:""+this.sid,init:this.init,started:new Date(this.started).toISOString(),timestamp:new Date(this.timestamp).toISOString(),status:this.status,errors:this.errors,did:"number"===typeof this.did||"string"===typeof this.did?""+this.did:void 0,duration:this.duration,attrs:Object(_["a"])({release:this.release,environment:this.environment,ip_address:this.ipAddress,user_agent:this.userAgent})})},t}(),b=3,w=100,x=100,k=function(){function t(t,e,n){void 0===e&&(e=new p),void 0===n&&(n=b),this._version=n,this._stack=[{}],this.getStackTop().scope=e,this.bindClient(t)}return t.prototype.isOlderThan=function(t){return this._version<t},t.prototype.bindClient=function(t){var e=this.getStackTop();e.client=t,t&&t.setupIntegrations&&t.setupIntegrations()},t.prototype.pushScope=function(){var t=p.clone(this.getScope());return this.getStack().push({client:this.getClient(),scope:t}),t},t.prototype.popScope=function(){return!(this.getStack().length<=1)&&!!this.getStack().pop()},t.prototype.withScope=function(t){var e=this.pushScope();try{t(e)}finally{this.popScope()}},t.prototype.getClient=function(){return this.getStackTop().client},t.prototype.getScope=function(){return this.getStackTop().scope},t.prototype.getStack=function(){return this._stack},t.prototype.getStackTop=function(){return this._stack[this._stack.length-1]},t.prototype.captureException=function(t,e){var n=this._lastEventId=Object(f["i"])(),r=e;if(!e){var i=void 0;try{throw new Error("Sentry syntheticException")}catch(t){i=t}r={originalException:t,syntheticException:i}}return this._invokeClient("captureException",t,Object(s["a"])(Object(s["a"])({},r),{event_id:n})),n},t.prototype.captureMessage=function(t,e,n){var r=this._lastEventId=Object(f["i"])(),i=n;if(!n){var o=void 0;try{throw new Error(t)}catch(a){o=a}i={originalException:t,syntheticException:o}}return this._invokeClient("captureMessage",t,e,Object(s["a"])(Object(s["a"])({},i),{event_id:r})),r},t.prototype.captureEvent=function(t,e){var n=this._lastEventId=Object(f["i"])();return this._invokeClient("captureEvent",t,Object(s["a"])(Object(s["a"])({},e),{event_id:n})),n},t.prototype.lastEventId=function(){return this._lastEventId},t.prototype.addBreadcrumb=function(t,e){var n=this.getStackTop(),r=n.scope,i=n.client;if(r&&i){var o=i.getOptions&&i.getOptions()||{},a=o.beforeBreadcrumb,u=void 0===a?null:a,l=o.maxBreadcrumbs,h=void 0===l?w:l;if(!(h<=0)){var p=Object(c["a"])(),d=Object(s["a"])({timestamp:p},t),m=u?Object(f["c"])((function(){return u(d,e)})):d;null!==m&&r.addBreadcrumb(m,Math.min(h,x))}}},t.prototype.setUser=function(t){var e=this.getScope();e&&e.setUser(t)},t.prototype.setTags=function(t){var e=this.getScope();e&&e.setTags(t)},t.prototype.setExtras=function(t){var e=this.getScope();e&&e.setExtras(t)},t.prototype.setTag=function(t,e){var n=this.getScope();n&&n.setTag(t,e)},t.prototype.setExtra=function(t,e){var n=this.getScope();n&&n.setExtra(t,e)},t.prototype.setContext=function(t,e){var n=this.getScope();n&&n.setContext(t,e)},t.prototype.configureScope=function(t){var e=this.getStackTop(),n=e.scope,r=e.client;n&&r&&t(n)},t.prototype.run=function(t){var e=S(this);try{t(this)}finally{S(e)}},t.prototype.getIntegration=function(t){var e=this.getClient();if(!e)return null;try{return e.getIntegration(t)}catch(n){return v["a"].warn("Cannot retrieve integration "+t.id+" from the current Hub"),null}},t.prototype.startSpan=function(t){return this._callExtensionMethod("startSpan",t)},t.prototype.startTransaction=function(t,e){return this._callExtensionMethod("startTransaction",t,e)},t.prototype.traceHeaders=function(){return this._callExtensionMethod("traceHeaders")},t.prototype.captureSession=function(t){if(void 0===t&&(t=!1),t)return this.endSession();this._sendSessionUpdate()},t.prototype.endSession=function(){var t,e,n,r,i;null===(n=null===(e=null===(t=this.getStackTop())||void 0===t?void 0:t.scope)||void 0===e?void 0:e.getSession())||void 0===n||n.close(),this._sendSessionUpdate(),null===(i=null===(r=this.getStackTop())||void 0===r?void 0:r.scope)||void 0===i||i.setSession()},t.prototype.startSession=function(t){var e=this.getStackTop(),n=e.scope,r=e.client,i=r&&r.getOptions()||{},o=i.release,a=i.environment,u=new y(Object(s["a"])(Object(s["a"])({release:o,environment:a},n&&{user:n.getUser()}),t));if(n){var c=n.getSession&&n.getSession();c&&c.status===l.Ok&&c.update({status:l.Exited}),this.endSession(),n.setSession(u)}return u},t.prototype._sendSessionUpdate=function(){var t=this.getStackTop(),e=t.scope,n=t.client;if(e){var r=e.getSession&&e.getSession();r&&n&&n.captureSession&&n.captureSession(r)}},t.prototype._invokeClient=function(t){for(var e,n=[],r=1;r<arguments.length;r++)n[r-1]=arguments[r];var i=this.getStackTop(),o=i.scope,a=i.client;a&&a[t]&&(e=a)[t].apply(e,Object(s["e"])(n,[o]))},t.prototype._callExtensionMethod=function(t){for(var e=[],n=1;n<arguments.length;n++)e[n-1]=arguments[n];var r=E(),i=r.__SENTRY__;if(i&&i.extensions&&"function"===typeof i.extensions[t])return i.extensions[t].apply(this,e);v["a"].warn("Extension method "+t+" couldn't be found, doing nothing.")},t}();function E(){var t=Object(f["e"])();return t.__SENTRY__=t.__SENTRY__||{extensions:{},hub:void 0},t}function S(t){var e=E(),n=D(e);return L(e,t),n}function C(){var t=E();return O(t)&&!D(t).isOlderThan(b)||L(t,new k),Object(g["b"])()?A(t):D(t)}function A(t){var e,n,r;try{var i=null===(r=null===(n=null===(e=E().__SENTRY__)||void 0===e?void 0:e.extensions)||void 0===n?void 0:n.domain)||void 0===r?void 0:r.active;if(!i)return D(t);if(!O(i)||D(i).isOlderThan(b)){var o=D(t).getStackTop();L(i,new k(o.client,p.clone(o.scope)))}return D(i)}catch(a){return D(t)}}function O(t){return!!(t&&t.__SENTRY__&&t.__SENTRY__.hub)}function D(t){return t&&t.__SENTRY__&&t.__SENTRY__.hub||(t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.hub=new k),t.__SENTRY__.hub}function L(t,e){return!!t&&(t.__SENTRY__=t.__SENTRY__||{},t.__SENTRY__.hub=e,!0)}var T=n("fbdd"),j=[/^Script error\.?$/,/^Javascript error: Script error\.? on line 0$/],P=function(){function t(e){void 0===e&&(e={}),this._options=e,this.name=t.id}return t.prototype.setupOnce=function(){m((function(e){var n=C();if(!n)return e;var r=n.getIntegration(t);if(r){var i=n.getClient(),o=i?i.getOptions():{},a=r._mergeOptions(o);if(r._shouldDropEvent(e,a))return null}return e}))},t.prototype._shouldDropEvent=function(t,e){return this._isSentryError(t,e)?(v["a"].warn("Event dropped due to being internal Sentry Error.\nEvent: "+Object(f["d"])(t)),!0):this._isIgnoredError(t,e)?(v["a"].warn("Event dropped due to being matched by `ignoreErrors` option.\nEvent: "+Object(f["d"])(t)),!0):this._isDeniedUrl(t,e)?(v["a"].warn("Event dropped due to being matched by `denyUrls` option.\nEvent: "+Object(f["d"])(t)+".\nUrl: "+this._getEventFilterUrl(t)),!0):!this._isAllowedUrl(t,e)&&(v["a"].warn("Event dropped due to not being matched by `allowUrls` option.\nEvent: "+Object(f["d"])(t)+".\nUrl: "+this._getEventFilterUrl(t)),!0)},t.prototype._isSentryError=function(t,e){if(!e.ignoreInternal)return!1;try{return t&&t.exception&&t.exception.values&&t.exception.values[0]&&"SentryError"===t.exception.values[0].type||!1}catch(n){return!1}},t.prototype._isIgnoredError=function(t,e){return!(!e.ignoreErrors||!e.ignoreErrors.length)&&this._getPossibleEventMessages(t).some((function(t){return e.ignoreErrors.some((function(e){return Object(T["a"])(t,e)}))}))},t.prototype._isDeniedUrl=function(t,e){if(!e.denyUrls||!e.denyUrls.length)return!1;var n=this._getEventFilterUrl(t);return!!n&&e.denyUrls.some((function(t){return Object(T["a"])(n,t)}))},t.prototype._isAllowedUrl=function(t,e){if(!e.allowUrls||!e.allowUrls.length)return!0;var n=this._getEventFilterUrl(t);return!n||e.allowUrls.some((function(t){return Object(T["a"])(n,t)}))},t.prototype._mergeOptions=function(t){return void 0===t&&(t={}),{allowUrls:Object(s["e"])(this._options.whitelistUrls||[],this._options.allowUrls||[],t.whitelistUrls||[],t.allowUrls||[]),denyUrls:Object(s["e"])(this._options.blacklistUrls||[],this._options.denyUrls||[],t.blacklistUrls||[],t.denyUrls||[]),ignoreErrors:Object(s["e"])(this._options.ignoreErrors||[],t.ignoreErrors||[],j),ignoreInternal:"undefined"===typeof this._options.ignoreInternal||this._options.ignoreInternal}},t.prototype._getPossibleEventMessages=function(t){if(t.message)return[t.message];if(t.exception)try{var e=t.exception.values&&t.exception.values[0]||{},n=e.type,r=void 0===n?"":n,i=e.value,o=void 0===i?"":i;return[""+o,r+": "+o]}catch(a){return v["a"].error("Cannot extract message for event "+Object(f["d"])(t)),[]}return[]},t.prototype._getEventFilterUrl=function(t){try{if(t.stacktrace){var e=t.stacktrace.frames;return e&&e[e.length-1].filename||null}if(t.exception){var n=t.exception.values&&t.exception.values[0].stacktrace&&t.exception.values[0].stacktrace.frames;return n&&n[n.length-1].filename||null}return null}catch(r){return v["a"].error("Cannot extract url for event "+Object(f["d"])(t)),null}},t.id="InboundFilters",t}();function M(t,e){!0===e.debug&&v["a"].enable();var n=C(),r=new t(e);n.bindClient(r)}var B=n("a518");function R(){if(!("fetch"in Object(f["e"])()))return!1;try{return new Headers,new Request(""),new Response,!0}catch(t){return!1}}function I(t){return t&&/^function fetch\(\)\s+\{\s+\[native code\]\s+\}$/.test(t.toString())}function F(){if(!R())return!1;var t=Object(f["e"])();if(I(t.fetch))return!0;var e=!1,n=t.document;if(n&&"function"===typeof n.createElement)try{var r=n.createElement("iframe");r.hidden=!0,n.head.appendChild(r),r.contentWindow&&r.contentWindow.fetch&&(e=I(r.contentWindow.fetch)),n.head.removeChild(r)}catch(i){v["a"].warn("Could not create sandbox iframe for pure fetch check, bailing to window.fetch: ",i)}return e}function z(){if(!R())return!1;try{return new Request("_",{referrerPolicy:"origin"}),!0}catch(t){return!1}}function N(){var t=Object(f["e"])(),e=t.chrome,n=e&&e.app&&e.app.runtime,r="history"in t&&!!t.history.pushState&&!!t.history.replaceState;return!n&&r}var U,Z=Object(f["e"])(),$={},H={};function q(t){if(!H[t])switch(H[t]=!0,t){case"console":W();break;case"dom":at();break;case"xhr":J();break;case"fetch":Y();break;case"history":Q();break;case"error":ut();break;case"unhandledrejection":lt();break;default:v["a"].warn("unknown instrumentation type:",t)}}function V(t){t&&"string"===typeof t.type&&"function"===typeof t.callback&&($[t.type]=$[t.type]||[],$[t.type].push(t.callback),q(t.type))}function G(t,e){var n,r;if(t&&$[t])try{for(var i=Object(s["f"])($[t]||[]),o=i.next();!o.done;o=i.next()){var a=o.value;try{a(e)}catch(u){v["a"].error("Error while triggering instrumentation handler.\nType: "+t+"\nName: "+Object(B["a"])(a)+"\nError: "+u)}}}catch(c){n={error:c}}finally{try{o&&!o.done&&(r=i.return)&&r.call(i)}finally{if(n)throw n.error}}}function W(){"console"in Z&&["debug","info","warn","error","log","assert"].forEach((function(t){t in Z.console&&Object(_["c"])(Z.console,t,(function(e){return function(){for(var n=[],r=0;r<arguments.length;r++)n[r]=arguments[r];G("console",{args:n,level:t}),e&&Function.prototype.apply.call(e,Z.console,n)}}))}))}function Y(){F()&&Object(_["c"])(Z,"fetch",(function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r={args:e,fetchData:{method:K(e),url:X(e)},startTimestamp:Date.now()};return G("fetch",Object(s["a"])({},r)),t.apply(Z,e).then((function(t){return G("fetch",Object(s["a"])(Object(s["a"])({},r),{endTimestamp:Date.now(),response:t})),t}),(function(t){throw G("fetch",Object(s["a"])(Object(s["a"])({},r),{endTimestamp:Date.now(),error:t})),t}))}}))}function K(t){return void 0===t&&(t=[]),"Request"in Z&&Object(u["g"])(t[0],Request)&&t[0].method?String(t[0].method).toUpperCase():t[1]&&t[1].method?String(t[1].method).toUpperCase():"GET"}function X(t){return void 0===t&&(t=[]),"string"===typeof t[0]?t[0]:"Request"in Z&&Object(u["g"])(t[0],Request)?t[0].url:String(t[0])}function J(){if("XMLHttpRequest"in Z){var t=[],e=[],n=XMLHttpRequest.prototype;Object(_["c"])(n,"open",(function(n){return function(){for(var r=[],i=0;i<arguments.length;i++)r[i]=arguments[i];var o=this,a=r[1];o.__sentry_xhr__={method:Object(u["k"])(r[0])?r[0].toUpperCase():r[0],url:r[1]},Object(u["k"])(a)&&"POST"===o.__sentry_xhr__.method&&a.match(/sentry_key/)&&(o.__sentry_own_request__=!0);var s=function(){if(4===o.readyState){try{o.__sentry_xhr__&&(o.__sentry_xhr__.status_code=o.status)}catch(a){}try{var n=t.indexOf(o);if(-1!==n){t.splice(n);var i=e.splice(n)[0];o.__sentry_xhr__&&void 0!==i[0]&&(o.__sentry_xhr__.body=i[0])}}catch(a){}G("xhr",{args:r,endTimestamp:Date.now(),startTimestamp:Date.now(),xhr:o})}};return"onreadystatechange"in o&&"function"===typeof o.onreadystatechange?Object(_["c"])(o,"onreadystatechange",(function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];return s(),t.apply(o,e)}})):o.addEventListener("readystatechange",s),n.apply(o,r)}})),Object(_["c"])(n,"send",(function(n){return function(){for(var r=[],i=0;i<arguments.length;i++)r[i]=arguments[i];return t.push(this),e.push(r),G("xhr",{args:r,startTimestamp:Date.now(),xhr:this}),n.apply(this,r)}}))}}function Q(){if(N()){var t=Z.onpopstate;Z.onpopstate=function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=Z.location.href,i=U;if(U=r,G("history",{from:i,to:r}),t)return t.apply(this,e)},Object(_["c"])(Z.history,"pushState",e),Object(_["c"])(Z.history,"replaceState",e)}function e(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=e.length>2?e[2]:void 0;if(r){var i=U,o=String(r);U=o,G("history",{from:i,to:o})}return t.apply(this,e)}}}var tt,et,nt=1e3;function rt(t,e){if(!t)return!0;if(t.type!==e.type)return!0;try{if(t.target!==e.target)return!0}catch(n){}return!1}function it(t){if("keypress"!==t.type)return!1;try{var e=t.target;if(!e||!e.tagName)return!0;if("INPUT"===e.tagName||"TEXTAREA"===e.tagName||e.isContentEditable)return!1}catch(n){}return!0}function ot(t,e){return void 0===e&&(e=!1),function(n){if(n&&et!==n&&!it(n)){var r="keypress"===n.type?"input":n.type;(void 0===tt||rt(et,n))&&(t({event:n,name:r,global:e}),et=n),clearTimeout(tt),tt=Z.setTimeout((function(){tt=void 0}),nt)}}}function at(){if("document"in Z){var t=G.bind(null,"dom"),e=ot(t,!0);Z.document.addEventListener("click",e,!1),Z.document.addEventListener("keypress",e,!1),["EventTarget","Node"].forEach((function(e){var n=Z[e]&&Z[e].prototype;n&&n.hasOwnProperty&&n.hasOwnProperty("addEventListener")&&(Object(_["c"])(n,"addEventListener",(function(e){return function(n,r,i){if("click"===n||"keypress"==n)try{var o=this,a=o.__sentry_instrumentation_handlers__=o.__sentry_instrumentation_handlers__||{},s=a[n]=a[n]||{refCount:0};if(!s.handler){var u=ot(t);s.handler=u,e.call(this,n,u,i)}s.refCount+=1}catch(c){}return e.call(this,n,r,i)}})),Object(_["c"])(n,"removeEventListener",(function(t){return function(e,n,r){if("click"===e||"keypress"==e)try{var i=this,o=i.__sentry_instrumentation_handlers__||{},a=o[e];a&&(a.refCount-=1,a.refCount<=0&&(t.call(this,e,a.handler,r),a.handler=void 0,delete o[e]),0===Object.keys(o).length&&delete i.__sentry_instrumentation_handlers__)}catch(s){}return t.call(this,e,n,r)}})))}))}}var st=null;function ut(){st=Z.onerror,Z.onerror=function(t,e,n,r,i){return G("error",{column:r,error:i,line:n,msg:t,url:e}),!!st&&st.apply(this,arguments)}}var ct=null;function lt(){ct=Z.onunhandledrejection,Z.onunhandledrejection=function(t){return G("unhandledrejection",t),!ct||ct.apply(this,arguments)}}var ht="6.2.3",ft=Object.setPrototypeOf||({__proto__:[]}instanceof Array?pt:dt);function pt(t,e){return t.__proto__=e,t}function dt(t,e){for(var n in e)t.hasOwnProperty(n)||(t[n]=e[n]);return t}var mt=function(t){function e(e){var n=this.constructor,r=t.call(this,e)||this;return r.message=e,r.name=n.prototype.constructor.name,ft(r,n.prototype),r}return Object(s["b"])(e,t),e}(Error),vt=/^(?:(\w+):)\/\/(?:(\w+)(?::(\w+))?@)([\w.-]+)(?::(\d+))?\/(.+)/,gt="Invalid Dsn",_t=function(){function t(t){"string"===typeof t?this._fromString(t):this._fromComponents(t),this._validate()}return t.prototype.toString=function(t){void 0===t&&(t=!1);var e=this,n=e.host,r=e.path,i=e.pass,o=e.port,a=e.projectId,s=e.protocol,u=e.publicKey;return s+"://"+u+(t&&i?":"+i:"")+"@"+n+(o?":"+o:"")+"/"+(r?r+"/":r)+a},t.prototype._fromString=function(t){var e=vt.exec(t);if(!e)throw new mt(gt);var n=Object(s["c"])(e.slice(1),6),r=n[0],i=n[1],o=n[2],a=void 0===o?"":o,u=n[3],c=n[4],l=void 0===c?"":c,h=n[5],f="",p=h,d=p.split("/");if(d.length>1&&(f=d.slice(0,-1).join("/"),p=d.pop()),p){var m=p.match(/^\d+/);m&&(p=m[0])}this._fromComponents({host:u,pass:a,path:f,projectId:p,port:l,protocol:r,publicKey:i})},t.prototype._fromComponents=function(t){"user"in t&&!("publicKey"in t)&&(t.publicKey=t.user),this.user=t.publicKey||"",this.protocol=t.protocol,this.publicKey=t.publicKey||"",this.pass=t.pass||"",this.host=t.host,this.port=t.port||"",this.path=t.path||"",this.projectId=t.projectId},t.prototype._validate=function(){var t=this;if(["protocol","publicKey","host","projectId"].forEach((function(e){if(!t[e])throw new mt(gt+": "+e+" missing")})),!this.projectId.match(/^\d+$/))throw new mt(gt+": Invalid projectId "+this.projectId);if("http"!==this.protocol&&"https"!==this.protocol)throw new mt(gt+": Invalid protocol "+this.protocol);if(this.port&&isNaN(parseInt(this.port,10)))throw new mt(gt+": Invalid port "+this.port)},t}(),yt=[];function bt(t){var e=t.defaultIntegrations&&Object(s["e"])(t.defaultIntegrations)||[],n=t.integrations,r=[];if(Array.isArray(n)){var i=n.map((function(t){return t.name})),o=[];e.forEach((function(t){-1===i.indexOf(t.name)&&-1===o.indexOf(t.name)&&(r.push(t),o.push(t.name))})),n.forEach((function(t){-1===o.indexOf(t.name)&&(r.push(t),o.push(t.name))}))}else"function"===typeof n?(r=n(e),r=Array.isArray(r)?r:[r]):r=Object(s["e"])(e);var a=r.map((function(t){return t.name})),u="Debug";return-1!==a.indexOf(u)&&r.push.apply(r,Object(s["e"])(r.splice(a.indexOf(u),1))),r}function wt(t){-1===yt.indexOf(t.name)&&(t.setupOnce(m,C),yt.push(t.name),v["a"].log("Integration installed: "+t.name))}function xt(t){var e={};return bt(t).forEach((function(t){e[t.name]=t,wt(t)})),e}var kt,Et=function(){function t(t,e){this._integrations={},this._processing=0,this._backend=new t(e),this._options=e,e.dsn&&(this._dsn=new _t(e.dsn))}return t.prototype.captureException=function(t,e,n){var r=this,i=e&&e.event_id;return this._process(this._getBackend().eventFromException(t,e).then((function(t){return r._captureEvent(t,e,n)})).then((function(t){i=t}))),i},t.prototype.captureMessage=function(t,e,n,r){var i=this,o=n&&n.event_id,a=Object(u["i"])(t)?this._getBackend().eventFromMessage(String(t),e,n):this._getBackend().eventFromException(t,n);return this._process(a.then((function(t){return i._captureEvent(t,n,r)})).then((function(t){o=t}))),o},t.prototype.captureEvent=function(t,e,n){var r=e&&e.event_id;return this._process(this._captureEvent(t,e,n).then((function(t){r=t}))),r},t.prototype.captureSession=function(t){t.release?(this._sendSession(t),t.update({init:!1})):v["a"].warn("Discarded session because of missing release")},t.prototype.getDsn=function(){return this._dsn},t.prototype.getOptions=function(){return this._options},t.prototype.flush=function(t){var e=this;return this._isClientProcessing(t).then((function(n){return e._getBackend().getTransport().close(t).then((function(t){return n&&t}))}))},t.prototype.close=function(t){var e=this;return this.flush(t).then((function(t){return e.getOptions().enabled=!1,t}))},t.prototype.setupIntegrations=function(){this._isEnabled()&&(this._integrations=xt(this._options))},t.prototype.getIntegration=function(t){try{return this._integrations[t.id]||null}catch(e){return v["a"].warn("Cannot retrieve integration "+t.id+" from the current Client"),null}},t.prototype._updateSessionFromEvent=function(t,e){var n,r,i,o=!1,a=!1,u=e.exception&&e.exception.values;if(u){a=!0;try{for(var c=Object(s["f"])(u),h=c.next();!h.done;h=c.next()){var f=h.value,p=f.mechanism;if(p&&!1===p.handled){o=!0;break}}}catch(g){n={error:g}}finally{try{h&&!h.done&&(r=c.return)&&r.call(c)}finally{if(n)throw n.error}}}var d=e.user;if(!t.userAgent){var m=e.request?e.request.headers:{};for(var v in m)if("user-agent"===v.toLowerCase()){i=m[v];break}}t.update(Object(s["a"])(Object(s["a"])({},o&&{status:l.Crashed}),{user:d,userAgent:i,errors:t.errors+Number(a||o)})),this.captureSession(t)},t.prototype._sendSession=function(t){this._getBackend().sendSession(t)},t.prototype._isClientProcessing=function(t){var e=this;return new h((function(n){var r=0,i=1,o=setInterval((function(){0==e._processing?(clearInterval(o),n(!0)):(r+=i,t&&r>=t&&(clearInterval(o),n(!1)))}),i)}))},t.prototype._getBackend=function(){return this._backend},t.prototype._isEnabled=function(){return!1!==this.getOptions().enabled&&void 0!==this._dsn},t.prototype._prepareEvent=function(t,e,n){var r=this,i=this.getOptions().normalizeDepth,o=void 0===i?3:i,a=Object(s["a"])(Object(s["a"])({},t),{event_id:t.event_id||(n&&n.event_id?n.event_id:Object(f["i"])()),timestamp:t.timestamp||Object(c["a"])()});this._applyClientOptions(a),this._applyIntegrationsMetadata(a);var u=e;n&&n.captureContext&&(u=p.clone(u).update(n.captureContext));var l=h.resolve(a);return u&&(l=u.applyToEvent(a,n)),l.then((function(t){return"number"===typeof o&&o>0?r._normalizeEvent(t,o):t}))},t.prototype._normalizeEvent=function(t,e){if(!t)return null;var n=Object(s["a"])(Object(s["a"])(Object(s["a"])(Object(s["a"])(Object(s["a"])({},t),t.breadcrumbs&&{breadcrumbs:t.breadcrumbs.map((function(t){return Object(s["a"])(Object(s["a"])({},t),t.data&&{data:Object(_["d"])(t.data,e)})}))}),t.user&&{user:Object(_["d"])(t.user,e)}),t.contexts&&{contexts:Object(_["d"])(t.contexts,e)}),t.extra&&{extra:Object(_["d"])(t.extra,e)});return t.contexts&&t.contexts.trace&&(n.contexts.trace=t.contexts.trace),n},t.prototype._applyClientOptions=function(t){var e=this.getOptions(),n=e.environment,r=e.release,i=e.dist,o=e.maxValueLength,a=void 0===o?250:o;"environment"in t||(t.environment="environment"in e?n:"production"),void 0===t.release&&void 0!==r&&(t.release=r),void 0===t.dist&&void 0!==i&&(t.dist=i),t.message&&(t.message=Object(T["d"])(t.message,a));var s=t.exception&&t.exception.values&&t.exception.values[0];s&&s.value&&(s.value=Object(T["d"])(s.value,a));var u=t.request;u&&u.url&&(u.url=Object(T["d"])(u.url,a))},t.prototype._applyIntegrationsMetadata=function(t){var e=t.sdk,n=Object.keys(this._integrations);e&&n.length>0&&(e.integrations=n)},t.prototype._sendEvent=function(t){this._getBackend().sendEvent(t)},t.prototype._captureEvent=function(t,e,n){return this._processEvent(t,e,n).then((function(t){return t.event_id}),(function(t){v["a"].error(t)}))},t.prototype._processEvent=function(t,e,n){var r=this,i=this.getOptions(),o=i.beforeSend,a=i.sampleRate;if(!this._isEnabled())return h.reject(new mt("SDK not enabled, will not send event."));var s="transaction"===t.type;return!s&&"number"===typeof a&&Math.random()>a?h.reject(new mt("Discarding event because it's not included in the random sample (sampling rate = "+a+")")):this._prepareEvent(t,n,e).then((function(t){if(null===t)throw new mt("An event processor returned null, will not send event.");var n=e&&e.data&&!0===e.data.__sentry__;if(n||s||!o)return t;var r=o(t,e);if("undefined"===typeof r)throw new mt("`beforeSend` method has to return `null` or a valid event.");return Object(u["m"])(r)?r.then((function(t){return t}),(function(t){throw new mt("beforeSend rejected with "+t)})):r})).then((function(t){if(null===t)throw new mt("`beforeSend` returned `null`, will not send event.");var e=n&&n.getSession&&n.getSession();return!s&&e&&r._updateSessionFromEvent(e,t),r._sendEvent(t),t})).then(null,(function(t){if(t instanceof mt)throw t;throw r.captureException(t,{data:{__sentry__:!0},originalException:t}),new mt("Event processing pipeline threw an error, original event will not be sent. Details have been sent as a new event.\nReason: "+t)}))},t.prototype._process=function(t){var e=this;this._processing+=1,t.then((function(t){return e._processing-=1,t}),(function(t){return e._processing-=1,t}))},t}();(function(t){t["Unknown"]="unknown",t["Skipped"]="skipped",t["Success"]="success",t["RateLimit"]="rate_limit",t["Invalid"]="invalid",t["Failed"]="failed"})(kt||(kt={})),function(t){function e(e){return e>=200&&e<300?t.Success:429===e?t.RateLimit:e>=400&&e<500?t.Invalid:e>=500?t.Failed:t.Unknown}t.fromHttpCode=e}(kt||(kt={}));var St,Ct=function(){function t(){}return t.prototype.sendEvent=function(t){return h.resolve({reason:"NoopTransport: Event has been skipped because no Dsn is configured.",status:kt.Skipped})},t.prototype.close=function(t){return h.resolve(!0)},t}(),At=function(){function t(t){this._options=t,this._options.dsn||v["a"].warn("No DSN provided, backend will not do anything."),this._transport=this._setupTransport()}return t.prototype.eventFromException=function(t,e){throw new mt("Backend has to implement `eventFromException` method")},t.prototype.eventFromMessage=function(t,e,n){throw new mt("Backend has to implement `eventFromMessage` method")},t.prototype.sendEvent=function(t){this._transport.sendEvent(t).then(null,(function(t){v["a"].error("Error while sending event: "+t)}))},t.prototype.sendSession=function(t){this._transport.sendSession?this._transport.sendSession(t).then(null,(function(t){v["a"].error("Error while sending session: "+t)})):v["a"].warn("Dropping session because custom transport doesn't implement sendSession")},t.prototype.getTransport=function(){return this._transport},t.prototype._setupTransport=function(){return new Ct},t}();(function(t){t["Fatal"]="fatal",t["Error"]="error",t["Warning"]="warning",t["Log"]="log",t["Info"]="info",t["Debug"]="debug",t["Critical"]="critical"})(St||(St={})),function(t){function e(e){switch(e){case"debug":return t.Debug;case"info":return t.Info;case"warn":case"warning":return t.Warning;case"error":return t.Error;case"fatal":return t.Fatal;case"critical":return t.Critical;case"log":default:return t.Log}}t.fromString=e}(St||(St={}));var Ot="?",Dt=/^\s*at (?:(.*?) ?\()?((?:file|https?|blob|chrome-extension|address|native|eval|webpack|<anonymous>|[-a-z]+:|.*bundle|\/).*?)(?::(\d+))?(?::(\d+))?\)?\s*$/i,Lt=/^\s*(.*?)(?:\((.*?)\))?(?:^|@)?((?:file|https?|blob|chrome|webpack|resource|moz-extension|capacitor).*?:\/.*?|\[native code\]|[^@]*(?:bundle|\d+\.js)|\/[\w\-. /=]+)(?::(\d+))?(?::(\d+))?\s*$/i,Tt=/^\s*at (?:((?:\[object object\])?.+) )?\(?((?:file|ms-appx|https?|webpack|blob):.*?):(\d+)(?::(\d+))?\)?\s*$/i,jt=/(\S+) line (\d+)(?: > eval line \d+)* > eval/i,Pt=/\((\S*)(?::(\d+))(?::(\d+))\)/,Mt=/Minified React error #\d+;/i;function Bt(t){var e=null,n=0;t&&("number"===typeof t.framesToPop?n=t.framesToPop:Mt.test(t.message)&&(n=1));try{if(e=It(t),e)return Ft(e,n)}catch(r){}try{if(e=Rt(t),e)return Ft(e,n)}catch(r){}return{message:zt(t),name:t&&t.name,stack:[],failed:!0}}function Rt(t){if(!t||!t.stack)return null;for(var e,n,r,i,o=[],a=t.stack.split("\n"),s=0;s<a.length;++s){if(r=Dt.exec(a[s])){var u=r[2]&&0===r[2].indexOf("native");e=r[2]&&0===r[2].indexOf("eval"),e&&(n=Pt.exec(r[2]))&&(r[2]=n[1],r[3]=n[2],r[4]=n[3]),i={url:r[2]&&0===r[2].indexOf("address at ")?r[2].substr("address at ".length):r[2],func:r[1]||Ot,args:u?[r[2]]:[],line:r[3]?+r[3]:null,column:r[4]?+r[4]:null}}else if(r=Tt.exec(a[s]))i={url:r[2],func:r[1]||Ot,args:[],line:+r[3],column:r[4]?+r[4]:null};else{if(!(r=Lt.exec(a[s])))continue;e=r[3]&&r[3].indexOf(" > eval")>-1,e&&(n=jt.exec(r[3]))?(r[1]=r[1]||"eval",r[3]=n[1],r[4]=n[2],r[5]=""):0!==s||r[5]||void 0===t.columnNumber||(o[0].column=t.columnNumber+1),i={url:r[3],func:r[1]||Ot,args:r[2]?r[2].split(","):[],line:r[4]?+r[4]:null,column:r[5]?+r[5]:null}}!i.func&&i.line&&(i.func=Ot),o.push(i)}return o.length?{message:zt(t),name:t.name,stack:o}:null}function It(t){if(!t||!t.stacktrace)return null;for(var e,n=t.stacktrace,r=/ line (\d+).*script (?:in )?(\S+)(?:: in function (\S+))?$/i,i=/ line (\d+), column (\d+)\s*(?:in (?:<anonymous function: ([^>]+)>|([^)]+))\((.*)\))? in (.*):\s*$/i,o=n.split("\n"),a=[],s=0;s<o.length;s+=2){var u=null;(e=r.exec(o[s]))?u={url:e[2],func:e[3],args:[],line:+e[1],column:null}:(e=i.exec(o[s]))&&(u={url:e[6],func:e[3]||e[4],args:e[5]?e[5].split(","):[],line:+e[1],column:+e[2]}),u&&(!u.func&&u.line&&(u.func=Ot),a.push(u))}return a.length?{message:zt(t),name:t.name,stack:a}:null}function Ft(t,e){try{return Object(s["a"])(Object(s["a"])({},t),{stack:t.stack.slice(e)})}catch(n){return t}}function zt(t){var e=t&&t.message;return e?e.error&&"string"===typeof e.error.message?e.error.message:e:"No error message"}var Nt=50;function Ut(t){var e=Ht(t.stack),n={type:t.name,value:t.message};return e&&e.length&&(n.stacktrace={frames:e}),void 0===n.type&&""===n.value&&(n.value="Unrecoverable error caught"),n}function Zt(t,e,n){var r={exception:{values:[{type:Object(u["f"])(t)?t.constructor.name:n?"UnhandledRejection":"Error",value:"Non-Error "+(n?"promise rejection":"exception")+" captured with keys: "+Object(_["b"])(t)}]},extra:{__serialized__:Object(_["e"])(t)}};if(e){var i=Bt(e),o=Ht(i.stack);r.stacktrace={frames:o}}return r}function $t(t){var e=Ut(t);return{exception:{values:[e]}}}function Ht(t){if(!t||!t.length)return[];var e=t,n=e[0].func||"",r=e[e.length-1].func||"";return-1===n.indexOf("captureMessage")&&-1===n.indexOf("captureException")||(e=e.slice(1)),-1!==r.indexOf("sentryWrapped")&&(e=e.slice(0,-1)),e.slice(0,Nt).map((function(t){return{colno:null===t.column?void 0:t.column,filename:t.url||e[0].url,function:t.func||"?",in_app:!0,lineno:null===t.line?void 0:t.line}})).reverse()}function qt(t,e,n){var r=n&&n.syntheticException||void 0,i=Gt(e,r,{attachStacktrace:t.attachStacktrace});return Object(f["a"])(i,{handled:!0,type:"generic"}),i.level=St.Error,n&&n.event_id&&(i.event_id=n.event_id),h.resolve(i)}function Vt(t,e,n,r){void 0===n&&(n=St.Info);var i=r&&r.syntheticException||void 0,o=Wt(e,i,{attachStacktrace:t.attachStacktrace});return o.level=n,r&&r.event_id&&(o.event_id=r.event_id),h.resolve(o)}function Gt(t,e,n){var r;if(void 0===n&&(n={}),Object(u["e"])(t)&&t.error){var i=t;return t=i.error,r=$t(Bt(t)),r}if(Object(u["a"])(t)||Object(u["b"])(t)){var o=t,a=o.name||(Object(u["a"])(o)?"DOMError":"DOMException"),c=o.message?a+": "+o.message:a;return r=Wt(c,e,n),Object(f["b"])(r,c),"code"in o&&(r.tags=Object(s["a"])(Object(s["a"])({},r.tags),{"DOMException.code":""+o.code})),r}if(Object(u["d"])(t))return r=$t(Bt(t)),r;if(Object(u["h"])(t)||Object(u["f"])(t)){var l=t;return r=Zt(l,e,n.rejection),Object(f["a"])(r,{synthetic:!0}),r}return r=Wt(t,e,n),Object(f["b"])(r,""+t,void 0),Object(f["a"])(r,{synthetic:!0}),r}function Wt(t,e,n){void 0===n&&(n={});var r={message:t};if(n.attachStacktrace&&e){var i=Bt(e),o=Ht(i.stack);r.stacktrace={frames:o}}return r}function Yt(t){if(t.metadata&&t.metadata.sdk){var e=t.metadata.sdk,n=e.name,r=e.version;return{name:n,version:r}}}function Kt(t,e){return e?(t.sdk=t.sdk||{name:e.name,version:e.version},t.sdk.name=t.sdk.name||e.name,t.sdk.version=t.sdk.version||e.version,t.sdk.integrations=Object(s["e"])(t.sdk.integrations||[],e.integrations||[]),t.sdk.packages=Object(s["e"])(t.sdk.packages||[],e.packages||[]),t):t}function Xt(t,e){var n=Yt(e),r=JSON.stringify(Object(s["a"])({sent_at:(new Date).toISOString()},n&&{sdk:n})),i=JSON.stringify({type:"session"});return{body:r+"\n"+i+"\n"+JSON.stringify(t),type:"session",url:e.getEnvelopeEndpointWithUrlEncodedAuth()}}function Jt(t,e){var n=Yt(e),r=t.type||"event",i="transaction"===r,o=t.debug_meta||{},a=o.transactionSampling,u=Object(s["d"])(o,["transactionSampling"]),c=a||{},l=c.method,h=c.rate;0===Object.keys(u).length?delete t.debug_meta:t.debug_meta=u;var f={body:JSON.stringify(n?Kt(t,e.metadata.sdk):t),type:r,url:i?e.getEnvelopeEndpointWithUrlEncodedAuth():e.getStoreEndpointWithUrlEncodedAuth()};if(i){var p=JSON.stringify(Object(s["a"])({event_id:t.event_id,sent_at:(new Date).toISOString()},n&&{sdk:n})),d=JSON.stringify({type:t.type,sample_rates:[{id:l,rate:h}]}),m=p+"\n"+d+"\n"+f.body;f.body=m}return f}var Qt="7",te=function(){function t(t,e){void 0===e&&(e={}),this.dsn=t,this._dsnObject=new _t(t),this.metadata=e}return t.prototype.getDsn=function(){return this._dsnObject},t.prototype.getBaseApiEndpoint=function(){var t=this._dsnObject,e=t.protocol?t.protocol+":":"",n=t.port?":"+t.port:"";return e+"//"+t.host+n+(t.path?"/"+t.path:"")+"/api/"},t.prototype.getStoreEndpoint=function(){return this._getIngestEndpoint("store")},t.prototype.getStoreEndpointWithUrlEncodedAuth=function(){return this.getStoreEndpoint()+"?"+this._encodedAuth()},t.prototype.getEnvelopeEndpointWithUrlEncodedAuth=function(){return this._getEnvelopeEndpoint()+"?"+this._encodedAuth()},t.prototype.getStoreEndpointPath=function(){var t=this._dsnObject;return(t.path?"/"+t.path:"")+"/api/"+t.projectId+"/store/"},t.prototype.getRequestHeaders=function(t,e){var n=this._dsnObject,r=["Sentry sentry_version="+Qt];return r.push("sentry_client="+t+"/"+e),r.push("sentry_key="+n.publicKey),n.pass&&r.push("sentry_secret="+n.pass),{"Content-Type":"application/json","X-Sentry-Auth":r.join(", ")}},t.prototype.getReportDialogEndpoint=function(t){void 0===t&&(t={});var e=this._dsnObject,n=this.getBaseApiEndpoint()+"embed/error-page/",r=[];for(var i in r.push("dsn="+e.toString()),t)if("dsn"!==i)if("user"===i){if(!t.user)continue;t.user.name&&r.push("name="+encodeURIComponent(t.user.name)),t.user.email&&r.push("email="+encodeURIComponent(t.user.email))}else r.push(encodeURIComponent(i)+"="+encodeURIComponent(t[i]));return r.length?n+"?"+r.join("&"):n},t.prototype._getEnvelopeEndpoint=function(){return this._getIngestEndpoint("envelope")},t.prototype._getIngestEndpoint=function(t){var e=this.getBaseApiEndpoint(),n=this._dsnObject;return""+e+n.projectId+"/"+t+"/"},t.prototype._encodedAuth=function(){var t=this._dsnObject,e={sentry_key:t.publicKey,sentry_version:Qt};return Object(_["f"])(e)},t}(),ee=function(){function t(t){this._limit=t,this._buffer=[]}return t.prototype.isReady=function(){return void 0===this._limit||this.length()<this._limit},t.prototype.add=function(t){var e=this;return this.isReady()?(-1===this._buffer.indexOf(t)&&this._buffer.push(t),t.then((function(){return e.remove(t)})).then(null,(function(){return e.remove(t).then(null,(function(){}))})),t):h.reject(new mt("Not adding Promise due to buffer limit reached."))},t.prototype.remove=function(t){var e=this._buffer.splice(this._buffer.indexOf(t),1)[0];return e},t.prototype.length=function(){return this._buffer.length},t.prototype.drain=function(t){var e=this;return new h((function(n){var r=setTimeout((function(){t&&t>0&&n(!1)}),t);h.all(e._buffer).then((function(){clearTimeout(r),n(!0)})).then(null,(function(){n(!0)}))}))},t}(),ne=function(){function t(t){this.options=t,this._buffer=new ee(30),this._rateLimits={},this._api=new te(t.dsn,t._metadata),this.url=this._api.getStoreEndpointWithUrlEncodedAuth()}return t.prototype.sendEvent=function(t){throw new mt("Transport Class has to implement `sendEvent` method")},t.prototype.close=function(t){return this._buffer.drain(t)},t.prototype._handleResponse=function(t){var e=t.requestType,n=t.response,r=t.headers,i=t.resolve,o=t.reject,a=kt.fromHttpCode(n.status),s=this._handleRateLimit(r);s&&v["a"].warn("Too many requests, backing off until: "+this._disabledUntil(e)),a!==kt.Success?o(n):i({status:a})},t.prototype._disabledUntil=function(t){return this._rateLimits[t]||this._rateLimits.all},t.prototype._isRateLimited=function(t){return this._disabledUntil(t)>new Date(Date.now())},t.prototype._handleRateLimit=function(t){var e,n,r,i,o=Date.now(),a=t["x-sentry-rate-limits"],u=t["retry-after"];if(a){try{for(var c=Object(s["f"])(a.trim().split(",")),l=c.next();!l.done;l=c.next()){var h=l.value,p=h.split(":",2),d=parseInt(p[0],10),m=1e3*(isNaN(d)?60:d);try{for(var v=(r=void 0,Object(s["f"])(p[1].split(";"))),g=v.next();!g.done;g=v.next()){var _=g.value;this._rateLimits[_||"all"]=new Date(o+m)}}catch(y){r={error:y}}finally{try{g&&!g.done&&(i=v.return)&&i.call(v)}finally{if(r)throw r.error}}}}catch(b){e={error:b}}finally{try{l&&!l.done&&(n=c.return)&&n.call(c)}finally{if(e)throw e.error}}return!0}return!!u&&(this._rateLimits.all=new Date(o+Object(f["g"])(o,u)),!0)},t}();function re(){var t,e,n=Object(f["e"])(),r=n.document;if("function"===typeof(null===(t=r)||void 0===t?void 0:t.createElement))try{var i=r.createElement("iframe");if(i.hidden=!0,r.head.appendChild(i),null===(e=i.contentWindow)||void 0===e?void 0:e.fetch)return i.contentWindow.fetch.bind(n);r.head.removeChild(i)}catch(o){v["a"].warn("Could not create sandbox iframe for pure fetch check, bailing to window.fetch: ",o)}return n.fetch.bind(n)}var ie=function(t){function e(e,n){void 0===n&&(n=re());var r=t.call(this,e)||this;return r._fetch=n,r}return Object(s["b"])(e,t),e.prototype.sendEvent=function(t){return this._sendRequest(Jt(t,this._api),t)},e.prototype.sendSession=function(t){return this._sendRequest(Xt(t,this._api),t)},e.prototype._sendRequest=function(t,e){var n=this;if(this._isRateLimited(t.type))return Promise.reject({event:e,type:t.type,reason:"Transport locked till "+this._disabledUntil(t.type)+" due to too many requests.",status:429});var r={body:t.body,method:"POST",referrerPolicy:z()?"origin":""};return void 0!==this.options.fetchParameters&&Object.assign(r,this.options.fetchParameters),void 0!==this.options.headers&&(r.headers=this.options.headers),this._buffer.add(new h((function(e,i){n._fetch(t.url,r).then((function(r){var o={"x-sentry-rate-limits":r.headers.get("X-Sentry-Rate-Limits"),"retry-after":r.headers.get("Retry-After")};n._handleResponse({requestType:t.type,response:r,headers:o,resolve:e,reject:i})})).catch(i)})))},e}(ne),oe=function(t){function e(){return null!==t&&t.apply(this,arguments)||this}return Object(s["b"])(e,t),e.prototype.sendEvent=function(t){return this._sendRequest(Jt(t,this._api),t)},e.prototype.sendSession=function(t){return this._sendRequest(Xt(t,this._api),t)},e.prototype._sendRequest=function(t,e){var n=this;return this._isRateLimited(t.type)?Promise.reject({event:e,type:t.type,reason:"Transport locked till "+this._disabledUntil(t.type)+" due to too many requests.",status:429}):this._buffer.add(new h((function(e,r){var i=new XMLHttpRequest;for(var o in i.onreadystatechange=function(){if(4===i.readyState){var o={"x-sentry-rate-limits":i.getResponseHeader("X-Sentry-Rate-Limits"),"retry-after":i.getResponseHeader("Retry-After")};n._handleResponse({requestType:t.type,response:i,headers:o,resolve:e,reject:r})}},i.open("POST",t.url),n.options.headers)n.options.headers.hasOwnProperty(o)&&i.setRequestHeader(o,n.options.headers[o]);i.send(t.body)})))},e}(ne),ae=function(t){function e(){return null!==t&&t.apply(this,arguments)||this}return Object(s["b"])(e,t),e.prototype.eventFromException=function(t,e){return qt(this._options,t,e)},e.prototype.eventFromMessage=function(t,e,n){return void 0===e&&(e=St.Info),Vt(this._options,t,e,n)},e.prototype._setupTransport=function(){if(!this._options.dsn)return t.prototype._setupTransport.call(this);var e=Object(s["a"])(Object(s["a"])({},this._options.transportOptions),{dsn:this._options.dsn,_metadata:this._options._metadata});return this._options.transport?new this._options.transport(e):R()?new ie(e):new oe(e)},e}(At);function se(t){for(var e=[],n=1;n<arguments.length;n++)e[n-1]=arguments[n];var r=C();if(r&&r[t])return r[t].apply(r,Object(s["e"])(e));throw new Error("No hub defined or "+t+" was not found on the hub, please open a bug report.")}function ue(t,e){var n;try{throw new Error("Sentry syntheticException")}catch(t){n=t}return se("captureException",t,{captureContext:e,originalException:t,syntheticException:n})}function ce(t){se("withScope",t)}var le=0;function he(){return le>0}function fe(){le+=1,setTimeout((function(){le-=1}))}function pe(t,e,n){if(void 0===e&&(e={}),"function"!==typeof t)return t;try{if(t.__sentry__)return t;if(t.__sentry_wrapped__)return t.__sentry_wrapped__}catch(a){return t}var r=function(){var r=Array.prototype.slice.call(arguments);try{n&&"function"===typeof n&&n.apply(this,arguments);var i=r.map((function(t){return pe(t,e)}));return t.handleEvent?t.handleEvent.apply(this,i):t.apply(this,i)}catch(o){throw fe(),ce((function(t){t.addEventProcessor((function(t){var n=Object(s["a"])({},t);return e.mechanism&&(Object(f["b"])(n,void 0,void 0),Object(f["a"])(n,e.mechanism)),n.extra=Object(s["a"])(Object(s["a"])({},n.extra),{arguments:r}),n})),ue(o)})),o}};try{for(var i in t)Object.prototype.hasOwnProperty.call(t,i)&&(r[i]=t[i])}catch(u){}t.prototype=t.prototype||{},r.prototype=t.prototype,Object.defineProperty(t,"__sentry_wrapped__",{enumerable:!1,value:r}),Object.defineProperties(r,{__sentry__:{enumerable:!1,value:!0},__sentry_original__:{enumerable:!1,value:t}});try{var o=Object.getOwnPropertyDescriptor(r,"name");o.configurable&&Object.defineProperty(r,"name",{get:function(){return t.name}})}catch(u){}return r}function de(t){if(void 0===t&&(t={}),t.eventId)if(t.dsn){var e=document.createElement("script");e.async=!0,e.src=new te(t.dsn).getReportDialogEndpoint(t),t.onLoad&&(e.onload=t.onLoad),(document.head||document.body).appendChild(e)}else v["a"].error("Missing dsn option in showReportDialog call");else v["a"].error("Missing eventId option in showReportDialog call")}var me=n("bc5b"),ve=function(){function t(e){this.name=t.id,this._options=Object(s["a"])({console:!0,dom:!0,fetch:!0,history:!0,sentry:!0,xhr:!0},e)}return t.prototype.addSentryBreadcrumb=function(t){this._options.sentry&&C().addBreadcrumb({category:"sentry."+("transaction"===t.type?"transaction":"event"),event_id:t.event_id,level:t.level,message:Object(f["d"])(t)},{event:t})},t.prototype.setupOnce=function(){var t=this;this._options.console&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._consoleBreadcrumb.apply(t,Object(s["e"])(e))},type:"console"}),this._options.dom&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._domBreadcrumb.apply(t,Object(s["e"])(e))},type:"dom"}),this._options.xhr&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._xhrBreadcrumb.apply(t,Object(s["e"])(e))},type:"xhr"}),this._options.fetch&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._fetchBreadcrumb.apply(t,Object(s["e"])(e))},type:"fetch"}),this._options.history&&V({callback:function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];t._historyBreadcrumb.apply(t,Object(s["e"])(e))},type:"history"})},t.prototype._consoleBreadcrumb=function(t){var e={category:"console",data:{arguments:t.args,logger:"console"},level:St.fromString(t.level),message:Object(T["b"])(t.args," ")};if("assert"===t.level){if(!1!==t.args[0])return;e.message="Assertion failed: "+(Object(T["b"])(t.args.slice(1)," ")||"console.assert"),e.data.arguments=t.args.slice(1)}C().addBreadcrumb(e,{input:t.args,level:t.level})},t.prototype._domBreadcrumb=function(t){var e;try{e=t.event.target?Object(me["a"])(t.event.target):Object(me["a"])(t.event)}catch(n){e="<unknown>"}0!==e.length&&C().addBreadcrumb({category:"ui."+t.name,message:e},{event:t.event,name:t.name,global:t.global})},t.prototype._xhrBreadcrumb=function(t){if(t.endTimestamp){if(t.xhr.__sentry_own_request__)return;var e=t.xhr.__sentry_xhr__||{},n=e.method,r=e.url,i=e.status_code,o=e.body;C().addBreadcrumb({category:"xhr",data:{method:n,url:r,status_code:i},type:"http"},{xhr:t.xhr,input:o})}else;},t.prototype._fetchBreadcrumb=function(t){t.endTimestamp&&(t.fetchData.url.match(/sentry_key/)&&"POST"===t.fetchData.method||(t.error?C().addBreadcrumb({category:"fetch",data:t.fetchData,level:St.Error,type:"http"},{data:t.error,input:t.args}):C().addBreadcrumb({category:"fetch",data:Object(s["a"])(Object(s["a"])({},t.fetchData),{status_code:t.response.status}),type:"http"},{input:t.args,response:t.response})))},t.prototype._historyBreadcrumb=function(t){var e=Object(f["e"])(),n=t.from,r=t.to,i=Object(f["h"])(e.location.href),o=Object(f["h"])(n),a=Object(f["h"])(r);o.path||(o=i),i.protocol===a.protocol&&i.host===a.host&&(r=a.relative),i.protocol===o.protocol&&i.host===o.host&&(n=o.relative),C().addBreadcrumb({category:"navigation",data:{from:n,to:r}})},t.id="Breadcrumbs",t}(),ge=function(t){function e(e){void 0===e&&(e={});var n=this;return e._metadata=e._metadata||{},e._metadata.sdk=e._metadata.sdk||{name:"sentry.javascript.browser",packages:[{name:"npm:@sentry/browser",version:ht}],version:ht},n=t.call(this,ae,e)||this,n}return Object(s["b"])(e,t),e.prototype.showReportDialog=function(t){void 0===t&&(t={});var e=Object(f["e"])().document;e&&(this._isEnabled()?de(Object(s["a"])(Object(s["a"])({},t),{dsn:t.dsn||this.getDsn()})):v["a"].error("Trying to call showReportDialog with Sentry Client disabled"))},e.prototype._prepareEvent=function(e,n,r){return e.platform=e.platform||"javascript",t.prototype._prepareEvent.call(this,e,n,r)},e.prototype._sendEvent=function(e){var n=this.getIntegration(ve);n&&n.addSentryBreadcrumb(e),t.prototype._sendEvent.call(this,e)},e}(Et),_e=["EventTarget","Window","Node","ApplicationCache","AudioTrackList","ChannelMergerNode","CryptoOperation","EventSource","FileReader","HTMLUnknownElement","IDBDatabase","IDBRequest","IDBTransaction","KeyOperation","MediaController","MessagePort","ModalWindow","Notification","SVGElementInstance","Screen","TextTrack","TextTrackCue","TextTrackList","WebSocket","WebSocketWorker","Worker","XMLHttpRequest","XMLHttpRequestEventTarget","XMLHttpRequestUpload"],ye=function(){function t(e){this.name=t.id,this._options=Object(s["a"])({XMLHttpRequest:!0,eventTarget:!0,requestAnimationFrame:!0,setInterval:!0,setTimeout:!0},e)}return t.prototype.setupOnce=function(){var t=Object(f["e"])();if(this._options.setTimeout&&Object(_["c"])(t,"setTimeout",this._wrapTimeFunction.bind(this)),this._options.setInterval&&Object(_["c"])(t,"setInterval",this._wrapTimeFunction.bind(this)),this._options.requestAnimationFrame&&Object(_["c"])(t,"requestAnimationFrame",this._wrapRAF.bind(this)),this._options.XMLHttpRequest&&"XMLHttpRequest"in t&&Object(_["c"])(XMLHttpRequest.prototype,"send",this._wrapXHR.bind(this)),this._options.eventTarget){var e=Array.isArray(this._options.eventTarget)?this._options.eventTarget:_e;e.forEach(this._wrapEventTarget.bind(this))}},t.prototype._wrapTimeFunction=function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=e[0];return e[0]=pe(r,{mechanism:{data:{function:Object(B["a"])(t)},handled:!0,type:"instrument"}}),t.apply(this,e)}},t.prototype._wrapRAF=function(t){return function(e){return t.call(this,pe(e,{mechanism:{data:{function:"requestAnimationFrame",handler:Object(B["a"])(t)},handled:!0,type:"instrument"}}))}},t.prototype._wrapEventTarget=function(t){var e=Object(f["e"])(),n=e[t]&&e[t].prototype;n&&n.hasOwnProperty&&n.hasOwnProperty("addEventListener")&&(Object(_["c"])(n,"addEventListener",(function(e){return function(n,r,i){try{"function"===typeof r.handleEvent&&(r.handleEvent=pe(r.handleEvent.bind(r),{mechanism:{data:{function:"handleEvent",handler:Object(B["a"])(r),target:t},handled:!0,type:"instrument"}}))}catch(o){}return e.call(this,n,pe(r,{mechanism:{data:{function:"addEventListener",handler:Object(B["a"])(r),target:t},handled:!0,type:"instrument"}}),i)}})),Object(_["c"])(n,"removeEventListener",(function(t){return function(e,n,r){var i,o=n;try{var a=null===(i=o)||void 0===i?void 0:i.__sentry_wrapped__;a&&t.call(this,e,a,r)}catch(s){}return t.call(this,e,o,r)}})))},t.prototype._wrapXHR=function(t){return function(){for(var e=[],n=0;n<arguments.length;n++)e[n]=arguments[n];var r=this,i=["onload","onerror","onprogress","onreadystatechange"];return i.forEach((function(t){t in r&&"function"===typeof r[t]&&Object(_["c"])(r,t,(function(e){var n={mechanism:{data:{function:t,handler:Object(B["a"])(e)},handled:!0,type:"instrument"}};return e.__sentry_original__&&(n.mechanism.data.handler=Object(B["a"])(e.__sentry_original__)),pe(e,n)}))})),t.apply(this,e)}},t.id="TryCatch",t}(),be=function(){function t(e){this.name=t.id,this._onErrorHandlerInstalled=!1,this._onUnhandledRejectionHandlerInstalled=!1,this._options=Object(s["a"])({onerror:!0,onunhandledrejection:!0},e)}return t.prototype.setupOnce=function(){Error.stackTraceLimit=50,this._options.onerror&&(v["a"].log("Global Handler attached: onerror"),this._installGlobalOnErrorHandler()),this._options.onunhandledrejection&&(v["a"].log("Global Handler attached: onunhandledrejection"),this._installGlobalOnUnhandledRejectionHandler())},t.prototype._installGlobalOnErrorHandler=function(){var e=this;this._onErrorHandlerInstalled||(V({callback:function(n){var r=n.error,i=C(),o=i.getIntegration(t),a=r&&!0===r.__sentry_own_request__;if(o&&!he()&&!a){var s=i.getClient(),c=Object(u["i"])(r)?e._eventFromIncompleteOnError(n.msg,n.url,n.line,n.column):e._enhanceEventWithInitialFrame(Gt(r,void 0,{attachStacktrace:s&&s.getOptions().attachStacktrace,rejection:!1}),n.url,n.line,n.column);Object(f["a"])(c,{handled:!1,type:"onerror"}),i.captureEvent(c,{originalException:r})}},type:"error"}),this._onErrorHandlerInstalled=!0)},t.prototype._installGlobalOnUnhandledRejectionHandler=function(){var e=this;this._onUnhandledRejectionHandlerInstalled||(V({callback:function(n){var r=n;try{"reason"in n?r=n.reason:"detail"in n&&"reason"in n.detail&&(r=n.detail.reason)}catch(l){}var i=C(),o=i.getIntegration(t),a=r&&!0===r.__sentry_own_request__;if(!o||he()||a)return!0;var s=i.getClient(),c=Object(u["i"])(r)?e._eventFromRejectionWithPrimitive(r):Gt(r,void 0,{attachStacktrace:s&&s.getOptions().attachStacktrace,rejection:!0});c.level=St.Error,Object(f["a"])(c,{handled:!1,type:"onunhandledrejection"}),i.captureEvent(c,{originalException:r})},type:"unhandledrejection"}),this._onUnhandledRejectionHandlerInstalled=!0)},t.prototype._eventFromIncompleteOnError=function(t,e,n,r){var i,o=/^(?:[Uu]ncaught (?:exception: )?)?(?:((?:Eval|Internal|Range|Reference|Syntax|Type|URI|)Error): )?(.*)$/i,a=Object(u["e"])(t)?t.message:t;if(Object(u["k"])(a)){var s=a.match(o);s&&(i=s[1],a=s[2])}var c={exception:{values:[{type:i||"Error",value:a}]}};return this._enhanceEventWithInitialFrame(c,e,n,r)},t.prototype._eventFromRejectionWithPrimitive=function(t){return{exception:{values:[{type:"UnhandledRejection",value:"Non-Error promise rejection captured with value: "+String(t)}]}}},t.prototype._enhanceEventWithInitialFrame=function(t,e,n,r){t.exception=t.exception||{},t.exception.values=t.exception.values||[],t.exception.values[0]=t.exception.values[0]||{},t.exception.values[0].stacktrace=t.exception.values[0].stacktrace||{},t.exception.values[0].stacktrace.frames=t.exception.values[0].stacktrace.frames||[];var i=isNaN(parseInt(r,10))?void 0:r,o=isNaN(parseInt(n,10))?void 0:n,a=Object(u["k"])(e)&&e.length>0?e:Object(f["f"])();return 0===t.exception.values[0].stacktrace.frames.length&&t.exception.values[0].stacktrace.frames.push({colno:i,filename:a,function:"?",in_app:!0,lineno:o}),t},t.id="GlobalHandlers",t}(),we="cause",xe=5,ke=function(){function t(e){void 0===e&&(e={}),this.name=t.id,this._key=e.key||we,this._limit=e.limit||xe}return t.prototype.setupOnce=function(){m((function(e,n){var r=C().getIntegration(t);return r?r._handler(e,n):e}))},t.prototype._handler=function(t,e){if(!t.exception||!t.exception.values||!e||!Object(u["g"])(e.originalException,Error))return t;var n=this._walkErrorTree(e.originalException,this._key);return t.exception.values=Object(s["e"])(n,t.exception.values),t},t.prototype._walkErrorTree=function(t,e,n){if(void 0===n&&(n=[]),!Object(u["g"])(t[e],Error)||n.length+1>=this._limit)return n;var r=Bt(t[e]),i=Ut(r);return this._walkErrorTree(t[e],e,Object(s["e"])([i],n))},t.id="LinkedErrors",t}(),Ee=Object(f["e"])(),Se=function(){function t(){this.name=t.id}return t.prototype.setupOnce=function(){m((function(e){var n,r,i;if(C().getIntegration(t)){if(!Ee.navigator&&!Ee.location&&!Ee.document)return e;var o=(null===(n=e.request)||void 0===n?void 0:n.url)||(null===(r=Ee.location)||void 0===r?void 0:r.href),a=(Ee.document||{}).referrer,u=(Ee.navigator||{}).userAgent,c=Object(s["a"])(Object(s["a"])(Object(s["a"])({},null===(i=e.request)||void 0===i?void 0:i.headers),a&&{Referer:a}),u&&{"User-Agent":u}),l=Object(s["a"])(Object(s["a"])({},o&&{url:o}),{headers:c});return Object(s["a"])(Object(s["a"])({},e),{request:l})}return e}))},t.id="UserAgent",t}(),Ce=[new i.InboundFilters,new i.FunctionToString,new ye,new ve,new be,new ke,new Se];function Ae(t){if(void 0===t&&(t={}),void 0===t.defaultIntegrations&&(t.defaultIntegrations=Ce),void 0===t.release){var e=Object(f["e"])();e.SENTRY_RELEASE&&e.SENTRY_RELEASE.id&&(t.release=e.SENTRY_RELEASE.id)}void 0===t.autoSessionTracking&&(t.autoSessionTracking=!0),M(ge,t),t.autoSessionTracking&&Oe()}function Oe(){var t=Object(f["e"])(),e=t.document;if("undefined"!==typeof e){var n=C();"startSession"in n&&(n.startSession(),n.captureSession(),V({callback:function(){n.startSession(),n.captureSession()},type:"history"}))}else v["a"].warn("Session tracking in non-browser environment with @sentry/browser is not supported.")}},dca8:function(t,e,n){var r=n("23e7"),i=n("bb2f"),o=n("d039"),a=n("861d"),s=n("f183").onFreeze,u=Object.freeze,c=o((function(){u(1)}));r({target:"Object",stat:!0,forced:c,sham:!i},{freeze:function(t){return u&&a(t)?u(s(t)):t}})},dd40:function(t,e){t.exports=function(t){if(!t.webpackPolyfill){var e=Object.create(t);e.children||(e.children=[]),Object.defineProperty(e,"loaded",{enumerable:!0,get:function(){return e.l}}),Object.defineProperty(e,"id",{enumerable:!0,get:function(){return e.i}}),Object.defineProperty(e,"exports",{enumerable:!0}),e.webpackPolyfill=1}return e}},ddb0:function(t,e,n){var r=n("da84"),i=n("fdbc"),o=n("e260"),a=n("9112"),s=n("b622"),u=s("iterator"),c=s("toStringTag"),l=o.values;for(var h in i){var f=r[h],p=f&&f.prototype;if(p){if(p[u]!==l)try{a(p,u,l)}catch(m){p[u]=l}if(p[c]||a(p,c,h),i[h])for(var d in o)if(p[d]!==o[d])try{a(p,d,o[d])}catch(m){p[d]=o[d]}}}},df75:function(t,e,n){var r=n("ca84"),i=n("7839");t.exports=Object.keys||function(t){return r(t,i)}},df7c:function(t,e,n){(function(t){function n(t,e){for(var n=0,r=t.length-1;r>=0;r--){var i=t[r];"."===i?t.splice(r,1):".."===i?(t.splice(r,1),n++):n&&(t.splice(r,1),n--)}if(e)for(;n--;n)t.unshift("..");return t}function r(t){"string"!==typeof t&&(t+="");var e,n=0,r=-1,i=!0;for(e=t.length-1;e>=0;--e)if(47===t.charCodeAt(e)){if(!i){n=e+1;break}}else-1===r&&(i=!1,r=e+1);return-1===r?"":t.slice(n,r)}function i(t,e){if(t.filter)return t.filter(e);for(var n=[],r=0;r<t.length;r++)e(t[r],r,t)&&n.push(t[r]);return n}e.resolve=function(){for(var e="",r=!1,o=arguments.length-1;o>=-1&&!r;o--){var a=o>=0?arguments[o]:t.cwd();if("string"!==typeof a)throw new TypeError("Arguments to path.resolve must be strings");a&&(e=a+"/"+e,r="/"===a.charAt(0))}return e=n(i(e.split("/"),(function(t){return!!t})),!r).join("/"),(r?"/":"")+e||"."},e.normalize=function(t){var r=e.isAbsolute(t),a="/"===o(t,-1);return t=n(i(t.split("/"),(function(t){return!!t})),!r).join("/"),t||r||(t="."),t&&a&&(t+="/"),(r?"/":"")+t},e.isAbsolute=function(t){return"/"===t.charAt(0)},e.join=function(){var t=Array.prototype.slice.call(arguments,0);return e.normalize(i(t,(function(t,e){if("string"!==typeof t)throw new TypeError("Arguments to path.join must be strings");return t})).join("/"))},e.relative=function(t,n){function r(t){for(var e=0;e<t.length;e++)if(""!==t[e])break;for(var n=t.length-1;n>=0;n--)if(""!==t[n])break;return e>n?[]:t.slice(e,n-e+1)}t=e.resolve(t).substr(1),n=e.resolve(n).substr(1);for(var i=r(t.split("/")),o=r(n.split("/")),a=Math.min(i.length,o.length),s=a,u=0;u<a;u++)if(i[u]!==o[u]){s=u;break}var c=[];for(u=s;u<i.length;u++)c.push("..");return c=c.concat(o.slice(s)),c.join("/")},e.sep="/",e.delimiter=":",e.dirname=function(t){if("string"!==typeof t&&(t+=""),0===t.length)return".";for(var e=t.charCodeAt(0),n=47===e,r=-1,i=!0,o=t.length-1;o>=1;--o)if(e=t.charCodeAt(o),47===e){if(!i){r=o;break}}else i=!1;return-1===r?n?"/":".":n&&1===r?"/":t.slice(0,r)},e.basename=function(t,e){var n=r(t);return e&&n.substr(-1*e.length)===e&&(n=n.substr(0,n.length-e.length)),n},e.extname=function(t){"string"!==typeof t&&(t+="");for(var e=-1,n=0,r=-1,i=!0,o=0,a=t.length-1;a>=0;--a){var s=t.charCodeAt(a);if(47!==s)-1===r&&(i=!1,r=a+1),46===s?-1===e?e=a:1!==o&&(o=1):-1!==e&&(o=-1);else if(!i){n=a+1;break}}return-1===e||-1===r||0===o||1===o&&e===r-1&&e===n+1?"":t.slice(e,r)};var o="b"==="ab".substr(-1)?function(t,e,n){return t.substr(e,n)}:function(t,e,n){return e<0&&(e=t.length+e),t.substr(e,n)}}).call(this,n("4362"))},e01a:function(t,e,n){"use strict";var r=n("23e7"),i=n("83ab"),o=n("da84"),a=n("5135"),s=n("861d"),u=n("9bf2").f,c=n("e893"),l=o.Symbol;if(i&&"function"==typeof l&&(!("description"in l.prototype)||void 0!==l().description)){var h={},f=function(){var t=arguments.length<1||void 0===arguments[0]?void 0:String(arguments[0]),e=this instanceof f?new l(t):void 0===t?l():l(t);return""===t&&(h[e]=!0),e};c(f,l);var p=f.prototype=l.prototype;p.constructor=f;var d=p.toString,m="Symbol(test)"==String(l("test")),v=/^Symbol\((.*)\)[^)]+$/;u(p,"description",{configurable:!0,get:function(){var t=s(this)?this.valueOf():this,e=d.call(t);if(a(h,t))return"";var n=m?e.slice(7,-1):e.replace(v,"$1");return""===n?void 0:n}}),r({global:!0,forced:!0},{Symbol:f})}},e11e:function(t,e,n){
/* @preserve
 * Leaflet 1.7.1, a JS library for interactive maps. http://leafletjs.com
 * (c) 2010-2019 Vladimir Agafonkin, (c) 2010-2011 CloudMade
 */
(function(t,n){n(e)})(0,(function(t){"use strict";var e="1.7.1";function n(t){var e,n,r,i;for(n=1,r=arguments.length;n<r;n++)for(e in i=arguments[n],i)t[e]=i[e];return t}var r=Object.create||function(){function t(){}return function(e){return t.prototype=e,new t}}();function i(t,e){var n=Array.prototype.slice;if(t.bind)return t.bind.apply(t,n.call(arguments,1));var r=n.call(arguments,2);return function(){return t.apply(e,r.length?r.concat(n.call(arguments)):arguments)}}var o=0;function a(t){return t._leaflet_id=t._leaflet_id||++o,t._leaflet_id}function s(t,e,n){var r,i,o,a;return a=function(){r=!1,i&&(o.apply(n,i),i=!1)},o=function(){r?i=arguments:(t.apply(n,arguments),setTimeout(a,e),r=!0)},o}function u(t,e,n){var r=e[1],i=e[0],o=r-i;return t===r&&n?t:((t-i)%o+o)%o+i}function c(){return!1}function l(t,e){var n=Math.pow(10,void 0===e?6:e);return Math.round(t*n)/n}function h(t){return t.trim?t.trim():t.replace(/^\s+|\s+$/g,"")}function f(t){return h(t).split(/\s+/)}function p(t,e){for(var n in Object.prototype.hasOwnProperty.call(t,"options")||(t.options=t.options?r(t.options):{}),e)t.options[n]=e[n];return t.options}function d(t,e,n){var r=[];for(var i in t)r.push(encodeURIComponent(n?i.toUpperCase():i)+"="+encodeURIComponent(t[i]));return(e&&-1!==e.indexOf("?")?"&":"?")+r.join("&")}var m=/\{ *([\w_-]+) *\}/g;function v(t,e){return t.replace(m,(function(t,n){var r=e[n];if(void 0===r)throw new Error("No value provided for variable "+t);return"function"===typeof r&&(r=r(e)),r}))}var g=Array.isArray||function(t){return"[object Array]"===Object.prototype.toString.call(t)};function _(t,e){for(var n=0;n<t.length;n++)if(t[n]===e)return n;return-1}var y="data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=";function b(t){return window["webkit"+t]||window["moz"+t]||window["ms"+t]}var w=0;function x(t){var e=+new Date,n=Math.max(0,16-(e-w));return w=e+n,window.setTimeout(t,n)}var k=window.requestAnimationFrame||b("RequestAnimationFrame")||x,E=window.cancelAnimationFrame||b("CancelAnimationFrame")||b("CancelRequestAnimationFrame")||function(t){window.clearTimeout(t)};function S(t,e,n){if(!n||k!==x)return k.call(window,i(t,e));t.call(e)}function C(t){t&&E.call(window,t)}var A={extend:n,create:r,bind:i,lastId:o,stamp:a,throttle:s,wrapNum:u,falseFn:c,formatNum:l,trim:h,splitWords:f,setOptions:p,getParamString:d,template:v,isArray:g,indexOf:_,emptyImageUrl:y,requestFn:k,cancelFn:E,requestAnimFrame:S,cancelAnimFrame:C};function O(){}function D(t){if("undefined"!==typeof L&&L&&L.Mixin){t=g(t)?t:[t];for(var e=0;e<t.length;e++)t[e]===L.Mixin.Events&&console.warn("Deprecated include of L.Mixin.Events: this property will be removed in future releases, please inherit from L.Evented instead.",(new Error).stack)}}O.extend=function(t){var e=function(){this.initialize&&this.initialize.apply(this,arguments),this.callInitHooks()},i=e.__super__=this.prototype,o=r(i);for(var a in o.constructor=e,e.prototype=o,this)Object.prototype.hasOwnProperty.call(this,a)&&"prototype"!==a&&"__super__"!==a&&(e[a]=this[a]);return t.statics&&(n(e,t.statics),delete t.statics),t.includes&&(D(t.includes),n.apply(null,[o].concat(t.includes)),delete t.includes),o.options&&(t.options=n(r(o.options),t.options)),n(o,t),o._initHooks=[],o.callInitHooks=function(){if(!this._initHooksCalled){i.callInitHooks&&i.callInitHooks.call(this),this._initHooksCalled=!0;for(var t=0,e=o._initHooks.length;t<e;t++)o._initHooks[t].call(this)}},e},O.include=function(t){return n(this.prototype,t),this},O.mergeOptions=function(t){return n(this.prototype.options,t),this},O.addInitHook=function(t){var e=Array.prototype.slice.call(arguments,1),n="function"===typeof t?t:function(){this[t].apply(this,e)};return this.prototype._initHooks=this.prototype._initHooks||[],this.prototype._initHooks.push(n),this};var T={on:function(t,e,n){if("object"===typeof t)for(var r in t)this._on(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._on(t[i],e,n)}return this},off:function(t,e,n){if(t)if("object"===typeof t)for(var r in t)this._off(r,t[r],e);else{t=f(t);for(var i=0,o=t.length;i<o;i++)this._off(t[i],e,n)}else delete this._events;return this},_on:function(t,e,n){this._events=this._events||{};var r=this._events[t];r||(r=[],this._events[t]=r),n===this&&(n=void 0);for(var i={fn:e,ctx:n},o=r,a=0,s=o.length;a<s;a++)if(o[a].fn===e&&o[a].ctx===n)return;o.push(i)},_off:function(t,e,n){var r,i,o;if(this._events&&(r=this._events[t],r))if(e){if(n===this&&(n=void 0),r)for(i=0,o=r.length;i<o;i++){var a=r[i];if(a.ctx===n&&a.fn===e)return a.fn=c,this._firingCount&&(this._events[t]=r=r.slice()),void r.splice(i,1)}}else{for(i=0,o=r.length;i<o;i++)r[i].fn=c;delete this._events[t]}},fire:function(t,e,r){if(!this.listens(t,r))return this;var i=n({},e,{type:t,target:this,sourceTarget:e&&e.sourceTarget||this});if(this._events){var o=this._events[t];if(o){this._firingCount=this._firingCount+1||1;for(var a=0,s=o.length;a<s;a++){var u=o[a];u.fn.call(u.ctx||this,i)}this._firingCount--}}return r&&this._propagateEvent(i),this},listens:function(t,e){var n=this._events&&this._events[t];if(n&&n.length)return!0;if(e)for(var r in this._eventParents)if(this._eventParents[r].listens(t,e))return!0;return!1},once:function(t,e,n){if("object"===typeof t){for(var r in t)this.once(r,t[r],e);return this}var o=i((function(){this.off(t,e,n).off(t,o,n)}),this);return this.on(t,e,n).on(t,o,n)},addEventParent:function(t){return this._eventParents=this._eventParents||{},this._eventParents[a(t)]=t,this},removeEventParent:function(t){return this._eventParents&&delete this._eventParents[a(t)],this},_propagateEvent:function(t){for(var e in this._eventParents)this._eventParents[e].fire(t.type,n({layer:t.target,propagatedFrom:t.target},t),!0)}};T.addEventListener=T.on,T.removeEventListener=T.clearAllEventListeners=T.off,T.addOneTimeEventListener=T.once,T.fireEvent=T.fire,T.hasEventListeners=T.listens;var j=O.extend(T);function P(t,e,n){this.x=n?Math.round(t):t,this.y=n?Math.round(e):e}var M=Math.trunc||function(t){return t>0?Math.floor(t):Math.ceil(t)};function B(t,e,n){return t instanceof P?t:g(t)?new P(t[0],t[1]):void 0===t||null===t?t:"object"===typeof t&&"x"in t&&"y"in t?new P(t.x,t.y):new P(t,e,n)}function R(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function I(t,e){return!t||t instanceof R?t:new R(t,e)}function F(t,e){if(t)for(var n=e?[t,e]:t,r=0,i=n.length;r<i;r++)this.extend(n[r])}function z(t,e){return t instanceof F?t:new F(t,e)}function N(t,e,n){if(isNaN(t)||isNaN(e))throw new Error("Invalid LatLng object: ("+t+", "+e+")");this.lat=+t,this.lng=+e,void 0!==n&&(this.alt=+n)}function U(t,e,n){return t instanceof N?t:g(t)&&"object"!==typeof t[0]?3===t.length?new N(t[0],t[1],t[2]):2===t.length?new N(t[0],t[1]):null:void 0===t||null===t?t:"object"===typeof t&&"lat"in t?new N(t.lat,"lng"in t?t.lng:t.lon,t.alt):void 0===e?null:new N(t,e,n)}P.prototype={clone:function(){return new P(this.x,this.y)},add:function(t){return this.clone()._add(B(t))},_add:function(t){return this.x+=t.x,this.y+=t.y,this},subtract:function(t){return this.clone()._subtract(B(t))},_subtract:function(t){return this.x-=t.x,this.y-=t.y,this},divideBy:function(t){return this.clone()._divideBy(t)},_divideBy:function(t){return this.x/=t,this.y/=t,this},multiplyBy:function(t){return this.clone()._multiplyBy(t)},_multiplyBy:function(t){return this.x*=t,this.y*=t,this},scaleBy:function(t){return new P(this.x*t.x,this.y*t.y)},unscaleBy:function(t){return new P(this.x/t.x,this.y/t.y)},round:function(){return this.clone()._round()},_round:function(){return this.x=Math.round(this.x),this.y=Math.round(this.y),this},floor:function(){return this.clone()._floor()},_floor:function(){return this.x=Math.floor(this.x),this.y=Math.floor(this.y),this},ceil:function(){return this.clone()._ceil()},_ceil:function(){return this.x=Math.ceil(this.x),this.y=Math.ceil(this.y),this},trunc:function(){return this.clone()._trunc()},_trunc:function(){return this.x=M(this.x),this.y=M(this.y),this},distanceTo:function(t){t=B(t);var e=t.x-this.x,n=t.y-this.y;return Math.sqrt(e*e+n*n)},equals:function(t){return t=B(t),t.x===this.x&&t.y===this.y},contains:function(t){return t=B(t),Math.abs(t.x)<=Math.abs(this.x)&&Math.abs(t.y)<=Math.abs(this.y)},toString:function(){return"Point("+l(this.x)+", "+l(this.y)+")"}},R.prototype={extend:function(t){return t=B(t),this.min||this.max?(this.min.x=Math.min(t.x,this.min.x),this.max.x=Math.max(t.x,this.max.x),this.min.y=Math.min(t.y,this.min.y),this.max.y=Math.max(t.y,this.max.y)):(this.min=t.clone(),this.max=t.clone()),this},getCenter:function(t){return new P((this.min.x+this.max.x)/2,(this.min.y+this.max.y)/2,t)},getBottomLeft:function(){return new P(this.min.x,this.max.y)},getTopRight:function(){return new P(this.max.x,this.min.y)},getTopLeft:function(){return this.min},getBottomRight:function(){return this.max},getSize:function(){return this.max.subtract(this.min)},contains:function(t){var e,n;return t="number"===typeof t[0]||t instanceof P?B(t):I(t),t instanceof R?(e=t.min,n=t.max):e=n=t,e.x>=this.min.x&&n.x<=this.max.x&&e.y>=this.min.y&&n.y<=this.max.y},intersects:function(t){t=I(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>=e.x&&r.x<=n.x,a=i.y>=e.y&&r.y<=n.y;return o&&a},overlaps:function(t){t=I(t);var e=this.min,n=this.max,r=t.min,i=t.max,o=i.x>e.x&&r.x<n.x,a=i.y>e.y&&r.y<n.y;return o&&a},isValid:function(){return!(!this.min||!this.max)}},F.prototype={extend:function(t){var e,n,r=this._southWest,i=this._northEast;if(t instanceof N)e=t,n=t;else{if(!(t instanceof F))return t?this.extend(U(t)||z(t)):this;if(e=t._southWest,n=t._northEast,!e||!n)return this}return r||i?(r.lat=Math.min(e.lat,r.lat),r.lng=Math.min(e.lng,r.lng),i.lat=Math.max(n.lat,i.lat),i.lng=Math.max(n.lng,i.lng)):(this._southWest=new N(e.lat,e.lng),this._northEast=new N(n.lat,n.lng)),this},pad:function(t){var e=this._southWest,n=this._northEast,r=Math.abs(e.lat-n.lat)*t,i=Math.abs(e.lng-n.lng)*t;return new F(new N(e.lat-r,e.lng-i),new N(n.lat+r,n.lng+i))},getCenter:function(){return new N((this._southWest.lat+this._northEast.lat)/2,(this._southWest.lng+this._northEast.lng)/2)},getSouthWest:function(){return this._southWest},getNorthEast:function(){return this._northEast},getNorthWest:function(){return new N(this.getNorth(),this.getWest())},getSouthEast:function(){return new N(this.getSouth(),this.getEast())},getWest:function(){return this._southWest.lng},getSouth:function(){return this._southWest.lat},getEast:function(){return this._northEast.lng},getNorth:function(){return this._northEast.lat},contains:function(t){t="number"===typeof t[0]||t instanceof N||"lat"in t?U(t):z(t);var e,n,r=this._southWest,i=this._northEast;return t instanceof F?(e=t.getSouthWest(),n=t.getNorthEast()):e=n=t,e.lat>=r.lat&&n.lat<=i.lat&&e.lng>=r.lng&&n.lng<=i.lng},intersects:function(t){t=z(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>=e.lat&&r.lat<=n.lat,a=i.lng>=e.lng&&r.lng<=n.lng;return o&&a},overlaps:function(t){t=z(t);var e=this._southWest,n=this._northEast,r=t.getSouthWest(),i=t.getNorthEast(),o=i.lat>e.lat&&r.lat<n.lat,a=i.lng>e.lng&&r.lng<n.lng;return o&&a},toBBoxString:function(){return[this.getWest(),this.getSouth(),this.getEast(),this.getNorth()].join(",")},equals:function(t,e){return!!t&&(t=z(t),this._southWest.equals(t.getSouthWest(),e)&&this._northEast.equals(t.getNorthEast(),e))},isValid:function(){return!(!this._southWest||!this._northEast)}},N.prototype={equals:function(t,e){if(!t)return!1;t=U(t);var n=Math.max(Math.abs(this.lat-t.lat),Math.abs(this.lng-t.lng));return n<=(void 0===e?1e-9:e)},toString:function(t){return"LatLng("+l(this.lat,t)+", "+l(this.lng,t)+")"},distanceTo:function(t){return $.distance(this,U(t))},wrap:function(){return $.wrapLatLng(this)},toBounds:function(t){var e=180*t/40075017,n=e/Math.cos(Math.PI/180*this.lat);return z([this.lat-e,this.lng-n],[this.lat+e,this.lng+n])},clone:function(){return new N(this.lat,this.lng,this.alt)}};var Z={latLngToPoint:function(t,e){var n=this.projection.project(t),r=this.scale(e);return this.transformation._transform(n,r)},pointToLatLng:function(t,e){var n=this.scale(e),r=this.transformation.untransform(t,n);return this.projection.unproject(r)},project:function(t){return this.projection.project(t)},unproject:function(t){return this.projection.unproject(t)},scale:function(t){return 256*Math.pow(2,t)},zoom:function(t){return Math.log(t/256)/Math.LN2},getProjectedBounds:function(t){if(this.infinite)return null;var e=this.projection.bounds,n=this.scale(t),r=this.transformation.transform(e.min,n),i=this.transformation.transform(e.max,n);return new R(r,i)},infinite:!1,wrapLatLng:function(t){var e=this.wrapLng?u(t.lng,this.wrapLng,!0):t.lng,n=this.wrapLat?u(t.lat,this.wrapLat,!0):t.lat,r=t.alt;return new N(n,e,r)},wrapLatLngBounds:function(t){var e=t.getCenter(),n=this.wrapLatLng(e),r=e.lat-n.lat,i=e.lng-n.lng;if(0===r&&0===i)return t;var o=t.getSouthWest(),a=t.getNorthEast(),s=new N(o.lat-r,o.lng-i),u=new N(a.lat-r,a.lng-i);return new F(s,u)}},$=n({},Z,{wrapLng:[-180,180],R:6371e3,distance:function(t,e){var n=Math.PI/180,r=t.lat*n,i=e.lat*n,o=Math.sin((e.lat-t.lat)*n/2),a=Math.sin((e.lng-t.lng)*n/2),s=o*o+Math.cos(r)*Math.cos(i)*a*a,u=2*Math.atan2(Math.sqrt(s),Math.sqrt(1-s));return this.R*u}}),H=6378137,q={R:H,MAX_LATITUDE:85.0511287798,project:function(t){var e=Math.PI/180,n=this.MAX_LATITUDE,r=Math.max(Math.min(n,t.lat),-n),i=Math.sin(r*e);return new P(this.R*t.lng*e,this.R*Math.log((1+i)/(1-i))/2)},unproject:function(t){var e=180/Math.PI;return new N((2*Math.atan(Math.exp(t.y/this.R))-Math.PI/2)*e,t.x*e/this.R)},bounds:function(){var t=H*Math.PI;return new R([-t,-t],[t,t])}()};function V(t,e,n,r){if(g(t))return this._a=t[0],this._b=t[1],this._c=t[2],void(this._d=t[3]);this._a=t,this._b=e,this._c=n,this._d=r}function G(t,e,n,r){return new V(t,e,n,r)}V.prototype={transform:function(t,e){return this._transform(t.clone(),e)},_transform:function(t,e){return e=e||1,t.x=e*(this._a*t.x+this._b),t.y=e*(this._c*t.y+this._d),t},untransform:function(t,e){return e=e||1,new P((t.x/e-this._b)/this._a,(t.y/e-this._d)/this._c)}};var W=n({},$,{code:"EPSG:3857",projection:q,transformation:function(){var t=.5/(Math.PI*q.R);return G(t,.5,-t,.5)}()}),Y=n({},W,{code:"EPSG:900913"});function K(t){return document.createElementNS("http://www.w3.org/2000/svg",t)}function X(t,e){var n,r,i,o,a,s,u="";for(n=0,i=t.length;n<i;n++){for(a=t[n],r=0,o=a.length;r<o;r++)s=a[r],u+=(r?"L":"M")+s.x+" "+s.y;u+=e?Dt?"z":"x":""}return u||"M0 0"}var J=document.documentElement.style,Q="ActiveXObject"in window,tt=Q&&!document.addEventListener,et="msLaunchUri"in navigator&&!("documentMode"in document),nt=Tt("webkit"),rt=Tt("android"),it=Tt("android 2")||Tt("android 3"),ot=parseInt(/WebKit\/([0-9]+)|$/.exec(navigator.userAgent)[1],10),at=rt&&Tt("Google")&&ot<537&&!("AudioNode"in window),st=!!window.opera,ut=!et&&Tt("chrome"),ct=Tt("gecko")&&!nt&&!st&&!Q,lt=!ut&&Tt("safari"),ht=Tt("phantom"),ft="OTransition"in J,pt=0===navigator.platform.indexOf("Win"),dt=Q&&"transition"in J,mt="WebKitCSSMatrix"in window&&"m11"in new window.WebKitCSSMatrix&&!it,vt="MozPerspective"in J,gt=!window.L_DISABLE_3D&&(dt||mt||vt)&&!ft&&!ht,_t="undefined"!==typeof orientation||Tt("mobile"),yt=_t&&nt,bt=_t&&mt,wt=!window.PointerEvent&&window.MSPointerEvent,xt=!(!window.PointerEvent&&!wt),kt=!window.L_NO_TOUCH&&(xt||"ontouchstart"in window||window.DocumentTouch&&document instanceof window.DocumentTouch),Et=_t&&st,St=_t&&ct,Ct=(window.devicePixelRatio||window.screen.deviceXDPI/window.screen.logicalXDPI)>1,At=function(){var t=!1;try{var e=Object.defineProperty({},"passive",{get:function(){t=!0}});window.addEventListener("testPassiveEventSupport",c,e),window.removeEventListener("testPassiveEventSupport",c,e)}catch(n){}return t}(),Ot=function(){return!!document.createElement("canvas").getContext}(),Dt=!(!document.createElementNS||!K("svg").createSVGRect),Lt=!Dt&&function(){try{var t=document.createElement("div");t.innerHTML='<v:shape adj="1"/>';var e=t.firstChild;return e.style.behavior="url(#default#VML)",e&&"object"===typeof e.adj}catch(n){return!1}}();function Tt(t){return navigator.userAgent.toLowerCase().indexOf(t)>=0}var jt={ie:Q,ielt9:tt,edge:et,webkit:nt,android:rt,android23:it,androidStock:at,opera:st,chrome:ut,gecko:ct,safari:lt,phantom:ht,opera12:ft,win:pt,ie3d:dt,webkit3d:mt,gecko3d:vt,any3d:gt,mobile:_t,mobileWebkit:yt,mobileWebkit3d:bt,msPointer:wt,pointer:xt,touch:kt,mobileOpera:Et,mobileGecko:St,retina:Ct,passiveEvents:At,canvas:Ot,svg:Dt,vml:Lt},Pt=wt?"MSPointerDown":"pointerdown",Mt=wt?"MSPointerMove":"pointermove",Bt=wt?"MSPointerUp":"pointerup",Rt=wt?"MSPointerCancel":"pointercancel",It={},Ft=!1;function zt(t,e,n,r){return"touchstart"===e?Ut(t,n,r):"touchmove"===e?Vt(t,n,r):"touchend"===e&&Gt(t,n,r),this}function Nt(t,e,n){var r=t["_leaflet_"+e+n];return"touchstart"===e?t.removeEventListener(Pt,r,!1):"touchmove"===e?t.removeEventListener(Mt,r,!1):"touchend"===e&&(t.removeEventListener(Bt,r,!1),t.removeEventListener(Rt,r,!1)),this}function Ut(t,e,n){var r=i((function(t){t.MSPOINTER_TYPE_TOUCH&&t.pointerType===t.MSPOINTER_TYPE_TOUCH&&$e(t),qt(t,e)}));t["_leaflet_touchstart"+n]=r,t.addEventListener(Pt,r,!1),Ft||(document.addEventListener(Pt,Zt,!0),document.addEventListener(Mt,$t,!0),document.addEventListener(Bt,Ht,!0),document.addEventListener(Rt,Ht,!0),Ft=!0)}function Zt(t){It[t.pointerId]=t}function $t(t){It[t.pointerId]&&(It[t.pointerId]=t)}function Ht(t){delete It[t.pointerId]}function qt(t,e){for(var n in t.touches=[],It)t.touches.push(It[n]);t.changedTouches=[t],e(t)}function Vt(t,e,n){var r=function(t){t.pointerType===(t.MSPOINTER_TYPE_MOUSE||"mouse")&&0===t.buttons||qt(t,e)};t["_leaflet_touchmove"+n]=r,t.addEventListener(Mt,r,!1)}function Gt(t,e,n){var r=function(t){qt(t,e)};t["_leaflet_touchend"+n]=r,t.addEventListener(Bt,r,!1),t.addEventListener(Rt,r,!1)}var Wt=wt?"MSPointerDown":xt?"pointerdown":"touchstart",Yt=wt?"MSPointerUp":xt?"pointerup":"touchend",Kt="_leaflet_";function Xt(t,e,n){var r,i,o=!1,a=250;function s(t){if(xt){if(!t.isPrimary)return;if("mouse"===t.pointerType)return}else if(t.touches.length>1)return;var e=Date.now(),n=e-(r||e);i=t.touches?t.touches[0]:t,o=n>0&&n<=a,r=e}function u(t){if(o&&!i.cancelBubble){if(xt){if("mouse"===t.pointerType)return;var n,a,s={};for(a in i)n=i[a],s[a]=n&&n.bind?n.bind(i):n;i=s}i.type="dblclick",i.button=0,e(i),r=null}}return t[Kt+Wt+n]=s,t[Kt+Yt+n]=u,t[Kt+"dblclick"+n]=e,t.addEventListener(Wt,s,!!At&&{passive:!1}),t.addEventListener(Yt,u,!!At&&{passive:!1}),t.addEventListener("dblclick",e,!1),this}function Jt(t,e){var n=t[Kt+Wt+e],r=t[Kt+Yt+e],i=t[Kt+"dblclick"+e];return t.removeEventListener(Wt,n,!!At&&{passive:!1}),t.removeEventListener(Yt,r,!!At&&{passive:!1}),t.removeEventListener("dblclick",i,!1),this}var Qt,te,ee,ne,re,ie=we(["transform","webkitTransform","OTransform","MozTransform","msTransform"]),oe=we(["webkitTransition","transition","OTransition","MozTransition","msTransition"]),ae="webkitTransition"===oe||"OTransition"===oe?oe+"End":"transitionend";function se(t){return"string"===typeof t?document.getElementById(t):t}function ue(t,e){var n=t.style[e]||t.currentStyle&&t.currentStyle[e];if((!n||"auto"===n)&&document.defaultView){var r=document.defaultView.getComputedStyle(t,null);n=r?r[e]:null}return"auto"===n?null:n}function ce(t,e,n){var r=document.createElement(t);return r.className=e||"",n&&n.appendChild(r),r}function le(t){var e=t.parentNode;e&&e.removeChild(t)}function he(t){while(t.firstChild)t.removeChild(t.firstChild)}function fe(t){var e=t.parentNode;e&&e.lastChild!==t&&e.appendChild(t)}function pe(t){var e=t.parentNode;e&&e.firstChild!==t&&e.insertBefore(t,e.firstChild)}function de(t,e){if(void 0!==t.classList)return t.classList.contains(e);var n=_e(t);return n.length>0&&new RegExp("(^|\\s)"+e+"(\\s|$)").test(n)}function me(t,e){if(void 0!==t.classList)for(var n=f(e),r=0,i=n.length;r<i;r++)t.classList.add(n[r]);else if(!de(t,e)){var o=_e(t);ge(t,(o?o+" ":"")+e)}}function ve(t,e){void 0!==t.classList?t.classList.remove(e):ge(t,h((" "+_e(t)+" ").replace(" "+e+" "," ")))}function ge(t,e){void 0===t.className.baseVal?t.className=e:t.className.baseVal=e}function _e(t){return t.correspondingElement&&(t=t.correspondingElement),void 0===t.className.baseVal?t.className:t.className.baseVal}function ye(t,e){"opacity"in t.style?t.style.opacity=e:"filter"in t.style&&be(t,e)}function be(t,e){var n=!1,r="DXImageTransform.Microsoft.Alpha";try{n=t.filters.item(r)}catch(i){if(1===e)return}e=Math.round(100*e),n?(n.Enabled=100!==e,n.Opacity=e):t.style.filter+=" progid:"+r+"(opacity="+e+")"}function we(t){for(var e=document.documentElement.style,n=0;n<t.length;n++)if(t[n]in e)return t[n];return!1}function xe(t,e,n){var r=e||new P(0,0);t.style[ie]=(dt?"translate("+r.x+"px,"+r.y+"px)":"translate3d("+r.x+"px,"+r.y+"px,0)")+(n?" scale("+n+")":"")}function ke(t,e){t._leaflet_pos=e,gt?xe(t,e):(t.style.left=e.x+"px",t.style.top=e.y+"px")}function Ee(t){return t._leaflet_pos||new P(0,0)}if("onselectstart"in document)Qt=function(){Pe(window,"selectstart",$e)},te=function(){Be(window,"selectstart",$e)};else{var Se=we(["userSelect","WebkitUserSelect","OUserSelect","MozUserSelect","msUserSelect"]);Qt=function(){if(Se){var t=document.documentElement.style;ee=t[Se],t[Se]="none"}},te=function(){Se&&(document.documentElement.style[Se]=ee,ee=void 0)}}function Ce(){Pe(window,"dragstart",$e)}function Ae(){Be(window,"dragstart",$e)}function Oe(t){while(-1===t.tabIndex)t=t.parentNode;t.style&&(De(),ne=t,re=t.style.outline,t.style.outline="none",Pe(window,"keydown",De))}function De(){ne&&(ne.style.outline=re,ne=void 0,re=void 0,Be(window,"keydown",De))}function Le(t){do{t=t.parentNode}while((!t.offsetWidth||!t.offsetHeight)&&t!==document.body);return t}function Te(t){var e=t.getBoundingClientRect();return{x:e.width/t.offsetWidth||1,y:e.height/t.offsetHeight||1,boundingClientRect:e}}var je={TRANSFORM:ie,TRANSITION:oe,TRANSITION_END:ae,get:se,getStyle:ue,create:ce,remove:le,empty:he,toFront:fe,toBack:pe,hasClass:de,addClass:me,removeClass:ve,setClass:ge,getClass:_e,setOpacity:ye,testProp:we,setTransform:xe,setPosition:ke,getPosition:Ee,disableTextSelection:Qt,enableTextSelection:te,disableImageDrag:Ce,enableImageDrag:Ae,preventOutline:Oe,restoreOutline:De,getSizedParentNode:Le,getScale:Te};function Pe(t,e,n,r){if("object"===typeof e)for(var i in e)Fe(t,i,e[i],n);else{e=f(e);for(var o=0,a=e.length;o<a;o++)Fe(t,e[o],n,r)}return this}var Me="_leaflet_events";function Be(t,e,n,r){if("object"===typeof e)for(var i in e)ze(t,i,e[i],n);else if(e){e=f(e);for(var o=0,a=e.length;o<a;o++)ze(t,e[o],n,r)}else{for(var s in t[Me])ze(t,s,t[Me][s]);delete t[Me]}return this}function Re(){if(xt)return!(et||lt)}var Ie={mouseenter:"mouseover",mouseleave:"mouseout",wheel:!("onwheel"in window)&&"mousewheel"};function Fe(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):"");if(t[Me]&&t[Me][i])return this;var o=function(e){return n.call(r||t,e||window.event)},s=o;xt&&0===e.indexOf("touch")?zt(t,e,o,i):kt&&"dblclick"===e&&!Re()?Xt(t,o,i):"addEventListener"in t?"touchstart"===e||"touchmove"===e||"wheel"===e||"mousewheel"===e?t.addEventListener(Ie[e]||e,o,!!At&&{passive:!1}):"mouseenter"===e||"mouseleave"===e?(o=function(e){e=e||window.event,Xe(t,e)&&s(e)},t.addEventListener(Ie[e],o,!1)):t.addEventListener(e,s,!1):"attachEvent"in t&&t.attachEvent("on"+e,o),t[Me]=t[Me]||{},t[Me][i]=o}function ze(t,e,n,r){var i=e+a(n)+(r?"_"+a(r):""),o=t[Me]&&t[Me][i];if(!o)return this;xt&&0===e.indexOf("touch")?Nt(t,e,i):kt&&"dblclick"===e&&!Re()?Jt(t,i):"removeEventListener"in t?t.removeEventListener(Ie[e]||e,o,!1):"detachEvent"in t&&t.detachEvent("on"+e,o),t[Me][i]=null}function Ne(t){return t.stopPropagation?t.stopPropagation():t.originalEvent?t.originalEvent._stopped=!0:t.cancelBubble=!0,Ke(t),this}function Ue(t){return Fe(t,"wheel",Ne),this}function Ze(t){return Pe(t,"mousedown touchstart dblclick",Ne),Fe(t,"click",Ye),this}function $e(t){return t.preventDefault?t.preventDefault():t.returnValue=!1,this}function He(t){return $e(t),Ne(t),this}function qe(t,e){if(!e)return new P(t.clientX,t.clientY);var n=Te(e),r=n.boundingClientRect;return new P((t.clientX-r.left)/n.x-e.clientLeft,(t.clientY-r.top)/n.y-e.clientTop)}var Ve=pt&&ut?2*window.devicePixelRatio:ct?window.devicePixelRatio:1;function Ge(t){return et?t.wheelDeltaY/2:t.deltaY&&0===t.deltaMode?-t.deltaY/Ve:t.deltaY&&1===t.deltaMode?20*-t.deltaY:t.deltaY&&2===t.deltaMode?60*-t.deltaY:t.deltaX||t.deltaZ?0:t.wheelDelta?(t.wheelDeltaY||t.wheelDelta)/2:t.detail&&Math.abs(t.detail)<32765?20*-t.detail:t.detail?t.detail/-32765*60:0}var We={};function Ye(t){We[t.type]=!0}function Ke(t){var e=We[t.type];return We[t.type]=!1,e}function Xe(t,e){var n=e.relatedTarget;if(!n)return!0;try{while(n&&n!==t)n=n.parentNode}catch(r){return!1}return n!==t}var Je={on:Pe,off:Be,stopPropagation:Ne,disableScrollPropagation:Ue,disableClickPropagation:Ze,preventDefault:$e,stop:He,getMousePosition:qe,getWheelDelta:Ge,fakeStop:Ye,skipped:Ke,isExternalTarget:Xe,addListener:Pe,removeListener:Be},Qe=j.extend({run:function(t,e,n,r){this.stop(),this._el=t,this._inProgress=!0,this._duration=n||.25,this._easeOutPower=1/Math.max(r||.5,.2),this._startPos=Ee(t),this._offset=e.subtract(this._startPos),this._startTime=+new Date,this.fire("start"),this._animate()},stop:function(){this._inProgress&&(this._step(!0),this._complete())},_animate:function(){this._animId=S(this._animate,this),this._step()},_step:function(t){var e=+new Date-this._startTime,n=1e3*this._duration;e<n?this._runFrame(this._easeOut(e/n),t):(this._runFrame(1),this._complete())},_runFrame:function(t,e){var n=this._startPos.add(this._offset.multiplyBy(t));e&&n._round(),ke(this._el,n),this.fire("step")},_complete:function(){C(this._animId),this._inProgress=!1,this.fire("end")},_easeOut:function(t){return 1-Math.pow(1-t,this._easeOutPower)}}),tn=j.extend({options:{crs:W,center:void 0,zoom:void 0,minZoom:void 0,maxZoom:void 0,layers:[],maxBounds:void 0,renderer:void 0,zoomAnimation:!0,zoomAnimationThreshold:4,fadeAnimation:!0,markerZoomAnimation:!0,transform3DLimit:8388608,zoomSnap:1,zoomDelta:1,trackResize:!0},initialize:function(t,e){e=p(this,e),this._handlers=[],this._layers={},this._zoomBoundLayers={},this._sizeChanged=!0,this._initContainer(t),this._initLayout(),this._onResize=i(this._onResize,this),this._initEvents(),e.maxBounds&&this.setMaxBounds(e.maxBounds),void 0!==e.zoom&&(this._zoom=this._limitZoom(e.zoom)),e.center&&void 0!==e.zoom&&this.setView(U(e.center),e.zoom,{reset:!0}),this.callInitHooks(),this._zoomAnimated=oe&&gt&&!Et&&this.options.zoomAnimation,this._zoomAnimated&&(this._createAnimProxy(),Pe(this._proxy,ae,this._catchTransitionEnd,this)),this._addLayers(this.options.layers)},setView:function(t,e,r){if(e=void 0===e?this._zoom:this._limitZoom(e),t=this._limitCenter(U(t),e,this.options.maxBounds),r=r||{},this._stop(),this._loaded&&!r.reset&&!0!==r){void 0!==r.animate&&(r.zoom=n({animate:r.animate},r.zoom),r.pan=n({animate:r.animate,duration:r.duration},r.pan));var i=this._zoom!==e?this._tryAnimatedZoom&&this._tryAnimatedZoom(t,e,r.zoom):this._tryAnimatedPan(t,r.pan);if(i)return clearTimeout(this._sizeTimer),this}return this._resetView(t,e),this},setZoom:function(t,e){return this._loaded?this.setView(this.getCenter(),t,{zoom:e}):(this._zoom=t,this)},zoomIn:function(t,e){return t=t||(gt?this.options.zoomDelta:1),this.setZoom(this._zoom+t,e)},zoomOut:function(t,e){return t=t||(gt?this.options.zoomDelta:1),this.setZoom(this._zoom-t,e)},setZoomAround:function(t,e,n){var r=this.getZoomScale(e),i=this.getSize().divideBy(2),o=t instanceof P?t:this.latLngToContainerPoint(t),a=o.subtract(i).multiplyBy(1-1/r),s=this.containerPointToLatLng(i.add(a));return this.setView(s,e,{zoom:n})},_getBoundsCenterZoom:function(t,e){e=e||{},t=t.getBounds?t.getBounds():z(t);var n=B(e.paddingTopLeft||e.padding||[0,0]),r=B(e.paddingBottomRight||e.padding||[0,0]),i=this.getBoundsZoom(t,!1,n.add(r));if(i="number"===typeof e.maxZoom?Math.min(e.maxZoom,i):i,i===1/0)return{center:t.getCenter(),zoom:i};var o=r.subtract(n).divideBy(2),a=this.project(t.getSouthWest(),i),s=this.project(t.getNorthEast(),i),u=this.unproject(a.add(s).divideBy(2).add(o),i);return{center:u,zoom:i}},fitBounds:function(t,e){if(t=z(t),!t.isValid())throw new Error("Bounds are not valid.");var n=this._getBoundsCenterZoom(t,e);return this.setView(n.center,n.zoom,e)},fitWorld:function(t){return this.fitBounds([[-90,-180],[90,180]],t)},panTo:function(t,e){return this.setView(t,this._zoom,{pan:e})},panBy:function(t,e){if(t=B(t).round(),e=e||{},!t.x&&!t.y)return this.fire("moveend");if(!0!==e.animate&&!this.getSize().contains(t))return this._resetView(this.unproject(this.project(this.getCenter()).add(t)),this.getZoom()),this;if(this._panAnim||(this._panAnim=new Qe,this._panAnim.on({step:this._onPanTransitionStep,end:this._onPanTransitionEnd},this)),e.noMoveStart||this.fire("movestart"),!1!==e.animate){me(this._mapPane,"leaflet-pan-anim");var n=this._getMapPanePos().subtract(t).round();this._panAnim.run(this._mapPane,n,e.duration||.25,e.easeLinearity)}else this._rawPanBy(t),this.fire("move").fire("moveend");return this},flyTo:function(t,e,n){if(n=n||{},!1===n.animate||!gt)return this.setView(t,e,n);this._stop();var r=this.project(this.getCenter()),i=this.project(t),o=this.getSize(),a=this._zoom;t=U(t),e=void 0===e?a:e;var s=Math.max(o.x,o.y),u=s*this.getZoomScale(a,e),c=i.distanceTo(r)||1,l=1.42,h=l*l;function f(t){var e=t?-1:1,n=t?u:s,r=u*u-s*s+e*h*h*c*c,i=2*n*h*c,o=r/i,a=Math.sqrt(o*o+1)-o,l=a<1e-9?-18:Math.log(a);return l}function p(t){return(Math.exp(t)-Math.exp(-t))/2}function d(t){return(Math.exp(t)+Math.exp(-t))/2}function m(t){return p(t)/d(t)}var v=f(0);function g(t){return s*(d(v)/d(v+l*t))}function _(t){return s*(d(v)*m(v+l*t)-p(v))/h}function y(t){return 1-Math.pow(1-t,1.5)}var b=Date.now(),w=(f(1)-v)/l,x=n.duration?1e3*n.duration:1e3*w*.8;function k(){var n=(Date.now()-b)/x,o=y(n)*w;n<=1?(this._flyToFrame=S(k,this),this._move(this.unproject(r.add(i.subtract(r).multiplyBy(_(o)/c)),a),this.getScaleZoom(s/g(o),a),{flyTo:!0})):this._move(t,e)._moveEnd(!0)}return this._moveStart(!0,n.noMoveStart),k.call(this),this},flyToBounds:function(t,e){var n=this._getBoundsCenterZoom(t,e);return this.flyTo(n.center,n.zoom,e)},setMaxBounds:function(t){return t=z(t),t.isValid()?(this.options.maxBounds&&this.off("moveend",this._panInsideMaxBounds),this.options.maxBounds=t,this._loaded&&this._panInsideMaxBounds(),this.on("moveend",this._panInsideMaxBounds)):(this.options.maxBounds=null,this.off("moveend",this._panInsideMaxBounds))},setMinZoom:function(t){var e=this.options.minZoom;return this.options.minZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()<this.options.minZoom)?this.setZoom(t):this},setMaxZoom:function(t){var e=this.options.maxZoom;return this.options.maxZoom=t,this._loaded&&e!==t&&(this.fire("zoomlevelschange"),this.getZoom()>this.options.maxZoom)?this.setZoom(t):this},panInsideBounds:function(t,e){this._enforcingBounds=!0;var n=this.getCenter(),r=this._limitCenter(n,this._zoom,z(t));return n.equals(r)||this.panTo(r,e),this._enforcingBounds=!1,this},panInside:function(t,e){e=e||{};var n=B(e.paddingTopLeft||e.padding||[0,0]),r=B(e.paddingBottomRight||e.padding||[0,0]),i=this.getCenter(),o=this.project(i),a=this.project(t),s=this.getPixelBounds(),u=s.getSize().divideBy(2),c=I([s.min.add(n),s.max.subtract(r)]);if(!c.contains(a)){this._enforcingBounds=!0;var l=o.subtract(a),h=B(a.x+l.x,a.y+l.y);(a.x<c.min.x||a.x>c.max.x)&&(h.x=o.x-l.x,l.x>0?h.x+=u.x-n.x:h.x-=u.x-r.x),(a.y<c.min.y||a.y>c.max.y)&&(h.y=o.y-l.y,l.y>0?h.y+=u.y-n.y:h.y-=u.y-r.y),this.panTo(this.unproject(h),e),this._enforcingBounds=!1}return this},invalidateSize:function(t){if(!this._loaded)return this;t=n({animate:!1,pan:!0},!0===t?{animate:!0}:t);var e=this.getSize();this._sizeChanged=!0,this._lastCenter=null;var r=this.getSize(),o=e.divideBy(2).round(),a=r.divideBy(2).round(),s=o.subtract(a);return s.x||s.y?(t.animate&&t.pan?this.panBy(s):(t.pan&&this._rawPanBy(s),this.fire("move"),t.debounceMoveend?(clearTimeout(this._sizeTimer),this._sizeTimer=setTimeout(i(this.fire,this,"moveend"),200)):this.fire("moveend")),this.fire("resize",{oldSize:e,newSize:r})):this},stop:function(){return this.setZoom(this._limitZoom(this._zoom)),this.options.zoomSnap||this.fire("viewreset"),this._stop()},locate:function(t){if(t=this._locateOptions=n({timeout:1e4,watch:!1},t),!("geolocation"in navigator))return this._handleGeolocationError({code:0,message:"Geolocation not supported."}),this;var e=i(this._handleGeolocationResponse,this),r=i(this._handleGeolocationError,this);return t.watch?this._locationWatchId=navigator.geolocation.watchPosition(e,r,t):navigator.geolocation.getCurrentPosition(e,r,t),this},stopLocate:function(){return navigator.geolocation&&navigator.geolocation.clearWatch&&navigator.geolocation.clearWatch(this._locationWatchId),this._locateOptions&&(this._locateOptions.setView=!1),this},_handleGeolocationError:function(t){var e=t.code,n=t.message||(1===e?"permission denied":2===e?"position unavailable":"timeout");this._locateOptions.setView&&!this._loaded&&this.fitWorld(),this.fire("locationerror",{code:e,message:"Geolocation error: "+n+"."})},_handleGeolocationResponse:function(t){var e=t.coords.latitude,n=t.coords.longitude,r=new N(e,n),i=r.toBounds(2*t.coords.accuracy),o=this._locateOptions;if(o.setView){var a=this.getBoundsZoom(i);this.setView(r,o.maxZoom?Math.min(a,o.maxZoom):a)}var s={latlng:r,bounds:i,timestamp:t.timestamp};for(var u in t.coords)"number"===typeof t.coords[u]&&(s[u]=t.coords[u]);this.fire("locationfound",s)},addHandler:function(t,e){if(!e)return this;var n=this[t]=new e(this);return this._handlers.push(n),this.options[t]&&n.enable(),this},remove:function(){if(this._initEvents(!0),this.off("moveend",this._panInsideMaxBounds),this._containerId!==this._container._leaflet_id)throw new Error("Map container is being reused by another instance");try{delete this._container._leaflet_id,delete this._containerId}catch(e){this._container._leaflet_id=void 0,this._containerId=void 0}var t;for(t in void 0!==this._locationWatchId&&this.stopLocate(),this._stop(),le(this._mapPane),this._clearControlPos&&this._clearControlPos(),this._resizeRequest&&(C(this._resizeRequest),this._resizeRequest=null),this._clearHandlers(),this._loaded&&this.fire("unload"),this._layers)this._layers[t].remove();for(t in this._panes)le(this._panes[t]);return this._layers=[],this._panes=[],delete this._mapPane,delete this._renderer,this},createPane:function(t,e){var n="leaflet-pane"+(t?" leaflet-"+t.replace("Pane","")+"-pane":""),r=ce("div",n,e||this._mapPane);return t&&(this._panes[t]=r),r},getCenter:function(){return this._checkIfLoaded(),this._lastCenter&&!this._moved()?this._lastCenter:this.layerPointToLatLng(this._getCenterLayerPoint())},getZoom:function(){return this._zoom},getBounds:function(){var t=this.getPixelBounds(),e=this.unproject(t.getBottomLeft()),n=this.unproject(t.getTopRight());return new F(e,n)},getMinZoom:function(){return void 0===this.options.minZoom?this._layersMinZoom||0:this.options.minZoom},getMaxZoom:function(){return void 0===this.options.maxZoom?void 0===this._layersMaxZoom?1/0:this._layersMaxZoom:this.options.maxZoom},getBoundsZoom:function(t,e,n){t=z(t),n=B(n||[0,0]);var r=this.getZoom()||0,i=this.getMinZoom(),o=this.getMaxZoom(),a=t.getNorthWest(),s=t.getSouthEast(),u=this.getSize().subtract(n),c=I(this.project(s,r),this.project(a,r)).getSize(),l=gt?this.options.zoomSnap:1,h=u.x/c.x,f=u.y/c.y,p=e?Math.max(h,f):Math.min(h,f);return r=this.getScaleZoom(p,r),l&&(r=Math.round(r/(l/100))*(l/100),r=e?Math.ceil(r/l)*l:Math.floor(r/l)*l),Math.max(i,Math.min(o,r))},getSize:function(){return this._size&&!this._sizeChanged||(this._size=new P(this._container.clientWidth||0,this._container.clientHeight||0),this._sizeChanged=!1),this._size.clone()},getPixelBounds:function(t,e){var n=this._getTopLeftPoint(t,e);return new R(n,n.add(this.getSize()))},getPixelOrigin:function(){return this._checkIfLoaded(),this._pixelOrigin},getPixelWorldBounds:function(t){return this.options.crs.getProjectedBounds(void 0===t?this.getZoom():t)},getPane:function(t){return"string"===typeof t?this._panes[t]:t},getPanes:function(){return this._panes},getContainer:function(){return this._container},getZoomScale:function(t,e){var n=this.options.crs;return e=void 0===e?this._zoom:e,n.scale(t)/n.scale(e)},getScaleZoom:function(t,e){var n=this.options.crs;e=void 0===e?this._zoom:e;var r=n.zoom(t*n.scale(e));return isNaN(r)?1/0:r},project:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.latLngToPoint(U(t),e)},unproject:function(t,e){return e=void 0===e?this._zoom:e,this.options.crs.pointToLatLng(B(t),e)},layerPointToLatLng:function(t){var e=B(t).add(this.getPixelOrigin());return this.unproject(e)},latLngToLayerPoint:function(t){var e=this.project(U(t))._round();return e._subtract(this.getPixelOrigin())},wrapLatLng:function(t){return this.options.crs.wrapLatLng(U(t))},wrapLatLngBounds:function(t){return this.options.crs.wrapLatLngBounds(z(t))},distance:function(t,e){return this.options.crs.distance(U(t),U(e))},containerPointToLayerPoint:function(t){return B(t).subtract(this._getMapPanePos())},layerPointToContainerPoint:function(t){return B(t).add(this._getMapPanePos())},containerPointToLatLng:function(t){var e=this.containerPointToLayerPoint(B(t));return this.layerPointToLatLng(e)},latLngToContainerPoint:function(t){return this.layerPointToContainerPoint(this.latLngToLayerPoint(U(t)))},mouseEventToContainerPoint:function(t){return qe(t,this._container)},mouseEventToLayerPoint:function(t){return this.containerPointToLayerPoint(this.mouseEventToContainerPoint(t))},mouseEventToLatLng:function(t){return this.layerPointToLatLng(this.mouseEventToLayerPoint(t))},_initContainer:function(t){var e=this._container=se(t);if(!e)throw new Error("Map container not found.");if(e._leaflet_id)throw new Error("Map container is already initialized.");Pe(e,"scroll",this._onScroll,this),this._containerId=a(e)},_initLayout:function(){var t=this._container;this._fadeAnimated=this.options.fadeAnimation&&gt,me(t,"leaflet-container"+(kt?" leaflet-touch":"")+(Ct?" leaflet-retina":"")+(tt?" leaflet-oldie":"")+(lt?" leaflet-safari":"")+(this._fadeAnimated?" leaflet-fade-anim":""));var e=ue(t,"position");"absolute"!==e&&"relative"!==e&&"fixed"!==e&&(t.style.position="relative"),this._initPanes(),this._initControlPos&&this._initControlPos()},_initPanes:function(){var t=this._panes={};this._paneRenderers={},this._mapPane=this.createPane("mapPane",this._container),ke(this._mapPane,new P(0,0)),this.createPane("tilePane"),this.createPane("shadowPane"),this.createPane("overlayPane"),this.createPane("markerPane"),this.createPane("tooltipPane"),this.createPane("popupPane"),this.options.markerZoomAnimation||(me(t.markerPane,"leaflet-zoom-hide"),me(t.shadowPane,"leaflet-zoom-hide"))},_resetView:function(t,e){ke(this._mapPane,new P(0,0));var n=!this._loaded;this._loaded=!0,e=this._limitZoom(e),this.fire("viewprereset");var r=this._zoom!==e;this._moveStart(r,!1)._move(t,e)._moveEnd(r),this.fire("viewreset"),n&&this.fire("load")},_moveStart:function(t,e){return t&&this.fire("zoomstart"),e||this.fire("movestart"),this},_move:function(t,e,n){void 0===e&&(e=this._zoom);var r=this._zoom!==e;return this._zoom=e,this._lastCenter=t,this._pixelOrigin=this._getNewPixelOrigin(t),(r||n&&n.pinch)&&this.fire("zoom",n),this.fire("move",n)},_moveEnd:function(t){return t&&this.fire("zoomend"),this.fire("moveend")},_stop:function(){return C(this._flyToFrame),this._panAnim&&this._panAnim.stop(),this},_rawPanBy:function(t){ke(this._mapPane,this._getMapPanePos().subtract(t))},_getZoomSpan:function(){return this.getMaxZoom()-this.getMinZoom()},_panInsideMaxBounds:function(){this._enforcingBounds||this.panInsideBounds(this.options.maxBounds)},_checkIfLoaded:function(){if(!this._loaded)throw new Error("Set map center and zoom first.")},_initEvents:function(t){this._targets={},this._targets[a(this._container)]=this;var e=t?Be:Pe;e(this._container,"click dblclick mousedown mouseup mouseover mouseout mousemove contextmenu keypress keydown keyup",this._handleDOMEvent,this),this.options.trackResize&&e(window,"resize",this._onResize,this),gt&&this.options.transform3DLimit&&(t?this.off:this.on).call(this,"moveend",this._onMoveEnd)},_onResize:function(){C(this._resizeRequest),this._resizeRequest=S((function(){this.invalidateSize({debounceMoveend:!0})}),this)},_onScroll:function(){this._container.scrollTop=0,this._container.scrollLeft=0},_onMoveEnd:function(){var t=this._getMapPanePos();Math.max(Math.abs(t.x),Math.abs(t.y))>=this.options.transform3DLimit&&this._resetView(this.getCenter(),this.getZoom())},_findEventTargets:function(t,e){var n,r=[],i="mouseout"===e||"mouseover"===e,o=t.target||t.srcElement,s=!1;while(o){if(n=this._targets[a(o)],n&&("click"===e||"preclick"===e)&&!t._simulated&&this._draggableMoved(n)){s=!0;break}if(n&&n.listens(e,!0)){if(i&&!Xe(o,t))break;if(r.push(n),i)break}if(o===this._container)break;o=o.parentNode}return r.length||s||i||!Xe(o,t)||(r=[this]),r},_handleDOMEvent:function(t){if(this._loaded&&!Ke(t)){var e=t.type;"mousedown"!==e&&"keypress"!==e&&"keyup"!==e&&"keydown"!==e||Oe(t.target||t.srcElement),this._fireDOMEvent(t,e)}},_mouseEvents:["click","dblclick","mouseover","mouseout","contextmenu"],_fireDOMEvent:function(t,e,r){if("click"===t.type){var i=n({},t);i.type="preclick",this._fireDOMEvent(i,i.type,r)}if(!t._stopped&&(r=(r||[]).concat(this._findEventTargets(t,e)),r.length)){var o=r[0];"contextmenu"===e&&o.listens(e,!0)&&$e(t);var a={originalEvent:t};if("keypress"!==t.type&&"keydown"!==t.type&&"keyup"!==t.type){var s=o.getLatLng&&(!o._radius||o._radius<=10);a.containerPoint=s?this.latLngToContainerPoint(o.getLatLng()):this.mouseEventToContainerPoint(t),a.layerPoint=this.containerPointToLayerPoint(a.containerPoint),a.latlng=s?o.getLatLng():this.layerPointToLatLng(a.layerPoint)}for(var u=0;u<r.length;u++)if(r[u].fire(e,a,!0),a.originalEvent._stopped||!1===r[u].options.bubblingMouseEvents&&-1!==_(this._mouseEvents,e))return}},_draggableMoved:function(t){return t=t.dragging&&t.dragging.enabled()?t:this,t.dragging&&t.dragging.moved()||this.boxZoom&&this.boxZoom.moved()},_clearHandlers:function(){for(var t=0,e=this._handlers.length;t<e;t++)this._handlers[t].disable()},whenReady:function(t,e){return this._loaded?t.call(e||this,{target:this}):this.on("load",t,e),this},_getMapPanePos:function(){return Ee(this._mapPane)||new P(0,0)},_moved:function(){var t=this._getMapPanePos();return t&&!t.equals([0,0])},_getTopLeftPoint:function(t,e){var n=t&&void 0!==e?this._getNewPixelOrigin(t,e):this.getPixelOrigin();return n.subtract(this._getMapPanePos())},_getNewPixelOrigin:function(t,e){var n=this.getSize()._divideBy(2);return this.project(t,e)._subtract(n)._add(this._getMapPanePos())._round()},_latLngToNewLayerPoint:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return this.project(t,e)._subtract(r)},_latLngBoundsToNewLayerBounds:function(t,e,n){var r=this._getNewPixelOrigin(n,e);return I([this.project(t.getSouthWest(),e)._subtract(r),this.project(t.getNorthWest(),e)._subtract(r),this.project(t.getSouthEast(),e)._subtract(r),this.project(t.getNorthEast(),e)._subtract(r)])},_getCenterLayerPoint:function(){return this.containerPointToLayerPoint(this.getSize()._divideBy(2))},_getCenterOffset:function(t){return this.latLngToLayerPoint(t).subtract(this._getCenterLayerPoint())},_limitCenter:function(t,e,n){if(!n)return t;var r=this.project(t,e),i=this.getSize().divideBy(2),o=new R(r.subtract(i),r.add(i)),a=this._getBoundsOffset(o,n,e);return a.round().equals([0,0])?t:this.unproject(r.add(a),e)},_limitOffset:function(t,e){if(!e)return t;var n=this.getPixelBounds(),r=new R(n.min.add(t),n.max.add(t));return t.add(this._getBoundsOffset(r,e))},_getBoundsOffset:function(t,e,n){var r=I(this.project(e.getNorthEast(),n),this.project(e.getSouthWest(),n)),i=r.min.subtract(t.min),o=r.max.subtract(t.max),a=this._rebound(i.x,-o.x),s=this._rebound(i.y,-o.y);return new P(a,s)},_rebound:function(t,e){return t+e>0?Math.round(t-e)/2:Math.max(0,Math.ceil(t))-Math.max(0,Math.floor(e))},_limitZoom:function(t){var e=this.getMinZoom(),n=this.getMaxZoom(),r=gt?this.options.zoomSnap:1;return r&&(t=Math.round(t/r)*r),Math.max(e,Math.min(n,t))},_onPanTransitionStep:function(){this.fire("move")},_onPanTransitionEnd:function(){ve(this._mapPane,"leaflet-pan-anim"),this.fire("moveend")},_tryAnimatedPan:function(t,e){var n=this._getCenterOffset(t)._trunc();return!(!0!==(e&&e.animate)&&!this.getSize().contains(n))&&(this.panBy(n,e),!0)},_createAnimProxy:function(){var t=this._proxy=ce("div","leaflet-proxy leaflet-zoom-animated");this._panes.mapPane.appendChild(t),this.on("zoomanim",(function(t){var e=ie,n=this._proxy.style[e];xe(this._proxy,this.project(t.center,t.zoom),this.getZoomScale(t.zoom,1)),n===this._proxy.style[e]&&this._animatingZoom&&this._onZoomTransitionEnd()}),this),this.on("load moveend",this._animMoveEnd,this),this._on("unload",this._destroyAnimProxy,this)},_destroyAnimProxy:function(){le(this._proxy),this.off("load moveend",this._animMoveEnd,this),delete this._proxy},_animMoveEnd:function(){var t=this.getCenter(),e=this.getZoom();xe(this._proxy,this.project(t,e),this.getZoomScale(e,1))},_catchTransitionEnd:function(t){this._animatingZoom&&t.propertyName.indexOf("transform")>=0&&this._onZoomTransitionEnd()},_nothingToAnimate:function(){return!this._container.getElementsByClassName("leaflet-zoom-animated").length},_tryAnimatedZoom:function(t,e,n){if(this._animatingZoom)return!0;if(n=n||{},!this._zoomAnimated||!1===n.animate||this._nothingToAnimate()||Math.abs(e-this._zoom)>this.options.zoomAnimationThreshold)return!1;var r=this.getZoomScale(e),i=this._getCenterOffset(t)._divideBy(1-1/r);return!(!0!==n.animate&&!this.getSize().contains(i))&&(S((function(){this._moveStart(!0,!1)._animateZoom(t,e,!0)}),this),!0)},_animateZoom:function(t,e,n,r){this._mapPane&&(n&&(this._animatingZoom=!0,this._animateToCenter=t,this._animateToZoom=e,me(this._mapPane,"leaflet-zoom-anim")),this.fire("zoomanim",{center:t,zoom:e,noUpdate:r}),setTimeout(i(this._onZoomTransitionEnd,this),250))},_onZoomTransitionEnd:function(){this._animatingZoom&&(this._mapPane&&ve(this._mapPane,"leaflet-zoom-anim"),this._animatingZoom=!1,this._move(this._animateToCenter,this._animateToZoom),S((function(){this._moveEnd(!0)}),this))}});function en(t,e){return new tn(t,e)}var nn=O.extend({options:{position:"topright"},initialize:function(t){p(this,t)},getPosition:function(){return this.options.position},setPosition:function(t){var e=this._map;return e&&e.removeControl(this),this.options.position=t,e&&e.addControl(this),this},getContainer:function(){return this._container},addTo:function(t){this.remove(),this._map=t;var e=this._container=this.onAdd(t),n=this.getPosition(),r=t._controlCorners[n];return me(e,"leaflet-control"),-1!==n.indexOf("bottom")?r.insertBefore(e,r.firstChild):r.appendChild(e),this._map.on("unload",this.remove,this),this},remove:function(){return this._map?(le(this._container),this.onRemove&&this.onRemove(this._map),this._map.off("unload",this.remove,this),this._map=null,this):this},_refocusOnMap:function(t){this._map&&t&&t.screenX>0&&t.screenY>0&&this._map.getContainer().focus()}}),rn=function(t){return new nn(t)};tn.include({addControl:function(t){return t.addTo(this),this},removeControl:function(t){return t.remove(),this},_initControlPos:function(){var t=this._controlCorners={},e="leaflet-",n=this._controlContainer=ce("div",e+"control-container",this._container);function r(r,i){var o=e+r+" "+e+i;t[r+i]=ce("div",o,n)}r("top","left"),r("top","right"),r("bottom","left"),r("bottom","right")},_clearControlPos:function(){for(var t in this._controlCorners)le(this._controlCorners[t]);le(this._controlContainer),delete this._controlCorners,delete this._controlContainer}});var on=nn.extend({options:{collapsed:!0,position:"topright",autoZIndex:!0,hideSingleBase:!1,sortLayers:!1,sortFunction:function(t,e,n,r){return n<r?-1:r<n?1:0}},initialize:function(t,e,n){for(var r in p(this,n),this._layerControlInputs=[],this._layers=[],this._lastZIndex=0,this._handlingClick=!1,t)this._addLayer(t[r],r);for(r in e)this._addLayer(e[r],r,!0)},onAdd:function(t){this._initLayout(),this._update(),this._map=t,t.on("zoomend",this._checkDisabledLayers,this);for(var e=0;e<this._layers.length;e++)this._layers[e].layer.on("add remove",this._onLayerChange,this);return this._container},addTo:function(t){return nn.prototype.addTo.call(this,t),this._expandIfNotCollapsed()},onRemove:function(){this._map.off("zoomend",this._checkDisabledLayers,this);for(var t=0;t<this._layers.length;t++)this._layers[t].layer.off("add remove",this._onLayerChange,this)},addBaseLayer:function(t,e){return this._addLayer(t,e),this._map?this._update():this},addOverlay:function(t,e){return this._addLayer(t,e,!0),this._map?this._update():this},removeLayer:function(t){t.off("add remove",this._onLayerChange,this);var e=this._getLayer(a(t));return e&&this._layers.splice(this._layers.indexOf(e),1),this._map?this._update():this},expand:function(){me(this._container,"leaflet-control-layers-expanded"),this._section.style.height=null;var t=this._map.getSize().y-(this._container.offsetTop+50);return t<this._section.clientHeight?(me(this._section,"leaflet-control-layers-scrollbar"),this._section.style.height=t+"px"):ve(this._section,"leaflet-control-layers-scrollbar"),this._checkDisabledLayers(),this},collapse:function(){return ve(this._container,"leaflet-control-layers-expanded"),this},_initLayout:function(){var t="leaflet-control-layers",e=this._container=ce("div",t),n=this.options.collapsed;e.setAttribute("aria-haspopup",!0),Ze(e),Ue(e);var r=this._section=ce("section",t+"-list");n&&(this._map.on("click",this.collapse,this),rt||Pe(e,{mouseenter:this.expand,mouseleave:this.collapse},this));var i=this._layersLink=ce("a",t+"-toggle",e);i.href="#",i.title="Layers",kt?(Pe(i,"click",He),Pe(i,"click",this.expand,this)):Pe(i,"focus",this.expand,this),n||this.expand(),this._baseLayersList=ce("div",t+"-base",r),this._separator=ce("div",t+"-separator",r),this._overlaysList=ce("div",t+"-overlays",r),e.appendChild(r)},_getLayer:function(t){for(var e=0;e<this._layers.length;e++)if(this._layers[e]&&a(this._layers[e].layer)===t)return this._layers[e]},_addLayer:function(t,e,n){this._map&&t.on("add remove",this._onLayerChange,this),this._layers.push({layer:t,name:e,overlay:n}),this.options.sortLayers&&this._layers.sort(i((function(t,e){return this.options.sortFunction(t.layer,e.layer,t.name,e.name)}),this)),this.options.autoZIndex&&t.setZIndex&&(this._lastZIndex++,t.setZIndex(this._lastZIndex)),this._expandIfNotCollapsed()},_update:function(){if(!this._container)return this;he(this._baseLayersList),he(this._overlaysList),this._layerControlInputs=[];var t,e,n,r,i=0;for(n=0;n<this._layers.length;n++)r=this._layers[n],this._addItem(r),e=e||r.overlay,t=t||!r.overlay,i+=r.overlay?0:1;return this.options.hideSingleBase&&(t=t&&i>1,this._baseLayersList.style.display=t?"":"none"),this._separator.style.display=e&&t?"":"none",this},_onLayerChange:function(t){this._handlingClick||this._update();var e=this._getLayer(a(t.target)),n=e.overlay?"add"===t.type?"overlayadd":"overlayremove":"add"===t.type?"baselayerchange":null;n&&this._map.fire(n,e)},_createRadioElement:function(t,e){var n='<input type="radio" class="leaflet-control-layers-selector" name="'+t+'"'+(e?' checked="checked"':"")+"/>",r=document.createElement("div");return r.innerHTML=n,r.firstChild},_addItem:function(t){var e,n=document.createElement("label"),r=this._map.hasLayer(t.layer);t.overlay?(e=document.createElement("input"),e.type="checkbox",e.className="leaflet-control-layers-selector",e.defaultChecked=r):e=this._createRadioElement("leaflet-base-layers_"+a(this),r),this._layerControlInputs.push(e),e.layerId=a(t.layer),Pe(e,"click",this._onInputClick,this);var i=document.createElement("span");i.innerHTML=" "+t.name;var o=document.createElement("div");n.appendChild(o),o.appendChild(e),o.appendChild(i);var s=t.overlay?this._overlaysList:this._baseLayersList;return s.appendChild(n),this._checkDisabledLayers(),n},_onInputClick:function(){var t,e,n=this._layerControlInputs,r=[],i=[];this._handlingClick=!0;for(var o=n.length-1;o>=0;o--)t=n[o],e=this._getLayer(t.layerId).layer,t.checked?r.push(e):t.checked||i.push(e);for(o=0;o<i.length;o++)this._map.hasLayer(i[o])&&this._map.removeLayer(i[o]);for(o=0;o<r.length;o++)this._map.hasLayer(r[o])||this._map.addLayer(r[o]);this._handlingClick=!1,this._refocusOnMap()},_checkDisabledLayers:function(){for(var t,e,n=this._layerControlInputs,r=this._map.getZoom(),i=n.length-1;i>=0;i--)t=n[i],e=this._getLayer(t.layerId).layer,t.disabled=void 0!==e.options.minZoom&&r<e.options.minZoom||void 0!==e.options.maxZoom&&r>e.options.maxZoom},_expandIfNotCollapsed:function(){return this._map&&!this.options.collapsed&&this.expand(),this},_expand:function(){return this.expand()},_collapse:function(){return this.collapse()}}),an=function(t,e,n){return new on(t,e,n)},sn=nn.extend({options:{position:"topleft",zoomInText:"+",zoomInTitle:"Zoom in",zoomOutText:"&#x2212;",zoomOutTitle:"Zoom out"},onAdd:function(t){var e="leaflet-control-zoom",n=ce("div",e+" leaflet-bar"),r=this.options;return this._zoomInButton=this._createButton(r.zoomInText,r.zoomInTitle,e+"-in",n,this._zoomIn),this._zoomOutButton=this._createButton(r.zoomOutText,r.zoomOutTitle,e+"-out",n,this._zoomOut),this._updateDisabled(),t.on("zoomend zoomlevelschange",this._updateDisabled,this),n},onRemove:function(t){t.off("zoomend zoomlevelschange",this._updateDisabled,this)},disable:function(){return this._disabled=!0,this._updateDisabled(),this},enable:function(){return this._disabled=!1,this._updateDisabled(),this},_zoomIn:function(t){!this._disabled&&this._map._zoom<this._map.getMaxZoom()&&this._map.zoomIn(this._map.options.zoomDelta*(t.shiftKey?3:1))},_zoomOut:function(t){!this._disabled&&this._map._zoom>this._map.getMinZoom()&&this._map.zoomOut(this._map.options.zoomDelta*(t.shiftKey?3:1))},_createButton:function(t,e,n,r,i){var o=ce("a",n,r);return o.innerHTML=t,o.href="#",o.title=e,o.setAttribute("role","button"),o.setAttribute("aria-label",e),Ze(o),Pe(o,"click",He),Pe(o,"click",i,this),Pe(o,"click",this._refocusOnMap,this),o},_updateDisabled:function(){var t=this._map,e="leaflet-disabled";ve(this._zoomInButton,e),ve(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMinZoom())&&me(this._zoomOutButton,e),(this._disabled||t._zoom===t.getMaxZoom())&&me(this._zoomInButton,e)}});tn.mergeOptions({zoomControl:!0}),tn.addInitHook((function(){this.options.zoomControl&&(this.zoomControl=new sn,this.addControl(this.zoomControl))}));var un=function(t){return new sn(t)},cn=nn.extend({options:{position:"bottomleft",maxWidth:100,metric:!0,imperial:!0},onAdd:function(t){var e="leaflet-control-scale",n=ce("div",e),r=this.options;return this._addScales(r,e+"-line",n),t.on(r.updateWhenIdle?"moveend":"move",this._update,this),t.whenReady(this._update,this),n},onRemove:function(t){t.off(this.options.updateWhenIdle?"moveend":"move",this._update,this)},_addScales:function(t,e,n){t.metric&&(this._mScale=ce("div",e,n)),t.imperial&&(this._iScale=ce("div",e,n))},_update:function(){var t=this._map,e=t.getSize().y/2,n=t.distance(t.containerPointToLatLng([0,e]),t.containerPointToLatLng([this.options.maxWidth,e]));this._updateScales(n)},_updateScales:function(t){this.options.metric&&t&&this._updateMetric(t),this.options.imperial&&t&&this._updateImperial(t)},_updateMetric:function(t){var e=this._getRoundNum(t),n=e<1e3?e+" m":e/1e3+" km";this._updateScale(this._mScale,n,e/t)},_updateImperial:function(t){var e,n,r,i=3.2808399*t;i>5280?(e=i/5280,n=this._getRoundNum(e),this._updateScale(this._iScale,n+" mi",n/e)):(r=this._getRoundNum(i),this._updateScale(this._iScale,r+" ft",r/i))},_updateScale:function(t,e,n){t.style.width=Math.round(this.options.maxWidth*n)+"px",t.innerHTML=e},_getRoundNum:function(t){var e=Math.pow(10,(Math.floor(t)+"").length-1),n=t/e;return n=n>=10?10:n>=5?5:n>=3?3:n>=2?2:1,e*n}}),ln=function(t){return new cn(t)},hn=nn.extend({options:{position:"bottomright",prefix:'`
  
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script type="module" src="/js/chunk-vendors.c4f869d9.js"></script>`
  
  
  
  
Instances: 4
  
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
  
  
  
* URL: [https://camino.beta.gouv.fr/robots.txt](https://camino.beta.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/sitemap.xml](https://camino.beta.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/a-propos.](https://camino.beta.gouv.fr/a-propos.)
  
  
  * Method: `GET`
  
  
  
  
Instances: 3
  
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

  
  
  
  
### Storable but Non-Cacheable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are storable by caching components such as proxy servers, but will not be retrieved directly from the cache, without validating the request upstream, in response to similar requests from other users. </p>
  
  
  
* URL: [https://camino.beta.gouv.fr/](https://camino.beta.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/app.0a849ec7.js](https://camino.beta.gouv.fr/js/app.0a849ec7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/favicon.ico](https://camino.beta.gouv.fr/favicon.ico)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js](https://camino.beta.gouv.fr/js/chunk-vendors-legacy.61b722ca.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/stats.8edffcf7.js](https://camino.beta.gouv.fr/js/stats.8edffcf7.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://camino.beta.gouv.fr](https://camino.beta.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
Instances: 8
  
### Solution
<p></p>
  
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
  
  
  
* URL: [https://camino.beta.gouv.fr/css/app.bd9c7934.css](https://camino.beta.gouv.fr/css/app.bd9c7934.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `70710678`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `23592600`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `2147483647`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `40075017`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `16777216`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `15496570`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `20037508`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `1073741823`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `0511287798`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `314245179`
  
  
  
  
* URL: [https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js](https://camino.beta.gouv.fr/js/chunk-vendors.c4f869d9.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `18764656`
  
  
  
  
Instances: 11
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>70710678, which evaluates to: 1972-03-29 09:51:18</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3
