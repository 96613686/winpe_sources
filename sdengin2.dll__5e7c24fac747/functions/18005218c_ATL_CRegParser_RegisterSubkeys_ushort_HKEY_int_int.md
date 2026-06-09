# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18005218c`
- end: `0x180052704`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1400`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180051d8c`
- `0x18005218c`

## callees

- `0x18004f30c`
- `0x18004f974`
- `0x18004fd58`
- `0x18004ff04`
- `0x18004ff68`
- `0x180050964`
- `0x180051270`
- `0x1800514f4`
- `0x18005166c`
- `0x180051c78`
- `0x18005218c`
- `0x180052cbc`
- `0x180052d8c`
- `0x1800c9830`
- `0x1800c98f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18005254b`
- `msvcrt!wcsncpy_s` at `0x18005254b`
- `KERNEL32!lstrcmpiW` at `0x180052200`
- `KERNEL32!lstrcmpiW` at `0x180052213`
- `KERNEL32!lstrcmpiW` at `0x1800522e4`
- `KERNEL32!lstrcmpiW` at `0x180052313`
- `KERNEL32!lstrcmpiW` at `0x180052200`
- `KERNEL32!lstrcmpiW` at `0x180052213`
- `KERNEL32!lstrcmpiW` at `0x1800522e4`
- `KERNEL32!lstrcmpiW` at `0x180052313`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800523db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800523db`

## string_xrefs

- `0x180052209`: `ForceRemove`
- `0x1800522da`: `NoRemove`
- `0x1800521f6`: `Delete`

## pseudocode

```c

```
