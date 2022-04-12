## Differences from `did:sov`

Early instances of Indy Networks used the `did:sov` DID Method. The following summarizes the differences between that `did:sov` and `did:indy`.

- A `did:indy` DID includes a namespace component that enables resolving a DID to a specific instance of an Indy network (e.g. Sovrin, IDUnion, etc.).
- Identifiers for Indy ledger objects other than [[ref: NYM]]s are adjusted to contain a namespace component.
- `did:indy` DID validation is determined by NYM transaction `version`, as described in the [DID Creation](#nym-transaction-version) section. These restrictions MUST be enforced by the ledger.
- The specification includes rules for transforming a [[ref: NYM]] into a DIDDoc that meets the DID Core Specification.
    - An optional [[ref: NYM]] data item allows entities to extend the DIDDoc returned from a [[ref: NYM]] in arbitrary ways.
    - The controller can decide whether the DIDDoc will be JSON or JSON-LD.
    - Before writing a [[ref: NYM]] to the ledger, the [[ref: NYM]] content is verified to ensure that transforming the [[ref: NYM]] to a DIDDoc produces a valid JSON and may include DIDDoc validity checking.
    - The transformation of a read [[ref: NYM]] to a DIDDoc is left to the client of an Indy ledger.
- A convention for storing Indy network instance config ("genesis") files in a Hyperledger Indy project GitHub repository ("indy-did-networks") is introduced.
