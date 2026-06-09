# HrFromLastWin32Error(void)

- ea: `0x14000656c`
- end: `0x1400065a0`
- name: `?HrFromLastWin32Error@@YAJXZ`
- size: `52`
- prototype: `signed int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006360`
- `0x140006400`

## callees

- `0x14000656c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006570`

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
0x14000656c  sub     rsp, 28h
0x140006570  call    cs:__imp_GetLastError
0x140006576  mov     ecx, eax
0x140006578  mov     edx, 0E0000000h
0x14000657d  and     ecx, edx
0x14000657f  jz      short loc_14000658F
0x140006581  cmp     ecx, edx
0x140006583  jnz     short loc_14000658F
0x140006585  movzx   eax, ax
0x140006588  or      eax, 800F0000h
0x14000658d  jmp     short loc_14000659B
0x14000658f  test    eax, eax
0x140006591  jle     short loc_14000659B
0x140006593  movzx   eax, ax
0x140006596  or      eax, 80070000h
0x14000659b  add     rsp, 28h
0x14000659f  retn
```
