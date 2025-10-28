[← Back](../README.md)

---

<details open>
    <summary>Given a set of business requirements, identify the current system landscape and determine what standards, limitations, boundaries, and protocols exist.</summary>
    
    Modern systems must adhere to common standards and support common protocols in order to ensure reliable, secure, and intuitive interoperability.

    Common examples:
        - Standards
            - Web Service Standards
                - WSDL 1.1
                - SOAP 1.1
                - WSI-Basic Profile 1.1
                - HTTP
            - Open API 2.0
        - Protocols
            - OAuth 2.0
            - Bayeux (CometD)

    Each system also is constrained by boundaries and limitations. It is imperative that each system's boundaries and limitations are known.
    
    Examples below:
        - Boundaries
            - SOAP API transactions are limited to a single api call, so one API call should contain all information requred to achieve the desired result. 
        - Limitations
            - Salesforce governor limits like max number of callouts in an Apex transaction should be known.

    Below is a table that shows the standards, protocols, boundaries, and imitations that are common for each integration pattern

<table>
  <tr>
    <td rowspan="2">Row span</td>
    <td>Row 1, Col 2</td>
  </tr>
  <tr>
    <td>Row 2, Col 2</td>
  </tr>
</table>




| Pattern | Timing  | Method  | Protocol | Boundary | Limitation |
|---------|----------|----------|------------|------------|------------|
| REMOTE PROCESS INVOCATION - REQUEST & REPLY | Synchronous | Apex SOAP | WSDL 1.1<br> SOAP 1.1<br> WSI-Basic Profile 1.1<br> HTTP | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
|  | Synchronous | Apex REST | HTTP | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
|  | Synchronous | External Services (Flow) | HTTP<br> OpenAPI 2.0 | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
| REMOTE PROCESS INVOCATION - FIRE & FORGET | Asynchronous | Apex SOAP | WSDL 1.1<br> SOAP 1.1<br> WSI-Basic Profile 1.1<br> HTTP | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
|  | Asynchronous | Outbound Message | WSDL 1.1<br> SOAP 1.1<br> WSI-Basic Profile 1.1<br> HTTP | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
|  | Asynchronous | Apex REST | HTTP | (stateless) Confined to a single transaction<br> accessible from internet | SF Governor Limits |
| BATCH DATA SYNCHRONIZATION |  |  |  |  | SF Governor Limits |
| REMOTE CALL-IN |  |  |  |  | SF Governor Limits |
| UI UPDATE BASED ON DATA CHANGES |  |  |  |  | SF Governor Limits |
| DATA VIRTUALIZATION |  |  |  |  | SF Governor Limits |

    For the Salesforce side of integrations, there is a tool named "Salesforce Optimizer" that is helpful in identifying limit, high complexity, or other concerns that would be relevant to an integration. 
    
    The salesforce Optimizer tool reviews the following areas of a Salesforce instance:
        - Storage
            - Data and file storage usage limits
        - Fields
            - Field usage (look for unused), number of custom fields, field counts on page layouts
        - Custom Code
            - potential performance issues, Apex usage
        - Page Layouts
            - unassigned page layouts, excessive page layouts per object
        - Sharing Settings
            - org-wide defaults, role hierarchy complexity
        - Validation Rules
            - inactive validation rules, number of validation rules
        - User Management
            - profile usage, role assignments
        - Feature Usage
            - Chatter, files, Omni-channel, Path (Sales Path)




    SALESFORCE OPTIMIZER TOOL
</details>

<details>
<summary>Given an existing system landscape, analyze for constraints and/or pain-points to satisfy a business requirement(s).</summary>

**Notes:**
- 

</details>

<details>
<summary>Given a set of requirements, evaluate the authentication and authorization needs based on the system landscape.</summary>

**Notes:**
- 

</details>