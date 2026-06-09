# CResourceStream::InitializeAlreadyOpen(ushort const *,ushort const *,ushort)

- ea: `0x18005a358`
- end: `0x18005a4bf`
- name: `?InitializeAlreadyOpen@CResourceStream@@AEAAHPEBG0G@Z`
- size: `359`
- prototype: `__int64 __fastcall(CResourceStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180055574`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18001c270`
- `0x18005a358`
- `0x18005d38c`
- `0x18006a110`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x18005a416`
- `ntdll!LdrResSearchResource` at `0x18005a416`
- `ntdll!RtlNtStatusToDosError` at `0x18005a428`
- `ntdll!RtlNtStatusToDosError` at `0x18005a428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a46c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a436`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a46c`

## pseudocode

```c

```
