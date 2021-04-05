
# ZAP Scanning Report

Generated on Mon, 5 Apr 2021 01:55:23


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 4 |
| Low | 10 |
| Informational | 8 |

## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- | 
| CSP: style-src unsafe-inline | Medium | 3 | 
| CSP: Wildcard Directive | Medium | 3 | 
| Reverse Tabnabbing | Medium | 7 | 
| Sub Resource Integrity Attribute Missing | Medium | 1 | 
| Cookie No HttpOnly Flag | Low | 3 | 
| Cookie Without SameSite Attribute | Low | 13 | 
| Cookie Without Secure Flag | Low | 13 | 
| CSP: Notices | Low | 3 | 
| Dangerous JS Functions | Low | 1 | 
| Feature Policy Header Not Set | Low | 11 | 
| Incomplete or No Cache-control and Pragma HTTP Header Set | Low | 11 | 
| Server Leaks Information via "X-Powered-By" HTTP Response Header Field(s) | Low | 11 | 
| Strict-Transport-Security Multiple Header Entries (Non-compliant with Spec) | Low | 11 | 
| X-Content-Type-Options Header Missing | Low | 11 | 
| Base64 Disclosure | Informational | 11 | 
| Information Disclosure - Suspicious Comments | Informational | 13 | 
| Modern Web Application | Informational | 3 | 
| Non-Storable Content | Informational | 2 | 
| Storable and Cacheable Content | Informational | 7 | 
| Storable but Non-Cacheable Content | Informational | 2 | 
| Timestamp Disclosure - Unix | Informational | 1916 | 

## Alert Detail


  
  
  
  
### CSP: style-src unsafe-inline
##### Medium (Medium)
  
  
  
  
#### Description
<p>style-src includes unsafe-inline.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
Instances: 3
  
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

  
  
  
  
### CSP: Wildcard Directive
##### Medium (Medium)
  
  
  
  
#### Description
<p>The following directives either allow wildcard sources (or ancestors), are not defined, or are overly broadly defined: </p><p>form-action</p><p></p><p>The directive(s): form-action are among the directives that do not fallback to default-src, missing/excluding them is the same as allowing anything.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
Instances: 3
  
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

  
  
  
  
### Reverse Tabnabbing
##### Medium (Medium)
  
  
  
  
#### Description
<p>At least one link on this page is vulnerable to Reverse tabnabbing as it uses a target attribute without using both of the "noopener" and "noreferrer" keywords in the "rel" attribute, which allows the target page to take control of this page.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a target="_blank" rel="noopener" href="https://stats.data.gouv.fr/index.php?module=CoreHome&action=index&date=yesterday&period=day&idSite=160#?idSite=160&period=day&date=yesterday&segment=&category=Dashboard_Dashboard&subcategory=1">stats.data.gouv.fr</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a title="Voir le code source"
               href="https://github.com/betagouv/sante-psy"
               target="_blank"
               rel="noopener"
               >Voir le code source</a>`
  
  
  
  
Instances: 7
  
### Solution
<p>Do not use a target attribute, or if you have to then also add the attribute: rel="noopener noreferrer".</p>
  
### Reference
* https://owasp.org/www-community/attacks/Reverse_Tabnabbing
* https://dev.to/ben/the-targetblank-vulnerability-by-example
* https://mathiasbynens.github.io/rel-noopener/
* https://medium.com/@jitbit/target-blank-the-most-underestimated-vulnerability-ever-96e328301f4c

  
#### Source ID : 3

  
  
  
  
### Sub Resource Integrity Attribute Missing
##### Medium (High)
  
  
  
  
#### Description
<p>The integrity attribute is missing on a script or link tag served by an external server. The integrity tag prevents an attacker who have gained access to this server from injecting a malicious content. </p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="' + scripts[distGlobal_i] + '">`
  
  
  
  
Instances: 1
  
### Solution
<p>Provide a valid integrity attribute to the tag.</p>
  
### Reference
* https://developer.mozilla.org/en/docs/Web/Security/Subresource_Integrity

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### Cookie No HttpOnly Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the HttpOnly flag, which means that the cookie can be accessed by JavaScript. If a malicious script can be run on this page then the cookie will be accessible and can be transmitted to another site. If this is a session cookie then session hijacking may be possible.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
Instances: 3
  
### Solution
<p>Ensure that the HttpOnly flag is set for all cookies.</p>
  
