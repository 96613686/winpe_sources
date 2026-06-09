# __GSHandlerCheckCommon

- ea: `0x180006598`
- end: `0x1800065fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006574`
- `0x180006604`

## callees

- `0x180001510`
- `0x180006598`

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
0x180006598  mov     r10, rcx
0x18000659b  mov     r11, rdx
0x18000659e  mov     ecx, [r8]
0x1800065a1  and     ecx, 0FFFFFFF8h
0x1800065a4  test    byte ptr [r8], 4
0x1800065a8  jz      short loc_1800065BF
0x1800065aa  mov     eax, [r8+8]
0x1800065ae  movsxd  r9, dword ptr [r8+4]
0x1800065b2  neg     eax
0x1800065b4  movsxd  rdx, eax
0x1800065b7  add     r9, r10
0x1800065ba  and     r9, rdx
0x1800065bd  jmp     short loc_1800065C2
0x1800065bf  mov     r9, r10
0x1800065c2  movsxd  rax, ecx
0x1800065c5  mov     rdx, [rax+r9]
0x1800065c9  mov     rax, [r11+10h]
0x1800065cd  mov     ecx, [rax+8]
0x1800065d0  mov     rax, [r11+8]
0x1800065d4  test    byte ptr [rcx+rax+3], 0Fh
0x1800065d9  jz      short loc_1800065ED
0x1800065db  movzx   eax, byte ptr [rcx+rax+3]
0x1800065e0  mov     ecx, 0FFFFFFF0h
0x1800065e5  and     rax, rcx
0x1800065e8  add     rax, r10
0x1800065eb  jmp     short loc_1800065F0
0x1800065ed  mov     rax, r10
0x1800065f0  xor     rdx, rax
0x1800065f3  mov     rcx, rdx; StackCookie
0x1800065f6  jmp     __security_check_cookie
```
