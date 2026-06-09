# CServiceDatabase::FindServiceByDisplayName(ushort const *,Microsoft::WRL::ComPtr<CServiceRecord> &)

- ea: `0x1400067a4`
- end: `0x1400068f9`
- name: `?FindServiceByDisplayName@CServiceDatabase@@QEAAHPEBGAEAV?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, RTL_SRWLOCK **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006744`
- `0x140006e60`

## callees

- `0x140002890`
- `0x1400067a4`
- `0x140007130`
- `0x1400078dc`
- `0x14000cf60`
- `0x140012770`
- `0x14004b1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400067d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000682f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000685d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400067d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000682f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000685d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400067f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400068cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400067f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140006854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400068cd`

## pseudocode

```c

```
