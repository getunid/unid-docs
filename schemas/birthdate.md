---
title: BirthDate
description: description
---

# birthDate

BirthDate of a person.

## BirthDateCredentialV1

`BirthDateCredentialV1` is a type extension of credential subject into VC.

### BirthDatePerson

BirthDate of a person.

| Property | Type | Required | Notes |
| :--- | :--- | :--- | :--- |
| "@type" | `BirthDatePerson` | true |  |
| birthDate | `datetime` | ture |  |

### Example of BirthDateCredentialV1

```javascript
{
    "@context": [
        "https://docs.getunid.io/docs/2020/credentials/birthDate",
        "https://www.w3.org/2018/credentials/v1"
    ],
    "id": "https://sds.getunid.io/api/v1/credentials/",
    "type": ["VerifiableCredential", "BirthDateCredentialV1"],
    "issuer": "did:unid:test:issuer1234",
    "issuanceDate": "20201101T180000+0900",
    "credentialSubject": {
        "@type": "BirthDatePerson",
        "@id": "did:unid:test:example1234",
        "birthDate": "1990-12-12"
    },
    "proof": {
        "type": "EcdsaSecp256k1Signature2019",
        "created": "20201101T180000+0900",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:unid:test:issuer1234#signingKey",
        "jws": "eyJhbGc..."
    }
}
```

### birthDate.jsonld

```javascript
{
    "@context": {
        "@version": 1.1,
        "@protected": true,

        "id": "@id",
        "type": "@type",

        "BirthDateCredentialV1": {
            "@id": "https://docs.getunid.io/docs/2020/credentials/birthDate#BirthDateCredentialV1",
            "@context": {
                "@version": 1.1,
                "@protected": true,

                "id": "@id",
                "type": "@type",

                "BirthDatePerson": "http://schema.org/Person",
                "birthDate": "http://schema.org/birthDate"
            }
        }
    }
}
```

