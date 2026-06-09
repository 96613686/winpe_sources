# HNMgrSetSecondaryKey(_WLAN_HOSTED_NETWORK_KEY_DATA *,ulong *)

- ea: `0x18015c558`
- end: `0x18015c8db`
- name: `?HNMgrSetSecondaryKey@@YAKPEAU_WLAN_HOSTED_NETWORK_KEY_DATA@@PEAK@Z`
- size: `899`
- prototype: `__int64 __fastcall(struct _WLAN_HOSTED_NETWORK_KEY_DATA *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180128060`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1800868b8`
- `0x1800c6774`
- `0x180106340`
- `0x180107330`
- `0x180159514`
- `0x18015abb8`
- `0x18015c558`
- `0x18015d1f4`
- `0x18015d3ec`
- `0x18015ee88`
- `0x18015f090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015c7d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015c7d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015c686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015c686`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015c6a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015c6a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015c68c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015c68c`
- `ntdll!WinSqmIncrementDWORD` at `0x18015c62f`
- `ntdll!WinSqmIncrementDWORD` at `0x18015c62f`

## pseudocode

```c

```
