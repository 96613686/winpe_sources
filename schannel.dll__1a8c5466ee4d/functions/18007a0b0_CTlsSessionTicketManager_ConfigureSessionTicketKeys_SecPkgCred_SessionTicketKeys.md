# CTlsSessionTicketManager::ConfigureSessionTicketKeys(_SecPkgCred_SessionTicketKeys *)

- ea: `0x18007a0b0`
- end: `0x18007a335`
- name: `?ConfigureSessionTicketKeys@CTlsSessionTicketManager@@QEAAJPEAU_SecPkgCred_SessionTicketKeys@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CTlsSessionTicketManager *__hidden this, struct _SecPkgCred_SessionTicketKeys *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180073558`

## callees

- `0x180021da8`
- `0x180021e64`
- `0x180057c8c`
- `0x18007a028`
- `0x18007a0b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a154`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a154`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007a0dc`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007a0dc`
- `ntdll!RtlReleaseResource` at `0x18007a31c`
- `ntdll!RtlReleaseResource` at `0x18007a31c`
- `ncrypt!SslDeriveSessionTicketKey` at `0x18007a2a2`
- `ncrypt!SslDeriveSessionTicketKey` at `0x18007a2a2`

## pseudocode

```c

```
