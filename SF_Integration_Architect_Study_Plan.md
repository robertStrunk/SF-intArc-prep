# Salesforce Certified Integration Architect Study Plan
## Complete Guide to Passing the Exam

---

## 📋 Exam Overview

| **Attribute** | **Details** |
|---------------|-------------|
| **Exam Format** | 60 multiple-choice/multiple-select questions |
| **Duration** | 105 minutes (1 hour 45 minutes) |
| **Passing Score** | 67% (40/60 questions correct) |
| **Cost** | $400 USD (first attempt), $200 USD (retake) |
| **Delivery** | Proctored exam (onsite or online) |
| **Prerequisites** | None (but experience recommended) |
| **Validity** | Maintain via annual maintenance exams |

---

## 🎯 Exam Domains & Weightings

| **Domain** | **Weight** | **Study Time** |
|------------|------------|----------------|
| 1. Evaluate the Current System Landscape | 8% | 1 week |
| 2. Evaluate Business Needs | 11% | 1-2 weeks |
| 3. Translate Needs to Integration Requirements | 22% | 2-3 weeks |
| 4. Design Integration Solutions | 28% | 3-4 weeks |
| 5. Build Solution | 23% | 2-3 weeks |
| 6. Maintain Integration | 8% | 1 week |

**Total Recommended Study Time: 10-14 weeks**

---

## 📚 Domain 1: Evaluate the Current System Landscape (8%)

### Learning Objectives
- Identify existing system standards, limitations, and protocols
- Analyze system constraints to meet business requirements
- Evaluate authentication and authorization needs
- Assess current integration patterns in use

### Key Topics to Master

#### 1.1 System Analysis
- **Enterprise Architecture Assessment**
  - Identify existing systems (ERP, legacy, cloud)
  - Document current data flows
  - Catalog existing APIs and integration points
  - Understand system dependencies

- **Technical Standards**
  - REST vs SOAP protocols
  - Data formats (JSON, XML, CSV)
  - Communication protocols (HTTP/HTTPS, FTP, SFTP)
  - Message queuing systems

- **System Limitations**
  - Throughput capacity
  - Latency requirements
  - Concurrent user limits
  - Storage constraints

#### 1.2 Authentication & Authorization
- **Authentication Methods**
  - Username-Password
  - OAuth 2.0 flows
  - SAML SSO
  - JWT tokens
  - API keys
  - Certificate-based auth

- **Authorization Frameworks**
  - Role-based access control (RBAC)
  - Attribute-based access control (ABAC)
  - Scope management
  - Permission sets

#### 1.3 Integration Protocols
- **Synchronous Protocols**
  - REST API
  - SOAP API
  - GraphQL
  - HTTP/HTTPS

- **Asynchronous Protocols**
  - Message queues (MQ, RabbitMQ)
  - Event-driven architectures
  - Streaming APIs
  - Platform Events

### Hands-On Practice
- [ ] Document a sample enterprise system landscape
- [ ] Create an authentication flow diagram
- [ ] Compare REST vs SOAP for different use cases
- [ ] Identify constraints in a sample scenario

### Resources
- Trailhead: "API Basics" module
- Salesforce Developer Guide: REST API
- Salesforce Developer Guide: SOAP API
- Enterprise Integration Patterns book

---

## 📚 Domain 2: Evaluate Business Needs (11%)

### Learning Objectives
- Determine functional and non-functional integration requirements
- Classify data security levels (Confidential, Secure, Public)
- Identify factors impacting CRM success
- Recommend appropriate integration solutions

### Key Topics to Master

#### 2.1 Requirements Gathering
- **Functional Requirements**
  - Data synchronization needs
  - Real-time vs batch processing
  - CRUD operations required
  - Business process automation
  - User experience requirements

- **Non-Functional Requirements**
  - Performance (latency, throughput)
  - Availability (uptime requirements)
  - Scalability (future growth)
  - Reliability (error tolerance)
  - Security (compliance, encryption)
  - Maintainability

#### 2.2 Data Classification
- **Confidential Data**
  - PII (Personally Identifiable Information)
  - PHI (Protected Health Information)
  - PCI (Payment Card Information)
  - Trade secrets
  - Encryption at rest and in transit required

- **Secure Data**
  - Internal business data
  - Employee information
  - Financial records
  - Access control required

- **Public Data**
  - Marketing materials
  - Public-facing content
  - General product information

#### 2.3 Success Factors
- **Technical Factors**
  - Data quality and integrity
  - System availability
  - Performance metrics
  - Error handling

- **Business Factors**
  - User adoption
  - ROI measurement
  - Process efficiency
  - Customer satisfaction

- **Organizational Factors**
  - Change management
  - Training and documentation
  - Support structure
  - Governance

### Hands-On Practice
- [ ] Create a requirements document template
- [ ] Classify sample data fields by security level
- [ ] Define SLAs for an integration project
- [ ] Map business processes to technical requirements

### Resources
- Trailhead: "Data Security" module
- Salesforce Security Guide
- GDPR, CCPA, HIPAA compliance documentation

---

## 📚 Domain 3: Translate Needs to Integration Requirements (22%)

### Learning Objectives
- Create an inventory of systems and integration patterns
- Evaluate system and process constraints
- Identify security, authentication, and authorization requirements
- Assess performance needs
- Propose suitable integration solutions

### Key Topics to Master

#### 3.1 Integration Patterns (CRITICAL)

**Remote Process Invocation (Request-Reply)**
- **Pattern**: Salesforce initiates call to external system, waits for response
- **Use Cases**: 
  - Address validation
  - Credit card processing
  - Real-time inventory check
- **Salesforce Solutions**:
  - Apex HTTP Callouts
  - External Services
  - Flow HTTP Callouts
- **Considerations**: 
  - Timeout handling (120 seconds max)
  - Error handling
  - Retry logic

**Remote Process Invocation (Fire-and-Forget)**
- **Pattern**: Salesforce sends message, no response needed
- **Use Cases**:
  - Logging
  - Notifications
  - Non-critical updates
- **Salesforce Solutions**:
  - Apex @future callouts
  - Queueable Apex
  - Platform Events (outbound)
- **Considerations**:
  - No guaranteed delivery
  - Async processing

**Batch Data Synchronization**
- **Pattern**: Periodic bulk data exchange
- **Use Cases**:
  - Nightly data sync
  - Data warehouse updates
  - Historical data migration
- **Salesforce Solutions**:
  - Bulk API 2.0
  - Composite API
  - DataLoader
  - ETL tools (MuleSoft, Informatica)
- **Considerations**:
  - Data volume limits
  - Batch processing times
  - Deduplication strategy

**Remote Call-In**
- **Pattern**: External system initiates call to Salesforce
- **Use Cases**:
  - Mobile app updates
  - Web-to-Lead
  - Partner portal integration
