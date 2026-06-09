# __GSHandlerCheckCommon

- ea: `0x1800021cc`
- end: `0x18000222f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800021a8`
- `0x18001b2fc`
- `0x18001b364`

## callees

- `0x1800021cc`
- `0x18001b420`

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
0x1800021cc  mov     r10, rcx
0x1800021cf  mov     r11, rdx
0x1800021d2  mov     ecx, [r8]
0x1800021d5  and     ecx, 0FFFFFFF8h
0x1800021d8  test    byte ptr [r8], 4
0x1800021dc  jz      short loc_1800021F3
0x1800021de  mov     eax, [r8+8]
0x1800021e2  movsxd  r9, dword ptr [r8+4]
0x1800021e6  neg     eax
0x1800021e8  movsxd  rdx, eax
0x1800021eb  add     r9, r10
0x1800021ee  and     r9, rdx
0x1800021f1  jmp     short loc_1800021F6
0x1800021f3  mov     r9, r10
0x1800021f6  movsxd  rax, ecx
0x1800021f9  mov     rdx, [rax+r9]
0x1800021fd  mov     rax, [r11+10h]
0x180002201  mov     ecx, [rax+8]
0x180002204  mov     rax, [r11+8]
0x180002208  test    byte ptr [rcx+rax+3], 0Fh
0x18000220d  jz      short loc_180002221
0x18000220f  movzx   eax, byte ptr [rcx+rax+3]
0x180002214  mov     ecx, 0FFFFFFF0h
0x180002219  and     rax, rcx
0x18000221c  add     rax, r10
0x18000221f  jmp     short loc_180002224
0x180002221  mov     rax, r10
0x180002224  xor     rdx, rax
0x180002227  mov     rcx, rdx; StackCookie
0x18000222a  jmp     __security_check_cookie
```
