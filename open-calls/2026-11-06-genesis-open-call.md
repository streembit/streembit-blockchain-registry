# Genesis Open Call

One Accountable Node place and 36 validator places for the launch of the Streembit network.

Issued 2026-11-06 under Protocol Specification v1.0. Canonical reference 2026-genesis.

Published at https://sbrit.org/open-calls

## The call at a glance

**Places**
- 1 Accountable Node place, eligibility under How to become an Accountable Node
- 36 Validator places, eligibility under Validator Requirements

**Application window**
- Opens 2026-11-10 00:00 UTC
- Closes 2026-11-24 00:00 UTC

**How to apply**

Both classes register on the public test network. Registration instructions are published before the window opens.
- Accountable Node: register the required disclosures, the node's signing public keys and its endpoint.
- Validator: register the signing public key and endpoint.

**Readiness**

Accountable Node
- Operate a node on the public test network continuously for at least 48 hours before the window closes.
- Demonstrate control of the published signing key.
- Pass the published readiness checks before the window closes.

Validator
- Operate the validator software on the public test network continuously for at least 48 hours before the window closes.
- Pass the published readiness checks before the window closes. The checks also prove control of the signing key and the endpoint.

**Machine requirements**

Accountable Node
- At least 96 CPU cores
- 1024 GB memory
- NVMe disks
- 20 Gbps network link
- High availability (HA), with a switchover time of no more than 10 seconds

Validator
- At least 64 CPU cores
- 512 GB memory
- NVMe disks
- 20 Gbps network link
- High availability (load balanced)

**Who qualifies**
- Accountable Node: the registration is complete, made within the window, verified by the Foundation, and passes readiness.
- Validator: the registration is made within the window and passes readiness. Validators have no identity verification; readiness is verified.

**Selection rule**

For each class, every qualifying applicant is admitted up to the number of places. If qualifying applicants exceed the places, a random draw decides. Those not drawn form a waiting list in draw order. The draw is final.

**Draw**

Used only if qualifying applicants in a class exceed its places. The seed is the hash of the first block on the public test network produced after the window closes. Method: for each qualifying applicant in the class, compute SHA-256 over the raw bytes of the seed block hash followed by the raw bytes of the applicant's compressed signing public key (33 bytes). For an Accountable Node, this is its block-signing key. Order the applicants by the resulting hash, read as an unsigned big-endian number, lowest first. The first applicants up to the number of places are admitted; the rest form the waiting list in that order. Anyone can reproduce the draw from the seed and the registrations on the test network. The Foundation has no discretion between qualifying applicants.

**Selection recorded by** 2026-12-01: applications and the draw seed on the public test network. The admitted participants are registered on the Streembit chain in the bootstrap sequence at genesis.

## Text of the call

### Invitation

The Foundation invites applications for one Accountable Node place and 36 validator places on the Streembit network. These are the only places in the genesis producer and validator sets. No place is reserved for any applicant, and the order of receipt confers no priority.

Genesis proceeds only when at least one Accountable Node and two validators have been admitted through this call and have passed readiness. If this call does not produce the required participants, the window is extended through the same channels and genesis is postponed. If fewer applicants qualify than there are places, all qualifying applicants are admitted and the remaining places are carried to the next Open Call.

### Eligibility

Accountable Node applicants must meet the requirements in the section How to become an Accountable Node of the Protocol Specification. Validator applicants must meet the requirements in the section Validator Requirements.

- Accountable Node: a registered corporation or limited liability company in the United States, United Kingdom, European Union, Japan or Australia, with at least USD 10,000,000 in verifiable assets supported by audited financial statements.
- Validator: anyone. Validators are anonymous; no identity information is collected and no identity check is made.
- Neither role requires an upfront SBRIT deposit.
- Blacklisted participants are ineligible.

### What each applicant registers

All registrations are recorded on the public test network. No personal data is submitted.

- Accountable Node: company data only, as follows.
  - The company name, registration number and jurisdiction.
  - A link to its latest audited financial statements and to its business-registration record, for example its filings at the public company register, each with a hash of the document.
  - The node's signing public keys and endpoint.

  The linked documents must be available to the Foundation for verification. They are not published. The Foundation verifies the registration against them and with jurisdictional compliance checks.
- Validator: the signing public key and endpoint. Nothing else is registered.

### Results

The results are recorded on-chain, as set out in the Protocol Specification, section Open Call → Record. Applications and the draw seed are on the public test network. The admitted Accountable Node and validators are registered in the bootstrap sequence on the Streembit chain.

## Requirements

The requirements for each role and the lifecycle of an application are defined in the Protocol Specification, in the sections named in the at-a-glance section above.
