# CTSTimerManager::TimerThread(void)

- ea: `0x180026604`
- end: `0x180026845`
- name: `?TimerThread@CTSTimerManager@@QEAAKXZ`
- size: `577`
- prototype: `unsigned int __fastcall(CTSTimerManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180070260`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x18002558c`
- `0x180026604`
- `0x18002684c`
- `0x1800ce010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800266e2`
- `ntdll!NtQuerySystemTime` at `0x1800266e2`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002669f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002669f`
- `ntdll!RtlReleaseResource` at `0x1800266c4`
- `ntdll!RtlReleaseResource` at `0x180026764`
- `ntdll!RtlReleaseResource` at `0x1800267b5`
- `ntdll!RtlReleaseResource` at `0x1800266c4`
- `ntdll!RtlReleaseResource` at `0x180026764`
- `ntdll!RtlReleaseResource` at `0x1800267b5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026744`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026744`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180026674`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002677e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180026674`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002677e`

## string_xrefs

- `0x180026812`: `Ending execution of Timer Thread`

## pseudocode

```c

```
