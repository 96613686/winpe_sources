# UpdateServerCertificateSerialChainProperty(CSsl3TlsClientContext *,int)

- ea: `0x18000fcfc`
- end: `0x18000fdec`
- name: `?UpdateServerCertificateSerialChainProperty@@YAJPEAVCSsl3TlsClientContext@@H@Z`
- size: `240`
- prototype: `__int64 __fastcall(struct CSsl3TlsClientContext *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e720`
- `0x18000f510`

## callees

- `0x18000fcfc`
- `0x18000fdf4`
- `0x180091010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000fd44`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000fd44`
- `ntdll!RtlReleaseResource` at `0x18000fddb`
- `ntdll!RtlReleaseResource` at `0x18000fddb`
- `CRYPT32!I_CertFinishSslHandshake` at `0x18000fdba`
- `CRYPT32!I_CertFinishSslHandshake` at `0x18000fdba`

## pseudocode

```c

```
