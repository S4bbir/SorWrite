# Sorwrite API Documentation

## Authentication

### Register a new user
**POST** `/api/auth/register`

Registers a new user account.

**Request Body:**
```json
{
  "name": "string",
  "email": "string",
  "password": "string"
}
```

**Response:**
```json
{
  "success": true,
  "token": "string",
  "data": {
    "id": "string",
    "name": "string",
    "email": "string",
    "role": "string"
  }
}
```

### Login
**POST** `/api/auth/login`

Authenticates a user and returns a JWT token.

**Request Body:**
```json
{
  "email": "string",
  "password": "string"
}
```

**Response:**
```json
{
  "success": true,
  "token": "string",
  "data": {
    "id": "string",
    "name": "string",
    "email": "string",
    "role": "string"
  }
}
```

### Get current user
**GET** `/api/auth/me`

Returns the currently authenticated user's information.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "email": "string",
    "role": "string"
  }
}
```

## Queries

### Get all queries
**GET** `/api/queries`

Returns all queries for the authenticated user.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "count": "number",
  "data": [
    {
      "id": "string",
      "title": "string",
      "content": "string",
      "aiResponse": "string",
      "tags": ["string"],
      "isPublic": "boolean",
      "user": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ]
}
```

### Get single query
**GET** `/api/queries/:id`

Returns a specific query by ID.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "title": "string",
    "content": "string",
    "aiResponse": "string",
    "tags": ["string"],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Create new query
**POST** `/api/queries`

Creates a new query.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "title": "string",
  "content": "string",
  "tags": ["string"],
  "isPublic": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "title": "string",
    "content": "string",
    "aiResponse": "string",
    "tags": ["string"],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Update query
**PUT** `/api/queries/:id`

Updates an existing query.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "title": "string",
  "content": "string",
  "tags": ["string"],
  "isPublic": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "title": "string",
    "content": "string",
    "aiResponse": "string",
    "tags": ["string"],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Delete query
**DELETE** `/api/queries/:id`

Deletes a query.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {}
}
```

## Libraries

### Get all libraries
**GET** `/api/library`

Returns all libraries for the authenticated user.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "count": "number",
  "data": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "queries": ["string"],
      "isPublic": "boolean",
      "user": "string",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ]
}
```

### Get single library
**GET** `/api/library/:id`

Returns a specific library by ID.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "queries": [
      {
        "id": "string",
        "title": "string",
        "content": "string",
        "aiResponse": "string",
        "tags": ["string"],
        "isPublic": "boolean",
        "user": "string",
        "createdAt": "date",
        "updatedAt": "date"
      }
    ],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Create new library
**POST** `/api/library`

Creates a new library.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string",
  "isPublic": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "queries": ["string"],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Update library
**PUT** `/api/library/:id`

Updates an existing library.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string",
  "isPublic": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "queries": ["string"],
    "isPublic": "boolean",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Delete library
**DELETE** `/api/library/:id`

Deletes a library.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {}
}
```

## Tools

### Get all tools
**GET** `/api/tools`

Returns all active tools.

**Response:**
```json
{
  "success": true,
  "count": "number",
  "data": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "category": "string",
      "icon": "string",
      "endpoint": "string",
      "isPublic": "boolean",
      "isActive": "boolean",
      "createdAt": "date",
      "updatedAt": "date"
    }
  ]
}
```

### Get single tool
**GET** `/api/tools/:id`

Returns a specific tool by ID.

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "category": "string",
    "icon": "string",
    "endpoint": "string",
    "isPublic": "boolean",
    "isActive": "boolean",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Create new tool (Admin only)
**POST** `/api/tools`

Creates a new tool.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string",
  "category": "string",
  "icon": "string",
  "endpoint": "string",
  "isPublic": "boolean",
  "isActive": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "category": "string",
    "icon": "string",
    "endpoint": "string",
    "isPublic": "boolean",
    "isActive": "boolean",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Update tool (Admin only)
**PUT** `/api/tools/:id`

Updates an existing tool.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string",
  "category": "string",
  "icon": "string",
  "endpoint": "string",
  "isPublic": "boolean",
  "isActive": "boolean"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "category": "string",
    "icon": "string",
    "endpoint": "string",
    "isPublic": "boolean",
    "isActive": "boolean",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Delete tool (Admin only)
**DELETE** `/api/tools/:id`

Deletes a tool.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {}
}
```

## Subscription

### Get user subscription
**GET** `/api/subscription`

Returns the authenticated user's subscription information.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "user": "string",
    "plan": "string",
    "status": "string",
    "startDate": "date",
    "endDate": "date",
    "stripeSubscriptionId": "string",
    "stripeCustomerId": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Create/update subscription
**POST** `/api/subscription`

