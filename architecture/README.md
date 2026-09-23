                         Internet
                            │
                            ▼
                    ┌─────────────────┐
                    │   Public Tier   │
                    │                 │
                    │   Web / Access  │
                    └────────┬────────┘
                             │
                             ▼
                    ┌─────────────────┐
                    │ Application Tier│
                    │                 │
                    │ EC2 + Tomcat    │
                    └────────┬────────┘
                             │
                         MySQL : 3306
                             │
                             ▼
                    ┌─────────────────┐
                    │   Database Tier │
                    │                 │
                    │ RDS MySQL       │
                    │ Private Subnet  │
                    └─────────────────┘
