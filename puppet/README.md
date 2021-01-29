# Puppet Tasks
## General Puppet Tips
  * First validate your file for syntax errors by running `puppet parser validate <filename>` on the same directory e.g. `puppet parser validate news.pp`
  * Next, Dry-run the code in the specified hosts by running `sudo puppet agent -tv --noop` (You need to first SSH to that host)
  * Finally, run the actual code by running `sudo puppet agent -tv` 
  * Always verify the successful completion of tasks using the following steps:
    * Run the actual code, login to the target hosts and verify whether the required changes are complete

## Common mistakes
  * Not specifying which nodes to run by specifying a node definition
  ```ruby
  node 'stapp01.stratos.xfusioncorp.com', 'stapp02.stratos.xfusioncorp.com', 'stapp03.stratos.xfusioncorp.com' {
    include nginx_installer
  }
  ```