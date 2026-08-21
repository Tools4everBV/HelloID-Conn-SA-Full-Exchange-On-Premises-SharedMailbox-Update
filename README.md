# HelloID-Conn-SA-Full-Exchange-On-Premises-SharedMailbox-Update

| :information_source: Information                                                                                                                                                                                                                                                                                                                                                          |
| :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| This repository contains the connector and configuration code only. The implementer is responsible for acquiring the connection details such as username, password, certificate, etc. You might even need to sign a contract or agreement with the supplier before implementing this connector. Please contact the client's application manager to coordinate the connector requirements. |

## Description

_HelloID-Conn-SA-Full-Exchange-On-Premises-SharedMailbox-Update_ is a template designed for use with HelloID Service Automation (SA) Delegated Forms. It can be imported into HelloID and customized according to your requirements.

By using this delegated form, you can manage resource attributes across your connected systems. The following options are available:

1.  Search and select the resource
2.  Enter new values for the resource attributes
3.  The entered values are validated
4.  Resource attributes are updated with new values across connected systems
5.  Writing back values will be handled according to system-specific rules and configurations

## Getting started

### Requirements

- **Exchange On-Premises PowerShell Module**:<br>
  The Exchange Management Shell or Remote PowerShell session must be available to execute Exchange cmdlets.
- **Appropriate Permissions**:<br>
  The account used by the connector must have sufficient permissions to manage shared mailboxes in Exchange On-Premises, including permissions to update mailbox attributes and email addresses.

### Connection settings

The following user-defined variables are used by the connector.

| Setting        | Description                                          | Mandatory |
| -------------- | ---------------------------------------------------- | --------- |
| ExchangeServer | The hostname or FQDN of the Exchange server          | Yes       |
| Authentication | The authentication method (e.g., Kerberos, Basic)    | No        |
| ConnectionUri  | The URI for remote PowerShell connection to Exchange | Yes       |

## Remarks

### Alias Validation

- **Unique Alias Check**: The connector validates that the new alias is unique across all Exchange recipients before applying changes. This prevents conflicts and ensures data integrity.

### Display Name Validation

- **Unique Display Name Check**: The connector verifies that the display name is unique to avoid confusion and maintain a clear directory structure.

### Email Address Validation

- **Unique Email Address Check**: Email addresses are validated for uniqueness across the Exchange organization. The connector also ensures proper formatting and domain validation against accepted domains.

### Mail Domain Retrieval

- **Accepted Domains**: The connector retrieves all accepted mail domains from Exchange to validate email addresses and provide domain options during the update process.

## Development resources

### API endpoints

The following PowerShell cmdlets are used by the connector

| Cmdlet             | Description                    |
| ------------------ | ------------------------------ |
| Get-Mailbox        | Retrieve mailbox information   |
| Set-Mailbox        | Update mailbox properties      |
| Get-Recipient      | Check for existing recipients  |
| Get-AcceptedDomain | Retrieve accepted mail domains |

### API documentation

- [Exchange Server PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/exchange/exchange-management-shell)
- [Set-Mailbox Cmdlet Reference](https://learn.microsoft.com/en-us/powershell/module/exchange/set-mailbox)

## Getting help

> :bulb: **Tip:**  
> _For more information on Delegated Forms, please refer to our [documentation](https://docs.helloid.com/en/service-automation/delegated-forms.html) pages_.

## HelloID docs

The official HelloID documentation can be found at: https://docs.helloid.com/
