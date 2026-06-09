# __GSHandlerCheckCommon

- ea: `0x18000b9a8`
- end: `0x18000ba0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b984`

## callees

- `0x180005730`
- `0x18000b9a8`

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
0x18000b9a8  mov     r10, rcx
0x18000b9ab  mov     r11, rdx
0x18000b9ae  mov     ecx, [r8]
0x18000b9b1  and     ecx, 0FFFFFFF8h
0x18000b9b4  test    byte ptr [r8], 4
0x18000b9b8  jz      short loc_18000B9CF
0x18000b9ba  mov     eax, [r8+8]
0x18000b9be  movsxd  r9, dword ptr [r8+4]
0x18000b9c2  neg     eax
0x18000b9c4  movsxd  rdx, eax
0x18000b9c7  add     r9, r10
0x18000b9ca  and     r9, rdx
0x18000b9cd  jmp     short loc_18000B9D2
0x18000b9cf  mov     r9, r10
0x18000b9d2  movsxd  rax, ecx
0x18000b9d5  mov     rdx, [rax+r9]
0x18000b9d9  mov     rax, [r11+10h]
0x18000b9dd  mov     ecx, [rax+8]
0x18000b9e0  mov     rax, [r11+8]
0x18000b9e4  test    byte ptr [rcx+rax+3], 0Fh
0x18000b9e9  jz      short loc_18000B9FD
0x18000b9eb  movzx   eax, byte ptr [rcx+rax+3]
0x18000b9f0  mov     ecx, 0FFFFFFF0h
0x18000b9f5  and     rax, rcx
0x18000b9f8  add     rax, r10
0x18000b9fb  jmp     short loc_18000BA00
0x18000b9fd  mov     rax, r10
0x18000ba00  xor     rdx, rax
0x18000ba03  mov     rcx, rdx; StackCookie
0x18000ba06  jmp     __security_check_cookie
```
