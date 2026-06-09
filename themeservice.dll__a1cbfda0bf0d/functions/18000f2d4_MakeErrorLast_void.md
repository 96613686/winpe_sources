# MakeErrorLast(void)

- ea: `0x18000f2d4`
- end: `0x18000f2f8`
- name: `?MakeErrorLast@@YAJXZ`
- size: `36`
- prototype: `signed int(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d524`
- `0x18000d868`
- `0x18000d91c`
- `0x18000f700`

## callees

- `0x18000f2d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2d8`

## pseudocode

```c
signed int MakeErrorLast(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( !result )
    return -2147418113;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000f2d4  sub     rsp, 28h
0x18000f2d8  call    cs:__imp_GetLastError
0x18000f2de  test    eax, eax
0x18000f2e0  jz      short loc_18000F2EE
0x18000f2e2  jle     short loc_18000F2F3
0x18000f2e4  movzx   eax, ax
0x18000f2e7  or      eax, 80070000h
0x18000f2ec  jmp     short loc_18000F2F3
0x18000f2ee  mov     eax, 8000FFFFh
0x18000f2f3  add     rsp, 28h
0x18000f2f7  retn
```
