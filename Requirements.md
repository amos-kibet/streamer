### Functional Requirements

- Upload video

- View video

- Multiple device support

- Search

- Recommendations

### Technical Requirements

- Low latency

- Scalability

- High availability

### Services

|                   |                             |                  |               |                 |
| ----------------- | --------------------------- | ---------------- | ------------- | --------------- |
| User Subscription | User Service                |                  | User DB       |                 |
| Upload Video      | Upload Service              | Messaging Server | Video Storage | CDN             |
| Process Video     | Video Processing Transcoder |                  |               |                 |
| Fetch Catalogue   | Catalogue Service           |                  | Catalogue DB  | Catalogue Cache |
| Search            | Search Service              |                  | Search Index  |                 |
| Events            | Events Service              | Messaging Server | Storage       |                 |
| Recommendations   | Recommendations ML Service  |                  |               |                 |
| Analytics         | Analytics Service           |                  |               |                 |
