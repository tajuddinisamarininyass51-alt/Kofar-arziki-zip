# Kofaraziki Data - API Documentation

## Base URL
```
https://api.kofaraziki.com/v1
```

## Authentication
All API requests require authentication using Bearer token.

```
Authorization: Bearer <token>
```

## Response Format
All responses are returned in JSON format.

### Success Response (200)
```json
{
  "status": "success",
  "data": { ... },
  "message": "Operation completed successfully"
}
```

### Error Response
```json
{
  "status": "error",
  "code": "ERROR_CODE",
  "message": "Error description"
}
```

## Core Endpoints

### 1. User Management

#### Get User Profile
```
GET /users/profile
```
**Response:**
```json
{
  "user_id": "12345",
  "name": "Tajuddini Ahmad",
  "username": "bamimairu",
  "account_number": "6625847565",
  "balance": 29.7,
  "referral_bonus": 0.0
}
```

### 2. Wallet Management

#### Get Wallet Balance
```
GET /wallet/balance
```

#### Fund Wallet
```
POST /wallet/fund
```
**Request Body:**
```json
{
  "amount": 5000,
  "payment_method": "palmpay"
}
```

### 3. Services

#### Get Data Plans
```
GET /services/data/plans
```

#### Purchase Data
```
POST /services/data/purchase
```
**Request Body:**
```json
{
  "phone_number": "08012345678",
  "plan_id": "data_5gb",
  "amount": 2000
}
```

#### Get Airtime Providers
```
GET /services/airtime/providers
```

#### Purchase Airtime
```
POST /services/airtime/purchase
```
**Request Body:**
```json
{
  "phone_number": "08012345678",
  "provider_id": "mtn",
  "amount": 1000
}
```

### 4. Transactions

#### Get Transaction History
```
GET /transactions/history?limit=20&offset=0
```

#### Get Transaction Details
```
GET /transactions/{transaction_id}
```

### 5. Referrals

#### Get Referral Code
```
GET /referrals/code
```

#### Get Referral Stats
```
GET /referrals/stats
```

#### Get Referral List
```
GET /referrals/list
```

## Error Codes

| Code | Description |
|------|-------------|
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 409 | Conflict |
| 422 | Validation Error |
| 500 | Internal Server Error |
| 503 | Service Unavailable |

## Rate Limiting
- **Rate Limit:** 100 requests per minute
- **Headers:** `X-RateLimit-Limit`, `X-RateLimit-Remaining`

## Webhook Events
- `transaction.completed`
- `transaction.failed`
- `referral.earned`
- `wallet.funded`

---
*API Documentation - Version 1.0*
*Last Updated: 2026-09-05*
