# ATL::AtlHresultFromLastError(void)

- ea: `0x18000331c`
- end: `0x18000333e`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `34`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043c0`
- `0x1800050c8`
- `0x180007b54`

## callees

- `0x18000331c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003320`
- `KERNEL32!GetLastError` at `0x180003320`

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
0x18000331c  sub     rsp, 28h
0x180003320  call    cs:__imp_GetLastError
0x180003327  nop     dword ptr [rax+rax+00h]
0x18000332c  test    eax, eax
0x18000332e  jle     short loc_180003338
0x180003330  movzx   eax, ax
0x180003333  or      eax, 80070000h
0x180003338  add     rsp, 28h
0x18000333c  retn
```