- **Salesforce Solutions**:
  - REST API
  - SOAP API
  - Composite API
  - Custom Apex REST/SOAP services
- **Considerations**:
  - API limits
  - Authentication
  - Rate limiting

**UI Update Based on Data Changes**
- **Pattern**: UI refreshes when data changes in another system
- **Use Cases**:
  - Real-time dashboards
  - Live status updates
  - Collaborative editing
- **Salesforce Solutions**:
  - Lightning Web Components with refresh
  - Platform Events (Change Data Capture)
  - Streaming API
  - CometD
- **Considerations**:
  - Polling vs push
  - Browser limitations
  - User experience

**Data Virtualization**
- **Pattern**: Access external data without storing in Salesforce
- **Use Cases**:
  - Large datasets
  - Frequently changing data
  - Data residency requirements
- **Salesforce Solutions**:
  - Salesforce Connect (External Objects)
  - OData adapters
  - Custom adapters
- **Considerations**:
  - Query performance
  - Relationship limitations
  - Indexing

#### 3.2 Governor Limits (CRITICAL)

**API Limits**
- Daily API calls: 15,000 (Ent), 1,000,000+ (Unlimited)
- Concurrent long-running requests: 25
- Bulk API batch size: 10,000 records
- Bulk API daily limits: 15,000 batches or 150M records

**Apex Limits (per transaction)**
- SOQL queries: 100
- DML statements: 150
- Total heap size: 6 MB (sync), 12 MB (async)
- CPU time: 10 seconds (sync), 60 seconds (async)
- Callout timeout: 120 seconds
- Maximum callouts: 100

**Platform Event Limits**
- Publish: 2,000 events per hour (event delivery)
- High-volume: 250,000+ per hour
- Trigger batch size: 2,000 events

**Change Data Capture Limits**
- Standard entities: 5 enabled
- Custom entities: Unlimited
- 24-hour event retention

#### 3.3 Security Requirements

**Authentication Patterns**
- **OAuth 2.0 Flows**:
  - Web Server Flow (server-to-server)
  - User-Agent Flow (JavaScript)
  - JWT Bearer Flow (server-to-server, no user)
  - Username-Password Flow (not recommended)
  - Refresh Token Flow
  
- **Named Credentials**
  - Centralized credential management
  - Per-user vs per-org
  - External credential principals
  - Permission set mappings

- **Two-Way SSL/Mutual Authentication**
  - Client certificates
  - Certificate pinning

**Authorization**
- Profile and permission set management
- Field-level security
- Object permissions
- Sharing rules
- IP restrictions
- Session security policies

**Data Security**
- Encryption at rest (Platform Encryption)
- Encryption in transit (TLS 1.2+)
- Shield Platform Encryption
- Event monitoring
- Field audit trail

#### 3.4 Performance Requirements

**Latency Considerations**
- Real-time: < 1 second
- Near real-time: 1-5 seconds
- Batch: minutes to hours
- Network latency factors

**Throughput Requirements**
- Concurrent users
- Transactions per second
- Data volume per hour/day
- Peak load handling

**Scalability Planning**
- Horizontal scaling (multiple instances)
- Vertical scaling (more resources)
- Load balancing
- Caching strategies

### Hands-On Practice
- [ ] Design integration patterns for 5 different scenarios
- [ ] Create a governor limits mitigation strategy
- [ ] Configure OAuth 2.0 for a sample integration
- [ ] Calculate API call consumption for a batch process
- [ ] Design error handling for async patterns

### Resources
- **CRITICAL**: Study "Enterprise Integration Patterns" concepts
- Trailhead: "Apex Integration Services"
- Salesforce Limits Quick Reference Guide
- Security Implementation Guide

---

## 📚 Domain 4: Design Integration Solutions (28%)

### Learning Objectives
- Select appropriate integration patterns
- Define solution components to meet business needs
- Identify trade-offs, limitations, and constraints
- Specify suitable Salesforce APIs
- Design security mechanisms

### Key Topics to Master

#### 4.1 Salesforce APIs (CRITICAL)

**REST API**
- **Use Cases**: Mobile, web apps, lightweight integrations
- **Features**:
  - JSON format
  - Standard HTTP methods (GET, POST, PATCH, DELETE)
  - URI-based resources
  - OAuth 2.0 authentication
- **Best Practices**:
  - Use Composite API for multiple operations
  - Leverage field filtering (fields parameter)
  - Implement pagination (LIMIT, OFFSET)
  - Use ETags for conditional requests

**SOAP API**
- **Use Cases**: Enterprise integration, legacy systems
- **Features**:
  - XML format
  - WSDL contract
  - Strong typing
  - Supports complex queries
- **Best Practices**:
  - Use Enterprise WSDL (type-safe)
  - Implement proper fault handling
  - Batch operations when possible
  - Connection pooling

**Bulk API 2.0**
- **Use Cases**: Large data loads (>2,000 records)
- **Features**:
  - Asynchronous processing
  - Optimized for throughput
  - CSV, JSON, XML formats
  - Progress monitoring
- **Best Practices**:
  - Use for ETL processes
  - Monitor job status
  - Implement partial success handling
  - Serial vs parallel mode selection

**Streaming API & Platform Events**
- **Streaming API**:
  - PushTopic (custom queries)
  - Generic Streaming
  - CDC (Change Data Capture)
- **Platform Events**:
  - High-volume platform events (250K+/hour)
  - Standard volume (2,000/hour delivery)
  - Pub/sub pattern
  - Resume checkpoints
- **Best Practices**:
  - Use CDC for object changes
  - Platform Events for custom workflows
  - Implement durable streaming
  - Handle duplicate events

**Metadata API**
- **Use Cases**: Deployment automation, CI/CD
- **Features**:
  - Deploy/retrieve metadata
  - Package management
  - Org comparison
- **Tools**: Salesforce CLI, ANT Migration Tool, VS Code

**Composite API**
- **Composite** (related records, single transaction)
- **Composite Batch** (independent requests, not transactional)
- **Composite Graph** (complex dependencies)
- **SObject Collections** (bulk DML in REST)

**UI API**
- Lightning Data Service backend
- Form metadata
- Record layouts
- Picklist values

#### 4.2 Middleware Solutions

**MuleSoft Anypoint Platform**
- API-led connectivity
- DataWeave transformations
- Connector library
- API Manager

**Salesforce Integration Cloud (MuleSoft)**
- Pre-built connectors
- Managed integration
- API management

**Other Middleware**
- Informatica Cloud
- Dell Boomi
- Jitterbit
- Apache Camel
- Azure Logic Apps
- AWS Lambda + API Gateway

**When to Use Middleware**
- Complex transformations
- Multiple system orchestration
- Protocol conversion
- Legacy system integration
- High-volume batch processing

