# CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)

- ea: `0x180050a64`
- end: `0x180050d4f`
- name: `?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z`
- size: `747`
- prototype: `static int(struct IWinApiLite *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18002aed4`

## callees

- `0x180004824`
- `0x180004910`
- `0x180004b2c`
- `0x1800061a8`
- `0x180011010`
- `0x18001a0d0`
- `0x18001ac3c`
- `0x1800259dc`
- `0x18003f800`
- `0x180050a64`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b73`

## string_xrefs

- `0x180050b39`: `CWLIDCCHelper::GetSID`
- `0x180050c34`: `hr = StringCchPrintf( spQualifiedUser, MAX_PATH, L"%ls\\%ls", machineName, pUserName )`

## pseudocode

```c

```
