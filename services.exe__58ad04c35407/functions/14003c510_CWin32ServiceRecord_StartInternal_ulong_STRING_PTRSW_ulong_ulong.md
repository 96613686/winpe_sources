# CWin32ServiceRecord::StartInternal(ulong,_STRING_PTRSW *,ulong,ulong)

- ea: `0x14003c510`
- end: `0x14003d5df`
- name: `?StartInternal@CWin32ServiceRecord@@MEAAKKPEAU_STRING_PTRSW@@KK@Z`
- size: `4303`
- prototype: `__int64 __fastcall(CWin32ServiceRecord *this, int, struct _STRING_PTRSW *, int, unsigned int)`
- caller_count: `0`
- callee_count: `52`
- tags: `loader_planting, service_task`

## callees

- `0x140001548`
- `0x1400018ac`
- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x14000516c`
- `0x140005584`
- `0x140007770`
- `0x14000bac8`
- `0x14000bebc`
- `0x14000dc1c`
- `0x140013f60`
- `0x140014824`
- `0x1400188fc`
- `0x14001bd2c`
- `0x14001c87c`
- `0x14001f99c`
- `0x1400200b8`
- `0x1400202a0`
- `0x140020d84`
- `0x140021ef4`
- `0x140022ec4`
- `0x14002309c`
- `0x1400233ac`
- `0x140024864`
- `0x140025ac4`
- `0x1400266cc`
- `0x140026990`
- `0x14002a54c`
- `0x14002d730`
- `0x14002d988`
- `0x14002e930`
- `0x14002ea14`
- `0x140030258`
- `0x1400361ec`
- `0x140038698`
- `0x14003ae4c`
- `0x14003c510`
- `0x14004b1c0`
- `0x140062d1c`
- `0x140063928`
- `0x1400701a8`
- `0x1400707fc`
- `0x140070ee8`
- `0x14007a510`
- `0x140083168`
- `0x140083458`
- `0x1400838b0`
- `0x1400839a4`
- `0x140085fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003ce1d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003ce1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cd03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cf1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cf86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003d53c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cd03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cf1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003cf86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003d53c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ce27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ce27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003cc20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003cc20`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14003cfff`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x14003cfff`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003c62e`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003ce37`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003ce97`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003d54b`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003c62e`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003ce37`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003ce97`
- `ntdll!RtlAcquireResourceExclusive` at `0x14003d54b`
- `ntdll!RtlReleaseResource` at `0x14003c70b`
- `ntdll!RtlReleaseResource` at `0x14003c7a5`
- `ntdll!RtlReleaseResource` at `0x14003c878`
- `ntdll!RtlReleaseResource` at `0x14003cb57`
- `ntdll!RtlReleaseResource` at `0x14003ce79`
- `ntdll!RtlReleaseResource` at `0x14003cecf`
- `ntdll!RtlReleaseResource` at `0x14003d3c1`
- `ntdll!RtlReleaseResource` at `0x14003d40d`
- `ntdll!RtlReleaseResource` at `0x14003d4be`
- `ntdll!RtlReleaseResource` at `0x14003d5af`
- `ntdll!RtlReleaseResource` at `0x14003c70b`
- `ntdll!RtlReleaseResource` at `0x14003c7a5`
- `ntdll!RtlReleaseResource` at `0x14003c878`
- `ntdll!RtlReleaseResource` at `0x14003cb57`
- `ntdll!RtlReleaseResource` at `0x14003ce79`
- `ntdll!RtlReleaseResource` at `0x14003cecf`
- `ntdll!RtlReleaseResource` at `0x14003d3c1`
- `ntdll!RtlReleaseResource` at `0x14003d40d`
- `ntdll!RtlReleaseResource` at `0x14003d4be`
- `ntdll!RtlReleaseResource` at `0x14003d5af`
- `ntdll!RtlAcquireResourceShared` at `0x14003c910`
- `ntdll!RtlAcquireResourceShared` at `0x14003c910`
- `ntdll!NtClose` at `0x14003d4ea`
- `ntdll!NtClose` at `0x14003d4ea`
- `ntdll!RtlNtStatusToDosError` at `0x14003d4f2`
- `ntdll!RtlNtStatusToDosError` at `0x14003d4f2`
- `ntdll!RtlFreeHeap` at `0x14003c81c`
- `ntdll!RtlFreeHeap` at `0x14003cc8a`
- `ntdll!RtlFreeHeap` at `0x14003ce6c`
- `ntdll!RtlFreeHeap` at `0x14003d4db`
- `ntdll!RtlFreeHeap` at `0x14003c81c`
- `ntdll!RtlFreeHeap` at `0x14003cc8a`
- `ntdll!RtlFreeHeap` at `0x14003ce6c`
- `ntdll!RtlFreeHeap` at `0x14003d4db`
- `ntdll!TpPostWork` at `0x14003d373`
- `ntdll!TpPostWork` at `0x14003d373`

## pseudocode

```c

```