#### 4.3 Custom Integration Solutions

**Apex REST Services**
```apex
@RestResource(urlMapping='/Account/*')
global class AccountService {
    @HttpGet
    global static Account getAccount() {
        String accountId = RestContext.request.requestURI.substring(
            RestContext.request.requestURI.lastIndexOf('/')+1
        );
        return [SELECT Id, Name FROM Account WHERE Id = :accountId];
    }
}
```

**Apex SOAP Services**
```apex
global class AccountSoapService {
    webservice static Account getAccount(String accountId) {
        return [SELECT Id, Name FROM Account WHERE Id = :accountId];
    }
}
```

**Apex Callouts**
```apex
Http http = new Http();
HttpRequest request = new HttpRequest();
request.setEndpoint('https://api.example.com/data');
request.setMethod('GET');
request.setHeader('Authorization', 'Bearer ' + token);
HttpResponse response = http.send(request);
```

#### 4.4 Event-Driven Architecture

**Change Data Capture (CDC)**
- Automatic change notifications
- Standard and custom objects
- Near real-time (sub-second to seconds)
- Filter by fields
- **Use Case**: Data synchronization

**Platform Events**
- Publish-subscribe model
- Custom events
- Apex triggers on platform events
- Resume positions
- **Use Case**: Microservices communication

**Streaming API**
- PushTopic queries
- Long-polling CometD
- Bayeux protocol
- **Use Case**: Real-time UI updates

#### 4.5 Error Handling & Resilience

**Error Handling Strategies**
- Try-catch blocks
- Exception logging
- Custom exceptions
- Dead letter queues
- Retry policies (exponential backoff)

**Circuit Breaker Pattern**
- Detect failures
- Stop calling failing service
- Allow recovery time
- Automatic retry after timeout

**Idempotency**
- Unique message IDs
- Deduplication logic
- Safe to retry
- External ID fields

**Transaction Management**
- Savepoints in Apex
- All-or-nothing DML
- Database.insert(records, false) for partial success
- Platform Event publishing (separate transaction)

#### 4.6 Design Trade-Offs

| **Factor** | **Real-Time** | **Near Real-Time** | **Batch** |
|------------|---------------|--------------------|-----------|
| **Latency** | < 1 second | 1-60 seconds | Minutes to hours |
| **Complexity** | High | Medium | Low |
| **Resource Usage** | High | Medium | Low |
| **Cost** | High | Medium | Low |
| **Use Cases** | Payments, inventory | Notifications, updates | Data sync, reporting |

**API vs Middleware**
| **Direct API** | **Middleware** |
|----------------|----------------|
| Lower cost | Higher cost |
| Simpler | More complex |
| Less flexible | Highly flexible |
| Point-to-point | Hub-and-spoke |
| Good for few systems | Good for many systems |

### Hands-On Practice
- [ ] Build a custom Apex REST service
- [ ] Implement a callout with error handling
- [ ] Configure Change Data Capture
- [ ] Create a Platform Event flow
- [ ] Design a solution with Composite API
- [ ] Compare REST vs SOAP for 3 scenarios
- [ ] Design middleware architecture for multi-system integration
- [ ] Implement idempotency in an integration

### Resources
- Salesforce API Reference Documentation (ALL APIS)
- Trailhead: "Build Integrations Using Connected Apps"
- Trailhead: "Platform Events Basics"
- Trailhead: "Change Data Capture Basics"
- MuleSoft tutorials and certifications

---

## 📚 Domain 5: Build Solution (23%)

### Learning Objectives
- Design and implement APIs for Salesforce as provider and consumer
- Choose appropriate methods for outbound calls
- Consider scalability and error handling
- Develop security solutions for integrations
- Build resilience for system updates

### Key Topics to Master

#### 5.1 Salesforce as API Provider

**Exposing Data via REST**
```apex
@RestResource(urlMapping='/Cases/*')
global with sharing class CaseRESTService {
    
    @HttpGet
    global static Case getCaseById() {
        String caseId = RestContext.request.requestURI.substring(
            RestContext.request.requestURI.lastIndexOf('/')+1
        );
        
        try {
            Case c = [SELECT Id, CaseNumber, Subject, Status 
                     FROM Case 
                     WHERE Id = :caseId 
                     LIMIT 1];
            return c;
        } catch (QueryException e) {
            RestContext.response.statusCode = 404;
            return null;
        }
    }
    
    @HttpPost
    global static String createCase(String subject, String description) {
        Case c = new Case(
            Subject = subject,
            Description = description,
            Origin = 'API'
        );
        
        try {
            insert c;
            return c.Id;
        } catch (DmlException e) {
            RestContext.response.statusCode = 500;
            return 'Error: ' + e.getMessage();
        }
    }
    
    @HttpPatch
    global static String updateCase() {
        String caseId = RestContext.request.requestURI.substring(
            RestContext.request.requestURI.lastIndexOf('/')+1
        );
        
        Map<String, Object> params = (Map<String, Object>)
            JSON.deserializeUntyped(RestContext.request.requestBody.toString());
        
        Case c = new Case(Id = caseId);
        if (params.containsKey('Status')) {
            c.Status = (String)params.get('Status');
        }
        
        try {
            update c;
            return 'Success';
        } catch (DmlException e) {
            RestContext.response.statusCode = 500;
            return 'Error: ' + e.getMessage();
        }
    }
    
    @HttpDelete
    global static String deleteCase() {
        String caseId = RestContext.request.requestURI.substring(
            RestContext.request.requestURI.lastIndexOf('/')+1
        );
        
        try {
            delete new Case(Id = caseId);
            return 'Deleted';
        } catch (DmlException e) {
            RestContext.response.statusCode = 500;
            return 'Error: ' + e.getMessage();
        }
    }
}
```

**Best Practices for Apex REST Services**
- Use `with sharing` for record-level security
- Implement proper error handling
- Return appropriate HTTP status codes
- Validate input parameters
- Use field-level security checks
- Implement pagination for list operations
- Version your APIs (urlMapping='/v1/Cases/*')
- Document with OpenAPI/Swagger

**Exposing Data via SOAP**
```apex
global class AccountSOAPService {
    webservice static String createAccount(String name, String industry) {
        Account acc = new Account(
            Name = name,
            Industry = industry
        );
        insert acc;
        return acc.Id;
    }
    
    webservice static Account getAccount(String accountId) {
        return [SELECT Id, Name, Industry 
                FROM Account 
                WHERE Id = :accountId];
    }
}
```

#### 5.2 Salesforce as API Consumer

