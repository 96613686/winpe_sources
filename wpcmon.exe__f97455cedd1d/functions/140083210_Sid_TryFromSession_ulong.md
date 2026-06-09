# Sid::TryFromSession(ulong)

- ea: `0x140083210`
- end: `0x1400833f0`
- name: `?TryFromSession@Sid@@SA?AV?$Optional@VSid@@@@K@Z`
- size: `480`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400802ec`
- `0x140080a14`

## callees

- `0x1400057f0`
- `0x140083090`
- `0x140083210`
- `0x1400a8010`

## import_xrefs

- `WTSAPI32!WTSFreeMemory` at `0x140083259`
- `WTSAPI32!WTSFreeMemory` at `0x1400832f3`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140083246`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400832e5`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140083246`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x1400832e5`

## pseudocode

```c

```
