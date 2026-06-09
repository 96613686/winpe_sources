# LogIncompleteCertificateChainEvent(ulong,ushort const *,uchar,_CERT_CONTEXT const *,ulong)

- ea: `0x18005ef44`
- end: `0x18005efea`
- name: `?LogIncompleteCertificateChainEvent@@YAXKPEBGEPEBU_CERT_CONTEXT@@K@Z`
- size: `166`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, unsigned __int8, const struct _CERT_CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a860`

## callees

- `0x18005ef44`
- `0x18005f1e4`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005ef77`
- `ntdll!RtlInitUnicodeString` at `0x18005ef94`
- `ntdll!RtlInitUnicodeString` at `0x18005ef77`
- `ntdll!RtlInitUnicodeString` at `0x18005ef94`

## pseudocode

```c

```
