# Importar os dados do arquivo CSV
$users = Import-Csv -Path "C:\temp\usuarios.csv"

# Loop para criar cada usuário
foreach ($user in $users) {
    $password = ConvertTo-SecureString $user.Password -AsPlainText -Force
    New-ADUser -Name "$($user.FirstName) $($user.LastName)" `
               -GivenName $user.FirstName `
               -Surname $user.LastName `
               -SamAccountName $user.Username `
               -UserPrincipalName "$($user.Username)@seudominio.com" `
               -Path $user.OU `
               -AccountPassword $password `
               -Enabled $true `
               -ChangePasswordAtLogon $true
}
