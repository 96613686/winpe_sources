# ResultFromKnownLastError(void)

- ea: `0x18000bcc0`
- end: `0x18000bce5`
- name: `?ResultFromKnownLastError@@YAJXZ`
- size: `37`
- prototype: `__int64(void)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c90`
- `0x180005060`
- `0x180005300`
- `0x180006ba0`
- `0x180007970`
- `0x180007e40`
- `0x180009230`
- `0x18000b960`
- `0x18000e6ec`
- `0x18000e81c`
- `0x180011734`
- `0x180011840`
- `0x180011948`
- `0x180013770`
- `0x1800164c8`
- `0x180016aa8`
- `0x180016bd0`

## callees

- `0x18000bcc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc4`

## pseudocode

```c
signed int ResultFromKnownLastError(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x18000bcc0  sub     rsp, 28h
0x18000bcc4  call    cs:__imp_GetLastError
0x18000bcca  test    eax, eax
0x18000bccc  jle     short loc_18000BCD6
0x18000bcce  movzx   eax, ax
0x18000bcd1  or      eax, 80070000h
0x18000bcd6  test    eax, eax
0x18000bcd8  mov     ecx, 80004005h
0x18000bcdd  cmovns  eax, ecx
0x18000bce0  add     rsp, 28h
0x18000bce4  retn
```
