# UbpmpMachineOOBECompletedCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18002b0e0`
- end: `0x18002b19e`
- name: `?UbpmpMachineOOBECompletedCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a500`
- `0x18000a6e0`
- `0x18002b0e0`
- `0x18003625c`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b153`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b153`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b16b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002b16b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b17d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002b17d`

## pseudocode

```c

```
