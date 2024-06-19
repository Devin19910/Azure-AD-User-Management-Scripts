# Azure-AD-User-Management-Scripts
A collection of PowerShell scripts for managing users in Azure Active Directory (AD). These scripts can automate common tasks such as user creation, password resets, group management, and license assignments

` README.MD: An overview of the project, including prerequisites, installation steps, and usage instructions.
  `Scripts:
*CreateUser.ps1: Script to create a new user in Azure AD.
*ResetPassword.ps1: Script to reset user passwords.
*ManageGroups.ps1: Script to add/remove users from groups.
*AssignLicenses.ps1: Script to assign licenses to users.


# Connect to Azure AD
Connect-AzureAD

# Create a new user
$newUser = New-AzureADUser -DisplayName "John Doe" -UserPrincipalName "john.doe@yourdomain.com" -PasswordProfile (New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile -Property @{Password = "Password@123"; ForceChangePasswordNextSignIn = $true}) -MailNickname "john.doe" -AccountEnabled $true

Write-Output "User created: $($newUser.UserPrincipalName)"
