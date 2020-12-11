# mini-microservice
A mini microservice practice without database for learning microservice architecture, still working on it.

### Posts service (port 4000)
- Create a post
- List all posts

| Path | Method | Body | Goal |
|-|-|-|-|
| /posts | POST | {title: string} | Create a new post |
| /posts | GET | - | Retrieve all posts |
| /events | POST | {} | Get incoming events |

### Comments service (port 4001)
- Create a comment (Dependency on `List all posts`)
- List all comments (Dependency on `List all posts`)

| Path | Method | Body | Goal |
|-|-|-|-|
| /posts/:id/comments | POST | {content: string} | Create a comment associated with the given post ID |
| /posts/:id/comments | GET | - | Retrieve all comments associated with the given post ID |
| /events | POST | {} | Get incoming events |

### Query service (port 4002)
| Path | Method | Body | Goal |
|-|-|-|-|
| /posts | GET | - | Provide full posts and comments |
| /events | POST | {type: string, data: object} | Get incoming events, combine data to posts data by event type |

### Event-bus (port 4005)
- With async mode
  
| Path | Method | Body | Goal |
|-|-|-|-|
| /events | POST | {type: string, data: object} | Get incoming events, broadcast to all service with event data |