Creates or updates a subscription for the authenticated user.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "plan": "string",
  "stripeSubscriptionId": "string",
  "stripeCustomerId": "string"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "user": "string",
    "plan": "string",
    "status": "string",
    "startDate": "date",
    "endDate": "date",
    "stripeSubscriptionId": "string",
    "stripeCustomerId": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Cancel subscription
**PUT** `/api/subscription/cancel`

Cancels the authenticated user's subscription.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "user": "string",
    "plan": "string",
    "status": "string",
    "startDate": "date",
    "endDate": "date",
    "stripeSubscriptionId": "string",
    "stripeCustomerId": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

## Payment

### Create checkout session
**POST** `/api/payment/checkout`

Creates a Stripe checkout session for subscription payment.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "plan": "string" // 'pro' or 'enterprise'
}
```

**Response:**
```json
{
  "success": true,
  "sessionId": "string"
}
```

### Get subscription status
**GET** `/api/payment/subscription`

Returns the authenticated user's subscription status.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "plan": "string",
    "status": "string",
    "startDate": "date",
    "endDate": "date"
  }
}
```

### Cancel subscription
**POST** `/api/payment/cancel`

Cancels the authenticated user's subscription.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "message": "Subscription cancelled successfully"
}
```

## Teams

### Get all teams
**GET** `/api/teams`

Returns all teams the authenticated user is a member of.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "count": "number",
  "data": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "owner": {
        "id": "string",
        "name": "string",
        "email": "string"
      },
      "members": [
        {
          "user": {
            "id": "string",
            "name": "string",
            "email": "string"
          },
          "role": "string"
        }
      ],
      "libraries": ["string"],
      "createdAt": "date",
      "updatedAt": "date"
    }
  ]
}
```

### Get single team
**GET** `/api/teams/:id`

Returns a specific team by ID.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "owner": {
      "id": "string",
      "name": "string",
      "email": "string"
    },
    "members": [
      {
        "user": {
          "id": "string",
          "name": "string",
          "email": "string"
        },
        "role": "string"
      }
    ],
    "libraries": [
      {
        "id": "string",
        "name": "string",
        "description": "string",
        "queries": ["string"],
        "isPublic": "boolean",
        "user": "string",
        "createdAt": "date",
        "updatedAt": "date"
      }
    ],
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Create new team
**POST** `/api/teams`

Creates a new team.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "owner": "string",
    "members": [
      {
        "user": "string",
        "role": "string"
      }
    ],
    "libraries": ["string"],
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Update team
**PUT** `/api/teams/:id`

Updates an existing team.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string",
  "description": "string"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "owner": "string",
    "members": [
      {
        "user": "string",
        "role": "string"
      }
    ],
    "libraries": ["string"],
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Delete team
**DELETE** `/api/teams/:id`

Deletes a team.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {}
}
```

### Add member to team
**POST** `/api/teams/:id/members`

Adds a member to a team.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "userId": "string",
  "role": "string" // 'admin' or 'member'
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "owner": "string",
    "members": [
      {
        "user": {
          "id": "string",
          "name": "string",
          "email": "string"
        },
        "role": "string"
      }
    ],
    "libraries": ["string"],
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

### Remove member from team
**DELETE** `/api/teams/:id/members/:userId`

Removes a member from a team.

**Headers:**
```
Authorization: Bearer <token>
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "string",
    "name": "string",
    "description": "string",
    "owner": "string",
    "members": [
      {
        "user": {
          "id": "string",
          "name": "string",
          "email": "string"
        },
        "role": "string"
      }
    ],
    "libraries": ["string"],
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

## Diagrams

### Generate diagram
**POST** `/api/diagrams/generate`

Generates a diagram based on the provided topic and type.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "topic": "string",
  "type": "string" // 'concept', 'flow', 'process', or 'mind'
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "type": "string",
    "topic": "string",
    "diagram": {
      "nodes": [
        {
          "id": "string",
          "label": "string",
          "type": "string"
        }
      ],
      "edges": [
        {
          "from": "string",
          "to": "string"
        }
      ]
    }
  }
}
```

## Academic Essay

### Generate academic essay
**POST** `/api/academic-essay`

Generates a structured academic essay based on the provided topic.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "topic": "string"
}
```

**Response:**
```json
{
  "success": true,
  "data": "string" // The generated academic essay
}
```

## Citation Map

### Generate citation map
**POST** `/api/citation-map/generate`

Generates a citation map for a paper.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "paperTitle": "string",
  "doi": "string"
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "paper": {
      "id": "string",
      "title": "string",
      "authors": ["string"],
      "year": "number",
      "citations": "number"
    },
    "references": [
      {
        "id": "string",
        "title": "string",
        "authors": ["string"],
        "year": "number",
        "citations": "number"
      }
    ],
    "citations": [
      {
        "id": "string",
        "title": "string",
        "authors": ["string"],
        "year": "number",
        "citations": "number"
      }
    ]
  }
}