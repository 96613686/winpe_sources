# CTls13ServerHandshake::ComputeNewSessionTicketSize(ushort *)

- ea: `0x180033a80`
- end: `0x180033c94`
- name: `?ComputeNewSessionTicketSize@CTls13ServerHandshake@@QEAAKPEAG@Z`
- size: `532`
- prototype: `unsigned int __fastcall(CTls13ServerHandshake *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032f64`

## callees

- `0x180014240`
- `0x180021da8`
- `0x180033a80`
- `0x18007ce4c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033bd3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033bd3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180033b36`
- `ntdll!RtlAcquireResourceExclusive` at `0x180033b36`
- `ntdll!RtlReleaseResource` at `0x180033b6d`
- `ntdll!RtlReleaseResource` at `0x180033b6d`
- `ntdll!RtlNtStatusToDosError` at `0x180033bfa`
- `ntdll!RtlNtStatusToDosError` at `0x180033bfa`
- `bcrypt!BCryptGenRandom` at `0x180033aef`
- `bcrypt!BCryptGenRandom` at `0x180033aef`

## pseudocode

```c

```
