---
title: Starton Changelogs
displayed-sidebar: connectSidebar
---

# Starton Changelogs

## API domain migration

Starton domain has migrated from `api.starton.io` to `api.starton.com`. All API requests to Starton must now be redirected to the new domain. 

## V3 

Starton V3 has been deployed. Check out what's changing on the API side.

### GLOBAL

-   `/v2/`changed to `/v3/`. For most endpoints, `/v2/` will be deprecated in the near future. All new endpoints will be on `/v3/`.
-   You can now store and query a lot of entities by `metadata` allowing you to store additional information.

### LIBRARY

No breaking change from v2 to v3, but some IDs will be deprecated in the future.

-   IDs are now much more human-readable: `MINTABLE_NFT`, `FUNGIBLE_TOKEN`, etc. Former IDs (for example `sct_d4c1d5f2ed6f44d185bfb60eee2dbcaf`) are deprecated.
-   New `tag` and `blockchain` filter to allow you to query it more easily.
-   Filter by `name` now do a partial find.

### NOTIFY

No breaking change from v2 to v3

-   The service is now called Monitor, no impact on the API.
-   New `paused` filter.
-   New `name` filter.

### PROJECT

No breaking change from v2 to v3

-   New `color` field.
-   You can now edit project name, description, color, and metadata.

### API KEY

Big Breaking change from v2 to v3.

-   API keys are no longer in `/v2/project`. They have been migrated to `/v3/api-key`.
-   Results are now paginated.
-   Brand new response format, we don't return the key anymore. You can only see them once.
-   New `name` and `description` field.
-   Better format: now API keys are prefixed by live* and test keys (coming soon) will be prefixed by test*.

### AUTH

-   Brand new Authentication system.

### IPFS

Big Breaking change from v2 to v3.

-   API with the pinning service spec is now hosted on `/v3/ipfs/pinning-service`.
-   Brand new API on `/v3/ipfs` compliant with the rest of Starton API (pagination, filter, id, etc).
-   New endpoint to get storage usage.
-   V2 API `/v2/pinning` is still available but will be deprecated in the near future.

### WALLET

Breaking change.

-   Wallets now have a `name` and `description`.
-   Filter `deleteKms` is now `deleteKeyOnKms` and is defaulted to false.
-   the route has been moved inside `/v3/kms/wallet`.
-   You can now import a wallet from your KMS using `/v3/kms/wallet/import-provider-key`.
-   You can now set up a KMS allowing you to avoid sending credentials at each new wallet you want to create `/v3/kms`.
-   The endpoint to get the balance of the wallet is now moved to `/v3/data/`.
