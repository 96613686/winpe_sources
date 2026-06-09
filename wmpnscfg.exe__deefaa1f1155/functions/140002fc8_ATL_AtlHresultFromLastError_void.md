# ATL::AtlHresultFromLastError(void)

- ea: `0x140002fc8`
- end: `0x140002fe3`
- name: `?AtlHresultFromLastError@ATL@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003fac`
- `0x140004d0c`
- `0x140005034`

## callees

- `0x140002fc8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140002fcc`
- `KERNEL32!GetLastError` at `0x140002fcc`

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
0x140002fc8  sub     rsp, 28h
0x140002fcc  call    cs:__imp_GetLastError
0x140002fd2  test    eax, eax
0x140002fd4  jle     short loc_140002FDE
0x140002fd6  movzx   eax, ax
0x140002fd9  or      eax, 80070000h
0x140002fde  add     rsp, 28h
0x140002fe2  retn
```
