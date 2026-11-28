# Genesis Open Call: registration instructions

Issued [date] under the Genesis Open Call (canonical reference 2026-genesis) and Protocol Specification v1.0.

Published at https://sbrit.org/open-calls

These instructions say how an applicant registers on the public test network, how readiness is shown, and what an admitted applicant does before genesis. They add no requirement to the Open Call.

## The test network

- Accountable Node (transaction submission): [NODE_URL]
- Read mirror: [READ_URL]
- Node software: https://github.com/streembit/streembit-blockchain, release [version]
- Command line wallet: `npm install -g streembit-bc-cli`, version [version] or later
- Validator contract: [address]
- Accountable Node contract: [address]

All registrations and the draw seed of this Open Call are those of this network.

## Validator

No account, name or contact detail is asked for at any step.

1. **Prepare the node.** Build the node software on the machine that will run the validator and create its key pair. The key signs your registration and your attestations.
2. **Get test SBRIT for the registration fee.** Run `streembit-cli [faucet command]` for the address of your node key. The test network sends a small amount of test SBRIT to that address.
3. **Register.** Send `register` to the validator contract with `streembit-cli contract-call-send`, from the address of your node key and signed with that key, with:
   - `validatorId`: a name of your choice, not yet used on the test network
   - `signing_pubkey`: your node's public key
   - `endpoint`: the address at which your node is reachable
4. **Operate.** After your registration the test network's Accountable Node lists your endpoint as a peer and approves the registration. Start your node with the test network's `network`, `chainId` and `bootstrap` values and the Accountable Node as its peer. It synchronises, and then attests transactions and takes part in the test network's minting.
5. **Readiness.** Your node must stay synchronised and reachable at its registered endpoint for at least 48 hours without interruption before the window closes. During that time the Foundation sends transactions on the test network and observes that your validator attests them. Your registration and your node's signed requests prove control of the signing key; the 48 hours prove control of the endpoint.
6. **If admitted.** You send nothing further. The genesis policy, with the id, key and endpoint of every admitted validator taken from the test network registrations, is published at [location] by [date]. Put it into your node's configuration before the bootstrap, whose date is announced with it.

## Accountable Node

1. **Register.** Create the node's key pair, get test SBRIT as in step 2 of the validator section, and send `register` to the Accountable Node contract with:
   - the node id, the node's signing public keys and its endpoint
   - the required disclosures: company name, registration number, jurisdiction, and the link to and hash of the latest audited financial statements and of the business-registration record
   - under `verifications`, for each verification method of the governance rules, the reference or link to your evidence

   No personal data is submitted. The Foundation verifies the registration and its evidence before the draw; a registration that cannot be verified does not qualify.
2. **Operate a test network.** Start your own public test network from the node software: your node as the Accountable Node with at least two validators, as described in `scripts/bootstrap/README.md` of the node software. Keep it running for at least 48 hours.
3. **Report readiness.** While that network is still running, send a pull request to https://github.com/streembit/streembit-blockchain-registry that adds the file `open-calls/2026-genesis/[node id]-readiness.md` with:
   - the network's public endpoint
   - the node's public key
   - the genesis block hash
   - the block count and the tip hash at the time of the report
   - the two signature lines made with `streembit-cli [sign command]` and the node's key

   Keep the network running until the Foundation has checked it.
4. **Verification.** The Foundation checks the running network against the report, verifies the registration against the linked documents and makes the jurisdictional compliance checks.
5. **If admitted.** From your own GitHub account, send a pull request to https://github.com/streembit/streembit-blockchain that replaces the placeholder data in `contract_inputs/acnode_application.json` with your registered data and the two signature lines, by [date]. The bootstrap verifies the signature. The pull request is merged only if its data is the registration the Foundation verified. A place not taken up by that date goes to the waiting list.

## Dates

- Window: as stated in the Open Call, and in any notice of extension published through the same channels.
- Readiness must be complete before the window closes.
- Selection recorded by the date stated in the Open Call.
