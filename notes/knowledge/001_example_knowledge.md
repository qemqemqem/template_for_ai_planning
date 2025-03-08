---
title: JWT Implementation Best Practices
category: best_practices
created_date: 2025-03-07
last_updated: 2025-03-07
tags:
  - security
  - authentication
related_files:
  - auth_service.py
---

# JWT Implementation Best Practices

## Key Insights
- Always use short expiration times (15-60 minutes)
- Include only necessary claims to minimize token size
- Store tokens securely (HttpOnly cookies preferred over localStorage)
- Implement refresh token rotation for enhanced security

## Common Pitfalls
1. **Storing sensitive data in tokens**: JWTs are encoded, not encrypted
2. **Missing token validation**: Always verify signature and expiration
3. **Inadequate key management**: Rotate signing keys regularly
4. **No revocation mechanism**: Implement a token blacklist for critical systems

## Implementation Example
```python
# Generate token with appropriate settings
def create_access_token(user_id):
    expiration = datetime.utcnow() + timedelta(minutes=30)
    payload = {
        'sub': str(user_id),
        'exp': expiration,
        'iat': datetime.utcnow(),
        'type': 'access'
    }
    return jwt.encode(payload, SECRET_KEY, algorithm='HS256')
```

## Verification Process
Always implement complete validation:
1. Verify signature is valid
2. Check expiration time
3. Validate issuer if applicable
4. Verify audience for multi-service systems
