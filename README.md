# QuantHive - Quantum Computing Power Marketplace

## Overview

QuantHive is a decentralized marketplace for trading quantum computing power. It allows providers to list their quantum resources, while users can deposit tokens, book computational units, and execute quantum jobs. The contract also integrates demand-based pricing and job management to simulate a dynamic quantum computing marketplace.

## Key Features

* **Resource Listing**: Providers can list quantum computing resources with specified power and pricing.
* **Dynamic Pricing**: Resource costs adjust based on a demand factor set by an authorized oracle.
* **Balance Management**: Users can deposit, withdraw, and transfer funds securely.
* **Booking System**: Users book computational units directly from listed providers.
* **Job Queueing**: Quantum jobs can be queued with associated resource allocations.
* **Oracle Integration**: Contract owner (oracle) can update job statuses and market demand factors.
* **Market Valuation**: Tracks total value of all listed quantum resources.

## Contract Components

* **Constants**:

  * `contract-owner` - Administrator with authority to update oracles.
  * Error codes for invalid input, insufficient funds, unauthorized actions, and missing resources.

* **Data Maps**:

  * `quantum-resources` - Stores listed resources per provider and ID.
  * `user-balances` - Tracks balances for each user.

* **Data Variables**:

  * `next-resource-id` - Auto-incrementing ID for resources.
  * `job-status` - Tracks the current status of queued jobs.
  * `demand-factor` - Multiplier influencing dynamic pricing.
  * `total-market-value` - Cumulative valuation of all listed resources.

## Functions

* **Resource Management**:

  * `list-resource` - List new computing resources.
  * `update-resource-availability` - Change resource availability.
  * `get-resource-details` - Fetch information about a resource.

* **User Balance Management**:

  * `deposit` - Add STX funds into the marketplace.
  * `withdraw` - Withdraw STX funds from balance.
  * `get-balance` - Check a user’s available balance.

* **Booking and Jobs**:

  * `book-resource` - Reserve computational units from a resource.
  * `queue-job` - Queue a quantum job with job data.
  * `update-job-status` - Update job status (oracle-only).
  * `get-job-status` - Retrieve the current status of a job.

* **Market Controls**:

  * `update-demand-factor` - Oracle sets demand factor.
  * `get-current-price` - Get adjusted resource price considering demand.
  * `get-total-market-value` - Fetch total market value of listed resources.

## Usage Flow

1. **Providers** list quantum computing resources with pricing.
2. **Users** deposit funds and book computational units from providers.
3. **Jobs** are queued with associated resources, and status is updated via oracle.
4. **Pricing** dynamically shifts based on demand factor adjustments.
5. **Balances and market value** are tracked on-chain for transparency.
