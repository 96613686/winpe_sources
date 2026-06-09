# ATL::AtlHresultFromLastError(void)

- ea: `0x180008c58`
- end: `0x180008c73`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `signed int(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a348`
- `0x18000bb3c`
- `0x18000be5c`

## callees

- `0x180008c58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c5c`

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
0x180008c58  sub     rsp, 28h
0x180008c5c  call    cs:__imp_GetLastError
0x180008c62  test    eax, eax
0x180008c64  jle     short loc_180008C6E
0x180008c66  movzx   eax, ax
0x180008c69  or      eax, 80070000h
0x180008c6e  add     rsp, 28h
0x180008c72  retn
```
