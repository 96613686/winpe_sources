# __GSHandlerCheckCommon

- ea: `0x180029f28`
- end: `0x180029f8b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029f04`
- `0x180029f94`

## callees

- `0x1800015f0`
- `0x180029f28`

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
0x180029f28  mov     r10, rcx
0x180029f2b  mov     r11, rdx
0x180029f2e  mov     ecx, [r8]
0x180029f31  and     ecx, 0FFFFFFF8h
0x180029f34  test    byte ptr [r8], 4
0x180029f38  jz      short loc_180029F4F
0x180029f3a  mov     eax, [r8+8]
0x180029f3e  movsxd  r9, dword ptr [r8+4]
0x180029f42  neg     eax
0x180029f44  movsxd  rdx, eax
0x180029f47  add     r9, r10
0x180029f4a  and     r9, rdx
0x180029f4d  jmp     short loc_180029F52
0x180029f4f  mov     r9, r10
0x180029f52  movsxd  rax, ecx
0x180029f55  mov     rdx, [rax+r9]
0x180029f59  mov     rax, [r11+10h]
0x180029f5d  mov     ecx, [rax+8]
0x180029f60  mov     rax, [r11+8]
0x180029f64  test    byte ptr [rcx+rax+3], 0Fh
0x180029f69  jz      short loc_180029F7D
0x180029f6b  movzx   eax, byte ptr [rcx+rax+3]
0x180029f70  mov     ecx, 0FFFFFFF0h
0x180029f75  and     rax, rcx
0x180029f78  add     rax, r10
0x180029f7b  jmp     short loc_180029F80
0x180029f7d  mov     rax, r10
0x180029f80  xor     rdx, rax
0x180029f83  mov     rcx, rdx; StackCookie
0x180029f86  jmp     __security_check_cookie
```
