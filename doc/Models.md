

# **ApiKeyCredentials**
## Required: 
api_key
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| api_key | str | API key for the integration ||

# **BasicAuthCredentials**
## Required: 
username, password
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| username | str | Basic auth username for the integration ||
| password | str | Basic auth password for the integration ||

# **BlocklistSubscription**
## Required: 
id
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | None ||
| remediation | Optional[str] | None ||

# **CVESubscription**
## Required: 
id
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | CVE ID ||

# **HTTPValidationError**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| detail | list[ValidationError] | None ||

# **IntegrationCreateRequest**
## Required: 
name, entity_type, output_format
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Name of the integration ||
| description | str | Description of the integration ||
| entity_type | str | None ||
| output_format | str | None ||

# **IntegrationCreateResponse**
## Required: 
id, name, organization_id, created_at, updated_at, entity_type, output_format, blocklists, cves, endpoint, credentials
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | ID of the integration ||
| name | str | Name of the integration. Should be unique within the organization ||
| organization_id | str | ID of the owner organization ||
| description | str | Description of the integration ||
| created_at | str | Time the integration was created ||
| updated_at | str | Last time the integration was updated ||
| entity_type | str | None ||
| output_format | str | None ||
| last_pull | Optional[str] | Last time the integration pulled blocklists ||
| blocklists | list[BlocklistSubscription] | Blocklists that are subscribed by the integration ||
| cves | list[CVESubscription] | CVEs that are subscribed by the integration ||
| endpoint | str | Url that should be used by the firewall or the remediation component to fetch the integration's content ||
| stats | Stats | None ||
| tags | list[str] | Tags associated with the integration ||
| credentials | Union[ApiKeyCredentials, BasicAuthCredentials] | Credentials that were generated for the integration ||

# **IntegrationGetResponse**
## Required: 
id, name, organization_id, created_at, updated_at, entity_type, output_format, blocklists, cves, endpoint
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | ID of the integration ||
| name | str | Name of the integration. Should be unique within the organization ||
| organization_id | str | ID of the owner organization ||
| description | str | Description of the integration ||
| created_at | str | Time the integration was created ||
| updated_at | str | Last time the integration was updated ||
| entity_type | str | None ||
| output_format | str | None ||
| last_pull | Optional[str] | Last time the integration pulled blocklists ||
| blocklists | list[BlocklistSubscription] | Blocklists that are subscribed by the integration ||
| cves | list[CVESubscription] | CVEs that are subscribed by the integration ||
| endpoint | str | Url that should be used by the firewall or the remediation component to fetch the integration's content ||
| stats | Stats | None ||
| tags | list[str] | Tags associated with the integration ||

# **IntegrationGetResponsePage**
## Required: 
items, total, page, size, pages, links
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| items | list[IntegrationGetResponse] | None ||
| total | int | None ||
| page | int | None ||
| size | int | None ||
| pages | int | None ||
| links | Links | None ||

# **IntegrationType**
## Enum: 
FIREWALL_INTEGRATION, REMEDIATION_COMPONENT_INTEGRATION

# **IntegrationUpdateRequest**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | New name ||
| description | str | New description ||
| output_format | str | None ||
| regenerate_credentials | bool | Regenerate credentials for the integration ||

# **IntegrationUpdateResponse**
## Required: 
id, name, organization_id, created_at, updated_at, entity_type, output_format, blocklists, cves, endpoint
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | ID of the integration ||
| name | str | Name of the integration. Should be unique within the organization ||
| organization_id | str | ID of the owner organization ||
| description | str | Description of the integration ||
| created_at | str | Time the integration was created ||
| updated_at | str | Last time the integration was updated ||
| entity_type | str | None ||
| output_format | str | None ||
| last_pull | Optional[str] | Last time the integration pulled blocklists ||
| blocklists | list[BlocklistSubscription] | Blocklists that are subscribed by the integration ||
| cves | list[CVESubscription] | CVEs that are subscribed by the integration ||
| endpoint | str | Url that should be used by the firewall or the remediation component to fetch the integration's content ||
| stats | Stats | None ||
| tags | list[str] | Tags associated with the integration ||
| credentials | Optional[ApiKeyCredentials, BasicAuthCredentials] | Credentials for the integration ||

