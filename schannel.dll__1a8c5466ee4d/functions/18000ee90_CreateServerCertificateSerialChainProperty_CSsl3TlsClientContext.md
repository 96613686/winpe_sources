# CreateServerCertificateSerialChainProperty(CSsl3TlsClientContext *)

- ea: `0x18000ee90`
- end: `0x18000efaf`
- name: `?CreateServerCertificateSerialChainProperty@@YAJPEAVCSsl3TlsClientContext@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct CSsl3TlsClientContext *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f510`
- `0x180050f90`

## callees

- `0x18000ee90`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000eed9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000eed9`
- `ntdll!RtlReleaseResource` at `0x18000ef93`
- `ntdll!RtlReleaseResource` at `0x18000ef93`
- `CRYPT32!CryptMemFree` at `0x18000efa7`
- `CRYPT32!CryptMemFree` at `0x18000efa7`
- `CRYPT32!I_CertProcessSslHandshake` at `0x18000ef30`
- `CRYPT32!I_CertProcessSslHandshake` at `0x18000ef30`

## pseudocode

```c

```
