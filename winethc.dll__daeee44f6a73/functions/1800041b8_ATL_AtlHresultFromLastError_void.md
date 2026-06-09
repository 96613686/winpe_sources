# ATL::AtlHresultFromLastError(void)

- ea: `0x1800041b8`
- end: `0x1800041da`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b518`
- `0x18000ce24`
- `0x180010ae4`

## callees

- `0x1800041b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800041bc`
- `KERNEL32!GetLastError` at `0x1800041bc`

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
0x1800041b8  sub     rsp, 28h
0x1800041bc  call    cs:__imp_GetLastError
0x1800041c3  nop     dword ptr [rax+rax+00h]
0x1800041c8  test    eax, eax
0x1800041ca  jle     short loc_1800041D4
0x1800041cc  movzx   eax, ax
0x1800041cf  or      eax, 80070000h
0x1800041d4  add     rsp, 28h
0x1800041d8  retn
```