# **Links**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| first | Optional[str] | None ||
| last | Optional[str] | None ||
| self | Optional[str] | None ||
| next | Optional[str] | None ||
| prev | Optional[str] | None ||

# **OutputFormat**
## Enum: 
PLAIN_TEXT, F5, REMEDIATION_COMPONENT, FORTIGATE, PALOALTO, CHECKPOINT, CISCO, JUNIPER, MIKROTIK, PFSENSE, OPNSENSE, SOPHOS

# **Stats**
## Required: 
count
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| count | int | Number of total blocklists items the integration will pull ||

# **ValidationError**
## Required: 
loc, msg, type
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| loc | list[Union[str, int]] | None ||
| msg | str | None ||
| type | str | None ||

# **AffectedComponent**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| vendor | str | Vendor of the affected component ||
| product | str | Product name of the affected component ||

# **AllowlistSubscription**
## Required: 
id
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | None ||

# **AttackDetail**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Attack detail name ||
| label | str | Attack detail label ||
| description | str | Attack detail description ||
| references | list[str] | Attack detail references ||

# **Behavior**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Behavior name ||
| label | str | Behavior label ||
| description | str | Behavior description ||

# **CVEEvent**
## Required: 
date, description, label, name
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| date | str | Date of the event ||
| description | str | Description of the event ||
| label | str | Label of the event ||
| name | str | Name of the event ||

# **CVEResponseBase**
## Required: 
id, name, title, affected_components, crowdsec_score, nb_ips, published_date, has_public_exploit
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | ID of the CVE ||
| name | str | Name of the CVE ||
| title | str | Title of the CVE ||
| affected_components | list[AffectedComponent] | List of affected components ||
| crowdsec_score | int | Live Exploit Tracker score of the CVE ||
| first_seen | Optional[str] | First seen date ||
| last_seen | Optional[str] | Last seen date ||
| nb_ips | int | Number of unique IPs affected ||
| published_date | str | Published date of the CVE ||
| cvss_score | Optional[float] | CVSS score of the CVE ||
| has_public_exploit | bool | Indicates if there is a public exploit for the CVE ||
| rule_release_date | Optional[str] | Release date of the associated detection rule ||

# **CVEsubscription**
## Required: 
id
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | None ||

# **CWE**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Name of the CWE ||
| label | str | Label of the CWE ||
| description | str | Description of the CWE ||

# **Classification**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Classification name ||
| label | str | Classification label ||
| description | str | Classification description ||

# **Classifications**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| false_positives | list[Classification] | False positive classifications ||
| classifications | list[Classification] | Main classifications ||

# **EntityType**
## Enum: 
ORG, TAG, ENGINE, FIREWALL_INTEGRATION, REMEDIATION_COMPONENT_INTEGRATION, REMEDIATION_COMPONENT, LOG_PROCESSOR

# **GetCVEIPsResponsePage**
## Required: 
items, total, page, size, pages, links
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| items | list[IPItem] | None ||
| total | int | None ||
| page | int | None ||
| size | int | None ||
| pages | int | None ||
| links | Links | None ||

# **GetCVEResponse**
## Required: 
id, name, title, affected_components, crowdsec_score, nb_ips, published_date, has_public_exploit, references, description, crowdsec_analysis, cwes
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| id | str | ID of the CVE ||
| name | str | Name of the CVE ||
| title | str | Title of the CVE ||
| affected_components | list[AffectedComponent] | List of affected components ||
| crowdsec_score | int | Live Exploit Tracker score of the CVE ||
| first_seen | Optional[str] | First seen date ||
| last_seen | Optional[str] | Last seen date ||
| nb_ips | int | Number of unique IPs affected ||
| published_date | str | Published date of the CVE ||
| cvss_score | Optional[float] | CVSS score of the CVE ||
| has_public_exploit | bool | Indicates if there is a public exploit for the CVE ||
| rule_release_date | Optional[str] | Release date of the associated detection rule ||
| references | list[str] | List of references for the CVE ||
| description | str | Description of the CVE ||
| crowdsec_analysis | Optional[str] | CrowdSec analysis of the CVE ||
| cwes | list[CWE] | List of CWEs associated with the CVE ||
| events | list[CVEEvent] | List of events related to the CVE ||

