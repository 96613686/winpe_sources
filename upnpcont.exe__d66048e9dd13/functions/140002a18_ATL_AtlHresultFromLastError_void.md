# ATL::AtlHresultFromLastError(void)

- ea: `0x140002a18`
- end: `0x140002a33`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `signed int(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a54`
- `0x140004698`
- `0x14000550c`
- `0x140005834`

## callees

- `0x140002a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002a1c`

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
0x140002a18  sub     rsp, 28h
0x140002a1c  call    cs:__imp_GetLastError
0x140002a22  test    eax, eax
0x140002a24  jle     short loc_140002A2E
0x140002a26  movzx   eax, ax
0x140002a29  or      eax, 80070000h
0x140002a2e  add     rsp, 28h
0x140002a32  retn
```
