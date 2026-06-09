# ATL::AtlHresultFromLastError(void)

- ea: `0x180002ef4`
- end: `0x180002f0f`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `signed int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003978`
- `0x1800043ec`
- `0x180004714`

## callees

- `0x180002ef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ef8`

## pseudocode

```c
signed int ATL::AtlHresultFromLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180002ef4  sub     rsp, 28h
0x180002ef8  call    cs:__imp_GetLastError
0x180002efe  test    eax, eax
0x180002f00  jle     short loc_180002F0A
0x180002f02  movzx   eax, ax
0x180002f05  or      eax, 80070000h
0x180002f0a  add     rsp, 28h
0x180002f0e  retn
```