# **GetCVESubscribedIntegrationsResponsePage**
## Required: 
items, total, page, size, pages, links
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| items | list[IntegrationResponse] | None ||
| total | int | None ||
| page | int | None ||
| size | int | None ||
| pages | int | None ||
| links | Links | None ||

# **GetCVEsResponsePage**
## Required: 
items, total, page, size, pages, links
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| items | list[CVEResponseBase] | None ||
| total | int | None ||
| page | int | None ||
| size | int | None ||
| pages | int | None ||
| links | Links | None ||

# **History**
## Required: 
first_seen, last_seen, full_age, days_age
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| first_seen | str | First seen timestamp ||
| last_seen | str | Last seen timestamp ||
| full_age | int | Full age in days ||
| days_age | int | Days age ||

# **IPItem**
## Required: 
ip
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| ip | str | IP address ||
| reputation | str | Reputation of the IP ||
| ip_range | Optional[str] | IP range ||
| ip_range_score | Optional[int] | IP range score ||
| ip_range_24 | Optional[str] | IP range /24 ||
| ip_range_24_reputation | Optional[str] | IP range /24 reputation ||
| ip_range_24_score | Optional[int] | IP range /24 score ||
| as_name | Optional[str] | AS name ||
| as_num | Optional[int] | AS number ||
| background_noise_score | int | Background noise score ||
| background_noise | Optional[str] | Background noise level ||
| confidence | Optional[str] | Confidence level ||
| location | Optional[Location] | IP location information ||
| reverse_dns | Optional[str] | Reverse DNS ||
| behaviors | list[Behavior] | List of behaviors ||
| references | list[Reference] | List of references ||
| history | History | None ||
| classifications | Classifications | None ||
| mitre_techniques | list[MitreTechnique] | MITRE techniques ||
| cves | list[str] | List of CVEs ||
| attack_details | list[AttackDetail] | Attack details ||
| target_countries | Target Countries | Target countries ||
| scores | Scores | None ||

# **IntegrationResponse**
## Required: 
organization_id, entity_type, name, output_format
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| tags | list[str] | None ||
| organization_id | str | None ||
| created_at | str | Time the integration was created ||
| entity_type | str | None ||
| id | str | ID of the integration ||
| blocklists | list[BlocklistSubscription] | None ||
| allowlists | list[AllowlistSubscription] | None ||
| cves | list[CVEsubscription] | None ||
| name | str | Name of the integration ||
| updated_at | str | Last time the integration was updated ||
| description | Optional[str] | Description of the integration ||
| output_format | str | None ||
| last_pull | Optional[str] | Last time the integration pulled blocklists ||

# **Location**
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| country | Optional[str] | Country code ||
| city | Optional[str] | City name ||
| latitude | Optional[float] | Latitude coordinate ||
| longitude | Optional[float] | Longitude coordinate ||

# **MitreTechnique**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | MITRE technique ID ||
| label | str | MITRE technique label ||
| description | str | MITRE technique description ||

# **Reference**
## Required: 
name, label, description
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Reference name ||
| label | str | Reference label ||
| description | str | Reference description ||

# **ScoreBreakdown**
## Required: 
aggressiveness, threat, trust, anomaly, total
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| aggressiveness | int | Aggressiveness score ||
| threat | int | Threat score ||
| trust | int | Trust score ||
| anomaly | int | Anomaly score ||
| total | int | Total score ||

# **Scores**
## Required: 
overall, last_day, last_week, last_month
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| overall | ScoreBreakdown | None ||
| last_day | ScoreBreakdown | None ||
| last_week | ScoreBreakdown | None ||
| last_month | ScoreBreakdown | None ||

# **SubscribeCVEIntegrationRequest**
## Required: 
name
## Properties
| Property | Type | Description | Example |
|----------|------|-------------|---------|
| name | str | Name of the integration to subscribe ||