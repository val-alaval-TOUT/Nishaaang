If you receive an error message when trying the following command

`Import-Module .\nishang.psm1`

_Import-Module : Cannot bind argument to parameter 'Name' because it is an empty array._
_At line:1 char:1_
_+ Import-Module -DisableNameChecking_
_+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~_
    _+ CategoryInfo          : InvalidData: (:) [Import-Module], ParameterBindingValidationExcep_
   _tion_
    _+ FullyQualifiedErrorId : ParameterArgumentValidationErrorEmptyArrayNotAllowed,Microsoft.Po_
   _werShell.Commands.ImportModuleCommand_

Try the following:

(**Note**: Be careful running commands you are unfamiliar with! Consider reading through the Microsoft documentation before running this command. https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2)

`Set-ExecutionPolicy Unrestricted`

Choose `a` (for all)

At this point, if you were to re-run the command above (`Import-Module .\nishang.psm1`), you would likely **still** receive an error message of:

_WARNING: The names of some imported commands from the module 'nishang' include unapproved verbs_
_that might make them less discoverable. To find the commands with unapproved verbs, run the_
_Import-Module command again with the Verbose parameter. For a list of approved verbs, type_
_Get-Verb._
_WARNING: Some imported command names contain one or more of the following restricted characters:_
 _# , ( ) {{ }} [ ] & - / \ $ ^ ; : " ' < > | ? @ ` * % + = ~_

If you do see that error message, try the following:

`Import-Module -DisableNameChecking .\nishang.psm1`