### Reference
* https://owasp.org/www-community/HttpOnly

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie Without SameSite Attribute
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the SameSite attribute, which means that the cookie can be sent as a result of a 'cross-site' request. The SameSite attribute is an effective counter measure to cross-site request forgery, cross-site script inclusion, and timing attacks.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
Instances: 13
  
### Solution
<p>Ensure that the SameSite attribute is set to either 'lax' or ideally 'strict' for all cookies.</p>
  
### Reference
* https://tools.ietf.org/html/draft-ietf-httpbis-cookie-same-site

  
#### CWE Id : 16
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Cookie Without Secure Flag
##### Low (Medium)
  
  
  
  
#### Description
<p>A cookie has been set without the secure flag, which means that the cookie can be accessed via unencrypted connections.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `_csrf`
  
  
  * Evidence: `Set-Cookie: _csrf`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess.sig`
  
  
  * Evidence: `Set-Cookie: express:sess.sig`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `express:sess`
  
  
  * Evidence: `Set-Cookie: express:sess`
  
  
  
  
Instances: 13
  
### Solution
<p>Whenever a cookie contains sensitive information or is a session token, then it should always be passed using an encrypted channel. Ensure that the secure flag is set for cookies containing such sensitive information.</p>
  
### Reference
* https://owasp.org/www-project-web-security-testing-guide/v41/4-Web_Application_Security_Testing/06-Session_Management_Testing/02-Testing_for_Cookies_Attributes.html

  
#### CWE Id : 614
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### CSP: Notices
##### Low (Medium)
  
  
  
  
#### Description
<p>Warnings:</p><p>1:36: The block-all-mixed-content directive is an experimental directive that will be likely added to the CSP specification.</p><p>1:288: The upgrade-insecure-requests directive is an experimental directive that will be likely added to the CSP specification.</p><p></p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Content-Security-Policy`
  
  
  * Evidence: `default-src 'self';base-uri 'self';block-all-mixed-content;font-src 'self' https: data:;frame-ancestors 'self';img-src 'self' https://stats.data.gouv.fr/ data:;object-src 'none';script-src 'self' https://stats.data.gouv.fr/;script-src-attr 'none';style-src 'self' https: 'unsafe-inline';upgrade-insecure-requests`
  
  
  
  
