# CustomerConsentPOC

## Sequence diagram

![Sequence diagram](https://rawgit.com/e-nettet/CustomerConsentPOC/master/sequence-new.svg)

  1. Identity Service broadcasts its own Whisper address.
  2. Customer registers its Whisper address, email, and public key.
  3. Data Requester registers its Whisper address, email, and public key.
  4. Data Owner registers its Whisper address, email, and public key.
  5. Data Requester requests Customers identity.
  6. Data Requester receives Customers email, Whisper address, and public key.
  7. Data Requester requests Customers blockchain address, includes its own blockchain address, and signs the message with its private key.
  8. Customer requests Data Requesters identity. Needed to verify the signature.
  9. Customer receives Data Requesters email, Whisper address, and public key.
  10. Customer validates the signature, sends its blockchain address, and signs the message with its private key.
  11. Data Requester requests Data Owners identity.
  12. Data Requester receives Data Owners email, Whisper address, and public key.
  13. Data Requester requests Data Owners blockchain address, includes its own blockchain address, and signs the message with its private key.
  14. Data Owner requests Data Requesters identity. Needed to verify the signature.
  15. Data Owner receives Data Requesters email, Whisper address, and public key.
  16. Data Owner validates the signature, sends its blockchain address, and signs the message with its private key.
  17. Data Requester creates a Smart Contract with the blockchain addresses.
  18. Data Requester request a consent for the data specification. Data specification is encrypted with Customers public key.
  19. Consent request is forwarded to the Customer. Data specification is encrypted and unreadable by the Smart Contract.
  20. Customer requests Data Owners identity.
  21. Customer receives Data Owners email, Whisper address, and public key.
  22. Customer responds to the consent request. Response is encrypted with Data Owners public key.
  23. Consent response is forwarded to the Data Requester. Response is encrypted and unreadable by the Data Requester.
  24. Data Requester forwards the Customers response to the Data Owner through the Smart Contract.
  25. Smart Contract forwards the Customers response to the Data Owner.
  26. Data Owner publishes the data encrypted with the Data Requesters public key.
  27. Smart Contract forwards the data to the Data Requester.