**HTTP Callouts**
```apex
public class ExternalAPICallout {
    
    public static String getExternalData(String endpoint) {
        Http http = new Http();
        HttpRequest request = new HttpRequest();
        request.setEndpoint(endpoint);
        request.setMethod('GET');
        request.setHeader('Content-Type', 'application/json');
        request.setTimeout(120000); // 120 seconds max
        
        try {
            HttpResponse response = http.send(request);
            
            if (response.getStatusCode() == 200) {
                return response.getBody();
            } else {
                throw new CalloutException(
                    'HTTP ' + response.getStatusCode() + ': ' + 
                    response.getStatus()
                );
            }
        } catch (Exception e) {
            System.debug('Callout error: ' + e.getMessage());
            throw e;
        }
    }
    
    @future(callout=true)
    public static void postDataAsync(String endpoint, String jsonData) {
        Http http = new Http();
        HttpRequest request = new HttpRequest();
        request.setEndpoint(endpoint);
        request.setMethod('POST');
        request.setHeader('Content-Type', 'application/json');
        request.setBody(jsonData);
        
        HttpResponse response = http.send(request);
        
        // Log response
        System.debug('Response: ' + response.getBody());
    }
}
```

**Using Named Credentials**
```apex
HttpRequest request = new HttpRequest();
request.setEndpoint('callout:MyNamedCredential/api/data');
request.setMethod('GET');
// Authentication handled automatically by Named Credential
```

**Queueable Apex for Callouts**
```apex
public class QueueableCallout implements Queueable, Database.AllowsCallouts {
    private String endpoint;
    private String data;
    
    public QueueableCallout(String endpoint, String data) {
        this.endpoint = endpoint;
        this.data = data;
    }
    
    public void execute(QueueableContext context) {
        Http http = new Http();
        HttpRequest request = new HttpRequest();
        request.setEndpoint(endpoint);
        request.setMethod('POST');
        request.setHeader('Content-Type', 'application/json');
        request.setBody(data);
        
        try {
            HttpResponse response = http.send(request);
            
            if (response.getStatusCode() != 200) {
                // Retry logic
                if (shouldRetry()) {
                    System.enqueueJob(new QueueableCallout(endpoint, data));
                }
            }
        } catch (Exception e) {
            // Log error and potentially retry
            logError(e);
        }
    }
    
    private Boolean shouldRetry() {
        // Implement retry logic
        return true;
    }
    
    private void logError(Exception e) {
        // Implement error logging
        System.debug('Error: ' + e.getMessage());
    }
}
```

#### 5.3 Scalability Patterns

**Bulkification**
```apex
// BAD: Callout in a loop
for (Account acc : accounts) {
    makeCallout(acc.Id); // Governor limit: max 100 callouts
}

// GOOD: Batch callouts
List<String> accountIds = new List<String>();
for (Account acc : accounts) {
    accountIds.add(acc.Id);
}
makeBatchCallout(accountIds);
```

**Caching Strategy**
```apex
// Platform Cache for expensive operations
public class CacheService {
    
    public static String getCachedData(String key) {
        // Check org cache
        String cachedValue = (String)Cache.Org.get('local.CachePartition.' + key);
        
        if (cachedValue != null) {
            return cachedValue;
        }
        
        // Fetch from external system
        String freshValue = fetchFromExternal(key);
        
        // Store in cache for 1 hour (3600 seconds)
        Cache.Org.put('local.CachePartition.' + key, freshValue, 3600);
        
        return freshValue;
    }
    
    private static String fetchFromExternal(String key) {
        // Make HTTP callout
        return 'data';
    }
}
```

**Asynchronous Processing**
- `@future` methods for fire-and-forget
- Queueable Apex for chaining
- Batch Apex for large volumes
- Platform Events for decoupling

#### 5.4 Error Handling & Monitoring

**Comprehensive Error Handling**
```apex
public class RobustIntegration {
    
    public static void processIntegration(List<Record__c> records) {
        List<Integration_Log__c> logs = new List<Integration_Log__c>();
        
        for (Record__c record : records) {
            try {
                // Attempt integration
                callExternalSystem(record);
                
                // Log success
                logs.add(new Integration_Log__c(
                    Record__c = record.Id,
                    Status__c = 'Success',
                    Timestamp__c = System.now()
                ));
                
            } catch (CalloutException e) {
                // Network or HTTP error
                logs.add(new Integration_Log__c(
                    Record__c = record.Id,
                    Status__c = 'Failed',
                    Error_Message__c = e.getMessage(),
                    Error_Type__c = 'CalloutException',
                    Timestamp__c = System.now(),
                    Retry_Count__c = 0
                ));
                
                // Queue for retry
                queueRetry(record.Id);
                
            } catch (Exception e) {
                // Other errors
                logs.add(new Integration_Log__c(
                    Record__c = record.Id,
                    Status__c = 'Failed',
                    Error_Message__c = e.getMessage(),
                    Error_Type__c = e.getTypeName(),
                    Timestamp__c = System.now()
                ));
            }
        }
        
        insert logs;
    }
    
    private static void callExternalSystem(Record__c record) {
        // Implementation
    }
    
    private static void queueRetry(Id recordId) {
        // Schedule retry with exponential backoff
    }
}
```

**Monitoring & Alerting**
- Custom logging objects
- Platform Events for alerts
- Email notifications
- Integration with external monitoring (DataDog, Splunk)
- Event Monitoring (Shield)

#### 5.5 Security Implementation

**OAuth 2.0 Implementation**
```apex
// JWT Bearer Flow
public class OAuthJWTBearerFlow {
    
    public static String getAccessToken() {
        // Create JWT
        Auth.JWT jwt = new Auth.JWT();
        jwt.setSub('user@example.com');
        jwt.setAud('https://login.salesforce.com');
        jwt.setIss('3MVG9...');
        
        Auth.JWS jws = new Auth.JWS(jwt, 'certificate_name');
        String token = jws.getCompactSerialization();
        
        // Exchange JWT for access token
        Http http = new Http();
        HttpRequest request = new HttpRequest();
        request.setEndpoint('https://login.salesforce.com/services/oauth2/token');
        request.setMethod('POST');
        request.setHeader('Content-Type', 'application/x-www-form-urlencoded');
        request.setBody(
            'grant_type=urn:ietf:params:oauth:grant-type:jwt-bearer' +
            '&assertion=' + token
        );
        
        HttpResponse response = http.send(request);
        Map<String, Object> result = (Map<String, Object>)
            JSON.deserializeUntyped(response.getBody());
        
        return (String)result.get('access_token');
    }
}
```

**Field-Level Encryption**
```apex
// Check field accessibility
if (!Schema.sObjectType.Account.fields.SSN__c.isAccessible()) {
    throw new SecurityException('No access to SSN field');
}

// Use Platform Encryption for sensitive fields
// Enable in Setup → Platform Encryption
```

**API Security Best Practices**
- IP whitelisting in Profile/Permission Set
- Session security settings
- CORS configuration for web apps
- Rate limiting (enforced by Salesforce)
- Input validation and sanitization
- Shield Platform Encryption for data at rest