Instances: 3
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/tabulator-tables/js/tabulator.min.js](https://santepsy.etudiant.gouv.fr/static/tabulator-tables/js/tabulator.min.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `eVal`
  
  
  
  
Instances: 1
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js](https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/matomo.js](https://santepsy.etudiant.gouv.fr/static/js/matomo.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/tabulator-tables/js/tabulator.min.js](https://santepsy.etudiant.gouv.fr/static/tabulator-tables/js/tabulator.min.js)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/images/illustration_sante_psy.svg](https://santepsy.etudiant.gouv.fr/static/images/illustration_sante_psy.svg)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/css/custom.css](https://santepsy.etudiant.gouv.fr/static/css/custom.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/tabulator-tables/css/tabulator_modern.min.css](https://santepsy.etudiant.gouv.fr/static/tabulator-tables/css/tabulator_modern.min.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `Cache-Control`
  
  
  * Evidence: `public, max-age=0`
  
  
  
  
Instances: 11
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `X-Powered-By: Express`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/css/custom.css](https://santepsy.etudiant.gouv.fr/static/css/custom.css)
  
  
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

  
  
  
  
### Strict-Transport-Security Multiple Header Entries (Non-compliant with Spec)
##### Low (High)
  
  
  
  
#### Description
<p>HTTP Strict Transport Security (HSTS) headers were found, a response with multiple HSTS header entries is not compliant with the specification (RFC 6797) and only the first HSTS header will be processed others will be ignored by user agents or the HSTS policy may be incorrectly applied.</p><p>HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTPS connections (i.e. HTTP layered over TLS/SSL).</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/css/custom.css](https://santepsy.etudiant.gouv.fr/static/css/custom.css)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  
  
Instances: 11
  
### Solution
<p>Ensure that only one component in your stack: code, web server, application server, load balancer, etc. is configured to set or add a HTTP Strict-Transport-Security (HSTS) header.</p>
  
### Reference
* http://tools.ietf.org/html/rfc6797#section-8.1

  
#### CWE Id : 16
  
#### WASC Id : 15
  
#### Source ID : 3

  
  
  
  
### X-Content-Type-Options Header Missing
##### Low (Medium)
  
  
  
  
#### Description
<p>The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/matomo.js](https://santepsy.etudiant.gouv.fr/static/js/matomo.js)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/css/custom.css](https://santepsy.etudiant.gouv.fr/static/css/custom.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/images/favicon/favicon-32x32.png](https://santepsy.etudiant.gouv.fr/static/images/favicon/favicon-32x32.png)
  
  
  * Method: `GET`
  
  
  * Parameter: `X-Content-Type-Options`
  
  
  
  
Instances: 11
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `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`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Evidence: `18f2-ogmBYv5w9gMWOOZRNHR5dBDijAA`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Evidence: `1c5f-sozUmciNyelX+wgKCbGjy3JQYsc`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `27c4-3qbf4Z7py27BjtDq3RU24DYYV9s`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `27c4-3qbf4Z7py27BjtDq3RU24DYYV9s`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Evidence: `8194-OB6rpeiRlHdGb5IjwA+xrRE8zec`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `eyJmbGFzaCI6eyJlcnJvciI6WyJDZXR0ZSBwYWdlIG4nZXhpc3RlIHBhcy4iXX19`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Evidence: `1e12-hIKMIDLLgpnyioCLl8XnWdToisU`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `com/Emilie-Le-Pabic-Psychologue-Clinicienne-105809558170029`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/images/flyer_etudiants.pdf](https://santepsy.etudiant.gouv.fr/static/images/flyer_etudiants.pdf)
  
  
  * Method: `GET`
  
  
  * Evidence: `60/Type/FontDescriptor/XHeight`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `eyJmbGFzaCI6eyJlcnJvciI6WyJDZXR0ZSBwYWdlIG4nZXhpc3RlIHBhcy4iXX19`
  
  
  
  
Instances: 11
  
### Solution
<p>Manually confirm that the Base64 data does not leak sensitive information, and that the data cannot be aggregated/used to exploit other vulnerabilities.</p>
  
### Other information
<p>wOFF\x0000\x0001\x0000\x0000\x0000\x0000\x0015D\x0000\x000b\x0000\x0000\x0000\x0000,�\x0000\x0001\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000GSUB\x0000\x0000\x0001\x0008\x0000\x0000\x0000;\x0000\x0000\x0000T �%zOS/2\x0000\x0000\x0001D\x0000\x0000\x0000A\x0000\x0000\x0000VI�N�cmap\x0000\x0000\x0001�\x0000\x0000\x0001n\x0000\x0000\x00056���glyf\x0000\x0000\x0002�\x0000\x0000\x000e\x001a\x0000\x0000\x001d�\x000c�8�head\x0000\x0000\x0011\x0014\x0000\x0000\x00000\x0000\x0000\x00006\x001b�\x0011Phhea\x0000\x0000\x0011D\x0000\x0000\x0000\x001e\x0000\x0000\x0000$\x0008p\x0004\x0008hmtx\x0000\x0000\x0011d\x0000\x0000\x0000\x0011\x0000\x0000\x0001\x001cH \x0000\x0000loca\x0000\x0000\x0011x\x0000\x0000\x0000�\x0000\x0000\x0000���maxp\x0000\x0000\x0012\x0008\x0000\x0000\x0000\x001f\x0000\x0000\x0000 \x0001V\x0000Yname\x0000\x0000\x0012(\x0000\x0000\x0001\x001d\x0000\x0000\x0001�\x0014���post\x0000\x0000\x0013H\x0000\x0000\x0001�\x0000\x0000\x0004���Tkx�c`d``�b0`�c`rq�	a��I,�c�b`a�\x0000�<2�1'3=��\x0003�\x0003ʱ�i\x000e f��\x0002\x0000&;\x0005H\x0000x�c`d��8��������\x0003H���L\x000e\x000cV��@����\x0001+\x0008HsMap���э��\x0001�\x001c�\x0003\x000c\x001f� 9\x0000y@\x000b
\x0000\x0000\x0000x����m�@\x0000\x0005�E�I�9�s�6kp�W��r\x000f����]\x0019G��\x0001\x0017L�.�n�Y;�\x0015������z�љo�ߙ/�ӹ�p�*~��X�\x0017�������آ�^���\x0006h3�\x0010Ì0�\x0018�L0�\x0014��0�\x001c�,��\x0012ˬ��\x001a�l��\x0016���\x001e���\x000f9�\x0013N9�\x000b.��\x001bn��\x0007\x001ey�\x0017^y�\x000f>)�i��h;4�����WtV�+��p'TE��Uw�K�V`{\x0002�\x001bؾ�����\x001a\x0008l;��j0�C�\x001d\x000e�H`G\x0003;\x0016���N\x0004v2�S��\x000e�L`g\x0003;\x0017���.\x0004v1�K�]\x000e�J`W\x0003�\x0016���n\x0004v3�[��\x000e�N`w\x0003�\x0017���\x001e�|u\x0018أ�\x001e\x0007�$���=\x000b�y`/\x0002{\x0019ث�^\x0007�&����\x000b�}`\x001f\x0002�\x0018ا�>\x0007�%���}\x000b�{`?\x0002�\x0019�2(\x0001�ԵD\x0000\x0000x��Y\x000bl[g\x0015����<����K����q��a���rZŹN�Gh��ЦY;�f\x001dc���ѭPM���бʠ�G���д\x0002�xT02	\x000c�xH�\x001a�@\x0015Hӄ�@\x0010�`�;����Wꔔ������?�;�?�;�!\x0002!\x001f\x001f0m\x0014v\x0010;q�5�@HvȎ\x0015f�,�\x0003��E,\x001a�</p><p>x)��6���P\x001c�p`\x0001�\x000b�؉\x0003�\x0006\x0013��}\x0007���F3ݛ���2r��3�~�����Qv\x0010�K\x001f�\x0015l��u{{Gg��z\x0006\x0006f�\x0007�@*JpE� �HH�7�ȝGل\x0003\x000e�\x0002�@�:d�\x001bh��ߌ\x0017D|���\x0006]q\x0008��n�@(����vG\x0011r\x001d\x0008\x0007wt���O�'Cǟ�r�P���_^�[[��\x001bw���f��\x001f\x0006�����g�!\x001a��\x001d��}|�\x0010n�z��\x000eG׭�/2<�^\x0018Z;��\x001a�x��X�����]�'bH���Č�\x0012B</p><p>�Q�vGp="a),�$_�\x0017�/g�-L�����vv���tZMg��x��\x001d�"�Xdێ˹\x0001�a\x000f����r��%��\x0001�"\x000c�y�3�I�\x0016�y$��g�DP3�j\x0017U�"��
ZUn�\x000b�Ia�؈DV\x0011R\x0005\x000e\\x000e��-N\x000cpy\x001c�\x0014��/=\x0006�\x0016�na�ne�\x0019�5�
+�TU\x0015V/����a�8\x001ak��\x001a�%{���D&à�����J�XN\x0003x@@_��[N�v�P�=\x0014R��Z�\x001d���S��\x000c���w�?�yRIH\x0013�U\x0010C\x000fГP��\x001e�\x001eNB��u6>\x0002�\x0015�_t'ç�+E�XdC�͡c�Cڛڬ\x0002mW��,ē�s\x001f�Yx�~�d\x0003:\x0015�U �	�3{��G�pF��p\x001c�'	�r\x000f����*�\x0012�\x0006�Y6\x0003�R����G��t�\x0018=��:�@�=��9G_F,l�d��\x0013@H\x0001�zF�ހ��vQ?g`OF��8���\x001bJ&o�D_����e�\x0000{�*�\x000fqe�-(�</p><p>\x0002��\x0008AmN���Ou�g1H</p><p>^�c;V�\x0007#\x000b͑Ap��\x000c�\x0007����\x000e�1�	0MM�\x0008�f�\x00117�\x001b\x0003��/nɆ�q���6����L�6���+�,\x000e�v3l�\x001ef\x000cƼ��F��v�E�_�-8�D2ּ\x0010'le\x0000}l�'�G����]�?��\x001dJ>F:8\x000e3x�p'�\x0018�t{1�7	��\x0006B�=6��a�@8�p"��h/�
O$�</p><p>�;��#��~���\x000b+�R\x001a�S�3Z\r:%a�)e2�\x0013#���\x0017�{��L|$�\x0018P��\x0013n+H5{\x0018\x001d�\x0008iI��<�h�Icz\x000c\x0005��jJp����\x0015�-�ƛW�B7W�V9=i{u�M"M1��\����쇘\x0018�����\x000fxb\x0014ש i_�\x0016���X &c����2\�{Q��\x0006�,��a����\x00144\x000c/�\x0017�\x0011|�1��\x0001s�\x0001].�����i�S��S��r�¥ie\x001a��D�n���1�k8'�Q0f�h^��U�#\x000c�W�y\x001c��y�۹\x001f�\x001c��80Bͅ�/\x0012�xXβ�0�Q�R6�+��9m/�;�W��`q@?�\x0010yN�\x000b�����b�NV�<R�p��U�m�z��\x0004����\x0016�a�\x001a�"\x001d�\x0004�������&�!�ZBbȮU9�N	�\x0016�`�u(ژ�u\x0018��j\x0015N@��m��\x0015�M�\x0000�o'�Ă��@4t3V\x00193'��\�}֠e�j]�;���~[��R�.��k;�o"VR��=\x0000��H�:�OR���&7[��β�&E��\x0016\x000bʴfw��\x0014lZM>��\x0000$V��E9\x001bnBǡ\x001e<�e���c���W��\x0014x�=z\x001a�*�]�.;)9�]��;j��\x001e��\x000fc\x001d�\x000bd�\�Y�\x0015�X���u̟\x000fl��g^i�U�7\x001e?���}�������=;�\x000f���u\x0003�w��0�\x0013����#�\x0010�v{��	v\x0010V���}���=}��5�#[v��2Һ�0��1\x0015\x000f�1\x0015\x000f���\x0003�z��\x0011\x0017iB��0gE�nP ���\x001aJ\x0017��\x0002\x0016hÓ\x001c\x0010]4V\x0011�VS0\x0007�.*�f��Y��\x0001�o�yeՊ;�=�\x0014��|>�Jx�*�x�w;&['w��i��9�5��\x000b�\x000f����}}�����)�c��ݱ=�\x0015*�K\x000f\��֧��J.x���;�\x001f\x001c����5]��5��vN���9���ղ/9|����U#kV<���_�\x0017~N���\x001dz\x001c�75 ��!\x0003aU.\x000e\x0001�D\x001d\x0013ܙ\x001c\x000fì�J���\x000cK\x001f\x000c�c�S�M��8\x001d'"�	���9\x0010��cH�6_\x0013</p><p>��x�.��DA)��Zz!�}	ch,c�s05��I\��W$'j�[�N�\x0014�h\x001ccJb�+\x0014��<�R\x0013@�1)\x0005�(a�ו+�:k\x00064�ݪW\x0019�E�\x0017x㗳{\x001c�ƌ�\x0007OQ���`CIԯ�A�\x0013\x0019z�v�\x0004�<�d/\x000b���\x0011\x0017�Ln�Ƌz\x0000���\x001e�]l�b���ۂ(R\x0010n</p><p>�j�k�	��#\x000f��.���gkU�l'c�!���z�`\x0007̶(��\x0012g\x001b�\x001eK���3\I���:��\x000c\x0007���4j��"绸��\x0014���)\x0001�;�Z�r��Ȱe+\x000e��^?�{	SI=\C:o�"�
\x000fr��k��\x0014�2E\x0010�/�N</p><p>������NK�~����[b�\x001c���	2۩�\x000f�b�)�:�FF<:�֡\x000e�?�\x0010{����V�#\x0003c8t\x0017��\x001e�+\x0014J�\x001f\x001cܟ\x0008��f*���Hh�_(*x
�|�G�\x0004\x0012V�XхV\x000eiI@�<�i8�\x0003fԔ���V#?K�T�-I �\x0002�H"����\x000e\x001e�#�J;=m3�ب}\x001f�7\x001a��&�\x0005e�1毑ZQ\x00056O\x0015-\x0016+ܣ\x001d�>+�\x00172p\x0018\x000e����=
j��h�wa����n�^[ f���c-�}xq�cٗ�y^��gYsr��9\x0007Ў��O�\x0005*���OK&�I�@�k�Ϧ�/\x0004�GZn�\x0004y��\x0004��(
\x001e�sܻ\x0014��E\e�5\x0000��,���%�TS=WUU�)/�5�ڏ�j*�3�$.�\x000b��\x0010��\x000e�\x0015D�[X�Ţ�\x0011�\uu�Ƞ.�S�\x0019�T1#��J�!n\x0001)�Fև�X_\x0019�c�5a��3jM.9�1�'��c=/r�X6��J\x000bˉT��4ց\x00070H3z���\x000es����R*%aC]����x��n��*O�e�^g�Z@�ӳ��� ���\x000fؗ�Pk��J�:s�\x0002ͨ\x000bW�z����JU�\x0017�^1�?��Hs�</p><p>�\x0007��He\x000f�R0�.�U\x001dKE�\x0014�
2m\x0013�]���¶��\x0015\x0011�\x0012ū����}��
]�wWt��M-.�QvE\x0011�:Z۳��DP�\x000bڝ��5}�NiC����Ў\x0014]\x0017�-4�\x0015{�6\x0010ًK\x00173��*�Sr���=��ʮ
w\x000c��4�\x0005�\x001b�\x0019��{��l�[S�uڃ�n\x0011�C�o�%�z\x0004\x001f	/aY\x000c�\x000bf\x0019;`�W\x001f\x0010�h$���K�����xL���\x00177vv�3}���\x001ev�2.�\x0005�Q�3�O���l]U�|n@{s�&~6���>�i�p\x001f_\x0003\x0002,�qg�@tB��M����\x0000{\x0017���}v�\x0010Ž���\x0007\x000f�j�5y6���מ~���O\x001c>t�\x000b?h	Z���������������np�<�/N�o�N�66�\/��#�ڟ>���\x0001�\x0015������*��e�'\x0013{Or,����0��,/����KZ�m̐��Z�dU\x0012\x0007�	s\x0014�aC�	�⎔g!R�:��m����\x0011��Z�\x0008��Oe\x0013�;ml�܌#X���K�6����Dٸ�g\x0019�V��Ͱ�£��K��6=t�d_��sl\x0010~\x0004�v���ࡍO\x0018k��l��Ts\x001cy�4\x001b�ߍ��䥾k���\x0008��\x0019ެ$�v>�O�/\x0002���y4��i����{��p�y��wl��	8���!���4�N�"��\x0008���M�G�;:�h\x000e\x0006�\x0013C��
\x001e�g��0[r�\x000fry��ɤ\x0015ٷD������K��\x0005(*jP�SP\x0003�^\x000bj��Ǌ"|[\x0014����\x001cR��w	�G?��Ԋ��T\-�\x0018�b���?�T\x0011`��\x000f��\x0012��\x000b�,�f�J��UV�YDm\x001e��l</p><p>�[�{�:\x001bϲ���������\x000b�U֊��{�p��#�\x001a�[�\x000e'�{\x000c�+��b��\x0019�\x0005r`Y\x0018��W���W~u} t�c��\x0002�A���U�\x0007�R~X\x0003��x1\x0019��ꦗ�%ϝS^{M9w.Y�\x000b��]�O�>x��A��}P�n	\x0007��X�\x0003�Ht\x001cG�8�Zn$4-</p><p>�r>�I\x000e�lݜ\x001c��h�2�#H~�\���ݯ�Mn~�����Q��\x0019S\x001e�\x001e3=7\x00165��.��%@/���#�/A\x0011H8\x0000\x0000x�c`d``\x0000⥎=O��m�2p�l\x0000�0�~��������c�\x0003r9\x0018�@�\x0000e	\x000ccx�c`d``>�_���e\x0003\x0003\x0010��c`d@\x0005�\x0000V�\x0003�\x0000\x0000x�c````�0��a\x0000\x001f�19\x0000\x0000\x0000\x0000\x0000\x0000\x0000\x0000L\x0000�\x0001\x001c\x00014\x0001d\x0001�\x0001�\x0001�\x0001�\x0001�\x0002\x001a\x0002.\x0002H\x0002b\x0002�\x0002�\x0002�\x0002�\x0002�\x0003\x0006\x0003@\x0003T\x0003�\x0003�\x0004\x0018\x0004D\x0004v\x0004�\x0004�\x0004�\x0005\x0010\x0005|\x0005�\x0006</p><p>\x0006:\x0006`\x0006�\x0006�\x0006�\x0007,\x0007~\x0007�\x0008</p><p>\x00084\x0008d\x0008~\x0008�\x0008�	\x001e	Z	�	�</p><p>N</p><p>�\x000b</p><p>\x000b^\x000b�\x000b�\x000b�\x000c$\x000cp\x000c~\x000c�
\x0010
N
�
�\x000e\x0014\x000eh\x000e�x�c`d``pg�e`e\x0000\x0001& �\x0002B\x0006��`>\x0003\x0000\x0017�\x0001�\x0000x�]��N�0\x0014�O��h\x0010\x0002!1��\x000bR�3�\x0001ڙ\x000e���I[%q丕*13�\x0014�<\x0005�ŉ{%*l��;�\x001e_\x001b�\x0003~\x0010�[\x0001��v��\x001b�\x000b�Iw�\x0003��\x0010!��GT/�c�b"\x001c�	o�\x0010\x000cn錑	�p�Z�O�]x@�\x0010\x001er�������\x00181��CL��>5u��űL�g_bm۽��<�y�ֵ��әڞU{*\x0016��*��R+S;]�F5�\x001ctꢝs�r:�ŏRSa�\x0014�n��F�#J$�W�\x001f�LX�tZa�\x0008������g\x00128�\x00193[�Y[�8{A�!�Ι1�H+�K�܆N�{\x0007:)�\x0008;��\x0012S��_>�W�0�Sb\x0000\x0000\x0000x�mR�z�0\x0010��\x001cI�4M</p><p>��,W�e�r�\x0005</p><p>��Pd��l\x0019����X������hwV\x001a�[�x����},`\x0011�p\x001e\x0017p\x0011\x001dt��\x0012�\x0018`\x0019C�`�1Vq	�q\x0005kX�\x0006��\x001a��\x0006n�\x00166q\x001bwp\x0017�p\x001f[��\x0003<�#<�\x0013�x�gx�\x0017��K��k��[��{|�G|�g|�.��\x001b�c\x000f?�\x0013����^_Hi�$��H��(QC\x0011\x0004���Ԋx�q\x0007zB+�
\x0015�rk͑\x001f�����ųv�V!w��xV�ٌ��9�)�K1ѵekc�\x0015\x001b\x001dL�<Y(kD�qJ�����"%m�Zņ
㎁,�H\x0002a)�\x0019���T�?U��\x0013s�	Im2Վ�Ǌ�K��*W�Wc�p�j#�)�*��%\x00189m��se\x0013�\x001d�\x001du��}\x0007L\x0018ra٧��Ϲ��h\x0004I4�\x0010\x001d�P\x001a�|݆ѓDIhl,��$�='��6e\x001e�H��XD�5B\x0014A���ߩT�\x001d\x001a����vV!�T�\x0013�#DWOm����G�	��o���3F]V�VeS�	���a�\x000b!:q���\\c��\x0015��</p><p>�\x000f�-O��`D�\x001d\x001a]�\x001c=��\x0016�\x0015qQ��9�U,WB�+�~��]��\x0007dYx�</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  * Evidence: `todo`
  
  
  
  
Instances: 7
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bTODO\b and was detected 2 times, the first in the element starting with: "<!-- todo(estellecomment) : import min css and js -->", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Information Disclosure - Suspicious Comments
##### Informational (Low)
  
  
  
  
#### Description
<p>The response appears to contain suspicious comments which may help an attacker. Note: Matches made within script blocks or files are against the entire content not only comments.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js](https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `user`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js](https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `query`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `from`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `TODO`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js](https://santepsy.etudiant.gouv.fr/static/js/build-psy-listing.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `TODO`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `SELECT`
  
  
  
  
Instances: 6
  
### Solution
<p>Remove all comments that return information that may help an attacker and fix any underlying problems they refer to.</p>
  
### Other information
<p>The following pattern was used: \bUSER\b and was detected in the element starting with: "    // New filter : this is the first input into search field by user", see evidence field for the suspicious comment/snippet.</p>
  
### Reference
* 

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Modern Web Application
##### Informational (Medium)
  
  
  
  
#### Description
<p>The application appears to be a modern web application. If you need to explore it automatically then the Ajax Spider may well be more effective than the standard one.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a class="rf-sidemenu__link" href="#etudiant" target="_self">Étudiants</a>`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js](https://santepsy.etudiant.gouv.fr/static/gouvfr/js/all.js)
  
  
  * Method: `GET`
  
  
  * Evidence: `<script src="' + scripts[distGlobal_i] + '">`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `<a>`
  
  
  
  
Instances: 3
  
### Solution
<p>This is an informational alert and so no changes are required.</p>
  
### Other information
<p>Links have been found with a target of '_self' - this is often used by modern frameworks to force a full page reload.</p>
  
### Reference
* 

  
#### Source ID : 3

  
  
  
  
### Non-Storable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are not storable by caching components such as proxy servers. If the response does not contain sensitive, personal or user-specific information, it may benefit from being stored and cached, to improve performance.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/sitemap.xml](https://santepsy.etudiant.gouv.fr/sitemap.xml)
  
  
  * Method: `GET`
  
  
  * Evidence: `302`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/robots.txt](https://santepsy.etudiant.gouv.fr/robots.txt)
  
  
  * Method: `GET`
  
  
  * Evidence: `302`
  
  
  
  
Instances: 2
  
### Solution
<p>The content may be marked as storable by ensuring that the following conditions are satisfied:</p><p>The request method must be understood by the cache and defined as being cacheable ("GET", "HEAD", and "POST" are currently defined as cacheable)</p><p>The response status code must be understood by the cache (one of the 1XX, 2XX, 3XX, 4XX, or 5XX response classes are generally understood)</p><p>The "no-store" cache directive must not appear in the request or response header fields</p><p>For caching by "shared" caches such as "proxy" caches, the "private" response directive must not appear in the response</p><p>For caching by "shared" caches such as "proxy" caches, the "Authorization" header field must not appear in the request, unless the response explicitly allows it (using one of the "must-revalidate", "public", or "s-maxage" Cache-Control response directives)</p><p>In addition to the conditions above, at least one of the following conditions must also be satisfied by the response:</p><p>It must contain an "Expires" header field</p><p>It must contain a "max-age" response directive</p><p>For "shared" caches such as "proxy" caches, it must contain a "s-maxage" response directive</p><p>It must contain a "Cache Control Extension" that allows it to be cached</p><p>It must have a status code that is defined as cacheable by default (200, 203, 204, 206, 300, 301, 404, 405, 410, 414, 501).   </p>
  
### Reference
* https://tools.ietf.org/html/rfc7234
* https://tools.ietf.org/html/rfc7231
* http://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html (obsoleted by rfc7234)

  
#### CWE Id : 524
  
#### WASC Id : 13
  
#### Source ID : 3

  
  
  
  
### Storable and Cacheable Content
##### Informational (Medium)
  
  
  
  
#### Description
<p>The response contents are storable by caching components such as proxy servers, and may be retrieved directly from the cache, rather than from the origin server by the caching servers, in response to similar requests from other users.  If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where "shared" caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.</p>
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies](https://santepsy.etudiant.gouv.fr/donnees-personnelles-et-gestion-des-cookies)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/faq](https://santepsy.etudiant.gouv.fr/faq)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr](https://santepsy.etudiant.gouv.fr)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/mentions-legales](https://santepsy.etudiant.gouv.fr/mentions-legales)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/psychologue/login](https://santepsy.etudiant.gouv.fr/psychologue/login)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/](https://santepsy.etudiant.gouv.fr/)
  
  
  * Method: `GET`
  
  
  
  
Instances: 7
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/css/custom.css](https://santepsy.etudiant.gouv.fr/static/css/custom.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css](https://santepsy.etudiant.gouv.fr/static/gouvfr/css/all.css)
  
  
  * Method: `GET`
  
  
  * Evidence: `max-age=0`
  
  
  
  
Instances: 2
  
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
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `839306537`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `179306535`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `359304508`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `349312355`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `069305779`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0767006870`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `339314825`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `759348659`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0768562614`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `709301782`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0686978393`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0624517231`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `769309147`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `889303582`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0231429059`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0661879924`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0651134051`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0769199668`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `340004019`
  
  
  
  
* URL: [https://santepsy.etudiant.gouv.fr/trouver-un-psychologue](https://santepsy.etudiant.gouv.fr/trouver-un-psychologue)
  
  
  * Method: `GET`
  
  
  * Evidence: `0610042272`
  
  
  
  
Instances: 1916
  
### Solution
<p>Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.</p>
  
### Other information
<p>839306537, which evaluates to: 1996-08-06 04:42:17</p>
  
### Reference
* http://projects.webappsec.org/w/page/13246936/Information%20Leakage

  
#### CWE Id : 200
  
#### WASC Id : 13
  
#### Source ID : 3
