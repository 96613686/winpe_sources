# __GSHandlerCheckCommon

- ea: `0x18002ade0`
- end: `0x18002ae43`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002adbc`
- `0x18002ae4c`
- `0x18002aeb4`

## callees

- `0x1800050f0`
- `0x18002ade0`

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
0x18002ade0  mov     r10, rcx
0x18002ade3  mov     r11, rdx
0x18002ade6  mov     ecx, [r8]
0x18002ade9  and     ecx, 0FFFFFFF8h
0x18002adec  test    byte ptr [r8], 4
0x18002adf0  jz      short loc_18002AE07
0x18002adf2  mov     eax, [r8+8]
0x18002adf6  movsxd  r9, dword ptr [r8+4]
0x18002adfa  neg     eax
0x18002adfc  movsxd  rdx, eax
0x18002adff  add     r9, r10
0x18002ae02  and     r9, rdx
0x18002ae05  jmp     short loc_18002AE0A
0x18002ae07  mov     r9, r10
0x18002ae0a  movsxd  rax, ecx
0x18002ae0d  mov     rdx, [rax+r9]
0x18002ae11  mov     rax, [r11+10h]
0x18002ae15  mov     ecx, [rax+8]
0x18002ae18  mov     rax, [r11+8]
0x18002ae1c  test    byte ptr [rcx+rax+3], 0Fh
0x18002ae21  jz      short loc_18002AE35
0x18002ae23  movzx   eax, byte ptr [rcx+rax+3]
0x18002ae28  mov     ecx, 0FFFFFFF0h
0x18002ae2d  and     rax, rcx
0x18002ae30  add     rax, r10
0x18002ae33  jmp     short loc_18002AE38
0x18002ae35  mov     rax, r10
0x18002ae38  xor     rdx, rax
0x18002ae3b  mov     rcx, rdx; StackCookie
0x18002ae3e  jmp     __security_check_cookie
```
