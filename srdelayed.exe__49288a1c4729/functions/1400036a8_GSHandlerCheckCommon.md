# __GSHandlerCheckCommon

- ea: `0x1400036a8`
- end: `0x14000370b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003684`

## callees

- `0x1400036a8`
- `0x140003770`

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
0x1400036a8  mov     r10, rcx
0x1400036ab  mov     r11, rdx
0x1400036ae  mov     ecx, [r8]
0x1400036b1  and     ecx, 0FFFFFFF8h
0x1400036b4  test    byte ptr [r8], 4
0x1400036b8  jz      short loc_1400036CF
0x1400036ba  mov     eax, [r8+8]
0x1400036be  movsxd  r9, dword ptr [r8+4]
0x1400036c2  neg     eax
0x1400036c4  movsxd  rdx, eax
0x1400036c7  add     r9, r10
0x1400036ca  and     r9, rdx
0x1400036cd  jmp     short loc_1400036D2
0x1400036cf  mov     r9, r10
0x1400036d2  movsxd  rax, ecx
0x1400036d5  mov     rdx, [rax+r9]
0x1400036d9  mov     rax, [r11+10h]
0x1400036dd  mov     ecx, [rax+8]
0x1400036e0  mov     rax, [r11+8]
0x1400036e4  test    byte ptr [rcx+rax+3], 0Fh
0x1400036e9  jz      short loc_1400036FD
0x1400036eb  movzx   eax, byte ptr [rcx+rax+3]
0x1400036f0  mov     ecx, 0FFFFFFF0h
0x1400036f5  and     rax, rcx
0x1400036f8  add     rax, r10
0x1400036fb  jmp     short loc_140003700
0x1400036fd  mov     rax, r10
0x140003700  xor     rdx, rax
0x140003703  mov     rcx, rdx; StackCookie
0x140003706  jmp     __security_check_cookie
```
