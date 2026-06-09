# ComputeSignatureLength(CSsl3TlsContext *,_eTlsSignatureAlgorithm,_eTlsHashAlgorithm,ulong *)

- ea: `0x1800398a0`
- end: `0x180039a3d`
- name: `?ComputeSignatureLength@@YAKPEAVCSsl3TlsContext@@W4_eTlsSignatureAlgorithm@@W4_eTlsHashAlgorithm@@PEAK@Z`
- size: `413`
- prototype: `unsigned int(struct CSsl3TlsContext *, enum _eTlsSignatureAlgorithm, enum _eTlsHashAlgorithm, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004ae78`
- `0x180055df0`
- `0x180085148`

## callees

- `0x1800398a0`
- `0x1800597b0`
- `0x18005a160`
- `0x180091010`

## import_xrefs

- `ncrypt!SslSignHash` at `0x18003998b`
- `ncrypt!SslSignHash` at `0x18003998b`
- `ncrypt!NCryptSignHash` at `0x180039a28`
- `ncrypt!NCryptSignHash` at `0x180039a28`

## pseudocode

```c

```
