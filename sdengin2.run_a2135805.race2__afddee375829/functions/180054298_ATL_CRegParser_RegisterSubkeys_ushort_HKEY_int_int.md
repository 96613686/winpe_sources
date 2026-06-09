# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180054298`
- end: `0x180054835`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1437`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180053e5c`
- `0x180054298`

## callees

- `0x1800511a8`
- `0x180051838`
- `0x180051c64`
- `0x180051e20`
- `0x180051e94`
- `0x1800528c8`
- `0x180053270`
- `0x180053514`
- `0x1800536b8`
- `0x180053d3c`
- `0x180054298`
- `0x180054e20`
- `0x180054ef8`
- `0x1800cf5c0`
- `0x1800cf680`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180054675`
- `msvcrt!wcsncpy_s` at `0x180054675`
- `KERNEL32!lstrcmpiW` at `0x18005430c`
- `KERNEL32!lstrcmpiW` at `0x180054325`
- `KERNEL32!lstrcmpiW` at `0x1800543fc`
- `KERNEL32!lstrcmpiW` at `0x180054431`
- `KERNEL32!lstrcmpiW` at `0x18005430c`
- `KERNEL32!lstrcmpiW` at `0x180054325`
- `KERNEL32!lstrcmpiW` at `0x1800543fc`
- `KERNEL32!lstrcmpiW` at `0x180054431`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800544ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800544ff`

## string_xrefs

- `0x18005431b`: `ForceRemove`
- `0x1800543f2`: `NoRemove`
- `0x180054302`: `Delete`

## pseudocode

```c

```