#### 5.6 Handling System Updates

**API Versioning**
```apex
// Always specify API version
@RestResource(urlMapping='/v2/Cases/*')
global class CaseServiceV2 {
    // New implementation
}
```

**Backward Compatibility**
- Deprecation warnings
- Support multiple versions
- Gradual migration
- Version negotiation

**Deployment Strategies**
- Blue-green deployment
- Canary releases
- Feature flags
- Rollback procedures

### Hands-On Practice
- [ ] Build a complete Apex REST service with all HTTP methods
- [ ] Implement OAuth 2.0 JWT flow
- [ ] Create error handling with retry logic
- [ ] Build a caching layer with Platform Cache
- [ ] Implement comprehensive logging
- [ ] Create a Named Credential and use it in Apex
- [ ] Build a bulk processing pattern with Queueable Apex
- [ ] Implement idempotency for an API

### Resources
- Apex Developer Guide (REST/SOAP sections)
- Trailhead: "Apex Integration Services"
- Trailhead: "Asynchronous Apex"
- OAuth 2.0 specification
- Platform Cache Best Practices

---

## 📚 Domain 6: Maintain Integration (8%)

### Learning Objectives
- Monitor integration performance
- Implement error handling, escalation, and recovery procedures
- Identify reporting needs for integration monitoring
- Troubleshoot integration issues

### Key Topics to Master

#### 6.1 Monitoring Strategies

**Native Salesforce Monitoring**
- **System Overview** (Setup → System Overview)
  - API usage
  - Storage usage
  - Batch Apex jobs
  
- **Debug Logs** (Setup → Debug Logs)
  - Apex execution
  - API calls
  - Trigger execution
  - Workflow rules
  
- **API Usage Notifications**
  - 75% threshold alerts
  - Email notifications
  
- **Apex Jobs** (Setup → Apex Jobs)
  - Scheduled jobs
  - Batch jobs
  - Future methods
  - Queueable jobs

**Event Monitoring (Shield)**
- API usage tracking
- Login events
- Report exports
- Large data volume downloads
- URI tracking

**Custom Monitoring**
```apex
// Create custom monitoring object
Integration_Monitor__c monitor = new Integration_Monitor__c(
    Integration_Name__c = 'CustomerSync',
    Start_Time__c = System.now(),
    Status__c = 'In Progress',
    Records_Processed__c = 0,
    Records_Failed__c = 0
);
insert monitor;

// Update after completion
monitor.End_Time__c = System.now();
monitor.Status__c = 'Completed';
monitor.Records_Processed__c = successCount;
monitor.Records_Failed__c = failureCount;
update monitor;
```

#### 6.2 Error Handling & Recovery

**Retry Mechanisms**
```apex
public class RetryHandler {
    
    private static final Integer MAX_RETRIES = 3;
    private static final Integer INITIAL_DELAY = 1000; // 1 second
    
    public static void executeWithRetry(String recordId, Integer attempt) {
        try {
            processRecord(recordId);
            logSuccess(recordId);
            
        } catch (CalloutException e) {
            if (attempt < MAX_RETRIES) {
                // Exponential backoff
                Integer delay = INITIAL_DELAY * Math.pow(2, attempt).intValue();
                
                // Schedule retry (using Queueable or Scheduled Apex)
                RetryJob job = new RetryJob(recordId, attempt + 1);
                System.enqueueJob(job);
                
                logRetry(recordId, attempt, e.getMessage());
            } else {
                // Max retries exceeded, send to dead letter queue
                createErrorRecord(recordId, e);
                sendAlert(recordId, e);
            }
        }
    }
}
```

**Dead Letter Queue Pattern**
```apex
// Store failed integrations for manual review
Integration_Error__c error = new Integration_Error__c(
    Record_Id__c = recordId,
    Error_Message__c = e.getMessage(),
    Error_Type__c = e.getTypeName(),
    Stack_Trace__c = e.getStackTraceString(),
    Timestamp__c = System.now(),
    Retry_Count__c = retryCount,
    Status__c = 'Requires Manual Review'
);
insert error;
```

**Circuit Breaker Pattern**
```apex
public class CircuitBreaker {
    
    private static Integer failureCount = 0;
    private static final Integer THRESHOLD = 5;
    private static Boolean isOpen = false;
    private static DateTime lastFailureTime;
    private static final Integer TIMEOUT = 60000; // 1 minute
    
    public static Boolean isAvailable() {
        if (isOpen) {
            // Check if timeout period has passed
            if (System.now().getTime() - lastFailureTime.getTime() > TIMEOUT) {
                // Half-open state: allow one request
                isOpen = false;
                failureCount = 0;
                return true;
            }
            return false;
        }
        return true;
    }
    
    public static void recordSuccess() {
        failureCount = 0;
        isOpen = false;
    }
    
    public static void recordFailure() {
        failureCount++;
        lastFailureTime = System.now();
        
        if (failureCount >= THRESHOLD) {
            isOpen = true;
            sendAlert('Circuit breaker opened due to repeated failures');
        }
    }
}
```

#### 6.3 Performance Monitoring

**Key Metrics to Track**
- Response time (latency)
- Throughput (transactions per second)
- Error rate
- API call consumption
- Success/failure ratio
- Processing time per record

**Performance Optimization**
```apex
// Track timing
Long startTime = System.now().getTime();

// Process integration
processIntegration();

Long endTime = System.now().getTime();
Long duration = endTime - startTime;

// Log performance metric
Performance_Log__c log = new Performance_Log__c(
    Integration_Name__c = 'CustomerSync',
    Duration_MS__c = duration,
    Timestamp__c = System.now()
);
insert log;

// Alert if performance degrades
if (duration > 5000) { // > 5 seconds
    sendPerformanceAlert(duration);
}
```

**Dashboards & Reports**
- Create custom reports for integration logs
- Build dashboards with charts:
  - Success rate over time
  - Error types distribution
  - Average response time
  - API usage trends
  - Daily integration volume

#### 6.4 Alerting & Escalation

**Email Alerts**
```apex
public static void sendErrorAlert(String integrationName, Exception e) {
    Messaging.SingleEmailMessage email = new Messaging.SingleEmailMessage();
    email.setToAddresses(new String[]{'integration-team@company.com'});
    email.setSubject('Integration Error: ' + integrationName);
    email.setPlainTextBody(
        'Integration: ' + integrationName + '\n' +
        'Error: ' + e.getMessage() + '\n' +
        'Type: ' + e.getTypeName() + '\n' +
        'Time: ' + System.now() + '\n' +
        'Stack Trace:\n' + e.getStackTraceString()
    );
    Messaging.sendEmail(new Messaging.SingleEmailMessage[]{email});
}
```

