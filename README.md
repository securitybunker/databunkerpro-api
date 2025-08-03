# DatabunkerPro API

DatabunkerPro is a privacy-compliant user data vault and tokenization engine that provides secure storage and management of user data with built-in privacy controls, consent management, and audit capabilities.

## API Documentation

### OpenAPI Specification

The complete API documentation is available in OpenAPI 3.0.3 format. You can access it in the following ways:

1. **Local File**: Use the `openapi.yaml` file in this repository
2. **Online Documentation**: Visit the hosted documentation at [https://securitybunker.github.io/databunkerpro-api/](https://securitybunker.github.io/databunkerpro-api/)

### Key Features

- **User Management**: Create, update, and manage user profiles with privacy controls
- **Consent Management**: Handle legal basis and user agreements for GDPR/DPDP compliance
- **Tokenization Management**: Secure tokenization of sensitive data like credit cards
- **Audit Trail**: Complete audit logging of all data access and modifications
- **Multi-tenant**: Support for multiple tenants with isolated data
- **Role-based Access**: Fine-grained access control with policies and roles
- **Bulk Operations**: Efficient bulk data operations with unlock mechanisms
- **Connector Support**: Integration with external databases and systems

### Authentication

All API calls require authentication via the `X-Bunker-Token` header. For multi-tenant setups, use the `X-Bunker-Tenant` header to specify the tenant context.

### Multi-Tenant Usage

Multi-tenancy is supported when DatabunkerPro is configured to work with PostgreSQL database.

When using DatabunkerPro in a multi-tenant environment:

- **Single Tenant**: Omit the `X-Bunker-Tenant` header (default behavior)
- **Multi-Tenant**: Include `X-Bunker-Tenant: your-tenant-name` header

**Example:**
```bash
# Single tenant
curl -X POST http://localhost:3000/v2/UserCreate \
  -H "X-Bunker-Token: your-token" \
  -d '{"profile":{"login":"user1"}}'

# Multi-tenant
curl -X POST http://localhost:3000/v2/UserCreate \
  -H "X-Bunker-Token: your-token" \
  -H "X-Bunker-Tenant: acme-corp" \
  -d '{"profile":{"login":"user1"}}'
```

### Base URL

The API is available at `/v2/` endpoint with all requests using POST method.

## Getting Started

1. **View Documentation**: Open the `openapi.yaml` file in your preferred OpenAPI viewer (like Swagger UI, ReDoc, or Postman)
2. **Online Documentation**: Visit [https://securitybunker.github.io/databunkerpro-api/](https://securitybunker.github.io/databunkerpro-api/) for the hosted interactive documentation
3. **API Testing**: Use the online documentation to test API endpoints directly in your browser

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, visit [https://databunker.com](https://databunker.com)
