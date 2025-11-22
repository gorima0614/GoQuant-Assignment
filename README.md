perpetual-dex-oracle/
├── README.md                     # Overview, build, deploy instructions
├── anchor-program/               # Part 1: Solana Anchor smart contract
│   ├── Cargo.toml
│   └── src/
│       ├── lib.rs                # Entry point, program logic, accounts
│       ├── instructions.rs      # Anchor program instructions (validation, update price)
│       └── state.rs             # Account state structs (e.g. PriceData)
├── backend-oracle-service/       # Part 2: Rust backend oracle clients & services
│   ├── Cargo.toml
│   ├── src/
│   │   ├── main.rs              # Entry point - run oracle manager and HTTP servers
│   │   ├── oracle_manager.rs    # OracleManager handling subscriptions and health
│   │   ├── pyth_client.rs       # Pyth oracle client
│   │   ├── switchboard_client.rs# Switchboard oracle client
│   │   ├── price_aggregator.rs  # Aggregate prices and consensus logic
│   │   ├── price_cache.rs        # Redis cache management
│   │   ├── api.rs                # REST API handlers and WebSocket streaming
│   │   ├── health_monitor.rs     # Oracle health monitoring logic
│   │   └── config.rs             # Configuration parsing and constants
├── migrations/
│   └── schema.sql                # Database schema and migration scripts
├── tests/                       # Integration and unit tests
│   ├── anchor_tests.rs          # Anchor program tests
│   └── backend_tests.rs         # Backend service tests
├── .env.example                 # Example configuration values for development/testing
└── scripts/
    ├── deploy_anchor.sh         # Script to build and deploy anchor program
    ├── run_backend.sh           # Script to build and run backend service locally
    └── migrate_db.sh            # Script to apply DB migrations