**Platform Event Alerts**
```apex
// Define custom platform event: Integration_Alert__e
Integration_Alert__e alert = new Integration_Alert__e(
    Integration_Name__c = 'CustomerSync',
    Severity__c = 'High',
    Message__c = 'Circuit breaker opened',
    Timestamp__c = System.now()
);
EventBus.publish(alert);

// Subscribe to alerts in monitoring app
trigger IntegrationAlertHandler on Integration_Alert__e (after insert) {
    for (Integration_Alert__e alert : Trigger.new) {
        if (alert.Severity__c == 'High') {
            // Send to PagerDuty, Slack, etc.
            notifyOpsTeam(alert);
        }
    }
}
```

**Escalation Procedures**
1. **Low Severity** (< 5% error rate)
   - Log to monitoring object
   - Automatic retry
   
2. **Medium Severity** (5-20% error rate)
   - Email notification
   - Create case for review
   
3. **High Severity** (> 20% error rate)
   - Immediate alert
   - Page on-call engineer
   - Activate circuit breaker

#### 6.5 Troubleshooting

**Common Integration Issues**

| **Issue** | **Symptoms** | **Solution** |
|-----------|--------------|--------------|
| **Timeout** | CalloutException after 120s | Optimize external service, increase timeout if possible, use async |
| **401 Unauthorized** | Authentication failure | Check credentials, refresh OAuth token, verify Named Credential |
| **429 Too Many Requests** | Rate limiting | Implement backoff, reduce call frequency, use batch API |
| **500 Internal Server Error** | External system error | Retry with backoff, contact external team, implement fallback |
| **API Limit Exceeded** | Too many API calls | Optimize queries, use Bulk API, cache data, upgrade edition |
| **Data Mapping Error** | Wrong field values | Validate transformations, check data types, verify field mappings |

**Debugging Techniques**
```apex
// Comprehensive debug logging
System.debug(LoggingLevel.ERROR, 'Integration failed for record: ' + recordId);
System.debug(LoggingLevel.INFO, 'Request: ' + request.getBody());
System.debug(LoggingLevel.INFO, 'Response: ' + response.getBody());

// Use debug log filters
// Setup → Debug Logs → New Debug Log
// Set trace flags for specific users/classes

// Test callouts with mocks
@isTest
private class IntegrationTest {
    
    @isTest
    static void testSuccessfulCallout() {
        Test.setMock(HttpCalloutMock.class, new SuccessMock());
        
        Test.startTest();
        String result = IntegrationService.callExternal();
        Test.stopTest();
        
        System.assertEquals('Success', result);
    }
}
```

#### 6.6 Maintenance Best Practices

**Regular Maintenance Tasks**
- Weekly:
  - Review error logs
  - Check API usage trends
  - Monitor performance metrics
  
- Monthly:
  - Analyze error patterns
  - Optimize slow integrations
  - Update documentation
  - Review security settings
  
- Quarterly:
  - Audit integration endpoints
  - Review governor limit usage
  - Update API versions
  - Conduct disaster recovery test

**Documentation**
- Integration architecture diagrams
- API specifications
- Error code reference
- Runbooks for common issues
- Contact information for external systems
- Change log

### Hands-On Practice
- [ ] Create a custom monitoring object and populate it
- [ ] Build an error handling framework with retry logic
- [ ] Implement circuit breaker pattern
- [ ] Create monitoring dashboard with reports
- [ ] Set up Platform Event alerting
- [ ] Write comprehensive integration tests
- [ ] Create troubleshooting runbook

### Resources
- Trailhead: "Monitor Asynchronous Apex"
- Event Monitoring Guide
- Apex Testing Best Practices
- Limits Quick Reference Guide

---

## 📅 12-Week Study Plan

### Week 1: Foundation & System Landscape
**Objectives:**
- Understand exam format and structure
- Master Domain 1 (Evaluate Current System Landscape - 8%)
- Review integration fundamentals

**Daily Activities:**
- Day 1: Review exam guide, set up study environment
- Day 2: Study authentication methods (OAuth, SAML, JWT)
- Day 3: Learn REST vs SOAP protocols
- Day 4: Practice system analysis and documentation
- Day 5: Hands-on: Document a sample enterprise architecture
- Day 6-7: Review and practice questions

**Resources:**
- Trailhead: API Basics
- Salesforce Authentication Flows documentation

**Deliverable:** Create a system landscape diagram for a fictional company

---

### Week 2: Business Needs & Requirements
**Objectives:**
- Master Domain 2 (Evaluate Business Needs - 11%)
- Understand data classification
- Learn requirements gathering

**Daily Activities:**
- Day 1: Functional vs non-functional requirements
- Day 2: Data classification (Confidential, Secure, Public)
- Day 3: Compliance requirements (GDPR, HIPAA, PCI)
- Day 4: SLA definition and measurement
- Day 5: Hands-on: Create requirements document for integration project
- Day 6-7: Review and practice questions

**Resources:**
- Salesforce Security Guide
- Trailhead: Data Security module

**Deliverable:** Requirements document with data classification

---

### Week 3: Integration Patterns (Part 1)
**Objectives:**
- Begin Domain 3 (Translate Needs to Integration Requirements - 22%)
- Master key integration patterns

**Daily Activities:**
- Day 1: Remote Process Invocation (Request-Reply)
- Day 2: Remote Process Invocation (Fire-and-Forget)
- Day 3: Batch Data Synchronization
- Day 4: Remote Call-In pattern
- Day 5: Hands-on: Implement each pattern in Developer Org
- Day 6-7: Review patterns and practice scenarios

**Resources:**
- Enterprise Integration Patterns book
- Trailhead: Apex Integration Services

**Deliverable:** Working examples of each pattern in Dev Org

---

### Week 4: Integration Patterns (Part 2) & Governor Limits
**Objectives:**
- Complete integration patterns
- Master governor limits

**Daily Activities:**
- Day 1: UI Update Based on Data Changes
- Day 2: Data Virtualization (Salesforce Connect)
- Day 3: Governor limits deep dive (API, Apex)
- Day 4: Platform Event and CDC limits
- Day 5: Hands-on: Implement UI update and Salesforce Connect
- Day 6-7: Governor limits practice and mitigation strategies

**Resources:**
- Salesforce Limits Quick Reference
- External Objects Implementation Guide

**Deliverable:** Governor limits mitigation plan for sample scenarios

---

### Week 5: Security & Performance
**Objectives:**
- Complete Domain 3
- Master authentication and authorization
- Understand performance requirements

**Daily Activities:**
- Day 1: OAuth 2.0 flows deep dive
- Day 2: Named Credentials and External Credentials
- Day 3: Field-level security and Platform Encryption
- Day 4: Performance metrics and latency
- Day 5: Hands-on: Implement OAuth 2.0 and Named Credentials
- Day 6-7: Security and performance practice questions

