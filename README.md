# Ideal Dental Services: Advanced Data Systems Portfolio

Case study: [Ideal Dental Services](https://www.idealdentalservices.com), a dental practice with two clinics in Abuja (Ceddi Plaza and Baze University Hospital).

| Folder | Portfolio | Contents |
| --- | --- | --- |
| `portfolio1-data-design` | 1. Data design and modelling | PostgreSQL 16 DDL (17 tables, constraints, triggers, views) and constraint tests |
| `portfolio2-query-optimisation` | 2. Query processing and optimisation | Synthetic 10-year data generator, 8 workload queries, indexes, benchmark harness, raw EXPLAIN ANALYZE plans |
| `portfolio3-transactions-concurrency` | 3. Transactions and concurrency | Two-session driver, 15 scenarios, transcripts and screenshots |
| `portfolio4-nosql-models` | 4. NoSQL and advanced data models | JSONB document store, Redis key-value, wide-column emulation, NetworkX graph; 500 sample documents |
| `portfolio5-distributed-cloud` | 5. Distributed and cloud databases | Five-node cluster build, replication, consistency, failover and sharding tests |
| `evidence` | All | Diagrams and charts used in the write-ups |

## Running it

Requirements: PostgreSQL 16 (with `btree_gist` and `postgres_fdw`), Redis 7, Python 3 with Pillow and NetworkX.

1. Portfolio 1: `psql -d ids -f portfolio1-data-design/ideal_dental_schema.sql -f portfolio1-data-design/test_data.sql`
2. Portfolio 2: load the schema without its `ix_` indexes, run `gen.sql` and `fix.sql`, then `python3 bench.py <db> before q/Q*.sql`, then `indexes.sql`.
3. Portfolios 3 to 5: see the scripts in each folder. They expect local sockets in `/tmp/pg` (main server) and `/tmp/p5` (cluster); edit the paths for your machine.

All patient, staff and payment data is synthetic. No real patient information is used.
