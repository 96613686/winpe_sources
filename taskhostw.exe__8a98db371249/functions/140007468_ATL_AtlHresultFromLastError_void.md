# ATL::AtlHresultFromLastError(void)

- ea: `0x140007468`
- end: `0x140007483`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `signed int(void)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002040`
- `0x1400022d0`
- `0x140002970`
- `0x140002e30`
- `0x1400068f0`
- `0x140006c10`

## callees

- `0x140007468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000746c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000746c`

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
0x140007468  sub     rsp, 28h
0x14000746c  call    cs:__imp_GetLastError
0x140007472  test    eax, eax
0x140007474  jle     short loc_14000747E
0x140007476  movzx   eax, ax
0x140007479  or      eax, 80070000h
0x14000747e  add     rsp, 28h
0x140007482  retn
```
