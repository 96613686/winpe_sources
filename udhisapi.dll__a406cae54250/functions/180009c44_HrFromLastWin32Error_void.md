# HrFromLastWin32Error(void)

- ea: `0x180009c44`
- end: `0x180009c78`
- name: `?HrFromLastWin32Error@@YAJXZ`
- size: `52`
- prototype: `signed int(void)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f08`
- `0x180005e60`
- `0x180006868`
- `0x1800083f0`
- `0x180009070`

## callees

- `0x180009c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c48`

## pseudocode

```c
signed int HrFromLastWin32Error(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( (result & 0xE0000000) == 0xE0000000 )
    return (unsigned __int16)result | 0x800F0000;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180009c44  sub     rsp, 28h
0x180009c48  call    cs:__imp_GetLastError
0x180009c4e  mov     ecx, eax
0x180009c50  mov     edx, 0E0000000h
0x180009c55  and     ecx, edx
0x180009c57  jz      short loc_180009C67
0x180009c59  cmp     ecx, edx
0x180009c5b  jnz     short loc_180009C67
0x180009c5d  movzx   eax, ax
0x180009c60  or      eax, 800F0000h
0x180009c65  jmp     short loc_180009C73
0x180009c67  test    eax, eax
0x180009c69  jle     short loc_180009C73
0x180009c6b  movzx   eax, ax
0x180009c6e  or      eax, 80070000h
0x180009c73  add     rsp, 28h
0x180009c77  retn
```
