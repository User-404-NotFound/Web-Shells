# PHP File Extensions Usage

> **Disclaimer**  
> This repository is currently under construction. The content is being updated and expanded. New file extensions and detailed descriptions will be added soon. Stay tuned!

This document outlines the usage of various PHP file extensions commonly used for web shells and their potential to be exploited for Remote Code Execution (RCE).

## File Extensions and Usage

1. **.inc**
   - Typically used for PHP include files (`include('file.inc')`) but they are not always executed as PHP files.

2. **.module**
   - Used in CMS like Drupal containing PHP code to define modules.

3. **.ajax**
   - Used for AJAX-related scripts though servers may misinterpret the file extension and treat it as PHP.

4. **.phar**
   - PHP Archive (PHAR) files which can contain PHP scripts and are used to package and distribute PHP applications.

5. **.fpm**
   - Related to PHP-FPM (FastCGI Process Manager) used for executing PHP code in some configurations.

6. **.cgi**
   - Common for Perl scripts but may also execute PHP code if the server is misconfigured.

7. **.hphp**
   - Used with HipHop PHP (HHVM) a runtime for executing PHP code.

8. **.phb**
   - Rarely used for PHP scripts but may be executed in specific configurations that allow PHP code.

9. **.dhtml**
   - Typically used for dynamic HTML files but in misconfigured environments it may allow PHP execution.

10. **.class.php**
    - Used to define PHP classes typically stored in `.class.php` files.

11. **.tpl.php**
    - Used in templating systems like Smarty where the file contains PHP code within the template.

12. **.module.php**
    - A variation of `.module` files used in CMS like Drupal containing PHP code.

13. **.action.php**
    - Used in MVC-based frameworks (e.g., Struts, Spring) to define actions in PHP.

14. **.admin.php**
    - Typically used for admin scripts and dashboards often with elevated privileges.

15. **.wsdl.php**
    - Used for Web Services Description Language (WSDL) files typically in SOAP-based web services.

16. **.php**
    - Standard PHP script files. This is the most common extension for PHP scripts.

17. **.php3**
    - An older file extension for PHP scripts, used primarily before PHP 4.0.

18. **.php4**
    - Used for PHP 4.x files. Older but still recognized in some legacy systems.

19. **.php5**
    - Similar to `.php4` but for PHP 5.x files.

---

