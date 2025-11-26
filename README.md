# CropFresh Protos

Shared Protocol Buffer definitions for all CropFresh microservices.

## Structure

```
proto/
├── auth.proto          # Authentication service definitions
├── catalog.proto       # Product catalog service definitions
├── order.proto         # Order management service definitions
├── logistics.proto     # Logistics and routing service definitions
├── payment.proto       # Payment processing service definitions
└── ai.proto            # AI orchestration service definitions
```

## Services

### AuthService
- User authentication (Login, Logout)
- Token management (Verify Token, Refresh)

### CatalogService
- Browse produce listings
- Inventory management

###OrderService
- Order lifecycle management
- Status tracking
- Cancellation and refunds

### LogisticsService
- Route assignment and optimization
- Real-time location tracking
- Delivery management

### PaymentService
- UPI payment processing
-Payment verification
- Refund handling
- Transaction history

### AIService
- Quality grading from photos
- Shelf-life prediction
- Buyer-farmer matching
- Dynamic pricing optimization

## Usage

### As Git Submodule (Recommended)

Add to each microservice:

```bash
git submodule add https://github.com/cropfresh/cropfresh-protos.git protos
git submodule update --init --recursive
```

### Initialization in Services

```bash
cd protos
git submodule update --init --recursive
```

## Updating Protos

1. Make changes in this repository
2. Commit and push changes
3. Update submodule in each service:

```bash
cd protos
git pull origin main
cd ..
git add protos
git commit -m "Update protos"
```

## Versioning

Following semantic versioning (semver):
- MAJOR: Breaking changes to RPC signatures
- MINOR: Backward-compatible additions
- PATCH: Bug fixes and documentation

## Documentation

- [Architecture](../../docs/architecture.md)
- [gRPC Best Practices](../../docs/grpc-patterns.md)
