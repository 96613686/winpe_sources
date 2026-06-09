# __GSHandlerCheckCommon

- ea: `0x14000e294`
- end: `0x14000e2f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e270`
- `0x14000e300`

## callees

- `0x140001390`
- `0x14000e294`

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
0x14000e294  mov     r10, rcx
0x14000e297  mov     r11, rdx
0x14000e29a  mov     ecx, [r8]
0x14000e29d  and     ecx, 0FFFFFFF8h
0x14000e2a0  test    byte ptr [r8], 4
0x14000e2a4  jz      short loc_14000E2BB
0x14000e2a6  mov     eax, [r8+8]
0x14000e2aa  movsxd  r9, dword ptr [r8+4]
0x14000e2ae  neg     eax
0x14000e2b0  movsxd  rdx, eax
0x14000e2b3  add     r9, r10
0x14000e2b6  and     r9, rdx
0x14000e2b9  jmp     short loc_14000E2BE
0x14000e2bb  mov     r9, r10
0x14000e2be  movsxd  rax, ecx
0x14000e2c1  mov     rdx, [rax+r9]
0x14000e2c5  mov     rax, [r11+10h]
0x14000e2c9  mov     ecx, [rax+8]
0x14000e2cc  mov     rax, [r11+8]
0x14000e2d0  test    byte ptr [rcx+rax+3], 0Fh
0x14000e2d5  jz      short loc_14000E2E9
0x14000e2d7  movzx   eax, byte ptr [rcx+rax+3]
0x14000e2dc  mov     ecx, 0FFFFFFF0h
0x14000e2e1  and     rax, rcx
0x14000e2e4  add     rax, r10
0x14000e2e7  jmp     short loc_14000E2EC
0x14000e2e9  mov     rax, r10
0x14000e2ec  xor     rdx, rax
0x14000e2ef  mov     rcx, rdx; StackCookie
0x14000e2f2  jmp     __security_check_cookie
```