**Resources:**
- OAuth 2.0 specification
- Security Implementation Guide
- Named Credentials documentation

**Deliverable:** Working OAuth implementation with Named Credentials

---

### Week 6: Salesforce APIs (Part 1)
**Objectives:**
- Begin Domain 4 (Design Integration Solutions - 28%)
- Master REST API, SOAP API, Bulk API

**Daily Activities:**
- Day 1: REST API deep dive
- Day 2: SOAP API and WSDL
- Day 3: Bulk API 2.0 for large data volumes
- Day 4: Composite API patterns
- Day 5: Hands-on: Build integrations using each API
- Day 6-7: API comparison and selection practice

**Resources:**
- Salesforce API Reference for all APIs
- Postman collection for Salesforce APIs

**Deliverable:** Working examples of REST, SOAP, and Bulk API calls

---

### Week 7: Salesforce APIs (Part 2) & Event-Driven
**Objectives:**
- Master Streaming API, Platform Events, CDC
- Understand event-driven architecture

**Daily Activities:**
- Day 1: Streaming API and PushTopics
- Day 2: Platform Events (publish/subscribe)
- Day 3: Change Data Capture
- Day 4: Metadata API and UI API
- Day 5: Hands-on: Implement event-driven integration
- Day 6-7: Event architecture practice and review

**Resources:**
- Trailhead: Platform Events Basics
- Trailhead: Change Data Capture Basics
- Streaming API Developer Guide

**Deliverable:** Event-driven integration with CDC and Platform Events

---

### Week 8: Middleware & Custom Solutions
**Objectives:**
- Continue Domain 4
- Understand middleware solutions
- Learn custom integration patterns

**Daily Activities:**
- Day 1: MuleSoft Anypoint Platform overview
- Day 2: Other middleware (Boomi, Informatica, Jitterbit)
- Day 3: When to use middleware vs direct API
- Day 4: Custom Apex REST and SOAP services
- Day 5: Hands-on: Build custom Apex REST service
- Day 6-7: Middleware selection practice

**Resources:**
- MuleSoft documentation
- Integration architecture patterns

**Deliverable:** Decision matrix for middleware vs direct API

---

### Week 9: Build Solutions & Error Handling
**Objectives:**
- Begin Domain 5 (Build Solution - 23%)
- Implement robust error handling

**Daily Activities:**
- Day 1: Salesforce as API provider (Apex REST)
- Day 2: Salesforce as API consumer (HTTP callouts)
- Day 3: Error handling patterns
- Day 4: Retry logic and circuit breaker
- Day 5: Hands-on: Build integration with error handling
- Day 6-7: Advanced error handling scenarios

**Resources:**
- Apex Developer Guide
- Error handling best practices

**Deliverable:** Robust integration with comprehensive error handling

---

### Week 10: Scalability & Security Implementation
**Objectives:**
- Continue Domain 5
- Master scalability patterns
- Implement security

**Daily Activities:**
- Day 1: Bulkification and batch processing
- Day 2: Asynchronous Apex (Future, Queueable, Batch)
- Day 3: Platform Cache for performance
- Day 4: OAuth implementation and field-level security
- Day 5: Hands-on: Scalable, secure integration
- Day 6-7: Performance optimization practice

**Resources:**
- Trailhead: Asynchronous Apex
- Platform Cache Best Practices

**Deliverable:** High-performance integration with caching

---

### Week 11: Monitoring & Maintenance
**Objectives:**
- Master Domain 6 (Maintain Integration - 8%)
- Implement monitoring and alerting

**Daily Activities:**
- Day 1: Native Salesforce monitoring tools
- Day 2: Custom monitoring with Platform Events
- Day 3: Error recovery and dead letter queue
- Day 4: Performance monitoring and dashboards
- Day 5: Hands-on: Build monitoring framework
- Day 6-7: Troubleshooting practice

**Resources:**
- Event Monitoring Guide
- Debug Logs Best Practices

**Deliverable:** Complete monitoring and alerting system

---

### Week 12: Review & Practice Exams
**Objectives:**
- Comprehensive review
- Practice exams
- Identify weak areas

**Daily Activities:**
- Day 1: Domain 1-2 review and practice questions
- Day 2: Domain 3 review and practice questions
- Day 3: Domain 4 review and practice questions
- Day 4: Domain 5 review and practice questions
- Day 5: Domain 6 review and full practice exam
- Day 6: Review incorrect answers, study weak areas
- Day 7: Final practice exam and confidence check

**Resources:**
- Official Salesforce practice exam
- Third-party practice exams (Focus on Force, Trailhead Playground)

**Deliverable:** Score 75%+ on practice exams consistently

---

## 🎓 Study Resources

### Official Salesforce Resources
1. **Exam Guide** (CRITICAL)
   - Download from Salesforce Certification site
   - Review all objectives
   
2. **Trailhead Modules**
   - API Basics
   - Apex Integration Services
   - Platform Events Basics
   - Change Data Capture Basics
   - Asynchronous Apex
   - Data Security
   
3. **Developer Guides**
   - REST API Developer Guide
   - SOAP API Developer Guide
   - Bulk API 2.0 Developer Guide
   - Streaming API Developer Guide
   - Platform Events Developer Guide
   - Apex Developer Guide (Integration section)
   
4. **Implementation Guides**
   - Security Implementation Guide
   - Named Credentials Guide
   - External Objects Implementation Guide
   - Platform Encryption Guide

### Third-Party Resources
1. **Books**
   - "Enterprise Integration Patterns" by Gregor Hohpe (CRITICAL)
   - "Salesforce Platform Integration Architecture" (Trailblazer Community)
   
2. **Online Courses**
   - Udemy: "Salesforce Certified Integration Architect Exam Prep"
   - Focus on Force: Integration Architect Study Guide
   
3. **Practice Exams**
   - Focus on Force practice exams
   - Trailhead Playground challenges
   - Salesforce official practice exam
   
4. **Communities**
   - Salesforce Stack Exchange
   - Trailblazer Community (Architect group)
   - Reddit: r/salesforce

### Hands-On Practice
1. **Developer Org Setup**
   - Sign up for free Developer Org
   - Install Postman for API testing
   - Set up Connected App
   
2. **Practice Projects**
   - Build REST API with Apex
   - Implement OAuth 2.0 flow
   - Create Platform Event integration
   - Set up Change Data Capture
   - Build monitoring dashboard
   - Implement Salesforce Connect
   
3. **API Testing**
   - Use Postman or Workbench
   - Test all major APIs
   - Practice with Composite API
   - Experiment with Bulk API

---

## ✅ Pre-Exam Checklist

