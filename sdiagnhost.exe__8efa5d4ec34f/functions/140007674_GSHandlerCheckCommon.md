# __GSHandlerCheckCommon

- ea: `0x140007674`
- end: `0x1400076d7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007650`
- `0x1400076e0`

## callees

- `0x140007674`
- `0x140007770`

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
0x140007674  mov     r10, rcx
0x140007677  mov     r11, rdx
0x14000767a  mov     ecx, [r8]
0x14000767d  and     ecx, 0FFFFFFF8h
0x140007680  test    byte ptr [r8], 4
0x140007684  jz      short loc_14000769B
0x140007686  mov     eax, [r8+8]
0x14000768a  movsxd  r9, dword ptr [r8+4]
0x14000768e  neg     eax
0x140007690  movsxd  rdx, eax
0x140007693  add     r9, r10
0x140007696  and     r9, rdx
0x140007699  jmp     short loc_14000769E
0x14000769b  mov     r9, r10
0x14000769e  movsxd  rax, ecx
0x1400076a1  mov     rdx, [rax+r9]
0x1400076a5  mov     rax, [r11+10h]
0x1400076a9  mov     ecx, [rax+8]
0x1400076ac  mov     rax, [r11+8]
0x1400076b0  test    byte ptr [rcx+rax+3], 0Fh
0x1400076b5  jz      short loc_1400076C9
0x1400076b7  movzx   eax, byte ptr [rcx+rax+3]
0x1400076bc  mov     ecx, 0FFFFFFF0h
0x1400076c1  and     rax, rcx
0x1400076c4  add     rax, r10
0x1400076c7  jmp     short loc_1400076CC
0x1400076c9  mov     rax, r10
0x1400076cc  xor     rdx, rax
0x1400076cf  mov     rcx, rdx; StackCookie
0x1400076d2  jmp     __security_check_cookie
```
