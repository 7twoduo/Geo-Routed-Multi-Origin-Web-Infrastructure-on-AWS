                                  ┌───────────────────────────────┐
                                  │           USER/BROWSER        │
                                  │ opens CloudFront URL          │
                                  └───────────────┬───────────────┘
                                                  │
                                                  ▼
                         ┌──────────────────────────────────────────────┐
                         │         AWS CLOUDFRONT DISTRIBUTION          │
                         │              geo_demo                        │
                         │ public entry point for all requests          │
                         └────────────────┬─────────────────────────────┘
                                          │
                                          ▼
                    ┌──────────────────────────────────────────────────────┐
                    │ CloudFront checks policies and viewer location data  │
                    │ - Cache policy includes Viewer-Country               │
                    │ - Origin request policy forwards Viewer-City         │
                    └────────────────┬─────────────────────────────────────┘
                                     │
                                     ▼
                    ┌──────────────────────────────────────────────────────┐
                    │            LAMBDA@EDGE geo_router                   │
                    │         event: origin-request                       │
                    │ decides which origin should receive request         │
                    └───────────────┬───────────────────────┬─────────────┘
                                    │                       │
                 if viewer is routed to Brazil              │ default / US route
                                    │                       │
                                    ▼                       ▼
                  ┌────────────────────────┐   ┌────────────────────────┐
                  │ Origin 1               │   │ Origin 2               │
                  │ alb_br DNS name        │   │ alb_us DNS name        │
                  └────────────┬───────────┘   └────────────┬───────────┘
                               │                            │
                               ▼                            ▼
                 ┌───────────────────────────┐  ┌───────────────────────────┐
                 │ Application Load Balancer │  │ Application Load Balancer │
                 │         alb_br            │  │         alb_us            │
                 └────────────┬──────────────┘  └────────────┬──────────────┘
                              │                              │
                              ▼                              ▼
                  ┌────────────────────────┐    ┌────────────────────────┐
                  │ Target Group           │    │ Target Group           │
                  │ tg_br                  │    │ tg_us                  │
                  └────────────┬───────────┘    └────────────┬───────────┘
                               │                             │
                               ▼                             ▼
                    ┌──────────────────────┐      ┌──────────────────────┐
                    │ EC2 second_instance  │      │ EC2 first_instance   │
                    │ in subnet2           │      │ in subnet1           │
                    │ serves webpage 2     │      │ serves webpage 1     │
                    └──────────────────────┘      └──────────────────────┘