### 1 Week Before Exam
- [ ] Completed all study material
- [ ] Scored 75%+ on at least 3 practice exams
- [ ] Built hands-on projects for each domain
- [ ] Reviewed all integration patterns
- [ ] Memorized governor limits
- [ ] Understood all API capabilities

### 3 Days Before Exam
- [ ] Final review of exam guide
- [ ] Review incorrect practice questions
- [ ] Quick reference sheet created
- [ ] Test technical setup (online exam)
- [ ] Review authentication flows diagram

### Day Before Exam
- [ ] Light review only (avoid cramming)
- [ ] Review integration pattern cheat sheet
- [ ] Relax and get good sleep
- [ ] Prepare exam environment (ID, workspace)

### Exam Day
- [ ] Eat proper breakfast
- [ ] Arrive 15 minutes early (onsite) or test tech (online)
- [ ] Have ID ready
- [ ] Clear workspace (online exam)
- [ ] Read each question carefully
- [ ] Flag uncertain questions for review
- [ ] Manage time (1.75 minutes per question)

---

## 🎯 Quick Reference Sheets

### Integration Patterns Quick Reference

| **Pattern** | **When to Use** | **Salesforce Solution** | **Key Consideration** |
|-------------|-----------------|-------------------------|----------------------|
| **Request-Reply** | Real-time data needed | HTTP Callout, External Services | 120s timeout |
| **Fire-and-Forget** | No response needed | @future, Queueable | No guaranteed delivery |
| **Batch Sync** | Large data volumes | Bulk API, ETL tools | Schedule off-peak |
| **Remote Call-In** | External system initiates | REST/SOAP API, Apex Web Services | API limits |
| **UI Update** | Real-time UI refresh | Platform Events, Streaming API | Browser support |
| **Data Virtualization** | Large external datasets | Salesforce Connect | Query performance |

### API Selection Guide

| **Use Case** | **Best API** | **Why** |
|--------------|--------------|---------|
| Mobile app | REST API | Lightweight, JSON |
| Enterprise integration | SOAP API | Strong typing, WSDL |
| Bulk data load | Bulk API 2.0 | Optimized for large volumes |
| Real-time events | Streaming API / Platform Events | Push notifications |
| Complex related records | Composite API | Single transaction |
| Metadata deployment | Metadata API | CI/CD automation |
| External data access | Salesforce Connect | No storage in SF |

### Governor Limits Cheat Sheet

| **Limit Type** | **Synchronous** | **Asynchronous** |
|----------------|-----------------|------------------|
| SOQL Queries | 100 | 200 |
| DML Statements | 150 | 150 |
| Heap Size | 6 MB | 12 MB |
| CPU Time | 10 seconds | 60 seconds |
| Callouts | 100 | 100 |
| Callout Timeout | 120 seconds | 120 seconds |

### OAuth 2.0 Flows

| **Flow** | **Use Case** | **User Interaction** |
|----------|--------------|----------------------|
| Web Server | Server-to-server with user context | Yes |
| User-Agent | JavaScript apps | Yes |
| JWT Bearer | Server-to-server no user | No |
| Username-Password | NOT RECOMMENDED | Yes |
| Refresh Token | Maintain session | No |

---

## 💡 Exam Tips

### During the Exam
1. **Time Management**: You have 1.75 minutes per question. Don't spend more than 3 minutes on any question.
2. **Flag Questions**: If unsure, flag it and move on. Review at the end.
3. **Elimination**: Eliminate obviously wrong answers first.
4. **Read Carefully**: Pay attention to words like "NOT", "EXCEPT", "ALWAYS", "NEVER".
5. **Scenario Questions**: Focus on requirements, constraints, and trade-offs.
6. **Multiple Select**: Usually 2-3 correct answers. Read all options.

### Common Traps
- Confusing Platform Events with Streaming API
- Mixing up OAuth flows
- Forgetting governor limits
- Choosing synchronous when async is better
- Overcomplicating with middleware when direct API works
- Ignoring security requirements

### Key Success Factors
- **Integration patterns**: Know them cold
- **Governor limits**: Memorize key limits
- **API selection**: Understand when to use each API
- **OAuth**: Know all flows and when to use them
- **Trade-offs**: Always consider pros/cons
- **Scalability**: Think about growth and volume

---

## 📊 Progress Tracking

### Weekly Milestones

| Week | Domain | Target Score | Actual Score | Notes |
|------|--------|--------------|--------------|-------|
| 1 | Domain 1 | 80% | | |
| 2 | Domain 2 | 80% | | |
| 3-4 | Domain 3 (Part 1) | 75% | | |
| 5 | Domain 3 (Part 2) | 80% | | |
| 6-7 | Domain 4 (Part 1) | 75% | | |
| 8 | Domain 4 (Part 2) | 80% | | |
| 9-10 | Domain 5 | 75% | | |
| 11 | Domain 6 | 80% | | |
| 12 | Full Exam | 75%+ | | |

### Hands-On Project Checklist

- [ ] Built custom Apex REST service
- [ ] Implemented OAuth 2.0 JWT flow
- [ ] Created Platform Event integration
- [ ] Set up Change Data Capture
- [ ] Configured Salesforce Connect
- [ ] Implemented error handling with retry
- [ ] Built monitoring dashboard
- [ ] Used Composite API
- [ ] Implemented bulk processing with Bulk API
- [ ] Created Named Credential and used in code

---

## 🎉 After Passing

### Next Steps
1. **Update LinkedIn**: Add certification badge
2. **Update Resume**: Highlight Integration Architect certification
3. **Join Communities**: Architect group on Trailblazer Community
4. **Consider Next Cert**:
   - Application Architect
   - System Architect
   - Technical Architect (CTA)
5. **Annual Maintenance**: Complete maintenance module each release

### Continuing Education
- Stay updated with Salesforce releases
- Experiment with new integration features
- Contribute to community (blog, answer questions)
- Build reference architectures
- Mentor others preparing for certification

---

## 📞 Support & Resources

### Official Salesforce
- Certification Portal: trailhead.salesforce.com/credentials
- Developer Documentation: developer.salesforce.com
- Trailblazer Community: trailblazer.salesforce.com

### Study Groups
- Salesforce Stack Exchange: salesforce.stackexchange.com
- Reddit: r/salesforce
- LinkedIn: Salesforce Architects group

### Questions or Issues?
- Trailblazer Community (search or post questions)
- Stack Exchange (technical questions)
- Salesforce Support (certification questions)

---

**Good luck on your Integration Architect certification journey! 🚀**

*Remember: This certification validates your expertise in designing enterprise-grade integrations. Focus on understanding patterns, trade-offs, and best practices rather than memorizing syntax.*

---

**Document Version: 1.0**  
**Last Updated: October 24, 2025**  
**Next Review: Check for latest exam guide updates before your exam**

