# __GSHandlerCheckCommon

- ea: `0x18000adc0`
- end: `0x18000ae23`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ad9c`

## callees

- `0x18000adc0`
- `0x18000ae80`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x18000adc0  mov     r10, rcx
0x18000adc3  mov     r11, rdx
0x18000adc6  mov     ecx, [r8]
0x18000adc9  and     ecx, 0FFFFFFF8h
0x18000adcc  test    byte ptr [r8], 4
0x18000add0  jz      short loc_18000ADE7
0x18000add2  mov     eax, [r8+8]
0x18000add6  movsxd  r9, dword ptr [r8+4]
0x18000adda  neg     eax
0x18000addc  movsxd  rdx, eax
0x18000addf  add     r9, r10
0x18000ade2  and     r9, rdx
0x18000ade5  jmp     short loc_18000ADEA
0x18000ade7  mov     r9, r10
0x18000adea  movsxd  rax, ecx
0x18000aded  mov     rdx, [rax+r9]
0x18000adf1  mov     rax, [r11+10h]
0x18000adf5  mov     ecx, [rax+8]
0x18000adf8  mov     rax, [r11+8]
0x18000adfc  test    byte ptr [rcx+rax+3], 0Fh
0x18000ae01  jz      short loc_18000AE15
0x18000ae03  movzx   eax, byte ptr [rcx+rax+3]
0x18000ae08  mov     ecx, 0FFFFFFF0h
0x18000ae0d  and     rax, rcx
0x18000ae10  add     rax, r10
0x18000ae13  jmp     short loc_18000AE18
0x18000ae15  mov     rax, r10
0x18000ae18  xor     rdx, rax
0x18000ae1b  mov     rcx, rdx; StackCookie
0x18000ae1e  jmp     __security_check_cookie
```
