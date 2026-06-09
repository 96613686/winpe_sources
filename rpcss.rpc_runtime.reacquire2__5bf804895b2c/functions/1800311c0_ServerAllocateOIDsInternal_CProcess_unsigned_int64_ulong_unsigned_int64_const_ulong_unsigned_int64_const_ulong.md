# ServerAllocateOIDsInternal(CProcess *,unsigned __int64 *,ulong,unsigned __int64 * const,ulong,unsigned __int64 * const,ulong *)

- ea: `0x1800311c0`
- end: `0x180031647`
- name: `?ServerAllocateOIDsInternal@@YAKPEAVCProcess@@PEA_KKQEA_KK2PEAK@Z`
- size: `1159`
- prototype: `unsigned int __usercall@<eax>(struct CProcess *@<rcx>, unsigned __int64 *@<rdx>, unsigned int@<r8d>, unsigned __int64 *const@<r9>, unsigned int, unsigned __int64 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180030d80`
- `0x180060450`

## callees

- `0x1800178e0`
- `0x1800194e0`
- `0x18001a3e0`
- `0x18001aed0`
- `0x18001b520`
- `0x18001c3c0`
- `0x18001c624`
- `0x1800311c0`
- `0x1800b7ac0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800313b2`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800313b2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003145c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003145c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003124e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003124e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003154b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031627`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003154b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031593`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031627`

## string_xrefs

- `0x180031297`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800314cf`: `onecore\com\combase\rpcss\objex\manager.cxx`
- `0x1800315dc`: `onecore\com\combase\rpcss\objex\manager.cxx`

## pseudocode

```c

```
